---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0f96fb2a74a0716542308037d183847c91b1dc04
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 52%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.5.1 (5 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que impedía que se mostraran los refinamientos de audiencia para determinadas actividades en la IU actualizada. (TGT-52057)
* Se ha corregido un problema que impedía el uso de audiencias combinadas en actividades de. (TGT-52346)
* Se ha corregido un problema que impedía la creación de una nueva actividad en un espacio de trabajo no predeterminado mediante una audiencia solo de actividad desde el mismo espacio de trabajo. (TGE-52349)
* Se ha corregido un problema que provocaba que las audiencias solo de actividad desaparecieran de la interfaz de usuario actualizada después de crear y seleccionar una audiencia nueva. (TGT=52091)
* Se ha corregido un problema que impedía el uso de audiencias duplicadas en las actividades de. (TGT-51200 y TGT-52057)
* Se ha corregido un problema que provocaba que las refinaciones de audiencia y las audiencias de actividad se invirtieran en la interfaz de usuario actualizada. (TGT-52158)
* Se ha corregido un problema que impedía la creación de una nueva actividad debido al error de entrada del usuario: &quot;espacio de trabajo no predeterminado no permitido para este usuario&quot;. (TGT-52267)
* Se ha corregido un problema que impedía que las ofertas se mostraran en la interfaz de usuario actualizada tanto para espacios de trabajo predeterminados como no predeterminados. [!DNL Target] ahora muestra ofertas de ambos espacios de trabajo. (TGT-52339)
* Se ha corregido un problema en el cual [!DNL Target] no advertía a los clientes al editar una actividad y cambiar un elemento de sitio web modificado. (TGT-52100)
* Se ha corregido un problema por el cual al editar una oferta con ofertas ad hoc se creaba una nueva oferta en lugar de actualizar la existente. (TGT-52135)
* Se ha corregido un problema que provocaba un error de carga no válida al mover ofertas a carpetas. (TGT-52325)
* Se ha corregido un problema que provocaba un error de entrada del usuario al mover ofertas a carpetas. (TGT-52296)
* Se agregó un campo `audienceMetadata` para cada actividad, y se aseguró de que se lea y actualice al editar la actividad. (TGT-51004)

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
