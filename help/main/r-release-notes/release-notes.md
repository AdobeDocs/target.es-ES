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
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.6.1 (4 de junio de 2026)

**Actividades**

+++Ver detalles

* **URL de actividad incompleta en [!UICONTROL Información general de actividad].** Se ha corregido un problema en el cual [!UICONTROL Información general de actividad] no mostraba la dirección URL completa de una actividad. (TGT-54029)

* **Formato de fecha no localizado en los informes de actividad.** Se ha corregido un problema por el cual el formato de fecha no se localizaba en la ficha **[!UICONTROL Informes]** al elegir la opción **Últimos X días** de la lista desplegable **[!UICONTROL Intervalo de fecha preestablecido]**. (TGT-51637)

* **No se puede guardar la actividad basada en formularios con ciertos caracteres GB18030 en [!UICONTROL Ubicación].** Se ha corregido un problema que impedía guardar una actividad basada en formularios cuando el campo **[!UICONTROL Ubicación]** contenía caracteres GB18030 específicos. (TGT-46980)

+++

**[!UICONTROL Públicos]**

+++Ver detalles

* **Calendario no localizado en el flujo Crear audiencia para chino simplificado y tradicional.** Se corrigió un problema en el cual el calendario de los campos **[!UICONTROL Start]** y **[!UICONTROL End]** de los atributos **[!UICONTROL Time frame]** no se localizaba en las configuraciones regionales del chino simplificado (CHS) y del chino tradicional (CHT) durante el flujo de Crear audiencia. (TGT-50619)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* **Información sobre herramientas no localizada en el generador de actividades actualizado.** Se han corregido problemas de localización en los que la información sobre herramientas de **[!UICONTROL Refinamientos]** y **[!UICONTROL Contenido]** no se había localizado en el generador de actividades actualizado de [!UICONTROL Compositor de experiencias visuales]. (TGT-53721)

* **Todos los visitantes sin localizar en [!UICONTROL Audiencias de experiencia].** Se ha corregido un problema en el cual la cadena **[!UICONTROL Todos los visitantes]** de **[!UICONTROL Audiencias de experiencia]** en el carril izquierdo no estaba localizada en [!UICONTROL Compositor de experiencias visuales]. (TGT-50086)

+++

**[!UICONTROL Informes]**

+++Ver detalles

* **Formato de fecha no localizado en la ventana [!UICONTROL Crear ajuste preestablecido].** Se ha corregido un problema en el cual el formato de fecha del campo **[!UICONTROL Intervalo de fechas]** de la ventana **[!UICONTROL Crear ajuste preestablecido]** no estaba localizado. (TGT-49239)

+++

**Localización**

+++Ver detalles

* **GB18030 visualización de caracteres en varias áreas.** Se han corregido problemas en los que algunos caracteres del área de uso privado se mostraban incorrectamente como cartas en la interfaz de usuario de **[!UICONTROL Audience]**, **[!UICONTROL Administration]** > **[!UICONTROL Properties]**, la configuración de la ventanilla móvil y las notificaciones de mensajes emergentes. (TGT-49622, TGT-49623, TGT-49624 y TGT-49625)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

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
