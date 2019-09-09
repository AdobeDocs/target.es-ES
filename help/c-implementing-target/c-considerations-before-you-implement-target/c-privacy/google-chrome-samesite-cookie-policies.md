---
description: Información sobre Target y el estándar SameSite IETF utilizado con Google Chrome versión 76.
keywords: google;samesite; cookies; chrome 80; ietf
seo-description: Información sobre Adobe Target y el estándar SameSite IETF introducido con Google Chrome versión 80.
seo-title: Políticas de cookies samesite de Adobe Target y Google
solution: Target
subtopic: Primeros pasos
title: Políticas de cookies de Google Chrome samesite
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Políticas de cookies de Google Chrome samesite

Google empezará a imponer nuevas directivas de cookies de forma predeterminada para los usuarios que comiencen con Chrome 80, que se lanzará a principios de 2020. Este artículo explica todo lo que necesita saber acerca de las nuevas políticas de cookies samesite, cómo [!DNL Adobe Target] admite estas políticas y cómo puede utilizar [!DNL Target] para cumplir con las nuevas políticas de cookies samesite de Google Chrome.

A partir de Chrome 80, los programadores web deben especificar explícitamente qué cookies pueden funcionar en distintos sitios web. Este es el primer de muchos anuncios que Google planea realizar para mejorar la privacidad y seguridad en la Web.

