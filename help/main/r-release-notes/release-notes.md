---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e3191da2ac21f51fa6e08af615659db1ccdd2d9
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 52%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba que las audiencias de experiencia desaparecieran de las actividades de. (TGT-52003)
* Se ha corregido un problema que provocaba elementos inesperados durante la entrega. (TGT-52011)
* Se ha corregido un problema que impedía que los clientes vieran la audiencia en el gráfico de segmentación de la página de vista Superior[!UICONTROL r]y durante la edición de la actividad. (TGT-52050)
* Se ha corregido un problema que impedía que los clientes reordenaran experiencias en orden de prioridad en actividades [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Se ha corregido un problema que provocaba un procesamiento incorrecto al deshacer cambios de estilo de texto. (TGT-51876)
* Se ha corregido un problema que al modificar una oferta de redireccionamiento, [!DNL Target] también quitaba los selectores [!UICONTROL ClickTrack] asociados con esa oferta. (TGT-51936)
* Se ha corregido un problema que provocaba que [!DNL Target] guardara el selector de forma incorrecta al cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Se ha corregido un problema que provocaba un error de nombre no válido después de abrir y cerrar el selector de mbox en la página [!UICONTROL Goals & Settings] sin realizar ningún cambio. (TGT-51983)
* Se ha corregido un problema que bloqueaba la edición de ofertas ad hoc creadas en la IU heredada de [!DNL Target]. (TGT-51984)
* Se ha corregido un problema que bloqueaba las actividades de edición que tienen ofertas ad-hoc que contienen código personalizado. (TGT-51995)
* Se ha corregido un problema que provocaba que las reglas de exclusión se mostraran como reglas de inclusión al editar definiciones de audiencia combinadas. (TGT-51999)
* Se ha corregido un problema que impedía que el código personalizado se mostrara correctamente durante la edición de experiencias. (TGT-52005)
* Se ha corregido un problema que hacía que la opción [!UICONTROL Insert Before] no estuviera disponible para insertar contenido antes de la barra de navegación. (TGT-52031)
* Se ha corregido un problema que impedía resaltar correctamente la experiencia predeterminada en los informes. (TGT-51716)
* Se ha corregido un problema que activaba un mensaje de `default message [Invalid optionLocalIds: xx]]` al crear una actividad. (TGT-52038)

## Versión 2.11.8 de at.js (31 de marzo de 2025)

* Se ha resuelto una vulnerabilidad identificada por CodeQL en la validación de sufijos de cadena para evitar casos extremos durante las operaciones de cambio de tamaño y movimiento. (TNT-51516)

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
