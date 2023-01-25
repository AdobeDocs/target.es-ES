---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 888c50e7052229c22136526d632f89fbaa548298
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 91%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.13.3 (25-26 de enero de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **25 de enero**: Región de Europa, Oriente Medio y África (EMEA)
* **25 de enero**: Región de Asia y el Pacífico (APAC)
* **26 de enero**: Región de América

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| Automated Personalization (AP) | Se ha agregado compatibilidad con ofertas JSON en actividades de [!UICONTROL Automated Personalization] (AP) mediante el Compositor de experiencias basadas en formularios.<br>Para obtener más información, consulte [Creación de ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md). (TGT-41460) |
| Recommendations | Nombres descriptivos en [!UICONTROL Analytics para Target] Ya está disponible la creación de informes de A4T. Anteriormente, solo se enumeraban los ID de experiencia de [!DNL Target]. Esta mejora alinea el sistema de informes entre [!DNL Adobe Analytics] y [!DNL Target] y ayuda a los clientes a optimizar la creación de informes en A4T. (TGT-41853) |
| Fragmentos de experiencia de AEM | Se ha agregado la capacidad de distinguir entre [!DNL Adobe Experience Manager] tipos de fragmento (AEM XF) que se exportan a [!DNL Target]. En lugar de la opción &quot;Fragmento de experiencia&quot;, [!DNL Target] ahora le permite filtrar y buscar por &quot;HTML XF&quot; y &quot;JSON XF&quot;. <br>Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). (TGT-44132) |

* Se ha corregido un problema que provocaba un “error 500” en actividades de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) que contienen recomendaciones. Este problema se originó cuando [!DNL Target] no pudo eliminar correctamente los objetos de criterios de la IU de [!DNL Target] y el backend de [!DNL Recommendations] que ya no están en uso. (TGT-44383)
* Se ha eliminado la ubicación del nombre de oferta mostrado en el informe [!UICONTROL Nivel de oferta] para actividades de [!UICONTROL Automated Personalization]. Este cambio hace que el informe sea más legible. (TGT-44294)
* Se ha cambiado el nombre de la opción “[!UICONTROL Fragmento de experiencia]” en el flujo de trabajo del [!UICONTROL Compositor de experiencias visuales] (VEC). La opción se conoce ahora como &quot;[!UICONTROL XF de HTML]&quot;. (TGT-44132)
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

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/main/r-release-notes/target-release-notes.md). |
