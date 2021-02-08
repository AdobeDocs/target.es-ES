---
keywords: at.js;2.0;1.x;cookies
description: Detalles sobre la administración de cookies de Adobe Target at.js 2.x y at.js 1.x
title: Cookies de at.js
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1821'
ht-degree: 98%

---


# Cookies de at.js {#at-js-cookies}

Información sobre at.js 2.x y at.js 1.Comportamiento de la cookie de *x*

## Comportamiento de la cookie at.js 2.x

Para la versión 2.0.0 de at.js, *solo se admiten cookies de origen*. Como en at.js 1.La cookie de origen, *x*, “mbox”, se almacena en `clientdomain.com`, donde `clientdomain` es su dominio.

at.js genera un ID de sesión y la almacena ahí la cookie. La primera respuesta contiene toda la información de la actividad, así como `TNT` o `PC ID` generados por los servidores de [!DNL Target]. A continuación, at.js escribe `TNT/PC ID` en la cookie.

[!DNL Experience Cloud ID Service]siempre establece la cookie `AMCV_###@AdobeOrg` de origen, aunque `ECID` se pasa en solicitudes de [!DNL Target].

### No se admiten cookies de terceros ni seguimiento de dominios cruzados.

El seguimiento entre dominios permite ver sesiones en dos sitios relacionados, pero con distintos dominios, como una sola sesión. Puede crear una actividad de [!DNL Target] que abarque `siteA.com` y `siteB.com`, y que el visitante permanezca en la misma experiencia cuando se compartan dominios. Esta funcionalidad se vincula a at.js 1.Comportamiento de cookies de terceros y de origen de *x*.

En at.js 1.*x*, la cookie de terceros se almacenó en el dominio `[CLIENTCODE].tt.omtrdc.net` y la de origen en `clientdomain.com`. La primera solicitud devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, y se devuelve una solicitud de redirección con un parámetro adicional (`mboxXDomainCheck=true`). Si el explorador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve. Este flujo de trabajo era posible gracias a at.js 1.*x* utilizó el método HTTP GET.

Sin embargo, en at.js 2.x, ya no se utiliza HTTP GET, sino HTTP POST. HTTP POST se utiliza a través de at.js para enviar cargas JSON a servidores Edge de [!DNL Target] en lugar de parámetros de valor clave. Esto significa que la solicitud de redirección para comprobar si un explorador admite cookies de terceros se interrumpe. Esto se debe a que las solicitudes HTTP GET son transacciones idempotentes mientras que HTTP POST no es idempotente ni se debe repetir arbitrariamente.

Por lo tanto, ni las cookies de terceros ni el seguimiento entre dominios son compatibles en at.js 2.0.0.

## at.js 1.Comportamiento de la cookie *x* {#at-js-1x-cookie-behavior}.

Para las versiones 1 de at.js.*x*, el comportamiento de la cookie depende de si es una cookie de origen, una cookie de terceros con una cookie de origen o solo una cookie de terceros.

### Cuándo usar cookies de origen o de terceros

La configuración del sitio determina las cookies que se utilizarán. A la hora de saber cuándo usar cookies de origen y cookies de terceros, resulta útil conocer el modo en que funciona Target. Para obtener más información, consulte [Funcionamiento de Adobe Target](/help/c-intro/how-target-works.md).

Hay tres casos principales para el uso de cookies:

1. Un dominio.

   Todas las pruebas tienen lugar en un dominio de primer nivel (`www.domain.com`, `store.domain.com`, `anysub.domain.com`, etc.).

   Usar solo cookies de origen. Este es el predeterminado.

1. Los usuarios cruzan dominios y quiere rastrear y comprobar su comportamiento en estos dominios.

   Ejemplo: un usuario visita su sitio para comprar pero cierra la compra a través de establecimientos de Yahoo. Tres métodos (acuda al representante de la cuenta para saber cuál es el más adecuado):

   * Habilitar cookies de origen y de terceros.
   * Habilitar solo las de terceros (no es habitual, pero presenta la ventaja de mantener la cookie de at.js fuera de su dominio).
   * Activar solo las cookies de origen y transmitir el parámetro `mboxSession` al cruzar el dominio.

      El parámetro `mboxSession` se debe pasar a una página de destino donde exista una referencia a at.js. No puede ser una página de redirector intermedia.

1. En un sitio de terceros, solo se usan adBox o Flashbox.

   Dos métodos (acuda al administrador de servicios de cliente para saber cuál es el más adecuado):

   * Habilitar cookies de origen y de terceros.

      Se requieren cookies de origen y de terceros para los Flashbox y los elementos creativos dinámicos.

   * Habilitar solo las cookies de terceros.

      Este método solo se aplica en el más que improbable caso de que se usen implementaciones de AdBoxes sin segmentación en el sitio.

### Comportamiento de cookie de origen

