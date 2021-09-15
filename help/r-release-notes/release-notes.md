---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de Target, los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de plataforma, cuando corresponda.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Migre a la versión más reciente de [!DNL Adobe Experience Platform Web SDK] o a la biblioteca de JavaScript at.js antes más recientes para evitar posibles problemas con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 21.9.1 (14 de septiembre de 2021)

En esta versión de mantenimiento se incluyen las siguientes mejoras, correcciones y cambios.

* Se han corregido problemas que evitaban que los clientes iniciaran sesión en el [!UICONTROL Compositor de experiencias visuales] (VEC) debido a las nuevas políticas de seguridad para cookies de terceros en algunos exploradores web. Este problema se trató en &quot;Páginas que no se cargan en el Compositor de experiencias visuales (VEC) o el Compositor de experiencias mejorado (EEC) al usar Google Chrome versión 80+&quot; en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Se ha corregido un problema que provocaba que los nombres de oferta en el VEC mostraran la ruta de la oferta en lugar del nombre descriptivo de la oferta. (TGT-41300)
* Los nombres de experiencia ahora se reflejan en [!DNL Analysis Workspace] para actividades A4T (TGT-38674)
* Se ha corregido un problema en [!DNL Recommendations] que producía cambios erróneos en el ID de entidad en una promoción de una actividad duplicada en la actividad original. (TGT-41482)
* Se ha corregido un problema que impedía que el botón &quot;Editar criterios&quot; se mostrara correctamente en la página [!UICONTROL Experiencias] de las actividades [!DNL Recommendations] del VEC. (TGT-39512)
* Se ha corregido un problema que impedía la sincronización de actividades cuando se duplicaban y copiaban en un espacio de trabajo de prueba. (TGT-40686)
* Se ha corregido un problema que impedía realizar modificaciones en un selector con [fragmentos de experiencia](/help/c-experiences/c-manage-content/aem-experience-fragments.md) al usar &quot;[!UICONTROL Insertar después]&quot; en el VEC. (TGT-41802)
* Se ha corregido un problema que impedía que el contenido JSON vacío en una oferta se enviara al servidor. [!DNL Target] ahora envía el objeto JSON aunque esté vacío. (TGT-41555)
* Se ha corregido un problema que provocaba que se abrieran los informes [!DNL Analytics] heredados en lugar de [!DNL Analysis Workspace] cuando los clientes hacían clic en &quot;[!UICONTROL Ver en Analytics]&quot; mientras visualizaban un informe. (TGT-41867)
* Se ha añadido una aclaración adicional al mensaje de interfaz de usuario mostrado cuando un cliente intenta seleccionar [!DNL Analytics] como fuente de informes (A4T) para una actividad [!UICONTROL Automated Personalization]. El mensaje indica que, &quot;[!DNL Target] es la única fuente admitida para las actividades [!UICONTROL Automated Personalization]&quot;. (TGT-41954)
* Se ha añadido una aclaración adicional al mensaje de error cuando los clientes intentan separar hosts con &quot;nueva línea&quot; en lugar de comas. (TGT-40671)
* Se ha corregido un problema que provocaba que las fechas &quot;[!UICONTROL Última actualización]&quot; de algunas actividades difieran de la IU en inglés para clientes españoles y japoneses (al ver la IU en español y japonés). (TGT-38980)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
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
