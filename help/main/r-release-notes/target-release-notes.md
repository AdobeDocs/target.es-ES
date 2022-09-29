---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 224f95c21db67d27b31f0a3fc44216ee6033f874
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 28%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 29 de septiembre de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.1 (versión escalonada del 4 al 6 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **4 de octubre**: Región de Europa, Oriente Medio y África (EMEA)
* **5 de octubre**: Región de Asia y el Pacífico (APAC)
* **6 de octubre**: Región de América

Esta versión contiene las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiencias | Las actualizaciones de la funcionalidad de los fragmentos de experiencia de AEM incluyen lo siguiente:<ul><li>Se ha agregado la capacidad de filtrar AEM fragmentos de experiencia por tipo (HTML o JSON) en la variable [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Se ha corregido un problema que permitía a los clientes insertar JSON [!UICONTROL Fragmento de experiencia] ofertas al usar el VEC, que no es compatible. Las ofertas JSON solo se pueden insertar al usar la variable [!UICONTROL Experiencia basada en formularios] compositor. (TGT-43846)</li></ul>Para obtener más información, consulte AEM [fragmentos de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nuevo [!UICONTROL Compositor de experiencias visuales] extensión para Google Chrome | Un nuevo [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] La extensión (VEC) para Chrome está disponible en Chrome Web Store.<br>A partir de enero de 2023, la variable [!DNL Target] La extensión VEC Helper dejará de funcionar en Google Chrome porque Google no permitirá extensiones con Manifest V2. Descargue la nueva extensión para seguir creando visualmente sus sitios web en [!DNL Target] a partir del nuevo año.<br>Los siguientes vínculos muestran las dos extensiones en la tienda web de Chrome:<ul><li>[Nueva extensión](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensión antigua](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul> |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<br>(Fecha exacta de lanzamiento por determinar). | Tenga en cuenta los siguientes cambios:<ul><li>Se ha agregado compatibilidad con las métricas binarias y de maximización en [!UICONTROL Analytics para Target] Informes de A4T para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades</li><li>Se ha eliminado el mensaje de advertencia de métricas binarias para [!UICONTROL Segmentación automática] actividades</li><li>Se ha mantenido el comportamiento para las actividades existentes hasta el 20 de febrero de 2023. Después de esta fecha, las actividades se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento</li><li>A partir del 20 de febrero de 2023, la compatibilidad con `averagetimespentonsite`, `bouncerate`y `entries` métricas en [!DNL Target] las actividades de quedarán obsoletas.</li></ul> |

* Se ha corregido un problema que impedía que la información de reglas de audiencia se mostrara correctamente en la variable [!UICONTROL Refinamientos de audiencias] ventana de información. (TGT-43917)
* Se ha mejorado el rendimiento del [!DNL Target] IU al cargar audiencias que se aproximan al [límite recomendado de reglas de segmentación](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Se ha corregido un problema que hacía que algunos componentes no se mostraran correctamente en la sección [!UICONTROL Modificaciones] en el panel [!UICONTROL Experiencias] página al crear o editar actividades en el VEC después de cambiar de [!UICONTROL Componer] a [!UICONTROL Examinar] en el menú contextual. (TGT-43300)
* Se ha corregido un problema que impedía que algunos clientes archivaran [!UICONTROL Prueba A/B] actividades que utilizan [!UICONTROL Segmentación automática]. (TGT-40978)
* Se ha agregado la capacidad de usar automáticamente una sola oferta en varias ubicaciones dentro de un único grupo de informes. (TGT-43974)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
