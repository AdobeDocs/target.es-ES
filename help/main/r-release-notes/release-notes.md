---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3d8da94a52046e70a89dc24d7923f743bee5c458
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.9.1 (versión escalonada del 13 al 15 de septiembre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **13 de septiembre**: región de Europa, Oriente Medio y África (EMEA)
* **14 de septiembre**: región de América
* **15 de septiembre**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha añadido una opción [!UICONTROL Dominio cruzado] al descargar at.js 2.10.0 (y versiones posteriores) para permitir o deshabilitar la configuración de cookies de terceros. (TGT-43674)
* Se han actualizado las notificaciones en la [!DNL Target] IU para informar a los clientes de si la importación de las fuentes [!DNL Recommendations] falla. (TGT-35811)
* Se ha solucionado un problema que provocaba que las [!UICONTROL Ofertas de decisión] no funcionaran correctamente dentro del [!UICONTROL Compositor de experiencias visuales] (VEC). (TGT-43866)
* Se ha corregido un problema que provocaba que se mostrara un mensaje de error al seleccionar el objetivo de conversión. [!UICONTROL Se ha hecho clic en un elemento] al crear una [!UICONTROL Prueba multivariada] (MVT). (TGT-43842)
* Se ha corregido un problema que impedía que la columna [!UICONTROL Impresiones] mostrara el archivo de informe CSV descargado para actividades de [!UICONTROL Automated Personalization] (AP). (TGT-43780)
* Se ha corregido un problema que impedía que los clientes editaran ofertas HTML/JSON después de duplicar experiencias al usar el [!UICONTROL Compositor de experiencias basadas en formularios]. (TGT-43633)
* Se ha corregido un problema que impedía que los clientes copiaran una actividad de [!UICONTROL Prueba A/B] de un espacio de trabajo no predeterminado a otro no predeterminado. (TGT-41910)
* Se ha corregido un problema para garantizar que los clientes puedan mostrar correctamente los usos de [!DNL Recommendations] objetos (diseños, criterios, colecciones, etc.) de [!UICONTROL Prueba A/B] y actividades de [!UICONTROL Segmentación de experiencias] (XT) que contienen recomendaciones y también eliminan objetos de criterios que ya no se utilizan de [!DNL Target] IU y [!DNL Recommendations] backend. (TGT-42331)
* Se ha corregido un problema que provocaba que apareciera una alerta de tiempo de espera de red en la IU de [!DNL Target] al recuperar parámetros. (TGT-43737)
* Se ha actualizado la IU para garantizar que se pueda acceder mediante el teclado a ciertas acciones de arrastrar y soltar. (TGT-42969)
* Se ha actualizado la IU para garantizar que las cadenas de texto estén correctamente localizadas.

## Versión 2.10.0 de at.js (13 de septiembre de 2022)

* Se ha añadido una opción [!UICONTROL Dominio cruzado] al descargar at.js 2.10.0 (y versiones posteriores) para permitir o deshabilitar la configuración de cookies de terceros. (TGT-43674)

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
