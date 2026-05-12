---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 42%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).


## Últimas actualizaciones: 12 de mayo de 2026

Servidor MCP **[!DNL Adobe Target] (Beta público)**

[!DNL Adobe Target] ahora proporciona un servidor MCP (Model Context Protocol) que muestra operaciones de experimentación, personalización y generación de informes directamente dentro de cualquier aplicación compatible con MCP. Con esta integración, los perfiles técnicos y de marketing pueden inspeccionar las pruebas A/B, analizar los informes de rendimiento, administrar audiencias y ofertas y realizar acciones controladas, todo ello utilizando indicadores en lenguaje natural en lugar de navegar por varias pantallas de interfaz de usuario o escribir consultas en la API de REST [!DNL Adobe Target]. Esta funcionalidad está disponible actualmente en **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.

Esta capacidad está disponible para todos los clientes en Public Beta.

Para obtener más información, consulte [[!DNL Adobe Target] Servidor MCP](../c-integrating-target-with-mac/mcp/target-mcp.md).


## [!DNL Target Standard/Premium] 26.5.1 (7 de mayo de 2026)

**Integraciones**

+++Ver detalles

* Administración de **[!DNL Adobe Target]en Experimentation Accelerator.** Se agregó compatibilidad para asignar [!DNL Target] espacios de trabajo a zonas protegidas de Experimentation Accelerator, de modo que los equipos puedan ver los experimentos de [!DNL Adobe Target] en Experimentation Accelerator en un solo lugar. [Más información](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**Actividades**

+++Ver detalles

* **[!UICONTROL Graph View]no está sincronizado con la tabla y la descarga.** Se ha corregido un problema en el cual los informes de actividad podían mostrar métricas que faltaban o cero en **[!UICONTROL Graph View]** para algunos intervalos de fechas a pesar de que **[!UICONTROL Table View]** y el informe descargado seguían mostrando los valores correctos. (TGT-54998)

+++

**[!UICONTROL Audiences]**

+++Ver detalles

* **La lista de uso de audiencia no se ha procesado completamente.** Se ha corregido un problema en el cual la sección **[!UICONTROL Usage]** de los detalles de audiencia podía mostrar solo un subconjunto de actividades asignadas incluso cuando se asociaban actividades adicionales a esa audiencia. (TGT-55094)

+++

**[!UICONTROL Administration]**

+++Ver detalles

* **Confirmación más clara para la ofuscación de IP del último octeto.** Cuando cambia **[!UICONTROL Obfuscate Visitor IP addresses]** a **[!UICONTROL Last octet]** en **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**, el cuadro de diálogo de confirmación ahora explica que [!DNL Target] oculta el último octeto de la dirección IP del visitante. (TGT-44821)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles

* **Página en blanco o incompleta con el Compositor de experiencias mejorado (EEC).** Se ha corregido un problema en el cual [!UICONTROL Visual Experience Composer] no podía cargar el sitio en el editor cuando **[!UICONTROL Enhanced Experience Composer]** estaba habilitado. (TGT-54576)

+++


<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| [Cambios de la documentación](/help/main/r-release-notes/doc-change.md) | Vea información detallada sobre las actualizaciones que se realizaron en esta guía y que no se incluyen en estas notas de la versión. |
| [Notas de la versión para versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium. |
| [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es){target=_blank} | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud. |

## Información de versión preliminar {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
