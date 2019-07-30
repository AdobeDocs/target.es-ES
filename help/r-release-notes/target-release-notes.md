---
description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
keywords: notas de la versión
seo-description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
seo-title: Notas de la versión de Adobe Target (versión preliminar)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: f49c0c94afe6bf8aadbfb76930b57bf7cd5602dc

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 24 de julio de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas de lanzamiento, las funciones y demás información están sujetos a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (24 de julio de 2019) {#tgt-19-7-1}

Esta versión incorpora las siguientes nuevas funciones y mejoras:

| Función / Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales para aplicaciones móviles | Aparece un nuevo panel Modificaciones en el VEC de la aplicación móvil que muestra los elementos configurados para el rastreo de clics. (TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Premium badgerecommendations](/help/assets/premium.png)<br>in A/B Test and Experience Targeting (XT) actividades | El estado Oferta de Recommendations (algoritmo) aparece en la página Información general de las actividades de prueba A/B y XT que contienen ofertas de Recomendaciones. Los estados incluyen: Resultados Ready, Resultados no preparados y Error de fuente. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Compatibilidad de seguimiento entre dominios para at. js 2.0 + a través de la biblioteca Experience Cloud ID (ECID) | Anteriormente, el seguimiento entre dominios no era compatible con at. js 2.*x*. Con esta versión, los clientes que utilizan at. js 2.0 o superior pueden utilizar el seguimiento entre dominios a través de la biblioteca ECID. La biblioteca ECID debe instalarse en la página junto con at. js 2.0 o superior para que funcione el seguimiento entre dominios. [Se debe usar la biblioteca de ID de Experience Cloud 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) .<br>Consulte [Compatibilidad con seguimiento entre dominios en at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain). |
| Compatibilidad de Target con ITP 2.1 y ITP 2.2 de Apple a través de la biblioteca Experience Cloud ID (ECID) 4.3 | Actualmente, los clientes de Target pueden mitigar ITP 2.1 y ITP 2.2 de Apple mediante el uso del programa de certificación CNAME de Adobe.<br>Con esta versión, Target introduce una integración sin fisuras con la biblioteca ECID 4.3, que aprovecha una cookie del lado del servidor para mitigar ITP 2.1 y ITP 2.2. Es muy recomendable que los clientes de Target implementen [la biblioteca ECID 4.3 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) junto con la biblioteca JavaScript de Target para mitigar cualquier versión futura de ITP. La biblioteca ECID continuará perfeccionando las mejoras que proporcionan una solución sólida para las políticas de cookie que cambian constantemente ingresadas por los navegadores.<br>Consulte [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md). |

## Versión 2.1.1 de at. js (24 de julio de 2019)

Esta versión de at. js es una versión de mantenimiento e incluye las siguientes mejoras y correcciones:

(Los números entre paréntesis son para uso interno de Adobe).

* Se ha corregido un problema que hacía que se activaran varias señalizaciones al utilizar la métrica Rastreo de clics en la página Objetivos y configuración del Compositor de experiencias visuales (VEC). (TNT-32812)
* Fixed an issue that caused `triggerView()` to not render offers more than once. (TNT-32780)
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. (TNT-32776)
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. (TNT-32614)
* Se ha corregido un problema que provocaba un error debido al uso de decodeuricomponent que causaba problemas cuando la dirección URL contenía un parámetro de cadena de consulta incorrecto. (TNT-32710)
* The beacon flag is now set to "true" in the context of delivery requests sent via the `Navigator.sendBeacon()` API. (TNT-32683)
* Se ha corregido un problema que impedía que las ofertas de Recommendations se mostraran en sitios web para algunos clientes. Los clientes podían ver el contenido de la oferta en la llamada de API de entrega pero la oferta no se aplicaba al sitio web. (TNT-32680)
* Se ha corregido un problema que provocaba que el seguimiento de clics en varias experiencias no funcionara según lo esperado. (TNT-32644)
* Se ha corregido un problema que impedía que at. js aplicara la segunda métrica después de que fallara la representación de la primera métrica. (TNT-32628)
* Fixed an issue when passing `mboxThirdPartyId` using the `targetPageParams` function that caused the request payload to not be present in either the query parameters or in the request payload. (TNT-32613)
* Se ha corregido un problema que provocaba que las respuestas de notificación de clics y visualización se bloquearan en exploradores basados en Chromium (incluido Google Chrome). (TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

**Mejoras, correcciones y cambios**

* Se ha corregido un problema que impedía borrar valores de exclusión en actividades de Recomendaciones al agregar valores duplicados. (TGT-34996)
* Ahora puede eliminar un diseño en una actividad de Recomendaciones desde la página Segmentación (Paso 2 del flujo de trabajo guiado de tres partes). Tenga en cuenta que para eliminar un diseño debe haber más de un diseño seleccionado. (TGT-35118)
* Se ha corregido un problema que impedía que las tarjetas de criterios personalizados para algunos clientes se cargaran correctamente en la interfaz de usuario de Target o que se podían editar. (TGT-35170)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
