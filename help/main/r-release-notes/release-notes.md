---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c5445903e7bbab210d0e72200c54ab07975c21c5
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 49%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.10.1 (versión escalonada del 5 al 7 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **5 de octubre**: Región de Asia y el Pacífico (APAC)
* **6 de octubre**: Región de América
* **7 de octubre**: Región de Europa, Oriente Medio y África (EMEA)

Esta versión contiene las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiencias | Las actualizaciones de la funcionalidad de fragmentos de experiencia de AEM incluyen lo siguiente:<ul><li>Se ha agregado la capacidad de filtrar AEM fragmentos de experiencia por tipo (HTML o JSON) en la variable [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Se ha corregido un problema que permitía a los clientes insertar JSON [!UICONTROL Fragmento de experiencia] ofertas al usar el VEC, que no es compatible. Las ofertas JSON solo se pueden insertar al usar la variable [!UICONTROL Experiencia basada en formularios] compositor. (TGT-43846)</li></ul>Para obtener más información, consulte AEM [fragmentos de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nuevo [!UICONTROL Compositor de experiencias visuales] extensión para Google Chrome | Un nuevo [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] La extensión (VEC) para Chrome está disponible en Chrome Web Store.<br>A partir de enero de 2023, la variable [!DNL Target] La extensión VEC Helper dejará de funcionar en Google Chrome porque Google no permitirá extensiones con Manifest V2. Descargue la nueva extensión para seguir creando visualmente sus sitios web en [!DNL Target] a partir del nuevo año.<br>Los siguientes vínculos muestran las dos extensiones en la tienda web de Chrome:<ul><li>[Nueva extensión](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensión antigua](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obtener más información, consulte [Extensión de Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<br>(Fecha exacta de lanzamiento por determinar). | Tenga en cuenta los siguientes cambios:<ul><li>Se ha agregado compatibilidad con las métricas binarias y de maximización en [!UICONTROL Analytics para Target] Informes de A4T para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades</li><li>Se ha mantenido el comportamiento para las actividades existentes hasta el 20 de febrero de 2023. Después de esta fecha, las actividades se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento</li><li>A partir del 20 de febrero de 2023, la compatibilidad con `averagetimespentonsite`, `bouncerate`y `entries` métricas en [!DNL Target] las actividades de quedarán obsoletas.</li></ul> |

* Se ha corregido un problema que impedía que la información de reglas de audiencia se mostrara correctamente en la variable [!UICONTROL Refinamientos de audiencias] ventana de información. (TGT-43917)
* Se ha mejorado el rendimiento del [!DNL Target] IU al cargar audiencias que se aproximan al [límite recomendado de reglas de segmentación](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Se ha corregido un problema que hacía que algunos componentes no se mostraran correctamente en la sección [!UICONTROL Modificaciones] en el panel [!UICONTROL Experiencias] página al crear o editar actividades en el VEC después de cambiar de [!UICONTROL Componer] a [!UICONTROL Examinar] en el menú contextual. (TGT-43300)
* Se ha corregido un problema que impedía que algunos clientes archivaran [!UICONTROL Prueba A/B] actividades que utilizan [!UICONTROL Segmentación automática]. (TGT-40978)
* Se ha agregado la capacidad de usar automáticamente una sola oferta en varias ubicaciones dentro de un único grupo de informes. (TGT-40689)

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