Dado que Facebook ha estado en la licencia urgente con respecto a la privacidad y seguridad, otros actores importantes como Apple y Google, han sido rápidos en aprovechar la oportunidad para crear nuevas identidades como promociones de privacidad y seguridad. Apple llevó el paquete al primer anuncio de sus políticas de cookies a principios de este año a través de ITP 2.1 y versiones anteriores, ITP 2.2. En ITP 2.1, Apple bloquea completamente las cookies de terceros y mantiene las cookies creadas en el explorador durante solo siete días. En ITP 2.2, las cookies se conservan sólo durante un día. El anuncio de Google no está casi cerca de agresivo como Apple pero es el primer paso hacia el mismo objetivo final. Para obtener más información sobre las políticas de Apple, consulte [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## ¿Qué son las cookies y cómo se utilizan?

Antes de sumergirse en los cambios de Google en las políticas de cookies, analicemos qué son las cookies y cómo se utilizan. Simplemente, las cookies son pequeños archivos de texto almacenados en el explorador Web que se utilizan para recordar atributos de usuario.

Las cookies son importantes porque mejoran la experiencia del usuario a medida que navegan por la web. Por ejemplo: si está comprando en un sitio web de comercio electrónico y agregando algo al carro pero no inicia sesión o compra en esa visita, las cookies recuerdan los artículos y los mantendrán en el carro de compras para la próxima visita. O bien, imagine si se le obligó a volver a introducir su nombre de usuario y contraseña cada vez que visite su sitio web favorito de medios sociales. Las cookies también resuelven el problema porque almacenan información que ayuda a los sitios a identificar quién lo está. Estos tipos de cookies se denominan cookies de origen porque el sitio Web que visitó las crea y utiliza.

También existen cookies de terceros. Para comprenderlos mejor, veamos este ejemplo:

Supongamos que una empresa hipotética de redes sociales llamada "Amigos" proporciona un botón Compartir que otros sitios implementan para permitir que los usuarios de Amigos compartan el contenido del sitio en la fuente Amigos. Ahora, un usuario lee un artículo de noticias en un sitio web de noticias que utiliza el botón Compartir y hace clic en él para publicar automáticamente en su cuenta de Amigos.

Para que esto ocurra, el navegador obtiene el botón Compartir amigos desde `platform.friends.com` la carga del artículo de noticias. En este proceso, el explorador adjunta las cookies de Amigos, que contienen las credenciales de inicio de sesión del usuario, a la solicitud a los servidores de Amigos. Esto permite que los amigos anuncien el artículo de noticias en su fuente en nombre del usuario sin requerir que el usuario inicie sesión.

Esto es posible mediante cookies de terceros. En este caso, la cookie de terceros se guarda en el explorador para que `platform.friends.com`pueda realizar `platform.friends.com` la publicación en la aplicación Amigos en nombre del usuario.

Si imagine por un momento cómo conseguir este caso de uso sin cookies de terceros, el usuario deberá seguir muchos pasos manuales. Primero, el usuario tendría que copiar el vínculo al artículo de noticias. Segundo, el usuario tendría que iniciar sesión en la aplicación Amigos por separado. A continuación, el usuario haría clic en el botón Crear anuncio. A continuación, el usuario copiaría y pegará el vínculo en el campo de texto y, finalmente, haga clic en Publicar. Como puede ver, las cookies de terceros ayudan enormemente a la experiencia del usuario a medida que se pueden reducir drásticamente los pasos manuales.

De forma más general, las cookies de terceros hacen posible que los datos se almacenen en el explorador del usuario sin que sea necesario que el usuario visite explícitamente un sitio Web.

## Razones de seguridad

Aunque las cookies mejoran las experiencias del usuario y la publicidad de energía, también pueden introducir vulnerabilidades de seguridad como ataques de falsificación de solicitudes entre sitios (CSRF). Por ejemplo, si un usuario inicia sesión en un sitio bancario para pagar facturas de tarjetas de crédito y abandona el sitio sin cerrar sesión y luego navega a un sitio malicioso en la misma sesión, puede producirse un ataque CSRF. El sitio malicioso podría incluir código que realice una solicitud al sitio bancario que se ejecuta cuando se carga la página. Dado que el usuario aún está autenticado en el sitio bancario, la cookie de sesión se puede utilizar para iniciar un ataque CSRF para iniciar un evento de transferencia de fondos fuera de la cuenta bancaria del usuario. Esto se debe a que cada vez que visita un sitio, todas las cookies se adjuntan en la solicitud HTTP. Y debido a estas preocupaciones sobre seguridad, Google está intentando mitigarlas.

## ¿Cómo utiliza Target las cookies?

Con todo lo que dice, veamos cómo [!DNL Target] usa las cookies. Para que pueda utilizar [!DNL Target] en primer lugar, debe instalar la biblioteca [!DNL Target] JavaScript en su sitio. Esto permite colocar una cookie de origen en el explorador del usuario que visita el sitio. A medida que el usuario interactúa con su sitio web, puede transferir los datos de comportamiento e interés del usuario a [!DNL Target] través de la biblioteca JavaScript. La biblioteca [!DNL Target] JavaScript utiliza cookies de origen para extraer información de identificación sobre el usuario para que se asigne a los datos de comportamiento y de comportamiento del usuario. A continuación, estos datos se utilizan [!DNL Target] para potenciar las actividades de personalización.

Target también utiliza cookies de terceros (a veces). Si posee varios sitios web que viven en distintos dominios y desea rastrear el viaje del usuario en esos sitios web, puede utilizar cookies de terceros aprovechando el seguimiento entre dominios. Al habilitar el seguimiento entre dominios en la biblioteca [!DNL Target] JavaScript, su cuenta empezará a utilizar cookies de terceros. Como un usuario salta de un dominio a otro, el explorador se comunica con el servidor back-end de [!DNL Target]y, en este proceso, se crea una cookie de terceros y se coloca en el explorador del usuario. A través de la cookie de terceros que reside en el navegador del usuario, [!DNL Target] puede ofrecer una experiencia coherente entre los distintos dominios para un único usuario.

## Nueva fórmula de cookie de Google

Para proporcionar garantías sobre cuándo se envían cookies entre sitios para que los usuarios estén protegidos, Google planea agregar compatibilidad con un estándar IETF denominado samesite, que requiere que los programadores web gestionen cookies con el componente de atributos samesite en el encabezado de Cookie Set-Cookie.

Existen tres valores diferentes que se pueden pasar al atributo SameSite: Estricto, Laxo o Ninguno.

| Valor | Descripción |
| --- | --- |
| Estricto | Solo se puede acceder a las cookies con este ajuste al visitar el dominio en el que se estableció inicialmente. En otras palabras: Estricto bloquea completamente el uso de la cookie entre sitios. Esta opción sería mejor para las aplicaciones que requieran alta seguridad, como bancos. |
| Laxo | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. Por lo tanto, esta opción se utilizará si la cookie puede ser utilizada por terceros, pero con una ventaja de seguridad añadida que impide que los usuarios sean victimizados por ataques CSRF. |
| Ninguna | Las cookies con esta configuración funcionarán de la misma manera que las cookies funcionan hoy. |

Con la información anterior en mente, Chrome 80 presenta dos configuraciones independientes para los usuarios: " Samesite por cookies predeterminadas "y" Cookies sin samesite debe ser seguro ". Estos ajustes se activarán de forma predeterminada en Chrome 80.

![Cuadro de diálogo samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Samesite por cookies predeterminadas**: Cuando se configura, se forzará automáticamente a utilizar `SameSite = Lax`todas las cookies que no especifican el atributo samesite.
* **Las cookies sin samesite deben ser seguras**: Cuando se configura, las cookies sin el atributo samesite o `SameSite = None` con necesidad de ser seguras. Seguras en este contexto significa que todas las solicitudes del explorador deben seguir el protocolo HTTPS. Las cookies que no respetan este requisito son rechazadas. Todos los sitios web deben utilizar HTTPS para cumplir este requisito.

## Target sigue las recomendaciones de seguridad de Google

En Adobe, siempre queremos apoyar las últimas prácticas recomendadas del sector para seguridad y privacidad. We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

Para la configuración «samesite by default cookies», [!DNL Target] seguirá ofreciendo personalización sin ningún impacto e intervención por parte de usted. [!DNL Target] usa cookies de origen y seguirá funcionando correctamente, ya que Google Chrome aplica el indicador `SameSite = Lax`.

En la opción «Cookies sin samesite debe ser segura», si no elige la función de seguimiento entre dominios en [!DNL Target], las cookies de origen de sí [!DNL Target] seguirán funcionando.

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. Esto significa que debe asegurarse de que los sitios utilicen el protocolo HTTPS. Las bibliotecas del lado del cliente utilizarán [!DNL Target] automáticamente el protocolo HTTPS y adjuntarán `SameSite = None` los indicadores y los indicadores seguros a cookies de terceros para [!DNL Target] garantizar que todas las actividades sigan entregándose.

## ¿Qué es necesario hacer?

Para comprender qué es lo que necesita para [!DNL Target] continuar trabajando para los usuarios de Google Chrome 80 +, consulte la tabla siguiente, de la cual verá las siguientes columnas:

* **Biblioteca de JavaScript de Target**: Si utiliza mbox. js, at. js 1.*x* o at.js 2.*x* en sus sitios.
* **Samesite por cookies predeterminadas = Habilitado**: Si los usuarios tienen "samesite por predeterminado cookies" habilitada,¿cómo le afecta a usted y es algo que debe hacer para [!DNL Target] continuar funcionando?
* **Las cookies sin samesite deben ser seguras = Habilitado**: Si los usuarios tienen la opción «Cookies sin samesite debe ser segura»,¿cómo le afectará y es algo que necesita para [!DNL Target] continuar funcionando?

| Biblioteca de JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| mbox. js solo con cookies de origen. | Sin impacto. | Sin impacto si no usa seguimiento entre dominios. |
| mbox. js con el seguimiento entre dominios habilitado. | Sin impacto. | Debe habilitar el protocolo HTTPS para el sitio.<br>[!DNL Target] utiliza una cookie de terceros para rastrear usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y tengan indicador seguro. El indicador Secure requiere que sus sitios usen el protocolo HTTPS. |
| at.js 1.*x* con cookies de origen. | Sin impacto. | Sin impacto si no usa seguimiento entre dominios. |
| at.js 1.*x* con el seguimiento entre dominios habilitado. | Sin impacto. | Debe habilitar el protocolo HTTPS para el sitio.<br>[!DNL Target] utiliza una cookie de terceros para rastrear usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y tengan indicador seguro. El indicador Secure requiere que sus sitios usen el protocolo HTTPS. |
| at.js 2.*x* | Sin impacto. | Sin impacto. |

## ¿Qué necesita hacer Target?

Entonces,¿qué debemos hacer en nuestra plataforma para ayudarle a cumplir con las nuevas políticas de cookies de Google Chrome 80 + samesite?

| Biblioteca de JavaScript de Target | SameSite con cookies predeterminadas = Habilitado | Las cookies sin SameSite debe ser seguras = Habilitado |
| --- | --- | --- |
| mbox. js solo con cookies de origen. | Sin impacto. | Sin impacto si no usa seguimiento entre dominios. |
| mbox. js con el seguimiento entre dominios habilitado. | Sin impacto. | [!DNL Target] agrega `SameSite = None` y Marca segura a la cookie de terceros cuando se llama [!DNL Target] a los servidores. |
| at.js 1.*x* con cookies de origen. | Sin impacto. | Sin impacto si no usa seguimiento entre dominios. |
| at.js 1.*x* con el seguimiento entre dominios habilitado. | Sin impacto. | at.js 1.*x* con el seguimiento entre dominios habilitado. |
| at.js 2.*x* | Sin impacto. | Sin impacto. |

## ¿Cuál es el impacto si no pasa a utilizar el protocolo HTTPS?

El único caso de uso que tendrá impacto es si utiliza la función de seguimiento entre dominios en [!DNL Target] mbox. js o at. js 1.*x*. Sin pasar a HTTPS, que es un requisito de Google, verá un pico en visitantes únicos de sus dominios porque Google retirará la cookie de terceros que usamos. Y debido a que se retirará la cookie de terceros, [!DNL Target] no podrá ofrecer una experiencia coherente y personalizada a medida que el usuario navega de un dominio a otro. La cookie de terceros se utiliza principalmente para identificar a un único usuario que navega por los dominios que posee.

## Conclusión.

Dado que el sector realiza avances para crear una Web más segura para los consumidores, [!DNL Adobe] tiene la absoluta intención de ayudar a nuestros clientes a ofrecer experiencias personalizadas de manera que garanticen la seguridad y privacidad de los usuarios finales. Todo lo que necesita hacer es seguir las optimizaciones mencionadas y aprovechar [!DNL Target] las ventajas de cumplir con las nuevas políticas de cookies samesite de Google Chrome.
