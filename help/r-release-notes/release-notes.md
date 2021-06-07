---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas JavaScript.
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: Notas de la versión
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 146395f5453093ca34b259a143ff4e4c63be949b
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 58%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de la API de Target, el SDK, la biblioteca JavaScript (at.js) y otros cambios de plataforma, cuando corresponda.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Migrar a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Target Standard/Premium 21.6.1 (7 de junio de 2021). 

Esta versión incluye las siguientes mejoras:

| Función | Detalles |
| --- | --- |
| ![Distintivo Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catálogo ] SearchAPI | Busque en su catálogo de productos y contenido [!DNL Recommendations] mediante programación a través de API para identificar los elementos que coinciden con un criterio de búsqueda y simplificar la administración del catálogo.<br>**Limitaciones y notas**:<ul><li>La búsqueda en el catálogo mediante API no es compatible con entornos con más de 2000 000 elementos.</li><li>Los resultados de búsqueda en el catálogo a través de API se actualizan más rápidamente que los resultados de búsqueda en el catálogo a través de la interfaz de usuario [!DNL Target]. La búsqueda en el catálogo en la interfaz de usuario [!DNL Target] puede tardar más tiempo en reflejar los resultados más recientes.</li></ul>Para obtener más información, consulte [Búsqueda de entidades](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) en la guía *[!DNL Adobe Target][!DNL Recommendations] API*. |

Esta versión de mantenimiento de la versión contiene las siguientes correcciones.

* Se ha corregido un problema que provocaba que el espacio de trabajo predeterminado cambiara a otro espacio de trabajo al actualizar la página [!UICONTROL Audiencias]. (TGT-38871)
* Se ha corregido un problema en [!UICONTROL Administración] > [!UICONTROL Implementación] que a veces provocaba un mensaje de error que indicaba que &quot;Es posible que el mbox global no esté sincronizado. Intenta reguardarlo&quot;.

## ![Adobe Experience Platform Web SDK ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] versión 2.5.0 (1 de junio de 2021)

Esta versión de [!DNL Platform Web SDK] incluye compatibilidad con lo siguiente:

| Función | Detalles |
| --- | --- |
| Compatibilidad de redireccionamiento con [!UICONTROL Analytics for Target] (A4T) | El SDK web de Platform ahora admite redirecciones [!DNL Target] al utilizar [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Para obtener más información, consulte  [Analytics  [!DNL Target] para implementación](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Versión 2.5.0 de at.js (13 de mayo de 2021)

Esta versión de at.js incluye las siguientes mejoras y cambios:

* [Compatibilidad de decisiones en el dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) para at.js.
* [Vista previa de vínculos](/help/c-activities/c-activity-qa/activity-qa.md) Compatibilidad con actividades de Automated Personalization

Esta versión también elimina la compatibilidad con Microsoft Internet Explorer 10, Internet Explorer 11 y todas las versiones anteriores. Microsoft Edge sigue siendo compatible con at.js 2.5.0 y versiones posteriores.

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

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
