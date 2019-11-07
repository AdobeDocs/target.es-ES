---
keywords: google;samesite;cookies;chrome 80;ietf
description: Información sobre Adobe Target y el estándar SameSite IETF introducido con Google Chrome versión 80.
title: Directivas de cookies de Adobe Target y SameSite de Google
subtopic: Primeros pasos
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Políticas de cookies de Google Chrome samesite

Google empezará a imponer nuevas directivas de cookies de forma predeterminada para los usuarios a partir de Chrome 80, que está previsto que se publique a principios de 2020. Este artículo explica todo lo que necesita saber sobre las nuevas directivas de cookies del SameSite, cómo [!DNL Adobe Target] admiten estas políticas y cómo puede utilizar [!DNL Target] para cumplir con las nuevas directivas de cookies del mismo sitio de Google Chrome.

A partir de Chrome 80, los desarrolladores web deben especificar explícitamente qué cookies pueden funcionar en distintos sitios web. Este es el primero de muchos anuncios que Google planea hacer para mejorar la privacidad y la seguridad en la web.

Dado que Facebook ha estado en el candelero con respecto a la privacidad y la seguridad, otros actores importantes como Apple, y ahora Google, han aprovechado la oportunidad para crear nuevas identidades como campeones de privacidad y seguridad. Apple lideró el paquete al anunciar por primera vez cambios en sus políticas de cookies a principios de este año a través de ITP 2.1 y recientemente, ITP 2.2. En ITP 2.1, Apple bloquea completamente las cookies de terceros y mantiene las cookies creadas en el explorador durante solo siete días. En ITP 2.2, las cookies se conservan sólo durante un día. El anuncio de Google no es tan agresivo como el de Apple, pero es el primer paso hacia el mismo objetivo final. Para obtener más información sobre las políticas de Apple, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## ¿Qué son las cookies y cómo se utilizan?

Antes de profundizar en los cambios de Google en sus políticas de cookies, vamos a tocar qué son las cookies y cómo se utilizan. En pocas palabras, las cookies son pequeños archivos de texto almacenados en el explorador Web que se utilizan para recordar los atributos del usuario.

Las cookies son importantes porque mejoran la experiencia del usuario a medida que navega por la web. Por ejemplo: si va a comprar en un sitio web de comercio electrónico y agrega algo al carro de compras pero no inicia sesión ni compra en esa visita, las cookies recuerdan los artículos y los guardan en el carro de compras para la próxima visita. O imaginen si se vieron obligados a volver a introducir su nombre de usuario y contraseña cada vez que visiten su sitio web de medios sociales favorito. Las cookies también resuelven ese problema, ya que almacenan información que ayuda a los sitios a identificar quién es usted. Este tipo de cookies se denominan cookies de origen porque son creadas y utilizadas por el sitio web que ha visitado.

También existen cookies de terceros. Para comprenderlos mejor, consideremos este ejemplo:

Digamos que una hipotética empresa de medios sociales llamada "Amigos" proporciona un botón Compartir que otros sitios implementan para permitir a los usuarios de Amigos compartir el contenido del sitio en la fuente Amigos. Ahora, un usuario lee un artículo de noticias en un sitio web de noticias que utiliza el botón Compartir y hace clic en él para publicar automáticamente en su cuenta de amigos.

Para que esto suceda, el explorador obtiene el botón Compartir amigos desde `platform.friends.com` cuando se carga el artículo de noticias. Dentro de este proceso, el explorador adjunta las cookies de Amigos, que contienen las credenciales de inicio de sesión del usuario, a la solicitud a los servidores de Amigos. Esto permite a los amigos publicar el artículo en su fuente en nombre del usuario sin que el usuario tenga que iniciar sesión.

Todo esto es posible mediante cookies de terceros. En este caso, la cookie de terceros se guarda en el navegador para `platform.friends.com`que pueda `platform.friends.com` publicarse en la aplicación de amigos en nombre del usuario.

Si imagina por un momento cómo lograr este caso de uso sin cookies de terceros, el usuario tendría que seguir muchos pasos manuales. Primero, el usuario tendría que copiar el enlace al artículo de noticias. En segundo lugar, el usuario tendría que iniciar sesión en la aplicación Amigos por separado. A continuación, el usuario haría clic en el botón Crear anuncio. A continuación, el usuario copiará y pegará el vínculo en el campo de texto y, finalmente, hará clic en Publicar. Como puede ver, las cookies de terceros ayudan enormemente a los usuarios, ya que los pasos manuales se pueden reducir drásticamente.

De manera más general, las cookies de terceros permiten almacenar datos en el explorador de un usuario sin que este tenga que visitar explícitamente un sitio web.

## Problemas de seguridad

