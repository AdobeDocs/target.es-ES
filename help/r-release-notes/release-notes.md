---
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.
keywords: Notas de la versión;versión preliminar
seo-description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
seo-title: Notas de la versión de Adobe Target (actual)
solution: Target
title: Notas de la versión de Target (actual)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51f52bb40a0af4dac63236d46e6d6f0286cbb877

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.

## Anuncios

**31 de julio de 2019**

[!UICONTROL Los permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirlo en espacios de trabajo para equipos o flujos de trabajo diferentes. La función [!UICONTROL Permisos] de Enterprise facilita la escala efectiva de los programas de optimización entre los equipos. Aunque esta función estaba disponible en [!DNL Target] la interfaz de usuario, las API de administración no tenían la compatibilidad correspondiente hasta [!DNL Target] la versión de febrero de 2019. Adobe ha actualizado las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por lo tanto, si bien anteriormente, las API de administración estaban restringidas al espacio de trabajo predeterminado, la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con [!UICONTROL acceso de aprobador] .

Con la próxima versión [!DNL Target] de septiembre de 2019 [!UICONTROL , los permisos] de Enterprise proporcionarán a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]o [!UICONTROL Observador].

**Acción requerida**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada. Antes de la versión de septiembre, todas las integraciones operaban usando el acceso [!UICONTROL de aprobador] , independientemente de la función seleccionada en la [!UICONTROL lista desplegable Función] del producto. Con la próxima versión, puede seleccionar la función que desee.

Esta acción debe realizarse durante el mes **de agosto de 2019**. Después de [!DNL Target] la versión de septiembre de 2019, los controles de acceso se activarán y podrá observar el acceso solo al espacio de trabajo predeterminado, si está configurado. No hay consecuencias adversas para configurar las funciones de integración con antelación.

