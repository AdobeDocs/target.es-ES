---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 145f4bd2b3353e429ce968622e47653170a60fda
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 19 de octubre de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.3 (versión escalonada del 25 al 27 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **25 de octubre**: región de Europa, Oriente Medio y África (EMEA)
* **26 de octubre**: región Asia-Pacífico (APAC)
* **27 de octubre**: región de América

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<br> (disponible para clientes seleccionados para realizar pruebas. Estará disponible para todos los clientes en una versión futura). | Tenga en cuenta los siguientes cambios:<ul><li>Se ha añadido compatibilidad con las métricas binarias y de maximización en la creación de informes de [!UICONTROL Analytics for Target] (A4T) para las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]</li><li>Se ha mantenido el comportamiento para las actividades existentes hasta febrero de 2023. Después de esta fecha, las actividades se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento</li><li>A partir del 20 de febrero de 2023, la compatibilidad con las métricas `averagetimespentonsite`, `bouncerate` y `entries` en las actividades de [!DNL Target] quedará obsoleta.</li></ul> |

* Se ha añadido información en la IU de [!DNL Target] para ayudar a los clientes a navegar por el generador de audiencias de forma más eficaz y para aprender a utilizar funciones que pueden ser desconocidas. (TGT-44139)
* Funcionalidad agregada para evitar que los clientes editen una actividad deshabilitada por [!DNL Target] porque utiliza métricas no admitidas. Un mensaje en la IU indica a los clientes que dupliquen la actividad y que luego actualicen las métricas de conversión.

   Con esta versión, las métricas `averagetimespentonsite`, `bouncerate` y `entries` en las actividades de [!DNL Target] quedarán obsoletas para las nuevas actividades. Las actividades existentes pueden seguir utilizando estas métricas hasta mayo de 2023.

* Se ha añadido información en la IU de [!DNL Target] para ayudar a los clientes a seleccionar criterios de optimización al crear o editar una actividad de [!UICONTROL Segmentación automática] que utiliza A4T.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
