---
keywords: versiones de at.js;versiones de at.js;notas de la versión
description: Detalles sobre los cambios en cada versión de Adobe Target at.js.
title: Detalles de las versiones de at.js
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '4075'
ht-degree: 83%

---


# Detalles de las versiones de at.js

Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target].

>[!IMPORTANT]
>
>El equipo de Destinatario admite at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que está ejecutando una versión compatible.
>
>[Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launchis es el método preferido para actualizar at.js. Los desarrolladores de extensiones agregan continuamente nuevas funciones a sus extensiones y corrigen con frecuencia errores. Estas actualizaciones se empaquetan en nuevas versiones de una extensión y están disponibles en el catálogo [!DNL Launch] como actualizaciones. Para obtener más información, consulte [Actualización de extensión](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/extensions/extension-upgrade.html) en la *Guía del usuario del Experience Platform Launch*.

## at.js 2.4.0 (14 de enero de 2021)

Esta versión de at.js es una versión de mantenimiento que incluye las siguientes correcciones:

* Añade la compatibilidad con ID de plataforma/perfil unificado en ID de cliente de API de envío.
* Corrige la inyección de etiquetas de estilo no válida.

## at.js 2.3.3 (13 de noviembre de 2020)

Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:

* Se ha corregido un problema relacionado con el rastreo de clics de mbox y A4T. Con 0n-clic, Destinatario activó una llamada de API de Envío con los parámetros de mbox y mbox correctos. Sin embargo, el SDID no coincidía con el de la llamada [!DNL Analytics], por lo que no había coincidencia ni coincidencia de visitas. (TNT-38372)

## at.js 2.3.2 (24 de julio de 2020)

Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:

* Se ha corregido un error que se producía cuando un script o código añadía una propiedad predeterminada a la ventana o al documento.

## at.js 1.8.2 (15 de junio de 2020)

Esta versión de at.js es una versión de mantenimiento que incluye la siguiente corrección:

* Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 1.** xmay crea incorrectamente el dominio del servidor, lo que provoca que la  [!DNL Target] solicitud falle. (TNT-35064)

## Versiones de at.js 2.3.1 (15 de junio de 2020)

Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:

* Se ha hecho que la configuración `deviceIdLifetime` sea reemplazable mediante [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Se ha corregido un problema que se producía al utilizar CNAME y la anulación de bordes, at.js 2.** xmay crea incorrectamente el dominio del servidor, lo que provoca que la  [!DNL Target] solicitud falle. (TNT-35065)
* Se corrigió un problema al utilizar la extensión [!DNL Target] [!DNL Launch] v2 y la extensión [!DNL Adobe Analytics] [!DNL Launch], [!DNL Target] retrasaba la llamada [!DNL Analytics] `sendBeacon`. (TNT-36407, TNT-35990, TNT-36000)

## Versión 2.3.0 de at.js (25 de marzo de 2020)

Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:

* Compatibilidad con la configuración de las funciones de directiva de seguridad de contenido en las etiquetas SCRIPT y STYLE que se anexan al DOM de la página al aplicar ofertas de Destinatario entregadas. Los clientes pueden establecer `targetGlobalSettings.cspScriptNonce` y `targetGlobalSettings.cspStyleNonce` para que at.js pueda establecer las variables de etiqueta de estilo y secuencia de comandos correspondientes en ofertas aplicadas. Consulte [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) para obtener más información.
* Se ha corregido un problema al compilar at.js con el compilador de Google Closure para la implementación del Administrador de etiquetas de Google.
* Se cambió el nombre de la cookie de comprobación at.js de `check` a `at_check` para evitar conflictos con las implementaciones de los clientes.

## Versión 1.8.1 de at.js (25 de marzo de 2020)

Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:

* Se cambió el nombre de la cookie de comprobación at.js de `check` a `at_check` para evitar conflictos con las implementaciones de los clientes.

## Versión 2.2.0 de at.js (10 de octubre de 2019)

Esta versión de at.js incluye las siguientes mejoras y correcciones:

* Se corrigió un problema en el cual el rastreo de clics no notificaba conversiones en Analytics para Destinatario (A4T) cuando el código de Adobe Analytics no estaba presente en los elementos de página.
* Se ha mejorado el rendimiento al usar tanto el servicio de ID de Experience Cloud (ECID) v4.4 como at.js 2.2 en las páginas web.
* Anteriormente, el ECID realizaba dos llamadas de bloqueo antes de que at.js pudiera recuperar experiencias. Esto se ha reducido a una sola llamada, lo que mejora significativamente el rendimiento.

   >[!NOTE]
   >
   >Actualice ECID Launch Extension a v4.4 para aprovechar esta mejora de rendimiento.

* La versión 2.2 de at.js también proporciona una nueva configuración denominada `serverState`. Esta configuración se puede utilizar para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Destinatario. La integración híbrida significa que se utiliza at.js v2.2+ en el cliente y la API de envío o un SDK de Destinatario en el servidor para ofrecer experiencias. `serverState` proporciona a at.js v2.2+ la capacidad de aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está ofreciendo. Para obtener más información, consulte &quot;serverState&quot; en [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).

## Versión 1.8.0 de at.js (10 de octubre de 2019)

Esta versión de at.js incluye las siguientes mejoras y correcciones:

* Se ha mejorado el rendimiento al usar tanto el servicio de ID de Experience Cloud (ECID) v4.4 como at.js 1.8 en las páginas web.
* Anteriormente, el ECID realizaba dos llamadas de bloqueo antes de que at.js pudiera recuperar experiencias. Esto se ha reducido a una sola llamada, lo que mejora significativamente el rendimiento.

>[!NOTE]
>
>Actualice ECID Launch Extension a v4.4 para aprovechar esta mejora de rendimiento.

## Versión 2.1.1 de at.js (24 de julio de 2019)

Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:

(Los números entre paréntesis son para uso interno de Adobe).

* Se ha corregido un problema que hacía que se activaran varios avisos al utilizar la métrica Rastreo de clics en la página Objetivos y configuración del Compositor de experiencias visuales (VEC). (TNT-32812)
* Se ha corregido un problema que causaba que `triggerView()` no procesara ofertas más de una vez. (TNT-32780)
* Se ha corregido un problema con `triggerView()` al garantizar que la solicitud contenga información de Experience Cloud ID (ECID). (TNT-32776)
* Se ha corregido un problema que impedía que se activara la notificación `triggerView()` aunque no hubiera vistas guardadas. (TNT-32614)
* Se ha corregido un problema que provocaba un error debido al uso de decodeURIcomponent, que causaba problemas cuando la dirección URL contenía un parámetro de cadena de consulta incorrecto. (TNT-32710)
* El indicador de señalización ahora se establece como “true” en el contexto de las solicitudes de envío enviadas mediante la API `Navigator.sendBeacon()`. (TNT-32683)
* Se ha corregido un problema que impedía que las ofertas de Recommendations se mostraran en sitios web para algunos clientes. Los clientes podían ver el contenido de la oferta en la llamada de API de entrega, pero la oferta no se aplicaba al sitio web. (TNT-32680)
* Se ha corregido un problema que provocaba que el seguimiento de clics en varias experiencias no funcionara según lo esperado. (TNT-32644)
* Se ha corregido un problema que impedía que at.js aplicara la segunda métrica después de que fallara la representación de la primera. (TNT-32628)
* Se ha corregido un problema al pasar `mboxThirdPartyId` con la función `targetPageParams` que provocaba que la carga útil de la solicitud no estuviera presente en los parámetros de consulta ni en la carga útil de la misma. (TNT-32613)
* Se ha corregido un problema que provocaba que las respuestas de notificación de clics y visualización se bloquearan en exploradores basados en Chromium (incluido Google Chrome). (TNT-32290)

## Versión 2.1.0 de at.js (3 de junio de 2019)

Esta versión incorpora las siguientes funciones y mejoras:

* **Compatibilidad de Adobe Opt-In**: Adobe Opt-in es una forma de simplificar las integraciones de soluciones de Adobe con plataformas de administración de consentimiento. Para obtener más información sobre Adobe Opt-in, consulte [Privacidad y Reglamento General de Protección de Datos (RGPD)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **Compatible con CSP estándar del sector**: at.js ya no utiliza eval() para ejecutar JavaScript.

* **Registro de análisis de cliente**: Proporcione a los clientes control total sobre cómo desean enviar datos de análisis a Adobe Analytics, ya sea en el lado del cliente o en el servidor.

   Para obtener más información, consulte [Inicio de sesión en el lado del cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) en *Antes de implementar*.

* **Enviar notificaciones**: Permita que los desarrolladores envíen notificaciones cuando su código procese una experiencia en lugar de utilizar `applyOffer()` o `applyOffers()`.

   Para obtener más información, consulte [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **El tamaño de at.js disminuyó ~24%**: El tamaño de at.js se reduce en ~24%. El menor tamaño de archivo mejora el rendimiento de carga de página y reduce el tiempo para descargar at.js en la página.

## Versión 2.0.1 de at.js (19 de marzo de 2019)

Esta es una versión de mantenimiento e incluye las siguientes mejoras y correcciones:

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

* Se ha corregido una condición de carrera en el código de sondeo DOM que provocaba excepciones de JavaScript para ciertos clientes. (TNT-31869)
* Se han desunido las notificaciones que visualizaban los controladores de eventos de seguimiento de clics. Inicialmente, Target no enviaba notificaciones si no se podían adjuntar controladores de eventos de clic que pertenecían a una vista representada. Target ahora envía una notificación de vista incluso cuando no se encuentran elementos de clic. (TNT-31969)
* Se ha corregido un problema que provocaba que el indicador de redireccionamiento de eventos de solicitud se defina siempre como verdadero. (TNT-31907)
* Se ha corregido un problema que provocaba que la acción de reorganizar VEC se registrara como éxito, incluso cuando faltaban elementos. (TNT-31924)
* Se ha corregido un problema que causaba que las notificaciones para determinados clientes no contenderan el token de propiedad de permisos de Enterprise. (TNT-31999)

## Versión 1.7.1 de at.js (19 de marzo de 2019)

Esta es una versión de mantenimiento e incluye la siguiente corrección:

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

* Se ha corregido una condición de carrera en el código de sondeo DOM que provocaba excepciones de JavaScript para ciertos clientes. (TNT-31869)

## Versión 2.0.0 de at.js {#at-js-200}

at.js 2 proporciona conjuntos de funciones enriquecidos que equipan su empresa para ejecutar personalizaciones en tecnologías de próxima generación del lado del cliente. Esta nueva versión se centra en actualizar at.js para tener interacciones armoniosas con aplicaciones de una sola página (SPA).

Estos son algunos de los beneficios de utilizar at.js 2.x que no están disponibles en versiones anteriores:

* La capacidad de almacenar en caché todas las ofertas al cargar la página para reducir el número de llamadas al servidor a una sola llamada.
* Importante mejora de las experiencias de los usuarios finales en su sitio porque las ofertas se muestran inmediatamente a través de la caché sin ningún tiempo de retraso que introducen las llamadas tradicionales al servidor.
* Código sencillo de una línea y configuración de desarrollador única para permitir que sus especialistas en marketing creen y ejecuten actividades A/B y Experiencia (XT) a través del Compositor de experiencias visuales (VEC) en sus aplicaciones de una sola página.

at.js 2.x presenta las siguientes funciones nuevas:

* getOffers()
* applyOffers()
* triggerView()

Las siguientes funciones han quedado obsoletas con la introducción de at.js 2.x:

* mboxCreate()
* mboxDefine
* registerExtension()

Para obtener más información, consulte [Actualización de at.js 1.x a at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) y [funciones at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>
>Si necesita compatibilidad con Adobe Opt-in para el [Reglamento General de Protección de Datos](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (RGPD), debe utilizar at.js 1.7.0 o at.js 2.1.0 en la actualidad.

## Versión 1.7.0 de at.js {#at-js-170}

at.js 1.7.0 ofrece soporte con Adobe Opt-In. Adobe Opt-In es una forma de simplificar las integraciones de soluciones de Adobe con plataformas de administración de consentimiento.

Para obtener más información sobre Adobe Opt-in, consulte [Privacidad y Reglamento General de Protección de Datos](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (RGPD).

Esta versión también corrige un problema en el que Target podía anular los parámetros de URL de redireccionamiento con parámetros procedentes de la dirección URL de redireccionamiento.

>[!NOTE]
>
>Si necesita compatibilidad con Adobe Opt-in para el RGPD, actualmente debe utilizar at.js 1.7.0 o 2.1.0.<br>Para obtener una lista de todas las versiones, consulte [Detalles de la versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Versión 1.6.4 de at.js {#at-js-164}

La versión at.js 1.6.4 es una versión de mantenimiento y aborda el siguiente problema:

* Se ha corregido una condición de carrera que se manifestaba en Microsoft Internet Explorer 11 y que provocaba que se aplicaran ofertas duplicadas.

## Versión 1.6.3 de at.js {#section_484A56774E004282B98FFFF851E4E670}

La versión 1.6.3 de at.js incluye las siguientes correcciones y mejoras:

* Los selectores eluden el CSS si contienen ID o clases de CSS que comiencen con un dígito, dos guiones o un guion seguido por un dígito (por ejemplo, n.º 123). (TNT-31061)
* Se ha corregido un problema introducido con at.js 1.6.2 en el que las ofertas del Compositor de experiencias visuales (VEC) de diferentes actividades y aplicables al mismo selector de CSS no respetaban la prioridad de la actividad. (TNT-31052)
* Se ha corregido un problema con el tiempo de espera de una promesa en entornos en los que no había compatibilidad nativa con las promesas. (TNT-30974)
* Los problemas se registran y comunican correctamente mediante el evento fallido de representación de contenido. Es posible que anteriormente JavaScript haya informado que se ejecutó correctamente, incluso si no era así. (TNT-30599)

## Versión 1.6.2 de at.js {#section_88BE2F69943D4280B8170F377886B58E}

Esta es una versión de mantenimiento y aborda el siguiente problema:

* Se ha solucionado un problema que en algunos sitios de clientes conducía a un bucle infinito “asíncrono”.

>[!IMPORTANT]
>
>Además, la versión 1.6.2 de at.js también contiene todas las mejoras y correcciones incluidas en las versiones 1.6.1 y 1.6.0 de at.js. Estas versiones ya no están disponibles para descargar. Le recomendamos que actualice a la versión 1.6.2 si usa 1.6.1 o 1.6.0

Estas son las mejoras y correcciones que se incluyeron en la versión 1.6.1 de at.js:

* Se ha solucionado un problema en at.js 1.6.0 que hacía que las experiencias de las recomendaciones se duplicaran en Microsoft Internet Explorer 11. (TNT-30593)
* at.js ahora garantiza que la lógica de anulación de bordes compruebe la existencia de una cookie de clúster de perímetro para evitar un número de perímetro diferente si un usuario salta los perímetros durante una sesión. (TNT-30563)
* Se ha solucionado un problema que impedía que at.js ejecutara acciones posteriores si el contenido HTML contenía un código JS no válido. at.js ahora registra el error y presenta las acciones restantes sin problemas. (TNT-30546)
* Se han realizado cambios para que haya una excepción cuando una página de redirección se vuelve a calificar para una actividad de redireccionamiento. (TNT-30532)
* Se ha solucionado un problema que impedía que el tiempo de espera de solicitud correcto se propagara desde la solicitud de la API getOffer(). (TNT-30498)
* Se ha solucionado un problema que impedía que at.js 1.6.0 guardara cookies al usar el protocolo de archivo. (TNT-30454)
* Se ha solucionado un problema que hacía que pareciera que no todas las experiencias se entregaban con redirecciones al usar Analytics for Target (A4T). (TNT-30444)
* Se ha solucionado un problema que hacía que la página se ocultara después de que la llamada de Target se realizara correctamente. (TNT-30358)

Estas son las mejoras y correcciones que se incluyeron en la versión 1.6.0 de at.js:

* Las ofertas de redireccionamiento ahora son automáticamente compatibles con la integración de Analytics for Target (A4T). Se ha eliminado la solución del lado del cliente. (TNT-30247)
* El enrutamiento de perímetro del lado del cliente ahora está habilitado de forma predeterminada. (TNT-30261)
* Se ha solucionado un problema con la representación de la acción del Compositor de experiencias visuales (VEC) cuando hay dependencias entre las acciones. (TNT-30248)

## Versión 1.5.0 de at.js {#section_128C6761884C4DA8AE50D6A605FF6F55}

Ya está disponible la versión 1.5.0 de at.js.

* Los detalles del evento `at-request-succeeded` contienen el indicador de redirección. Este indicador se puede utilizar para determinar si la página se redirigirá a una URL diferente. Si desea conocer la URL, suscríbase a `at-content-rendering-redirect`. (TNT-29834)
* Se solucionó un problema que provocaba que `window.targetGlobalSettings.enabled` fallara con una excepción de tiempo de ejecución si se establecía en Falso. (TNT-29829)
* Se solucionó un problema que provocaba que la página fallara al cargarse en el Compositor de experiencias visuales (VEC) si se incluía código personalizado en una solicitud mbox global y se utilizaba ocultación de texto. (TNT-29795)
* Se añadió compatibilidad con `screenOrientation`, `devicePixelRatio` y `webGLRenderer`. Estos nuevos parámetros de solicitud de Target se utilizan para la detección de iPhone X y otros dispositivos modernos. Para obtener más información, consulte [Móvil](/help/c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89). (TNT-29781)
* Se solucionó un problema por el cual no siempre se enviaba la sugerencia de ubicación de Adobe Audience Manager (AAM). (TNT-29695)
* En los navegadores compatibles, at.js 1.5.0 cambia a MutationObserver para el sondeo de selectores. Las versiones anteriores a at.js 1.0.0 utilizaban un polyfill MutationObserver que resultó problemático. Para evitar problemas de polyfill, la versión 1.5.0 utiliza el siguiente pseudocódigo a fin de decidir el mecanismo de programación que debe utilizarse:

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## Versión 1.3.0 de at.js {#section_24EAAE1CFA814EF8B19E61842F4D8321}

Ya está disponible la versión 1.3.0 de at.js.

* Los siguientes eventos nuevos sirven para ayudar a rastrear, depurar y personalizar la interacción con at.js:

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT

   Para obtener más información, consulte [Eventos personalizados de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md).

* Puede aumentar una solicitud at.js con parámetros adicionales que provengan de los proveedores de datos. Los proveedores de datos deben añadirse a `window.targetGlobalSettings` en `dataProviders key`.

   Para obtener más información, consulte [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

* Las solicitudes at.js ahora usan GET, pero cambiarán a POST cuando el tamaño de la URL exceda los 2048 caracteres. Hay una nueva propiedad llamada `urlSizeLimit` donde puede aumentar el límite de tamaño si es necesario. Este cambio permite que Target equipare at.js con AppMeasurement, que emplea la misma técnica.
* Target ahora impone que se use la clave `mbox` en la función `adobe.target.applyOffer(options)`. Esta clave se ha requerido en el pasado, pero Target impone ahora su uso para garantizar que Target tenga la validación adecuada y los clientes usen la función correctamente.
* at.js ha mejorado la funcionalidad de seguimiento de eventos y clics. at.js utiliza `navigator.sendBeacon()` para enviar datos de seguimiento de eventos y se volverá a utilizar XHR sincrónico cuando no se admita `navigator.sendBeacon()`. Este reutilización afecta principalmente a Internet Explorer 10 y 11 y algunas versiones de Safari. Safari añadirá compatibilidad para `navigator.sendBeacon()` en la próxima versión de iOS 11.3.
* Ahora, at.js puede presentar ofertas incluso cuando una página se abre en pestañas de fondo. Algunos clientes de Target encontraban un problema cuando `requestAnimationFrame()` se deshabilitaba debido al comportamiento de regulación del explorador para las pestañas de fondo.
* Esta versión agrega muchas mejoras de rendimiento, incluyendo pilas de llamadas más cortas al inspeccionar un perfil de la CPU de Chrome.
* at.js 1.3.0 ya no admite la publicación de contenido en Microsoft Internet Explorer 9. Para ver la lista de navegadores compatibles, consulte  [Exploradores admitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100). En el futuro, todas las solicitudes se ejecutarán a través de `XMLHttpRequest` con compatibilidad con CORS sin solicitudes JSONP. Este cambio mejora mucho la seguridad.

## Versión 1.2.3 de at.js {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

Ya está disponible la versión 1.2.3 de [!DNL at.js].

* Incorpora compatibilidad con ofertas JSON. Las ofertas JSON solo se admiten en actividades creadas con el Compositor de experiencias basadas en formularios. En estos momentos, la única forma de utilizar las ofertas JSON es mediante llamadas directas a API. Consulte [Creación ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D).

## Versión 1.2.2 de at.js {#section_4E96D13F2DFE4F1F81A1089877D53649}

Ya está disponible la versión 1.2.2 de [!DNL at.js].

* Se ha corregido un problema que devolvía un error de JavaScript cuando la biblioteca de Target se cargaba en una página que utilizaba el modo QUIRKS. (TNT-28312)
* Se ha corregido un problema que provocaba que el rastreo de clics de Target bloqueara las llamadas de recopilación de datos de Analytics. (TNT-28261)
* Se ha corregido un problema que provocaba que `getOffer() params` fallara cuando `targetPageParams()` devolvía una cadena vacía. (TNT-28359)
* Se ha corregido un problema con la generación del ID de sesión al utilizar x-solamente. (TNT-28361)

## Versión 1.2.1 de at.js {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

Ya está disponible la versión 1.2.1 de [!DNL at.js].

* Se ha corregido un error al rastrear los clics de un vínculo con target=&quot;_blank&quot; que impedía que Target lo abriera en una nueva pestaña.

## Versión 1.2.0 de at.js {#section_1C3A18C595C34B25A14A440D213F3B9C}

La versión 1.2 de [!DNL at.js] ya está disponible como una versión de mantenimiento que contiene principalmente correcciones de errores.

* Se ha corregido un problema que impedía utilizar acciones predeterminadas en casos especiales de rastreo de clics. (TNT-28089)
* Se ha corregido un problema producido al rastrear clics en un vínculo con `target="_blank"`, y que impedía que Target abriera el vínculo en una pestaña nueva. (TNT-28072)
* Se pueden usar direcciones IP como dominio de la cookie. (TNT-28002)
* Se ha corregido un problema que causaba parpadeo en las ofertas de redireccionamiento con un mbox global u otros mboxes regionales. (TNT-27978)
* Se ha corregido un problema por el que la configuración de una actividad de segmentación de experiencias fallaba dentro del VEC al cambiar entre Examinar y Componer. (TNT-27942)
* Se ha corregido la gestión incorrecta en clases de estilo de parpadeo para elementos de rastreo de clics. (TNT-27896)
* Se ha corregido un problema que causaba que los parámetros de mbox global se mezclaran con todos los parámetros de mbox. (TNT-27846)
* Se han realizado cambios para garantizar que [!DNL at.js] gestione adecuadamente Handlebars, Mustache y otras bibliotecas de creación de plantillas del lado del cliente. (TNT-27831)
* Se han realizado cambios para asegurar que `sdidParamExpiry` se inicialice apropiadamente y se pase al API de visitante. Esto es una regresión que se ha añadido a `at.js 1.1.0`. Las versiones anteriores de [!DNL at.js] no se ven afectadas. Solo afecta a los clientes que utilizan ofertas de redireccionamiento y A4T. (TNT-27791)
* Se han realizado cambios para garantizar que `SCRIPT` se ejecute independientemente del tipo de atributo utilizado. (TNT-27865)

## Versión 1.1.0 de at.js {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**Fecha:** 2 de agosto de 2017

En la versión 1.1 de [!DNL at.js] se incluyen las siguientes mejoras y correcciones:

* Se ha añadido la gestión de tokens de respuesta. Para obtener más información, consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).
* Se ha resuelto un problema para que `document.currentScript polyfill` no interfiera con Angular 1.X.
* Se han realizado cambios para asegurar que el rastreo de clics no interfiera con la propiedad Visibilidad. Los elementos de rastreo de clics se marcan con la clase CSS `at-element-click-tracking` en vez de con `at-element-marker`.

## Versión 1.0.0 de at.js {#section_37A3D23FC4AD42A68AA831B89E03E725}

**Fecha:** 7 de julio de 2017

En la versión 1.0 de at.js se incluyen las siguientes mejoras y correcciones:

* Compatibilidad con la carga asíncrona de at.js para cargar las páginas más rápido.
* Soporte para el ocultamiento previo el contenido de la página al cargar at.js de forma asíncrona.
* Mejores mensajes de error cuando se deshabilita el envío de contenido.
* Mejoras de rendimiento al enviar varias actividades.
* Compatibilidad con YUI Compressor.
* Realización de informes de errores/fallos para eventos personalizados durante el envío de actividades.
* Corrección de problemas de rendimiento en Microsoft Internet Explorer 11.
* Corrección para la función `getOffer()`, que generaba un error en algunos sitios web.
* Carga asíncrona de la biblioteca de Target. Para obtener más información, consulte [Preguntas más frecuentes de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## Versión 0.9.7 de at.js {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**Fecha:** 22 de mayo de 2017

En la versión 0.9.7 de [!DNL at.js] se incluyen las siguientes mejoras y correcciones:

* Se ha corregido un problema relacionado con una clave de recurso que faltaba en acciones `insertAfter` e `insertBefore` en el Compositor de experiencias visuales (VEC). Estos problemas estaban relacionados con la migración de ofertas visuales a plantillas de ofertas.

## Versión 0.9.6 de at.js {#section_EEFA6413F2F947AD8C4A88128B90245D}

**Fecha:** 13 de abril de 2017

En la versión 0.9.6 de [!DNL at.js] se incluyen las siguientes mejoras y correcciones:

* Compatibilidad con ofertas de redireccionamiento para A4T. Una vez que descargue e instale la versión 0.9.6 de [!DNL at.js], podrá usar ofertas de redireccionamiento en actividades que empleen [!DNL Adobe Analytics] como la fuente de informes de [!DNL Target] (A4T). Aparte de la versión 0.9.6 de [!DNL at.js], existen otros requisitos mínimos que su implementación debe cumplir para usar ofertas de redireccionamiento y A4T. Para obtener más información y otros detalles importantes adicionales que debe conocer, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Antes de [!DNL at.js] 0.9.6, cuando la API de visitantes estaba presente en la página y la opción `visitorApiTimeout` era demasiado agresiva, podía encontrar una situación en la que no se enviara ningún dato MCID en la solicitud de [!DNL Target]Target. Esto podía conllevar problemas como visitas no retenidas en [!DNL Analytics] al usar A4T.

   Este comportamiento se ha cambiado en [!DNL at.js] 0.9.6, incluso si el valor de `visitorApiTimeout` se define en, por ejemplo, 1 ms, Target tratará de recopilar los datos del SDID, los servidores de seguimiento y los ID de clientes, y de enviarlos en la solicitud de Target.

* Se ha añadido la opción `selectorsPollingTimeout`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Se ha cambiado el formato de la respuesta de `getOffer()`. Para obtener más información, consulte [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* Se ha añadido el registro en la consola de declaraciones `<!DOCTYPE>` no admitidas.
* Se ha corregido un problema por el que los complementos de [!DNL Target Classic] no se aplicaban correctamente cuando se enviaban varias ofertas predeterminadas a un único mbox. (TGT-22664)
* Se ha mejorado el establecimiento de cookies para los dominios de nivel superior (TLD) de dos letras con la finalidad de garantizar que la cookie de mbox se establezca correctamente en dichos dominios (por ejemplo, [!DNL test.no], [!DNL autodrives.ca], etc.).
* El algoritmo para extraer el dominio de nivel superior que debería usarse al guardar cookies ha cambiado en la versión 0.9.6 de at.js. Debido a ello, no es posible guardar cookies en direcciones que utilicen IP. La mayoría de las veces se usan direcciones IP con fines de prueba, pero como solución alternativa se pueden utilizar entradas DNS o ajustar el archivo de anfitriones en un cuadro local.
* Se ha corregido la gestión de las acciones mover y reorganizar cuando las propiedades son valores de cadena, no números enteros.

## Versión 0.9.4 de at.js {#section_A15B12F12CD94F07B3F56613A79A815F}

**Fecha:** 19 de enero de 2017

* Los nombres de mbox ahora pueden contener caracteres especiales, incluido el símbolo &amp;, para que sean coherentes con los requisitos de los nombres de mbox que usan mbox.js.

   Para acceder a una lista de caracteres especiales permitidos, consulte [Configuraciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812).

* Se ha añadido la opción de configuración `secureOnly` que indica si at.js debería utilizar solo HTTPS o se le debería permitir alternar entre HTTP y HTTPS según el protocolo de la página. Se trata de un ajuste avanzado que se establece en False de manera predeterminada y puede anularse mediante `targetGlobalSettings`.
* La opción [!UICONTROL Compatibilidad con navegadores anteriores] está disponible en la versión 0.9.3 (y anteriores) de at.js. Esta opción se ha eliminado en la versión 0.9.4 de at.js.

## Versión 0.9.3 de at.js {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**Fecha:** 10 de octubre de 2016

* Garantiza que las llamadas de mbox se realicen en Microsoft Internet Explorer 11 si los navegadores heredados están desactivados en la configuración de at.js.
* Garantiza que se procese el contenido predeterminado si una oferta remota dinámica falla (por ejemplo, si la URL es incorrecta y devuelve un error 404).
* Garantiza que los elementos se revelen rápidamente si los selectores de seguimiento de clics de VEC no se encuentran en DOM.

## Versión 0.9.2 de at.js {#section_148549CBB4F046BAA8F79C79B64EC889}

**Fecha:** 21 de septiembre de 2016

* Se ha añadido la opción de configuración `optoutEnabled` para habilitar o deshabilitar la exclusión de Device Graph. Si esta opción se establece en `true` y el visitante ha excluido el seguimiento, su navegador no hará llamadas de mbox. Device Graph está aún en versión beta. Esta opción está definida en `false` de forma predeterminada; si se usa Device Graph, hay que establecerla en `true`. En la versión 61 de mbox.js existe una opción parecida.
* Se ha añadido compatibilidad con `CustomEvent` para el mecanismo de notificación. Antes, el mecanismo de notificación de los eventos de at.js no se podía usar desde las API Standard del DOM, como `document.addEventListener()`. Ahora puede usar `document.addEventListener()` para suscribirse a los eventos de at.js, como eventos de solicitud y eventos de representación de contenido.
* Se ha arreglado un error relacionado con las ofertas creadas en el Compositor de experiencias visuales (VEC). Antes de esta versión, Target ocultaba los selectores y solo los mostraba cuando todos coincidían. En la versión 0.9.2 de at.js, Target muestra los selectores en cuanto coinciden.

## Versión 0.9.1 de at.js {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**Fecha:** 14 de julio de 2016

* Incorpora un tiempo de espera en at.js para el servicio de ID de visitante. Es independiente del propio tiempo de espera del servicio.
* Corrige un error en la versión 0.9.0 que afectaba a las implementaciones que usaban at.js en algunas páginas y mbox.js en otras.
* Si usa Adobe Analytics como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en las versiones 61 (o posterior) de mbox.js y 0.9.1 (o posterior) de at.js. La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

## Versión 0.9.0 de at.js {#section_2981CC9792F245389B39BB5B69F84C4E}

**Versión de Target:** 16.6.1

**Fecha:** 23 de junio de 2016

* Corrige un problema de pantalla blanca que surgía al usar las ofertas del VEC. Todo aquel que utilice [!DNL at.js] debería actualizar a esta nueva versión.
* Nueva API `registerExtension`.

   Esta nueva API ofrece a los desarrolladores acceso a ciertos módulos de jQuery utilizados en [!DNL at.js] para desarrollar extensiones (es decir, complementos) para la biblioteca. Este cambio conlleva varias implicaciones. Solo afectan a los usuarios que usan estas características:

   * La API `getSettings()` se ha eliminado, pero las mismas funciones están disponibles en `registerExtension()`.
   * La API `getTracking()` se ha eliminado, pero las mismas funciones están disponibles en `registerExtension()`.

   * Las extensiones existentes (por ejemplo, AngularJS) se deben actualizar para usar el método `registerExtension()`.

* Nueva API de notificación de at.js.

   El objetivo de este sistema de notificación es ofrecer más información sobre lo que [!DNL at.js] hace en la página y avisar cuando hay problemas. Un problema común del VEC es que un lanzamiento de TI modifica la página, un selector del VEC se interrumpe y la prueba deja de entregar el contenido correctamente. Uno de los objetivos de este sistema de notificación es poner en conocimiento de la página este problema de entrega con el fin de que los desarrolladores puedan acceder a la información para pasarla a un sistema como [!DNL Adobe Analytics] y de que se puedan enviar alertas a los propietarios del negocio con el aviso de que la prueba se ha interrumpido.

* Método de la nueva API.`targetGlobalSettings()`

   En lugar de definir la configuración en la [!DNL Target Standard/Premium UI] o usando las API de REST, puede anular la configuración en la biblioteca de at.js.

## Versión 0.8.0 de at.js {#section_E1C7B08EC0494388A022C28A8B8FE807}

**Fecha:** 5 de mayo de 2016.

Esta es la primera fecha de lanzamiento oficial de la biblioteca [!DNL at.js].

[!DNL at.js] es una biblioteca de implementación nueva para [!DNL Target] que está diseñada tanto para implementaciones web típicas como para aplicaciones de una sola página.

[!DNL at.js] reemplaza [!DNL mbox.js] por las implementaciones [!DNL Adobe Target].

>[!NOTE]
>
>Aunque [!DNL at.js] reemplaza a [!DNL mbox.js], mbox.js se seguirá admitiendo. Para la mayoría de las personas, [!DNL at.js] proporciona ventajas con respecto a [!DNL mbox.js]. Esto le da tiempo de probar [!DNL at.js] y cambiar la implementación en las páginas.

Entre otros beneficios, [!DNL at.js] mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.

[!DNL at.js] contiene los componentes que se incluían en [!DNL target.js], de modo que ya no se llama a [!DNL target.js].

Al implementar [!DNL at.js], tenga en cuente lo siguiente:

* Las versiones anteriores a Internet Explorer 8 no son compatibles.
* La implementación asíncrona significa que las integraciones anteriores, como el complemento de [!DNL Test&Target] a [!DNL SiteCatalyst], pueden no funcionar.
* Los complementos de [!DNL Target] que hacen referencia a objetos y métodos de [!DNL mbox.js] no son compatibles.
* Todas las llamadas a [!DNL Target] se realizan mediante una solicitud XMLHTTPRequest y el contenido se devuelve mediante JSON.
