---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7f5b4265adbb0e98b7250f99b0268ba5b70dec7c
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 76%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 5 de octubre de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.1 (versión escalonada del 6 al 10 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **6 de octubre**: región de América
* **7 de octubre**: región de Europa, Oriente Medio y África (EMEA)
* **10 de octubre**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiencias | Las actualizaciones de la funcionalidad de fragmentos de experiencia de AEM incluyen lo siguiente:<ul><li>Se ha agregado la capacidad de filtrar AEM fragmentos de experiencia por tipo (HTML o JSON) en la variable [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Se ha corregido un problema que permitía a los clientes insertar ofertas de [!UICONTROL Fragmento de experiencia] JSON al usar el VEC, lo cual no es compatible. Las ofertas JSON solo se pueden insertar al usar el compositor de [!UICONTROL Experiencias basadas en formularios]. (TGT-43846)</li></ul>Para obtener más información, consulte AEM [fragmentos de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nueva extensión del [!UICONTROL Compositor de experiencias visuales] para Google Chrome | Una nueva extensión [!UICONTROL Compositor de experiencias visuales] (VEC) de [!DNL Adobe Target] para Chrome está disponible en Chrome Web Store.<br>A partir de enero de 2023, la extensión del ayudante del VEC de [!DNL Target] dejará de funcionar en Google Chrome porque Google no permitirá extensiones con Manifest V2. Descargue la nueva extensión para continuar creando de forma visual sus sitios web en [!DNL Target] a partir del nuevo año.<br>Los siguientes vínculos muestran las dos extensiones en la Chrome Web Store:<ul><li>[Nueva extensión](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensión antigua](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obtener más información, consulte [Extensión de Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Actualizaciones de documentación | Las principales actualizaciones de la documentación son las siguientes:<ul><li>Nuevo y actualizado [Documentación de la API de administración e informes de Adobe Target](https://developer.adobe.com/target/administer/admin-api/){target=_blank} incluye una cobertura completa de los extremos de las API de administración y creación de informes, incluidas propiedades, ofertas, hosts, entornos, clientes, audiencias, actividades y mucho más.<br>Consulte este y contenido adicional para desarrolladores en la sección [[!DNL Adobe Target] [!UICONTROL Guía para desarrolladores]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Cálculos estadísticos en pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>Este artículo documenta los cálculos estadísticos detallados utilizados en las pruebas A/Bn manuales en [!DNL Adobe Target].<br>La información de este artículo sustituye al *Cálculos de Adobe Target para pruebas A/B* archivo pdf que anteriormente estaba disponible para su descarga en este sitio.</li></ul> |

* Se ha corregido un problema que impedía que la información de reglas de audiencias se mostrara correctamente en la ventana de información [!UICONTROL Refinamientos de audiencias]. (TGT-43917)
* Se ha mejorado el rendimiento de la IU de [!DNL Target] al cargar audiencias que se aproximan al [límite recomendado de las reglas de segmentación](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Se ha corregido un problema que hacía que algunos componentes no se mostraran correctamente en el panel [!UICONTROL Modificaciones] de la página [!UICONTROL Experiencias] al crear o editar actividades en el VEC después de cambiar del modo [!UICONTROL Componer] a [!UICONTROL Examinar]. (TGT-43300)
* Se ha corregido un problema que impedía que algunos clientes archivaran actividades de [!UICONTROL Prueba A/B] que utilizan [!UICONTROL Segmentación automática]. (TGT-40978)
* Se ha añadido la capacidad de usar automáticamente una sola oferta en varias ubicaciones dentro de un único grupo de creación de informes. (TGT-40689)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
