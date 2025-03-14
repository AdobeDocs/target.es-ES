---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: cd335504f5354aa9052ae7e958cf803cd90a9ae9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 39%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.3.6 (14 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto el error &quot;Entrada de usuario no válida&quot; en las actividades [!UICONTROL Visual Experience Composer] (VEC) con [!UICONTROL Click Tracking] habilitado cuando el mismo selector [!UICONTROL ClickTrack] se usa varias veces. (TGT-51921)
* Se ha corregido el error &quot;Entrada de usuario no válida&quot; en las actividades VEC con ubicaciones compartidas (por ejemplo, selector de HEAD) y ofertas idénticas. (TGT-51879)
* Se ha corregido un problema que provocaba que las modificaciones de experiencia se compartieran entre audiencias. (TGT-51815)
* Se han resuelto errores de validación al crear actividades debido a conflictos de ID de segmento. Los errores se produjeron cuando [!DNL Target] detectó actividades existentes usando segmentos anónimos. (TGT-51784)
* Se ha resuelto un problema que impedía que [!DNL Target] guardara actividades con reglas de exclusión en una audiencia. (TGT-51581)
* Se ha resuelto un problema que impedía a los clientes crear, eliminar o mover carpetas sin acceso al espacio de trabajo predeterminado. (TGT-51499)
* Se ha resuelto un problema que provocaba que las solicitudes de GET fallaran al recuperar la lista de métricas [!DNL Analytics]. (TGT-51106)

## [!DNL Target Standard/Premium] 25.3.5 (11 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema que impedía a los usuarios cambiar ofertas en el panel [!UICONTROL Modifications]. (TGT-51800)
* Se ha resuelto un problema en el cual las acciones se mostraban incorrectamente en el panel izquierdo para experiencias y audiencias, incluido el modo [!UICONTROL ClickTrack]. (TGT-51895)
* Se ha resuelto un problema en el cual los selectores de [!UICONTROL ClickTrack] no se aplicaban a la página de audiencia correcta. (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4 (7 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema en el cual las audiencias solo de actividad no eran visibles en el panel [!UICONTROL Audiences], lo que impedía su edición o reutilización. (TGT-51860)
* Se ha corregido un problema que bloqueaba la creación de actividades de [!DNL Target Standard] mediante la creación de informes de [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Se ha corregido un problema que excluía los contadores de ID locales de la carga útil durante las operaciones de creación y edición por lotes. (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2 (6 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema por el cual al copiar una actividad con una audiencia solo de actividad no se podía crear una nueva actividad y se utilizaba por error la audiencia de la actividad original. (TGT-51855)
* Se ha corregido un problema que impedía editar [!UICONTROL Experience Targeting] actividades (XT) con audiencias solo de actividad. (TGT-51846)
* Se ha corregido un problema en el cual el [!UICONTROL Visual Experience Composer] (VEC) no podía aplicar correctamente las modificaciones a una experiencia en la primera edición. (TGT-51843)
* Se ha corregido un problema que activaba un error de &quot;ID&quot; al hacer clic en ciertos elementos dentro del VEC. (TGT-51814)
* Se ha actualizado la administración de errores en el VEC durante la creación de actividades. (TGT-51759)
* Se ha corregido un problema por el cual una vista que faltaba en el panel [!UICONTROL Modifications] provocaba un error de &quot;entrada de usuario no válida&quot; al guardar la actividad. (TGT-51827)
* Se ha corregido un problema que impedía la creación de criterios de recomendaciones. (TGT-51834)
* Se ha añadido un mensaje de confirmación antes de redirigir a una dirección URL diferente. (TGT-51703)
* Se han corregido problemas con las pruebas de integración de GraphQL en ofertas y carpetas. (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 (3 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Una audiencia combinada puede incluir subgrupos, cada uno de los cuales contiene varias audiencias. En esta versión se ha corregido un problema que impedía que se mostraran las audiencias de subgrupos en el cuadro de diálogo [!UICONTROL Rules]. (TGT-51813)
* Se ha resuelto un problema en el cual algunas audiencias de experiencia se reemplazaban por [!UICONTROL All Visitors] al abrir actividades anteriores. (TGT-51812)
* Se ha resuelto un problema que impedía editar actividades con audiencias solo de actividad. (TGT-51807)
* Se ha resuelto un problema que impedía editar las modificaciones del encabezado de página en la interfaz de usuario de [!DNL Target] actualizada. (TGT-51797)
* Se ha resuelto un error nulo que se producía al duplicar una experiencia, eliminar otra experiencia y, a continuación, intentar guardar la actividad. (TGT-51796)
* Se ha resuelto un problema que impedía que las reglas de exclusión de audiencia se mostraran en el panel de información de la audiencia durante el paso [!UICONTROL Targeting] de creación de actividades. (TGT-51579)
* Se han actualizado los mensajes de error localizados en coreano. (TGT-51701 y TGT-51699)

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

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
