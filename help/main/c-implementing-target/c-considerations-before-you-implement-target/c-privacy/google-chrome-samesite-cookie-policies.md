---
keywords: google;samesite;cookies;chrome 80;ietf
description: Descubra cómo Adobe [!DNL Target] gestiona el estándar SameSite IETF introducido con Google Chrome versión 80 y lo que debe hacer para cumplir estas políticas.
title: How [!DNL Target] ¿Gestionar las políticas de cookies de Samesite de Google?
feature: Privacy & Security
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 7%

---

# Políticas de cookies de Google Chrome samesite

Google empezará a imponer nuevas políticas de cookies de forma predeterminada a los usuarios a partir de Chrome 80, que está previsto que se publique a principios de 2020. Este artículo explica todo lo que necesita saber sobre las nuevas políticas de cookies de SameSite, cómo [!DNL Adobe Target] admite estas directivas y cómo puede usar [!DNL Target] para cumplir con las nuevas directivas de cookies de SameSite de Google Chrome.

A partir de Chrome 80, los desarrolladores web deben especificar explícitamente qué cookies pueden funcionar en distintos sitios web. Este es el primero de muchos anuncios que Google planea hacer para mejorar la privacidad y seguridad en la web.

Dado el hecho de que Facebook ha estado en el primer puesto con respecto a la privacidad y la seguridad, otros jugadores importantes como Apple, y ahora Google, han sido rápidos en capitalizar la oportunidad de crear nuevas identidades como campeones de privacidad y seguridad. Apple lideró el paquete anunciando primero cambios en sus políticas de cookies a principios de este año a través de ITP 2.1 y recientemente, ITP 2.2. En ITP 2.1, Apple bloquea completamente las cookies de terceros y mantiene las cookies creadas en el explorador durante solo siete días. En ITP 2.2, las cookies se conservan solo durante un día. El anuncio de Google no es ni de lejos tan agresivo como el de Apple, pero es el primer paso hacia el mismo objetivo final. Para obtener más información sobre las directivas de Apple, consulte [Prevención inteligente del seguimiento de Apple (ITP) 2.x](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## ¿Qué son las cookies y cómo se utilizan?

Antes de profundizar en los cambios de Google en sus políticas de cookies, hablemos de qué son las cookies y cómo se utilizan. En pocas palabras, las cookies son pequeños archivos de texto almacenados en el explorador web que se utilizan para recordar atributos de usuario.

Las cookies son importantes porque mejoran la experiencia del usuario a medida que navega por la web. Por ejemplo, si está realizando compras en un sitio web de comercio electrónico y agrega algo al carro de compras pero no inicia sesión ni realiza compras en esa visita, las cookies recuerdan sus artículos y los mantienen en el carro de compras para la próxima visita. O imaginen si se vieron obligados a volver a introducir su nombre de usuario y contraseña cada vez que visiten su sitio web de medios sociales favorito. Las cookies también resuelven ese problema, ya que almacenan información que ayuda a los sitios a identificar quién es. Este tipo de cookies se denominan cookies de origen porque las crea y utiliza el sitio web que visitó.

También existen cookies de terceros. Para entenderlos mejor, veamos este ejemplo:

Digamos que una hipotética empresa de medios sociales llamada &quot;Amigos&quot; proporciona un botón Compartir que otros sitios implementan para permitir que los usuarios de Amigos compartan el contenido del sitio en la fuente de Amigos. Ahora, un usuario lee un artículo de noticias en un sitio web de noticias que está usando el botón Compartir y hace clic en él para publicar automáticamente en su cuenta de Amigos.

Para que esto suceda, el explorador recupera el botón Compartir amigos de `platform.friends.com` cuando se carga el artículo de noticias. Dentro de este proceso, el explorador adjunta las cookies de Amigos, que contienen las credenciales de inicio de sesión del usuario, a la solicitud a los servidores de Amigos. Esto permite a los Amigos publicar el artículo en su fuente en nombre del usuario sin que este tenga que iniciar sesión.

Todo esto es posible mediante el uso de cookies de terceros. En este caso, la cookie de terceros se guarda en el explorador durante `platform.friends.com`, de modo que `platform.friends.com` Puede realizar la publicación en la aplicación de amigos en nombre del usuario.

Si se imagina por un momento cómo lograr este caso de uso sin cookies de terceros, el usuario tendría que seguir muchos pasos manuales. En primer lugar, el usuario tendría que copiar el enlace al artículo. En segundo lugar, el usuario tendría que iniciar sesión en la aplicación de Amigos por separado. A continuación, el usuario haría clic en el botón Crear anuncio . A continuación, el usuario copiará y pegará el vínculo en el campo de texto y, finalmente, hará clic en Publicar. Como puede ver, las cookies de terceros ayudan enormemente a los usuarios, ya que los pasos manuales se pueden reducir drásticamente.

De forma más general, las cookies de terceros permiten que los datos se almacenen en el explorador de un usuario sin que este tenga que visitar explícitamente un sitio web.

## Cuestiones de seguridad

Aunque las cookies mejoran la experiencia del usuario y la publicidad potente, también pueden introducir vulnerabilidades de seguridad, como los ataques de falsificación de solicitudes entre sitios (CSRF). Por ejemplo, si un usuario inicia sesión en un sitio bancario para pagar cuentas de tarjeta de crédito y abandona el sitio sin cerrar la sesión y luego navega a un sitio malicioso en la misma sesión, puede ocurrir un ataque de CSRF. El sitio malintencionado puede incluir código que realiza una solicitud al sitio bancario que se ejecuta cuando se carga la página. Dado que el usuario sigue estando autenticado en el sitio bancario, la cookie de sesión se puede usar para iniciar un ataque CSRF para iniciar un evento de transferencia de fondos desde la cuenta bancaria del usuario. Esto se debe a que, cada vez que visita un sitio, todas las cookies se adjuntan en la solicitud HTTP. Y debido a estas preocupaciones de seguridad, Google ahora está tratando de mitigarlas.

## ¿Cómo [!DNL Target] ¿usar cookies?

Con todo esto dicho, veamos cómo [!DNL Target] utiliza cookies. Para que use [!DNL Target] en primer lugar, debe instalar el [!DNL Target] Biblioteca JavaScript de su sitio. Esto le permite colocar una cookie de origen en el explorador del usuario que visita el sitio. A medida que el usuario interactúa con el sitio web, puede pasar los datos de comportamiento e interés del usuario a [!DNL Target] a través de la biblioteca de JavaScript. La variable [!DNL Target] La biblioteca JavaScript utiliza cookies de origen para extraer información de identificación sobre el usuario y asignarla a los datos de comportamiento e interés del usuario. Estos datos los utiliza [!DNL Target] para potenciar las actividades de personalización.

Target también (a veces) utiliza cookies de terceros. Si es propietario de varios sitios web que residen en dominios diferentes y desea rastrear el recorrido del usuario en dichos sitios web, puede utilizar cookies de terceros aprovechando el seguimiento entre dominios. Al habilitar el seguimiento entre dominios en la variable [!DNL Target] biblioteca JavaScript, su cuenta empezará a usar cookies de terceros. Como un usuario va de un dominio a otro, el explorador se comunica con el servidor back-end de [!DNL Target], y en este proceso, se crea una cookie de terceros y se coloca en el explorador del usuario. A través de la cookie de terceros que reside en el explorador del usuario, [!DNL Target] puede ofrecer una experiencia coherente en distintos dominios para un único usuario.

## Nueva fórmula de cookie de Google

Para proporcionar garantías sobre cuándo se envían cookies entre sitios para que los usuarios estén protegidos, Google tiene previsto añadir compatibilidad con un estándar IETF denominado SameSite, que requiere que los desarrolladores web gestionen cookies con el componente de atributo SameSite en el encabezado Set-Cookie.

Existen tres valores diferentes que se pueden pasar al atributo SameSite: Estricto, Laxo o Ninguno.

| Valor | Descripción |
| --- | --- |
| Estricto | Solo se puede acceder a las cookies con este ajuste al visitar el dominio en el que se estableció inicialmente. En otras palabras: Estricto bloquea completamente el uso de la cookie entre sitios. Esta opción sería mejor para las aplicaciones que requieren alta seguridad, como bancos. |
| Laxo | Las cookies con esta configuración se envían solo en solicitudes del mismo sitio o navegación de nivel superior con solicitudes HTTP que no sean idempotentes, como `HTTP GET`. Por lo tanto, esta opción se utilizaría si la cookie puede ser utilizada por terceros, pero con una ventaja de seguridad añadida que impide que los usuarios sean victimas de ataques de CSRF. |
| Ninguna | Las cookies con esta configuración funcionarán de la misma manera que las cookies funcionan hoy en día. |

Teniendo en cuenta lo anterior, Chrome 80 introduce dos configuraciones independientes para los usuarios: &quot;SameSite con cookies predeterminadas&quot; y &quot;Las cookies sin SameSite deben ser seguras&quot;. Esta configuración está habilitada de forma predeterminada en Chrome 80.

![Cuadro de diálogo SameSite](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite con cookies predeterminadas**: Cuando se configura, todas las cookies que no especifican el atributo SameSite se verán obligadas a usar automáticamente `SameSite = Lax`.
* **Las cookies sin SameSite deben ser seguras**: Cuando se configura, las cookies sin el atributo SameSite o con `SameSite = None` debe ser seguro. Seguras en este contexto significa que todas las solicitudes del explorador deben seguir el protocolo HTTPS. Las cookies que no respetan este requisito son rechazadas. Todos los sitios web deben utilizar HTTPS para cumplir este requisito.

## Target sigue las recomendaciones de seguridad de Google

En Adobe, siempre queremos ofrecer soporte a las últimas prácticas recomendadas del sector en materia de seguridad y privacidad. Nos complace anunciar que [!DNL Target] admite la nueva configuración de seguridad y privacidad introducida por Google.

Para la configuración &quot;SameSite con cookies predeterminadas&quot;, [!DNL Target] seguirá ofreciendo personalización sin ningún impacto ni intervención por su parte. [!DNL Target] usa cookies de origen y seguirá funcionando correctamente, ya que Google Chrome aplica el indicador `SameSite = Lax`.

Para la opción &quot;Cookies sin SameSite debe ser seguro&quot;, si no elige la función de seguimiento entre dominios en [!DNL Target], las cookies de origen en [!DNL Target] seguirá funcionando.

Sin embargo, cuando decide utilizar el seguimiento entre dominios para aprovechar [!DNL Target] en varios dominios, Chrome requiere `SameSite = None` y indicadores de seguridad que se utilizarán para cookies de terceros. Esto significa que debe asegurarse de que los sitios utilicen el protocolo HTTPS. Bibliotecas del lado cliente en [!DNL Target] utilizará automáticamente el protocolo HTTPS y adjuntará el `SameSite = None` y Secure marca cookies de terceros en [!DNL Target] para garantizar que todas las actividades sigan funcionando.

## ¿Qué es necesario hacer?

Para comprender lo que debe hacer para tener [!DNL Target] siga funcionando para usuarios de Google Chrome 80+, consulte la siguiente tabla, de la que verá las siguientes columnas:

* **Biblioteca JavaScript de Target**: Si utiliza at.js 1.*x* o at.js 2.*x* en sus sitios.
* **SameSite con cookies predeterminadas = Habilitado**: Si los usuarios tienen habilitado &quot;SameSite con cookies predeterminadas&quot;, ¿cómo le afectará a usted? ¿Hay algo para lo que necesite hacer? [!DNL Target] para seguir trabajando.
* **Las cookies sin SameSite deben ser seguras = Habilitado**: Si los usuarios tienen habilitado &quot;Las cookies sin SameSite deben ser seguras&quot;, ¿cómo le afectará a usted? ¿Hay algo que necesite hacer para tener [!DNL Target] siga funcionando.

| Biblioteca JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| at.js 1.*x*  con cookie de origen. | Sin impacto. | Sin impacto si no utiliza el seguimiento entre dominios. |
| at.js 1.*x*  con seguimiento entre dominios habilitado. | Sin impacto. | Debe habilitar el protocolo HTTPS para su sitio.<br>[!DNL Target] utiliza una cookie de terceros para rastrear usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y marca segura. El indicador Secure requiere que sus sitios utilicen el protocolo HTTPS. |
| at.js 2.*x*  | Sin impacto. | Sin impacto. |

## Qué hace [!DNL Target] ¿necesita hacer?

Entonces, ¿qué hemos de hacer en nuestra plataforma para ayudarle a cumplir con las nuevas políticas de cookies de Google Chrome 80+ SameSite?

| Biblioteca JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| at.js 1.*x*  con cookie de origen. | Sin impacto. | Sin impacto si no utiliza el seguimiento entre dominios. |
| at.js 1.*x*  con seguimiento entre dominios habilitado. | Sin impacto. | at.js 1.*x*  con seguimiento entre dominios habilitado. |
| at.js 2.*x*  | Sin impacto. | Sin impacto. |

## ¿Cuál es el impacto si no pasa a utilizar el protocolo HTTPS?

El único caso de uso que le afectará es si utiliza la función de seguimiento entre dominios en [!DNL Target] a at.js 1.*x*. Sin pasar a HTTPS, que es un requisito de Google, verá un pico en los visitantes únicos en sus dominios, ya que Google eliminará la cookie de terceros que usamos. Y debido a que se eliminará la cookie de terceros, [!DNL Target] no podrá proporcionar una experiencia coherente y personalizada para ese usuario a medida que este navega de un dominio a otro. La cookie de terceros se utiliza principalmente para identificar a un único usuario que navega entre sus dominios.

## Conclusión. 

A medida que el sector realiza avances para crear una web más segura para los consumidores, [!DNL Adobe] está absolutamente comprometido a ayudar a nuestros clientes a ofrecer experiencias personalizadas de una manera que garantice la seguridad y la privacidad para los usuarios finales. Todo lo que debe hacer es seguir las prácticas recomendadas mencionadas anteriormente y aprovechar [!DNL Target] para cumplir con las nuevas directivas de cookies de SameSite de Google Chrome.
