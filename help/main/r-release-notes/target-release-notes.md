---
keywords: Notas; Libera; Actualizaciones; versión futura; Mejoras; nuevas características; Fija; Actualizaciones; Prelanzamiento; Acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 0618d39fc5966c64cceea8f5bcccb625fc243ebb
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 38%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: jueves, 02 de abril de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Actualización de permisos de Target (22 de abril de 2025)

Esta actualización futura mejora el control organizativo sobre [!DNL Target] instancia configuraciones, evitando actualizaciones accidentales que podrían afectar a actividad envío en varios equipos de pruebas y personalización.

A partir del 22 de abril de 2025, solo [!UICONTROL Product] los administradores podrán [!UICONTROL Solutions] actualizar la configuración en las secciones, independientemente de sus roles en [!DNL Target] los [!UICONTROL Administration] espacios de trabajo. Los usuarios que no tengan este permiso tendrán acceso de solo lectura a las [!UICONTROL Administration] secciones.

Para obtener más información, vea [Administración Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versión incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba que experiencia audiencias desaparecieran de las actividades. (TGT-52003)
* Se ha corregido un problema que provocaba elementos inesperados durante envío. (TGT-52011)
* Se ha corregido un problema que impedía a los clientes ver los audiencia en el gráfico de direccionamiento de Ove[!UICONTROL r]vista Página y durante la edición actividad. (TGT-52050)
* Se ha corregido un problema que impedía a los clientes reordenar las experiencias en orden de prioridad en [!UICONTROL Experience Targeting] actividades (XT). (TGT-52054)
* Se ha corregido un problema que provocaba una representación incorrecta al deshacer cambios de estilo de texto. (TGT-51876)
* Se ha corregido un problema que, al modificar un oferta de redirección, [!DNL Target] también quita cualquier [!UICONTROL ClickTrack] selector asociado a ese oferta. (TGT-51936)
* Se corrigió un problema que ocasionaba [!DNL Target] guardar incorrectamente el selector al cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Se ha corregido un problema que provocaba un error de nombre de no válido después de abrir y cerrar el selector de mbox en la [!UICONTROL Goals & Settings] Página sin realizar ningún cambio. (TGT-51983)
* Se ha corregido un problema que bloqueaba la edición anuncios las ofertas hoc creadas en el IU heredado [!DNL Target] . (TGT-51984)
* Se ha corregido un problema que bloqueaba la edición de actividades que tenían ofertas anuncios-hoc que contenían código personalizado. (TGT-51995)
* Se ha corregido un problema que hacía que las reglas de exclusión se mostraran como reglas de inclusión al editar definiciones de audiencia combinadas. (TGT-51999)
* Se ha corregido un problema que impedía que el código personalizado se mostrara correctamente durante la edición experiencia. (TGT-52005)
* Se ha corregido un problema que hacía que la [!UICONTROL Insert Before] opción no estuviera disponible para insertar contenido antes de la barra navegación. (TGT-52031)
* Se ha corregido un problema que impedía resaltar correctamente la experiencia predeterminada en sistema de informes. (TGT-51716)
* Se ha corregido un problema que activaba un `default message [Invalid optionLocalIds: xx]]` mensaje al crear una actividad. (TGT-52038)

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
