---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 54%

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
| Métricas continuas | Se ha agregado la capacidad de usar métricas continuas, como los ingresos, en [!UICONTROL Segmentación automática] y [!UICONTROL Asignación] actividades.<br>Anteriormente, [!UICONTROL Segmentación automática] y [!UICONTROL Asignación automática] los modelos de se optimizaron para funcionar solo con métricas binarias (basadas en conversión). (TGT-43649 y TGT-43649)<BR>Tenga en cuenta que esta función solo está disponible para clientes seleccionados. Esta función estará disponible para todos los clientes en una versión futura. |
| [!DNL Recommendations] nombres descriptivos | Se han añadido nombres descriptivos en [!UICONTROL Analytics para Target] Informes de A4T. Anteriormente, [!DNL Target] solo los ID de experiencia enumerados. Esta mejora alinea el sistema de informes entre [!DNL Adobe Analytics] y [!DNL Target] y ayuda a los clientes a optimizar la creación de informes en A4T. (TGT-41853 |

* Se ha añadido información sobre herramientas en la sección [!DNL Target] IU para ayudar a los clientes a navegar por el generador de audiencias de forma más eficaz y para aprender a utilizar funciones que pueden no ser familiares. (TGT-44139)
* Funcionalidad agregada para evitar que los clientes editen una actividad deshabilitada por [!DNL Target] porque utiliza métricas no admitidas. Un mensaje en la interfaz de usuario indica a los clientes que dupliquen la actividad y que luego actualicen la métrica de conversión.

   Con esta versión `averagetimespentonsite`, `bouncerate`y `entries` métricas en [!DNL Target] las actividades de quedarán obsoletas para las nuevas actividades. Las actividades existentes pueden seguir utilizando estas métricas hasta el 6 de febrero de 2023. (TGT-43860, TGT-43861 y TGT-43650)

* Se ha añadido una información de objeto en la sección [!DNL Target] IU para ayudar a los clientes a seleccionar criterios de optimización al crear o editar un [!UICONTROL Segmentación automática] actividad que utiliza A4T. (TGT-43713)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