La cookie de origen se almacena en `clientdomain.com`, donde `clientdomain` es su dominio.

at.js genera un `mboxSession ID` y lo almacena en la cookie. La primera respuesta de contiene la oferta, así como el JavaScript para almacenar el `mboxPC ID` que la aplicación ha generado en la cookie de

>[!NOTE]
>
>La cookie de origen `AMCV_###@AdobeOrg` siempre se establece con [!DNL Experience Cloud Visitor ID].

### Comportamiento de cookie de terceros

La cookie de terceros se almacena en `clientcode.tt.omtrdc.net` y la de origen en `clientdomain.com`, donde `clientdomain` es su dominio.

at.js genera un `mboxSession ID`. La primera solicitud de ubicación devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, y se devuelve una solicitud de redirección con un parámetro extra (`mboxXDomainCheck=true`).

Si el navegador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve.

Si el navegador rechaza cookies de terceros, la solicitud de redirección no incluye dichas cookies y se muestra el contenido predeterminado de todas las ubicaciones en la página. Como no hay cookies definidas, el mismo proceso anterior se vuelve a producir en cada solicitud de página.

### Comportamiento de cookies de terceros y de origen

La cookie de terceros se almacena en `clientcode.tt.omtrdc.net` y la de origen en `clientdomain.com`, donde `clientdomain` es su dominio.

at.js genera un `mboxSession ID`. La primera solicitud de ubicación devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, y se devuelve una solicitud de redirección con un parámetro extra (`mboxXDomainCheck=true`).

Si el navegador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve.

Algunos navegadores rechazan las cookies de terceros. Si se bloquea la cookie de terceros, la cookie de origen seguirá funcionando. [!DNL Target] intenta establecer la cookie de terceros y, en caso de no poder, [!DNL Target] solo puede realiza el seguimiento en el dominio específico del cliente. El seguimiento entre dominios no funcionará si se bloquean las cookies de terceros, a menos que se añada `mboxSession` al vínculo entre dominios. En dicho caso, se definirá otra cookie de origen que se sincronizará con la cookie de origen del dominio anterior.

## Configuración de la cookie

La cookie tiene varias configuraciones predeterminadas. En caso necesario, puede modificar esta configuración a excepción de la duración de la cookie. Acuda al representante de la cuenta cuando vaya a cambiar la configuración de la cookie.

| Configuración | Información |
|--- |--- |
| Nombre de la cookie | mbox. |
| Dominio de la cookie | Niveles segundo y superior de los dominios desde los que se proporciona el contenido. Dado que se proporciona desde el dominio de la compañía, se trata de una cookie de origen. Ejemplo: `mycompany.com`. |
| Dominio del servidor | `clientcode.tt.omtrdc.net`, usando el código de cliente de su cuenta. |
| Duración de la cookie | La cookie permanece en el explorador del visitante dos años después de su último inicio de sesión. La duración de la cookie no se puede cambiar. |
| Directiva P3P | Tal y como precisa la configuración predeterminada de la mayoría de los navegadores, la cookie se publica con una directiva P3P. Una directiva P3P indica el navegador que proporciona la cookie y el modo en que se va a usar la información. |

La cookie conserva una serie de valores para administrar la forma en que los visitantes viven las campañas de

| Valor | Definición |
|--- |--- |
| session ID | Identificador exclusivo de una sesión de usuario. De manera predeterminada, tiene una duración de 30 minutos. |
| pc ID | Identificador semipermanente del navegador de un visitante. Dura 14 días. |
| check | Sencillo valor de prueba que sirve para averiguar si un visitante admite cookies. Se establece cada vez que un visitante solicita una página. |
| disable | Se establece si el tiempo de carga de un visitante supera el tiempo de espera fijado en el archivo mbox.js. De manera predeterminada, tiene una duración de 1 hora. |

## Impacto en Target de los cambios que Apple ha introducido en el seguimiento de WebKit para visitantes con Safari

Tenga en cuenta lo siguiente:

### ¿Cómo funciona el seguimiento de Adobe Target?

| Cookies | Detalles |
|--- |--- |
| Dominios de origen | Esta es la implementación estándar para los clientes de Target.  La cookie “mbox” se establece en el dominio del cliente. |
| Seguimiento de terceros | El seguimiento de terceros es importante para los casos de uso de publicidad y segmentación en Target y en Adobe Audience Manager (AAM).  El seguimiento de terceros requiere técnicas de programación entre sitios.  Target utiliza dos cookies, “mboxSession” y “mboxPC”, que se establecen en el dominio `clientcode.tt.omtrd.net`. |

### ¿Cuál es el enfoque de Apple?

De Apple:

“La prevención inteligente del seguimiento es una nueva función de WebKit que reduce el seguimiento entre sitios mediante una mayor limitación de las cookies y otros datos de sitios web”.

