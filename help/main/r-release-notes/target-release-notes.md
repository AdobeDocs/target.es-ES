---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 24df83c228ef5ebb9f0cd2234a689244625be9a2
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 96%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 23 de enero de 2023**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.13.3 (25 de enero de 2023)

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

* Se ha agregado compatibilidad con ofertas JSON en actividades de [!UICONTROL Automated Personalization] (AP) mediante el Compositor de experiencias basadas en formularios. (TGT-41460)
* Implementado [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) para actividades AP para clientes seleccionados. Esta funcionalidad estará disponible para todos los clientes después de una fase inicial de prueba. (TGT-44341)
* Se han agregado nombres descriptivos en la creación de informes de [!UICONTROL Analytics for Target] de A4T. Anteriormente, solo se enumeraban los ID de experiencia de [!DNL Target]. Esta mejora alinea el sistema de informes entre [!DNL Adobe Analytics] y [!DNL Target] y ayuda a los clientes a optimizar la creación de informes en A4T. (TGT-41853)
* Se ha corregido un problema que provocaba un “error 500” en actividades de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) que contienen recomendaciones. Este problema se originó cuando [!DNL Target] no pudo eliminar correctamente los objetos de criterios de la IU de [!DNL Target] y el backend de [!DNL Recommendations] que ya no están en uso. (TGT-44383)
* Se ha eliminado la ubicación del nombre de oferta mostrado en el informe [!UICONTROL Nivel de oferta] para actividades de [!UICONTROL Automated Personalization]. Este cambio hace que el informe sea más legible. (TGT-44294)
* Se ha cambiado el nombre de la opción “[!UICONTROL Fragmento de experiencia]” en el flujo de trabajo del [!UICONTROL Compositor de experiencias visuales] (VEC). La opción se conoce ahora como &quot;[!UICONTROL XF de HTML]&quot;. (TGT-44132)
* Se ha añadido la capacidad de ver metadatos de ofertas de fragmentos de experiencia en la información sobre ofertas. (TGT-43838)
* Se han eliminado las opciones de calendario de 45 días y 90 días de la API y la [!UICONTROL Segmentación automática], la [!UICONTROL Información de personalización] y los [!UICONTROL Atributos importantes] de la IU [!DNL Target]. Debido a los patrones de uso y para mejorar el rendimiento, estos intervalos de fechas han quedado obsoletos. La IU se actualizó para reflejar los intervalos actualmente permitidos: 15, 30 y 60 días. (TGT-39357)
* Se ha desactivado la capacidad de cambiar la configuración [!UICONTROL Igual que el objetivo de optimización] en la página [!UICONTROL Objetivos y configuración] después de que la actividad esté activa. (TGT-43923)
* Se ha corregido un problema que provocaba problemas con el lugar de trabajo predeterminado en el backend de [!DNL Target] al actualizar desde [!DNL Target Standard] a [!DNL Target Premium]. (TGT-44081 y TGT-44306)
* Se ha cambiado el vínculo en la página [!UICONTROL Implementación] ([!UICONTROL Administración] > [!UICONTROL Implementación]) para “Métodos de implementación con decisiones en el dispositivo” para que apunten a la página que explica cómo utilizar la toma de decisiones en el dispositivo para todos los SDK admitidos: Node.js, Java, .NET y Python. Para obtener más información, consulte [Introducción a SDK de Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Se ha corregido un problema que provocaba problemas de carga de archivos al usar [!DNL Scene7] y [!DNL Target].
* Se ha mejorado la accesibilidad de la IU de [!DNL Target] para personas con discapacidades mediante el uso de los resultados de una auditoría de uso interna. Estas mejoras de accesibilidad incluyen funciones que anteriormente no eran accesibles mediante el teclado, mejoras de texto alternativo, la capacidad de hacer zoom en partes de la IU para que sean más utilizables, un enfoque de teclado mejorado y mucho más.   (TGT-42759)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
