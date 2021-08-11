---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target].
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: Notas de la versión
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 14a1755bf3f3e47baea3a2105679c9d2951948a4
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 62%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen las notas de la versión de las API de Target, los SDK, el [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de plataforma, cuando corresponde.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Migre a la versión más reciente de [!DNL Adobe Experience Platform Web SDK] o a la biblioteca de JavaScript at.js antes más recientes para evitar posibles problemas con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] SDK 2.1.8 de node.js (11 de agosto de 2021)

* Se ha añadido la recopilación de datos de telemetría de SDK
* Código de API de envío automatizada del cliente openapi

Para obtener más información sobre esta y las versiones anteriores, consulte el [Registro de cambios](https://github.com/adobe/target-nodejs-sdk/blob/main/CHANGELOG.md) en la [documentación del SDK de Target node.js](https://github.com/adobe/target-nodejs-sdk) en Github.

## [!DNL Target Standard/Premium] 21.8.1 (fecha por determinar)

>[!NOTE]
>
>La versión [!DNL Target Standard/Premium] 21.8.1 se ha retrasado. En lugar de lanzarse el 4 de agosto de 2021, la versión 21.8.1 se lanzará en los próximos días. Más información cuando esté disponible.

Esta versión de mantenimiento contiene muchas mejoras del back-end, incluido el siguiente cambio de cara al cliente:

* Se ha corregido un problema que provocaba que los informes para actividades de [!UICONTROL Personalización automática] creadas en el [!UICONTROL Compositor de experiencias basadas en formularios] hicieran referencia a ofertas eliminadas en los informes. Esto provocó que se mostrara el siguiente mensaje de error: &quot;Tenemos problemas para recuperar datos para este informe. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste.&quot; (TGT-41028)

## [!DNL Target Delivery API] (3 de agosto de 2021)

Esta versión contiene las siguientes mejoras:

* El límite de parámetros de mbox se ha aumentado a 100 parámetros. El límite anterior era de 50 parámetros. (TNT-41717)
* El límite de `categoryId` se ha aumentado a 256 caracteres. El límite anterior era de 128 caracteres.
* Se han añadido los siguientes detalles [!DNL Adobe Audience Manager] (AAM) a la API de envío:

   * UUID AAM: ID de AAM interno que se utiliza para identificar a un usuario de forma exclusiva.
   * dataPartnerId: El ID de un socio de datos.
   * dataPartnerUserId: ID de usuario proporcionado por un socio de datos.

   Anteriormente, la API de envío solo incluía `dcsLocationHint` y `blob`. (TNT-41644)

## at.js 2.6.0 (27 de julio de 2021)

* Se ha agregado un atributo seguro a las cookies cada vez que la configuración `secureOnly` de at.js se establece en `true`.
* Los tokens de respuesta ya están disponibles al utilizar `triggerView()`.
* Se ha corregido un problema relacionado con el evento `CONTENT_RENDERING_NO_OFFERS`. Ahora este evento se activa correctamente siempre que no haya contenido devuelto de [!DNL Target].
* [!DNL Anlytics for Target] (A4T) Los detalles de las métricas de clic se devuelven correctamente al usar solicitudes `prefetch`.
* La generación UUID ya no utiliza `Math.random()`, sino que depende de `window.crypto`.
* La caducidad de la cookie `sessionId` se amplía correctamente en cada llamada de red.
* La inicialización de la caché de la vista [!UICONTROL Aplicación de una sola página] (SPA) ahora se gestiona correctamente y respeta la configuración `viewsEnable`.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Detalles sobre los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
