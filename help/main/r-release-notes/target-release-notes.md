---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1cc630f12f4b9dc1d9c5700bc6174b40d4f0dae2
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 48%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 27 de marzo de 2023**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.3.1 (28-30 de marzo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **28 de marzo**: región de Europa, Oriente Medio y África (EMEA)
* **29 de marzo**: región Asia-Pacífico (APAC)
* **30 de marzo**: región de las Américas

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
|--- |--- |
| AEM fragmentos de contenido para una personalización y experimentación sin objetivos | Uso [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de contenido] en [!DNL Target] actividades. Combine la facilidad de uso y la potencia de la AEM con potentes capacidades de inteligencia artificial (IA) y aprendizaje automático (ML) en [!DNL Target] para probar y personalizar experiencias a escala. |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<p>(Fecha de la versión: 30 de marzo de 2023) | [!DNL Target] permite elegir métricas basadas en eventos binomiales o métricas basadas en eventos continuos al utilizar [!UICONTROL A4T] para actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].<P>Tenga en cuenta el siguiente cambio en las métricas admitidas:<ul><li>[!DNL Target] conservó el comportamiento anterior para las actividades existentes hasta el 9 de septiembre de 2023. Después de esta fecha, las actividades que utilizan métricas no compatibles se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento.</li></ul> |
| [!UICONTROL Asignación automática] utilizando [!UICONTROL Analytics para Target] (A4T) | Tutorial actualizado:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Asignación automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank}</li></ul> |
| [!UICONTROL Segmentación automática] utilizando [!UICONTROL Analytics para Target] (A4T) | Tutorial actualizado:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Segmentación automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank}</li></ul> |

* Se ha mejorado la sincronización de audiencias y actividades para que los elementos creados en [!DNL Adobe Experience Platform] y [!DNL Adobe Audience Manager] están disponibles en la [!DNL Target] IU más rápido. (TGT-44568)
* Se ha realizado un cambio para permitir que los usuarios eliminen el [!UICONTROL Dirección URL predeterminada] under [!UICONTROL Administración] > [!UICONTROL Compositor de experiencias visuales] > [!UICONTROL Dirección URL predeterminada]. Este cambio permite a los clientes volver a cambiar la dirección URL predeterminada a una cadena vacía, que anteriormente no era posible tras la configuración inicial. (TGT-44577)
* Se han eliminado restricciones que impedía a los clientes editar o eliminar audiencias predeterminadas (audiencias con nombres reservados). (TGT-44655)
* Se ha deshabilitado &quot;[!UICONTROL Listo]&quot; mientras se cargaban los spinners estaban visibles en el [!DNL Target] IU al crear [audiencias combinadas](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Se ha corregido la variable [!UICONTROL Idioma] vínculo en la parte inferior del [!UICONTROL Audiencias] para que se vincule correctamente al &quot;[!UICONTROL Preferencias de comunicación de la cuenta]&quot;. (TGT-43562)
* Se ha resuelto un problema que a veces impedía que los clientes crearan [!UICONTROL Prueba A/B] actividades después de seleccionar la variable [!UICONTROL Adobe Analytics] opción bajo [!UICONTROL Administración] > [!UICONTROL Informes] > [!UICONTROL Solución de Experience Cloud de informes]. (TGT-44844)
* Se ha corregido un problema que impedía que los clientes vieran la última experiencia en un [!UICONTROL Prueba multivariable] actividad con muchas experiencias desde dentro de [!UICONTROL Compositor de experiencias visuales] (VEC). La variable [Ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en la parte inferior del VEC, a veces impedía que los clientes vieran la última experiencia. (TGT-44578)
* Se ha corregido un problema que provocaba que la URL de exploración del VEC no reflejara la página actual que es visible en una sesión normal del explorador si la página requiere autorización o invoca redirecciones. (TGT-44350)
* Se ha corregido un problema que impedía que los clientes cambiaran la variable [!UICONTROL Filtrar criterios no compatibles] configurar en [!UICONTROL Recommendations] > [!UICONTROL Configuración]. (TGT-44398)
* Se ha corregido un problema que provocaba que las solicitudes de POST crearan nuevas [!DNL Recommendations] fuentes en las que se producen errores al usar [!UICONTROL Clasificaciones de Analytics] con grupos de informes con puntos en sus nombres. (TGT-44598)
* Vínculos actualizados en la variable [!DNL Target] La interfaz de usuario de señala al nuevo [Extensión de Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Seguridad mejorada para evitar intentos de falsificación de solicitudes del lado del servidor (SSRF) en [!DNL Recommendations] fuentes. (TGT-43769)
* Se ha corregido un problema que impedía a los clientes ver imágenes de vista previa en [!DNL Recommendations] diseños si el nombre de la imagen contiene [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* Se ha corregido un problema que provocaba algunos [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank} para escapar en la variable [!UICONTROL Modificaciones] panel mientras edita [!UICONTROL Texto/HTML] en una actividad [!UICONTROL Experiencias] página. (TGT-44600)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].


## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
