---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8cdf362d9e45153b26bca5a45ed59ef557adc016
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 44%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 14 de marzo de 2023**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.15.1 (8 y 9 de marzo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **8 de marzo**: región de América
* **Marzo de 9**: región de Europa, Oriente Medio y África (EMEA)
* **Marzo de 9**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] | [!DNL Target] permite elegir métricas basadas en eventos binomiales o métricas basadas en eventos continuos al utilizar [!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades.<P>Tenga en cuenta el siguiente cambio en las métricas admitidas:<ul><li>[!DNL Target] conservó el comportamiento anterior para las actividades existentes hasta (FECHA POR DETERMINAR). Después de esta fecha, las actividades que usen métricas no admitidas se suspenderán para forzar la migración de la actividad existente al nuevo comportamiento.</li></ul>Para obtener más información, consulte [Métricas de objetivo admitidas](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *Compatibilidad de A4T con actividades de asignación automática y segmentación automática*. |
| [!UICONTROL Asignación automática] usando [!UICONTROL Analytics for Target] (A4T) | Nuevo tutorial:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Asignación automática] actividades](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL Segmentación automática] usando [!UICONTROL Analytics for Target] (A4T) | Nuevo tutorial:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Segmentación automática] actividades](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

Esta versión incluye las siguientes correcciones:

* Actualizaciones para la creación de componentes web personalizados con [!UICONTROL Compositor de experiencias visuales] (VEC):

   * Se ha corregido la selección de elementos DOM sombreados en el VEC al mejorar el proceso de creación, de modo que no haya dependencia del [!DNL Target] tipo de implementación al crear la raíz en la sombra. Ahora, la selección de los elementos DOM sombreados en el VEC debería funcionar para cualquier sitio web.
   * Se ha corregido un problema que impedía cargar elementos HTML usando #Shadow DOM en el VEC. (TGT-35801)
   * SPA Se han corregido problemas del VEC con sitios web que utilizaban ShadowDOM, por lo que se eliminaron problemas de VEC. (TGT-43169)
   * Se ha corregido un problema con el objetivo de optimización: &quot;hacer clic en un elemento&quot; que no identificaba correctamente el selector de CSS en ShadowDOM.

>[!NOTE]
>
>Para garantizar la entrega de los cambios creados en el VEC, asegúrese de utilizar un [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) con una versión buena a 2.8.

**Problema conocido**: Seguimiento de clics en un elemento raíz de la sombra al utilizar [!DNL Adobe Experience Platform Web SDK] no funciona correctamente. (TNT-47012)

## Versión 2.10.2 de at.js (7 de marzo de 2023)

* Se ha corregido un problema que provocaba que `trackEvent` para devolver siempre un error.

Para obtener información sobre todas las versiones de at.js, consulte [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