Para obtener instrucciones paso a paso y más información, consulte [Concesión de integraciones de Adobe I/O a espacios de trabajo y asignación de funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Mobile VEC SDK iOS 2.1.0 y Android 1.1.0 (7 de agosto de 2019)

Esta versión del SDK Mobile VEC incluye las siguientes mejoras y correcciones:

(Los números entre paréntesis son para uso interno de Adobe).

* Se agregó compatibilidad con la vista previa de actividades visuales en dispositivos móviles. (TGT-27875)
* Se ha corregido un problema que provocaba una infracción estándar de Apple debido `UIImagePickerController` al uso.
* Se eliminó la dependencia GSON del SDK de Android. (TGT-31710)
* Se ha corregido un problema que hacía que la oferta de envío no se restableciera durante la creación. (TGT-35270)

## Target Standard/Premium 19.7.1 (24 de julio de 2019) {#tgt-19-7-1}

Esta versión incorpora las siguientes nuevas funciones y mejoras:

(Los números entre paréntesis son para uso interno de Adobe).

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales para aplicaciones móviles | Aparece un nuevo panel Modificaciones en el VEC de la aplicación móvil que muestra los elementos configurados para el rastreo de clics. (TGT -31741)<br> Consulte [Configuración del rastreo de clics en la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Premium badgerecommendations](/help/assets/premium.png)<br>in A/B Test and Experience Targeting (XT) actividades | El estado Oferta de Recommendations (algoritmo) aparece en la página Información general de las actividades de prueba A/B y XT que contienen ofertas de Recomendaciones. Los estados incluyen: Resultados Ready, Resultados no preparados y Error de fuente. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Compatibilidad de seguimiento entre dominios para at. js 2.0 + a través de la biblioteca Experience Cloud ID (ECID) | Anteriormente, el seguimiento entre dominios no era compatible con at. js 2.*x*. Con esta versión, los clientes que utilizan at. js 2.0 o superior pueden utilizar el seguimiento entre dominios a través de la biblioteca ECID. La biblioteca ECID debe instalarse en la página junto con at. js 2.0 o superior para que funcione el seguimiento entre dominios. [Se debe usar la biblioteca de ID de Experience Cloud 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) .<br>Consulte [Compatibilidad con seguimiento entre dominios en at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain). |
| Compatibilidad de Target con ITP 2.1 y ITP 2.2 de Apple a través de la biblioteca Experience Cloud ID (ECID) 4.3 | Actualmente, los clientes de Target pueden mitigar ITP 2.1 y ITP 2.2 de Apple mediante el uso del programa de certificación CNAME de Adobe.<br>Con esta versión, Target introduce una integración sin fisuras con la biblioteca ECID 4.3, que aprovecha una cookie del lado del servidor para mitigar ITP 2.1 y ITP 2.2. Es muy recomendable que los clientes de Target implementen [la biblioteca ECID 4.3 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) junto con la biblioteca JavaScript de Target para mitigar cualquier versión futura de ITP. La biblioteca ECID continuará perfeccionando las mejoras que proporcionan una solución sólida para las políticas de cookie que cambian constantemente ingresadas por los navegadores.<br>Consulte [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md). |

**Mejoras, correcciones y cambios**

* Se ha corregido un problema que impedía borrar valores de exclusión en actividades de Recomendaciones al agregar valores duplicados. (TGT-34996)
* Ahora puede eliminar un diseño en una actividad de Recomendaciones desde la página Segmentación (Paso 2 del flujo de trabajo guiado de tres partes). Tenga en cuenta que para eliminar un diseño debe haber más de un diseño seleccionado. (TGT-35118)
* Se ha corregido un problema que impedía que las tarjetas de criterios personalizados para algunos clientes se cargaran correctamente en la interfaz de usuario de Target o que se podían editar. (TGT-35170)

## Versión 2.1.1 de at. js (24 de julio de 2019)

Esta versión de at. js es una versión de mantenimiento e incluye las siguientes mejoras y correcciones:

(Los números entre paréntesis son para uso interno de Adobe).

* Se ha corregido un problema que hacía que se activaran varias señalizaciones al utilizar la métrica Rastreo de clics en la página Objetivos y configuración del Compositor de experiencias visuales (VEC). (TNT-32812)
* Se ha corregido un problema que causaba `triggerView()` que no se procesaran ofertas más de una vez. (TNT-32780)
* Se ha corregido un problema con `triggerView()` el cual garantizar que la solicitud contenga información de Marketing Cloud ID (MCID). (TNT-32776)
* Se ha corregido un problema que impedía que se activara `triggerView()` la notificación aunque no hubiera vistas guardadas. (TNT-32614)
* Se ha corregido un problema que provocaba un error debido al uso de decodeuricomponent que causaba problemas cuando la dirección URL contenía un parámetro de cadena de consulta incorrecto. (TNT-32710)
* El indicador de señalización ahora se establece en "true" en el contexto de las solicitudes de envío enviadas mediante `Navigator.sendBeacon()` la API. (TNT-32683)
* Se ha corregido un problema que impedía que las ofertas de Recommendations se mostraran en sitios web para algunos clientes. Los clientes podían ver el contenido de la oferta en la llamada de API de entrega pero la oferta no se aplicaba al sitio web. (TNT-32680)
* Se ha corregido un problema que provocaba que el seguimiento de clics en varias experiencias no funcionara según lo esperado. (TNT-32644)
* Se ha corregido un problema que impedía que at. js aplicara la segunda métrica después de que fallara la representación de la primera métrica. (TNT-32628)
* Se ha corregido un problema al pasar `mboxThirdPartyId` usando `targetPageParams` la función que provocaba que la carga útil de la solicitud no estuviera presente en los parámetros de consulta ni en la carga útil de la solicitud. (TNT-32613)
* Se ha corregido un problema que provocaba que las respuestas de notificación de clics y visualización se bloquearan en exploradores basados en Chromium (incluido Google Chrome). (TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte [Notas de la versión de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en la Lista prioritaria de actualización de productos Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
