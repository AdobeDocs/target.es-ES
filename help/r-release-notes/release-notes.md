---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: Notas de la versión
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 21c7675085bf5dc06bf9b1b38a82b2be4d4b0f76
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 100%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de la API de Target, el SDK, la biblioteca JavaScript (at.js) y otros cambios de plataforma, cuando corresponda.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Migre a la versión más reciente de [!DNL Adobe Experience Platform Web SDK] o a la biblioteca de JavaScript at.js antes más recientes para evitar posibles problemas con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## at.js 2.6.0 (16 de julio de 2021)

* Se ha agregado un atributo seguro a las cookies cada vez que la configuración `secureOnly` de at.js se establece en `true`.
* Los tokens de respuesta ya están disponibles al utilizar `triggerView()`.
* Se ha corregido un problema relacionado con el evento `CONTENT_RENDERING_NO_OFFERS`. Ahora este evento se activa correctamente siempre que no haya contenido devuelto de [!DNL Target].
* [!DNL Anlytics for Target] (A4T) Los detalles de las métricas de clic se devuelven correctamente al usar solicitudes `prefetch`.
* La generación UUID ya no utiliza `Math.random()`, sino que depende de `window.crypto`.
* La caducidad de la cookie `sessionId` se amplía correctamente en cada llamada de red.
* La inicialización de la caché de la vista [!UICONTROL Aplicación de una sola página] (SPA) ahora se gestiona correctamente y respeta la configuración `viewsEnable`.

## [!DNL Target Standard/Premium] 21.6.1 (30 de junio de 2021)

Esta versión incorpora las siguientes nuevas funciones y mejoras. Los números entre paréntesis son para uso interno de [!DNL Adobe].

| Función | Detalles |
| --- | --- |
| [!UICONTROL Analytics for Target] (A4T) | Ahora, al hacer clic en el vínculo “[!UICONTROL Ver en Analytics]” de la página [!UICONTROL Informes] de una actividad que utiliza [!DNL Analytics] como fuente de informes (A4T), [!DNL Analysis Workspace] se abre. Anteriormente, el vínculo abría Creación de informes [!DNL Analytics]. (TGT-36959) |

## Python SDK 1.0.0 (16 de junio de 2021)

Ya está disponible el nuevo SDK de Python de [!DNL Adobe Target] con funcionalidades de toma de decisiones en el dispositivo. Esta adición más reciente refuerza el conjunto de [!DNL Target] de SDK del lado del servidor. Estos SDK le ayudan a integrar con [!DNL Target] y aceleran el tiempo de valor, en el idioma de su elección. Las integraciones del lado del servidor se están convirtiendo en una opción popular, dado que el mercado está cambiando a un mundo sin cookies en el que los datos de origen son valiosos. Los SDK de Target están disponibles en los lenguajes de programación más populares del mercado (Python, Java, JavaScript, C# / .Net).

Para obtener más información, consulte la [Documentación del SDK de Python](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk) en la [Guía de SDK de Adobe Target](https://adobetarget-sdks.gitbook.io/docs/).

## ![Insignia del SDK web de Adobe Experience Platform](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] versión 2.5.0 (1 de junio de 2021)

Esta versión de [!DNL Platform Web SDK] incluye compatibilidad con lo siguiente:

| Función | Detalles |
| --- | --- |
| Compatibilidad de redireccionamiento con [!UICONTROL Analytics for Target] (A4T) | El SDK web de Platform ahora admite redirecciones [!DNL Target] al utilizar [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Para obtener más información, consulte [Implementación de Analytics para  [!DNL Target] ](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
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
