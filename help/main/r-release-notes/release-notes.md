---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e3a22ef34bc78b03b71c75968d2271b9a634a0cd
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 46%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.5.1 (7 de mayo de 2026)

**Integraciones**

+++Ver detalles

* Administración de **[!DNL Adobe Target]en Experimentation Accelerator.** Se agregó compatibilidad para asignar [!DNL Target] espacios de trabajo a zonas protegidas de Experimentation Accelerator, de modo que los equipos puedan ver los experimentos de [!DNL Adobe Target] en Experimentation Accelerator en un solo lugar. [Más información](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

## [!DNL Target Standard/Premium] 26.4.4 (28 de abril de 2026)

**Actividades**

+++Ver detalles

* **Error con el filtro de audiencia en los informes.** Se corrigió un problema en el cual al cambiar el filtro de audiencia dentro de **[!UICONTROL Goals & Settings]** se producía un error en la sección de informes de la interfaz de usuario de [!DNL Target]. (TGT-55006)

* **Ordenar actividades por prioridad.** Se agregó la ordenación por prioridad en la lista de actividades mediante el encabezado de columna **[!UICONTROL Priority]**, con un orden ascendente y descendente coherente con otras columnas que se pueden ordenar. (TGT-54948)

* **No se conservan las propiedades de actividad adicionales después de guardar.** Se corrigió un problema en el cual ciertas **[!UICONTROL Properties]** selecciones no persistían después de guardar y volver a abrir una actividad. (TGT-53889)

+++

**Localización**

+++Ver detalles

* **Etiquetas japonesas para [!UICONTROL Page Delivery] operadores de reglas.** Se han corregido cadenas ilegibles o dañadas para las etiquetas de operador de reglas de entrega de páginas en la IU japonesa. (TGT-53097)

+++

**API**

+++Ver detalles

* **Informando sobre compatibilidad con la API [!DNL GraphQL] para `segmentId`.** Se agregó `segmentId` a la API de informes [!DNL GraphQL]. (TGT-55021)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalles

* **Modificaciones mostradas en la experiencia incorrecta en el editor.** Se ha corregido un problema en el cual una eliminación u otra modificación podría aparecer en la experiencia incorrecta después de cambiar entre experiencias en [!UICONTROL Visual Experience Composer]. (TGT-54955)

* **Modificaciones eliminadas al eliminar insertar HTML.** Se ha corregido un problema en el cual al eliminar el bloque **[!UICONTROL HTML]** adicional agregado con **[!UICONTROL Insert before]** o **[!UICONTROL Insert after]** también se eliminaba una modificación vinculada que no tenía selector CSS. (TGT-54530)

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
