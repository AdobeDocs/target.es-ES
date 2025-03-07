---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7196b966c46043db536313c7841fe8611268d373
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 36%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: sábado, 07 de marzo de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.3.4 (7 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema en el cual las audiencias solo de actividad no eran visibles en el panel [!UICONTROL Audiences], lo que impedía su edición o reutilización. (TGT-51860)
* Se ha corregido un problema que bloqueaba la creación de actividades de [!DNL Target Standard] mediante la creación de informes de [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Se ha corregido un problema que excluía los contadores de ID locales de la carga útil durante las operaciones de creación y edición por lotes. (TGT-51867)
* Se mejoraron los informes de accesibilidad al integrar [!DNL Axe Developer Hub], mejorar la cobertura, la creación de informes, la colaboración en equipo, la compatibilidad con pruebas manuales, los estándares de cumplimiento y la experiencia del usuario.

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