Aunque las cookies mejoran la experiencia del usuario y la publicidad potente, también pueden introducir vulnerabilidades de seguridad como los ataques de falsificación de solicitudes entre sitios (CSRF). Por ejemplo: si un usuario inicia sesión en un sitio bancario para pagar facturas de tarjeta de crédito y abandona el sitio sin cerrar sesión y luego navega a un sitio malintencionado en la misma sesión, puede producirse un ataque de CSRF. El sitio malintencionado puede incluir código que realiza una solicitud al sitio bancario que se ejecuta cuando se carga la página. Dado que el usuario sigue autenticado en el sitio bancario, la cookie de sesión puede utilizarse para iniciar un ataque de CSRF a fin de iniciar un evento de transferencia de fondos desde la cuenta bancaria del usuario. Esto se debe a que cada vez que visita un sitio, todas las cookies se adjuntan en la solicitud HTTP. Y debido a estas preocupaciones de seguridad, Google ahora está tratando de mitigarlas.

## ¿Cómo utiliza Target las cookies?

Con todo lo dicho, veamos cómo [!DNL Target] usan las cookies. Para poder usar [!DNL Target] en primer lugar, debe instalar la biblioteca [!DNL Target] JavaScript en el sitio. Esto le permite colocar una cookie de origen en el explorador del usuario que visita el sitio. A medida que el usuario interactúa con el sitio web, puede pasar los datos de comportamiento e interés del usuario a [!DNL Target] través de la biblioteca JavaScript. La biblioteca [!DNL Target] JavaScript utiliza cookies de origen para extraer información de identificación del usuario y asignarla a los datos de comportamiento e interés del usuario. Estos datos son utilizados por [!DNL Target] el usuario para potenciar sus actividades de personalización.

Target también utiliza (a veces) cookies de terceros. Si tiene varios sitios web que viven en diferentes dominios y desea rastrear el viaje del usuario en esos sitios web, puede utilizar cookies de terceros mediante el seguimiento entre dominios. Al habilitar el seguimiento entre dominios en la biblioteca [!DNL Target] JavaScript, su cuenta comenzará a utilizar cookies de terceros. A medida que un usuario va de un dominio a otro, el explorador se comunica con el servidor back-end de [!DNL Target], y en este proceso se crea una cookie de terceros que se coloca en el explorador del usuario. A través de la cookie de terceros que reside en el navegador del usuario, [!DNL Target] puede ofrecer una experiencia coherente en distintos dominios para un único usuario.

## Nueva fórmula de cookie de Google

Para ofrecer garantías sobre cuándo se envían las cookies a través de los sitios para que los usuarios estén protegidos, Google planea agregar compatibilidad con un estándar IETF llamado SameSite, que requiere que los programadores Web administren las cookies con el componente de atributo SameSite en el encabezado Set-Cookie.

Existen tres valores diferentes que se pueden pasar al atributo SameSite: Estricto, Laxo o Ninguno.

| Valor | Descripción |
| --- | --- |
| Estricto | Solo se puede acceder a las cookies con este ajuste al visitar el dominio en el que se estableció inicialmente. En otras palabras: Estricto bloquea completamente el uso de la cookie entre sitios. Esta opción sería la mejor para las aplicaciones que requieren alta seguridad, como los bancos. |
| Laxo | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. Por lo tanto, esta opción se utilizaría si la cookie puede ser utilizada por terceros, pero con una ventaja de seguridad adicional que protege a los usuarios de ser víctimas de ataques de CSRF. |
| Ninguna | Las cookies con esta configuración funcionarán de la misma manera que las cookies en la actualidad. |

Teniendo en cuenta lo anterior, Chrome 80 introduce dos configuraciones independientes para los usuarios: "SameSite de forma predeterminada cookies" y "Las cookies sin SameSite deben ser seguras". Esta configuración se activará de forma predeterminada en Chrome 80.