“Esto es lo que se denomina seguimiento entre sitios, y la cookie empleada por `example-tracker.com` se denomina cookie de terceros. En nuestras pruebas hemos hallado sitios web populares con más de 70 de estos rastreadores, todos ellos dedicados a recopilar en silencio datos sobre los usuarios.”

| Enfoque | Detalles |
|--- |--- |
| Prevención inteligente del seguimiento | Para obtener más información, consulte [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) en el sitio del motor de navegación web de código abierto WebKit (en inglés). |
| Cookies | Cómo gestiona Safari las cookies:<ul><li>Las cookies de terceros que no están en un dominio al que el usuario accede directamente no se guardan nunca. Este comportamiento no es nuevo. Safari ya no admite las cookies de terceros.</li><li>Las cookies de terceros establecidas en un dominio al que el usuario accede directamente se purgan pasadas 24 horas.</li><li>Las cookies de origen se purgan pasados 30 días si el dominio de origen está clasificado como uno que realiza un seguimiento de los usuarios entre sitios. Esto podría aplicarse a las grandes empresas que envían a los usuarios a distintos dominios en línea. Apple no ha aclarado cómo clasificará exactamente estos dominios ni cómo puede determinar un dominio si está clasificado como uno que realiza un seguimiento de los usuarios entre sitios.</li></ul> |
| Aprendizaje automático para identificar dominios que abarcan varios sitios | De Apple:<br>Clasificador de aprendizaje automático: se utiliza un modelo de aprendizaje automático para clasificar qué dominios superiores de control privado tienen la capacidad de realizar un seguimiento de los usuarios entre sitios, basándose en las estadísticas recopiladas. De las distintas estadísticas recopiladas, tres vectores resultaron especialmente significativos para la clasificación, basándose en las prácticas de seguimiento actuales: subrecurso bajo número de dominios exclusivos, submarco bajo número de dominios exclusivos y número de dominios exclusivos a los que se redirecciona. Toda la recopilación y clasificación de datos se produce en el dispositivo.<br>Sin embargo, si el usuario interactúa con example.com como dominio principal, denominado con frecuencia dominio de origen, la prevención inteligente de seguimiento lo considera una señal de que el usuario está interesado en el sitio web y ajusta temporalmente su comportamiento como se ilustra en esta cronología:<br>Si el usuario interactuó con example.com en las últimas 24 horas, sus cookies estarán disponibles cuando `example.com` sea de terceros. Esto permite situaciones de inicio de sesión del tipo “Iniciar sesión con mi cuenta X en Y”.<ul><li>Los dominios visitados como dominio de primer nivel no se verán afectados. Sitios como OKTA, por ejemplo</li><li>Identifica los dominios que son subdominio o submarco de la página actual en varios dominios exclusivos.</li></ul> |

### ¿Cómo se verá afectado Adobe?

| Funcionalidad afectada | Detalles |
|--- |--- |
| Soporte para la no participación | Los cambios de Apple en el seguimiento de WebKit interrumpen el soporte para la no participación.<br>La no participación en Target emplea una cookie en el dominio `clientcode.tt.omtrdc.net`. Para obtener más información, consulte [Privacidad](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).<br>Target admite dos formas de no participación:<ul><li>Una por cliente (el cliente gestiona el vínculo de no participación).</li><li>Una mediante Adobe, que excluye al usuario de toda funcionalidad de Target para todos los clientes.</li></ul>Ambos métodos utilizan una cookie de terceros. |
| Actividades de Target | Los clientes pueden elegir la   [duración de perfil](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) para sus cuentas de Target, con un valor de hasta 90 días. El problema es que si la duración del perfil de la cuenta supera los 30 días y se purga la cookie de origen porque el dominio del cliente se ha marcado como un seguimiento de usuarios entre sitios, el comportamiento para los visitantes de Safari se verá afectado en las siguientes áreas de Target:<br>**Informes de Target**: Si un usuario de Safari entra en una actividad, regresa pasados 30 días y luego convierte ese usuario, cuenta como dos visitantes y una conversión.<br>Este comportamiento es el mismo para las actividades que utilizan Analytics como fuente de informes (A4T).<br>**Perfil y pertenencia a actividades**:<ul><li>Los datos de perfil se borran al caducar la cookie de origen.</li><li>La pertenencia a actividades se borra al caducar la cookie de origen.</li><li> Target no funciona en Safari para cuentas que utilizan una implementación de cookie de terceros, o de cookies de origen y de terceros. Nótese que este comportamiento no es nuevo. Safari lleva un tiempo sin admitir cookies de terceros.</li></ul><br>**Sugerencias**: si existe preocupación en cuanto a que el dominio del cliente pueda considerarse como uno que realiza un seguimiento de los usuarios entre sitios, lo más seguro es establecer en Target la duración del perfil en 30 días o menos. De este modo, se asegurará de que los usuarios reciban un seguimiento similar en Safari y en los demás navegadores. |
