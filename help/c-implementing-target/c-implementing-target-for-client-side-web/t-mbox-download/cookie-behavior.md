---
keywords: Información general y referencia;webkit;cookies;de origen;de terceros;de origen;de terceros
description: 'Obtenga más información sobre el comportamiento de las cookies (cookie de origen, cookie de terceros con cookie de origen o solo cookie de terceros). [!DNL Target] '
title: ¿Dónde Puedo Encontrar Información Sobre Las Cookies [!DNL Target] ?
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: e773db20ac593108aa3e54aae1bcb2c0f713e387
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 58%

---

# Cookies de Target

El comportamiento de la cookie depende de si es una cookie de origen, una cookie de terceros con una cookie de origen o solo una cookie de terceros.

>[!NOTE]
>
>Este tema contiene información sobre `mboxSession` y `mboxPC`. Las prácticas recomendadas de implementación recomiendan que no vincule ni almacene información confidencial con los datos de las cookies: `mboxSession` o `mboxPC`.

Consulte también [Eliminar la cookie de Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md).

## Cuándo usar cookies de origen o de terceros {#section_F71B29420C004A7FA3B1921E619B326E}

La configuración del sitio determina las cookies que se utilizarán. Es útil comprender cómo funciona [!DNL Target] al intentar comprender las cookies de origen y de terceros. Consulte [Cómo [!DNL Adobe Target] funciona](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) para obtener más información.

Hay tres casos principales para el uso de cookies:

1. Un dominio.

   Todas las pruebas tienen lugar en un dominio de nivel superior (`www.domain.com`, `store.domain.com`, `anysub.domain.com`, etc.).

   Enfoque: Utilice solo cookies de origen (la predeterminada).

1. Los usuarios cruzan dominios y quiere rastrear y comprobar su comportamiento en estos dominios.

   Ejemplo: un usuario visita su sitio para comprar pero cierra la compra a través de establecimientos de Yahoo. Tres métodos (acuda al representante de la cuenta para saber cuál es el más adecuado):

   * Habilitar cookies de origen y de terceros.
   * Habilitar solo las cookies de terceros (no es habitual, pero presenta la ventaja de mantener la cookie de mbox fuera de su dominio).
   * Activar solo las cookies de origen y transmitir el parámetro `mboxSession` al cruzar el dominio.

      Se debe pasar el parámetro `mboxSession` a una página de aterrizaje y hacer referencia al mismo desde la biblioteca JavaScript (Adobe Experience Platform Web SDK o at.js). No puede ser una página de redirector intermedia.

1. En un sitio de terceros, solo se usan AdBoxes o Flashboxes.

   Dos métodos (acuda al representante de la cuenta para determinar cuál es el más adecuado):

   * Habilitar cookies de origen y de terceros.

      Se requieren cookies de origen y de terceros para los Flashboxes y los elementos creativos dinámicos.

   * Habilitar solo las cookies de terceros.

      Este método solo se aplica en el más que improbable caso de que se usen implementaciones de AdBoxes sin segmentación en el sitio.

## Comportamiento de cookie de origen {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

La cookie de origen se almacena en [!DNL clientdomain.com], donde `clientdomain` es su dominio.

La biblioteca JavaScript genera un `mboxSession ID` y lo almacena en la cookie [!DNL Target]. La primera respuesta de mbox contiene la oferta y el JavaScript para almacenar el `mboxPC ID` generado por la aplicación en la cookie de mbox.