![SameSite, cuadro de diálogo](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite de forma predeterminada cookies**: Cuando se configura, todas las cookies que no especifican el atributo SameSite se verán obligadas a usar automáticamente `SameSite = Lax`.
* **Las cookies sin SameSite deben ser seguras**: Cuando se configuran, las cookies sin el atributo SameSite o con `SameSite = None` deben ser seguras. Seguras en este contexto significa que todas las solicitudes del explorador deben seguir el protocolo HTTPS. Las cookies que no respetan este requisito son rechazadas. Todos los sitios web deben utilizar HTTPS para cumplir este requisito.

## Target sigue las recomendaciones de seguridad de Google

En Adobe, siempre queremos ofrecer compatibilidad con las prácticas recomendadas más recientes del sector para la seguridad y la privacidad. We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

Para la configuración "SameSite de forma predeterminada cookies", [!DNL Target] seguirá ofreciendo personalización sin ningún impacto ni intervención por parte suya. [!DNL Target] usa cookies de origen y seguirá funcionando correctamente, ya que Google Chrome aplica el indicador `SameSite = Lax`.

Para la opción "Las cookies sin SameSite deben ser seguras", si no se ha incluido en la función de seguimiento entre dominios de [!DNL Target], las cookies de origen de [!DNL Target] seguirán funcionando.

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. Esto significa que debe asegurarse de que los sitios utilizan el protocolo HTTPS. Las bibliotecas del lado del cliente de [!DNL Target] utilizarán automáticamente el protocolo HTTPS y adjuntarán los indicadores `SameSite = None` y de seguridad a las cookies de terceros [!DNL Target] para garantizar que todas las actividades sigan funcionando.

## ¿Qué es necesario hacer?

Para comprender lo que debe hacer para que los usuarios de Google Chrome 80+ [!DNL Target] sigan funcionando, consulte la tabla siguiente, de la que verá las siguientes columnas:

* **Biblioteca** de JavaScript de Target: Si utiliza mbox.js, at.js 1.*x* o at.js 2.*x* en sus sitios.
* **SameSite de forma predeterminada cookies = Habilitado**: Si los usuarios tienen "SameSite de forma predeterminada" habilitado, ¿cómo le afecta y qué debe hacer para [!DNL Target] continuar funcionando?
* **Las cookies sin SameSite deben ser seguras = Habilitadas**: Si los usuarios tienen habilitada la opción "Las cookies sin SameSite deben ser seguras", ¿cómo le afecta y hay algo que necesite hacer para [!DNL Target] seguir funcionando?

| Biblioteca de JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| mbox.js solo con cookies de origen. | Sin impacto. | No tiene impacto si no utiliza el seguimiento entre dominios. |
| mbox.js con el seguimiento entre dominios habilitado. | Sin impacto. | Debe habilitar el protocolo HTTPS para el sitio.<br>[!DNL Target] utiliza una cookie de terceros para rastrear a los usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y un indicador de seguridad. El indicador de seguridad requiere que los sitios utilicen el protocolo HTTPS. |
| at.js 1.*x*  con cookie de origen. | Sin impacto. | No tiene impacto si no utiliza el seguimiento entre dominios. |
| at.js 1.*x*  con el seguimiento entre dominios habilitado. | Sin impacto. | Debe habilitar el protocolo HTTPS para el sitio.<br>[!DNL Target] utiliza una cookie de terceros para rastrear a los usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y un indicador de seguridad. El indicador de seguridad requiere que los sitios utilicen el protocolo HTTPS. |
| at.js 2.*x*  | Sin impacto. | Sin impacto. |

## ¿Qué debe hacer Target?

Entonces, ¿qué teníamos que hacer en nuestra plataforma para ayudarle a cumplir con las nuevas políticas de cookies Google Chrome 80+ SameSite?

| Biblioteca de JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| mbox.js solo con cookies de origen. | Sin impacto. | No tiene impacto si no utiliza el seguimiento entre dominios. |
| mbox.js con el seguimiento entre dominios habilitado. | Sin impacto. | [!DNL Target] agrega `SameSite = None` y marca de seguridad a la cookie de terceros cuando se llama a [!DNL Target] los servidores. |
| at.js 1.*x*  con cookie de origen. | Sin impacto. | No tiene impacto si no utiliza el seguimiento entre dominios. |
| at.js 1.*x*  con el seguimiento entre dominios habilitado. | Sin impacto. | at.js 1.*x*  con el seguimiento entre dominios habilitado. |
| at.js 2.*x*  | Sin impacto. | Sin impacto. |

## ¿Cuál es el impacto si no pasa a utilizar el protocolo HTTPS?

El único caso de uso que le afectará es si está utilizando la función de seguimiento entre dominios en [!DNL Target] mbox.js o at.js 1.*x*. Sin pasar a HTTPS, que es un requisito de Google, verá un pico de visitantes únicos en sus dominios porque Google eliminará la cookie de terceros que utilizamos. Y como la cookie de terceros se eliminará, no [!DNL Target] podrá proporcionar una experiencia consistente y personalizada para ese usuario a medida que el usuario navega de un dominio a otro. La cookie de terceros se utiliza principalmente para identificar a un único usuario que navega por los dominios que le pertenecen.

## Conclusión. 

A medida que la industria avanza en la creación de una web más segura para los consumidores, [!DNL Adobe] está totalmente comprometida a ayudar a nuestros clientes a ofrecer experiencias personalizadas de manera que se garantice la seguridad y la privacidad de los usuarios finales. Todo lo que necesita hacer es seguir las prácticas recomendadas antes mencionadas y aprovechar [!DNL Target] para cumplir con las nuevas directivas de cookies del mismo sitio de Google Chrome.