>[!NOTE]
>
>La cookie de origen [!DNL AMCV_###@AdobeOrg] siempre se establece con [!DNL Experience Cloud Visitor ID].

## Comportamiento de cookie de terceros {#section_4C3A83990BF8415BB1806602D84AED48}

La cookie de terceros se almacena en [!DNL clientcode.tt.omtrdc.net] y la de origen en [!DNL clientdomain.com], donde `clientdomain` es su dominio.

La biblioteca JavaScript genera un `mboxSession ID`. La primera solicitud de ubicación devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, y se devuelve una solicitud de redirección con un parámetro extra (`mboxXDomainCheck=true`).

Si el navegador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve.

Si el navegador rechaza cookies de terceros, la solicitud de redirección no incluye dichas cookies y se muestra el contenido predeterminado de todas las ubicaciones en la página. Como no hay cookies definidas, el mismo proceso anterior se vuelve a producir en cada solicitud de página.

>[!NOTE]
>
>La cookie [!DNL demdex.net] se establece si las cookies de terceros no están bloqueadas.

## Comportamiento de cookies de terceros y de origen {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

La cookie de terceros se almacena en [!DNL clientcode.tt.omtrdc.net] y la de origen en [!DNL clientdomain.com], donde `clientdomain` es su dominio.

La biblioteca JavaScript genera un `mboxSession ID`. La primera solicitud de ubicación devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, y se devuelve una solicitud de redirección con un parámetro extra (`mboxXDomainCheck=true`).

Si el navegador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve.

Algunos navegadores rechazan las cookies de terceros. Si se bloquea la cookie de terceros, la cookie de origen seguirá funcionando. [!DNL Target] intenta establecer la cookie de terceros y, en caso de no poder, [!DNL Target] solo puede realiza el seguimiento en el dominio específico del cliente. El seguimiento entre dominios no funcionará si la cookie de terceros está bloqueada, a menos que se añada `mboxSession` al vínculo entre dominios. En dicho caso, se definirá otra cookie de origen que se sincronizará con la cookie de origen del dominio anterior.

## Configuración de la cookie {#section_B498B8D1A34A444BBF84CC720EE9D87F}

La cookie tiene varias configuraciones predeterminadas. Puede cambiar esta configuración si es necesario, excepto la duración de la cookie. Acuda al representante de la cuenta cuando vaya a cambiar la configuración de la cookie.

| Configuración | Información |
|--- |--- |
| Nombre de la cookie | mbox. |
| Dominio de la cookie | Niveles segundo y superior de los dominios desde los que se proporciona el contenido. Dado que se proporciona desde el dominio de su empresa, la cookie es una cookie de origen.<br>Ejemplo: `mycompany.com`. |
| Dominio del servidor | `clientcode.tt.omtrdc.net`, usando el código de cliente de su cuenta. |
| Duración de la cookie | La cookie permanece en el explorador del visitante dos semanas después del último inicio de sesión. La duración de la cookie no se puede cambiar. |
| Directiva P3P | Tal y como precisa la configuración predeterminada de la mayoría de los navegadores, la cookie se publica con una directiva P3P. Una directiva P3P indica a un explorador que sirve la cookie y cómo se utiliza la información. |

La cookie conserva varios valores para administrar la forma en que los visitantes viven las campañas:

| Valor | Definición |
|--- |--- |
| session ID | ID único para una sesión de usuario. De forma predeterminada, este ID dura 30 minutos. |
| pc ID | Identificador semipermanente del navegador de un visitante. Dura 14 días. |
| check | Sencillo valor de prueba que sirve para averiguar si un visitante admite cookies. Se establece cada vez que un visitante solicita una página. |
| disable | Se establece si el tiempo de carga de un visitante supera el tiempo de espera fijado en el archivo de biblioteca JavaScript. De forma predeterminada, este valor dura una hora. |

## Impacto en [!DNL Target] para visitantes de Safari debido a cambios en el seguimiento de Apple WebKit {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**¿Cómo funciona el  [!DNL Adobe Target] seguimiento?**

| Cookies | Detalles |
|--- |--- |
| Dominios de origen | Implementación estándar para clientes [!DNL Target]. La cookie “mbox” se establece en el dominio del cliente. |
| Seguimiento de terceros | El seguimiento de terceros es importante para los casos de uso de publicidad y segmentación en [!DNL Target] y en [!DNL Adobe Audience Manager] (AAM). El seguimiento de terceros requiere técnicas de programación entre sitios. [!DNL Target] utiliza dos cookies, “mboxSession” y “mboxPC”, que se establecen en el dominio `clientcode.tt.omtrd.net`. |
**¿Cuál es el enfoque de Apple?**

De Apple:

“La prevención inteligente del seguimiento es una nueva función de WebKit que reduce el seguimiento entre sitios mediante una mayor limitación de las cookies y otros datos de sitios web”.

“Esto es lo que se denomina seguimiento entre sitios, y la cookie empleada por `example-tracker.com` se denomina cookie de terceros. En nuestras pruebas hemos hallado sitios web populares con más de 70 de estos rastreadores, todos ellos dedicados a recopilar en silencio datos sobre los usuarios.”

| Enfoque | Detalles |
|--- |--- |
| Prevención inteligente del seguimiento | Para obtener más información, consulte [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) en el sitio del motor de navegación web de código abierto WebKit (en inglés). |
| Cookies | Cómo gestiona Safari las cookies:<ul><li>Las cookies de terceros que no están en un dominio al que el usuario accede directamente no se guardan nunca. Este comportamiento no es nuevo. Safari ya no admite las cookies de terceros.</li><li>Las cookies de terceros establecidas en un dominio al que el usuario accede directamente se purgan pasadas 24 horas.</li><li>Las cookies de origen se purgan pasados 30 días si el dominio de origen está clasificado como uno que realiza un seguimiento de los usuarios entre sitios. Esto podría aplicarse a las grandes empresas que envían a los usuarios a distintos dominios en línea. Apple no ha dejado claro cómo se clasifican exactamente estos dominios ni cómo puede determinar un dominio si se han clasificado como usuarios de seguimiento entre sitios.</li></ul> |
| Aprendizaje automático para identificar dominios que abarcan varios sitios | De Apple:<br>Clasificador de aprendizaje automático: Un modelo de aprendizaje automático se utiliza para clasificar qué dominios superiores de control privado pueden rastrear al usuario entre sitios, según las estadísticas recopiladas. De las distintas estadísticas recopiladas, tres vectores resultaron especialmente significativos para la clasificación, basándose en las prácticas de seguimiento actuales: subrecurso bajo número de dominios exclusivos, submarco bajo número de dominios exclusivos y número de dominios exclusivos a los que se redirecciona. Toda la recopilación y clasificación de datos se produce en el dispositivo.<br>Sin embargo, si el usuario interactúa  `example.com` como el dominio principal, denominado con frecuencia dominio de origen, la prevención inteligente del seguimiento lo considera una señal de que el usuario está interesado en el sitio web y ajusta temporalmente su comportamiento como se muestra en esta cronología:<br>Si el usuario ha interactuado con  `example.com` las últimas 24 horas, las cookies están disponibles cuando  `example.com` es de terceros. Esta práctica permite situaciones de inicio de sesión de &quot;Iniciar sesión con mi cuenta X en Y&quot;.<ul><li>Los dominios visitados como dominio de nivel superior no se ven afectados. Sitios como OKTA, por ejemplo</li><li>Identifica los dominios que son subdominio o submarco de la página actual en varios dominios exclusivos.</li></ul> |

**¿Cómo se ve afectado el Adobe?**

| Funcionalidad afectada | Detalles |
|--- |--- |
| Soporte para la no participación | Los cambios de Apple en el seguimiento de WebKit interrumpen el soporte para la no participación.<br>[!DNL Target]La no participación en emplea una cookie en el dominio `clientcode.tt.omtrdc.net`. Para obtener más información, consulte [Privacidad](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).<br>[!DNL Target] admite dos exclusiones:<ul><li>Una por cliente (el cliente gestiona el vínculo de no participación).</li><li>Una vía [!DNL Adobe] que excluye al usuario de todas las funcionalidades [!DNL Target] para todos los clientes.</li></ul>Ambos métodos utilizan una cookie de terceros. |
| [!DNL Target] Recomendaciones | Los clientes pueden elegir su [duración de perfil](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) para sus cuentas [!DNL Target] (hasta 90 días). El problema es que si la duración del perfil de la cuenta supera los 30 días y se purga la cookie de origen porque el dominio del cliente se ha marcado como uno que realiza un seguimiento de los usuarios entre sitios, el comportamiento de los visitantes de Safari se verá afectado en las siguientes áreas de [!DNL Target]:<br>**[!DNL Target] informes **: Si un usuario de Safari entra en una actividad, regresa pasados 30 días y luego lo convierte, ese usuario se cuenta como dos visitantes y una conversión.<br>[!DNL Analytics]Este comportamiento es el mismo para las actividades que utilizan como fuente de informes (A4T).<br>** Pertenencia a perfil y actividad **:<ul><li>Los datos de perfil se borran al caducar la cookie de origen.</li><li>La pertenencia a actividades se borra al caducar la cookie de origen.</li><li> [!DNL Target] no funciona en Safari para cuentas que utilizan una implementación de cookie de terceros, o de cookies de origen y de terceros. Este comportamiento no es nuevo. Safari no ha permitido cookies de terceros durante un tiempo.</li></ul><br>**Sugerencias**: Si existe la preocupación de que el dominio del cliente pueda estar marcado como uno que realiza un seguimiento de los visitantes entre sesiones, lo más seguro es establecer la duración del perfil en 30 días o menos en  [!DNL Target]. Este límite garantiza que los usuarios reciban un seguimiento similar en Safari y en todos los demás navegadores. |
