---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 96%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: martes, 22 de enero de 2024**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Eliminación del atributo de público del explorador de iPad e iPhone (30 de abril de 2024)

| Eliminación | Detalles |
|--- |--- |
| [!DNL iPad] y [!DNL iPhone] se van a eliminar del [atributo de explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) que se utiliza para crear públicos.<p>Fecha de eliminación:<P>Martes, 30 de abril de 2024 | [!DNL Adobe Target] le permite [segmentar en función de varios atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que utilizan un [explorador específico u opciones del explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) cuando visitan su página.<P><B>A partir del 30 de abril de 2024, iPad e iPhone se eliminarán de la lista desplegable de tipos de [!UICONTROL explorador] disponibles al crear categorías para públicos.</b><P>Si tiene públicos destinados a iPads o iPhone que utilizan el atributo de [!UICONTROL Explorador], debe cambiar esta configuración antes del 30 de abril de 2024 para garantizar que estos públicos sigan funcionando según lo previsto.<p>Para ver ejemplos de configuraciones alternativas, consulte [Obsolescencia de iPad y iPhone a partir del atributo de audiencia del explorador (30 de abril de 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23, 24 y 25 de enero de 2024)

Esta versión está programada para los siguientes días:

* **22 de enero**: región de Europa, Oriente Medio y África (EMEA)
* **23 de enero**: región de Asia-Pacífico (APAC)
* **25 de enero**: región de América

Esta versión incluye las siguientes mejoras y correcciones:

* Las actividades de [!UICONTROL Analytics for Target] (A4T) con métricas de metas de ingresos no mostraban “Ingresos” como nombre de columna y la métrica de ingresos no se mostraba en formato ($) en la creación de informes. Se trataba de un problema estético que se ha corregido. (TGT-46995)
* Se ha corregido un problema que hacía que los intervalos de fecha de los informes no funcionaran correctamente. (TGT-47396)
* Se ha corregido un problema que provocaba que se mostrara un estado incorrecto en la página [!UICONTROL Todas las actividades] después de que los clientes activaran o desactivaran una actividad mediante el icono de [!UICONTROL Más acciones]. (TGT-47367)
* Se ha corregido un problema que provocaba que el informe [!UICONTROL Atributos importantes] no se mostrara para un único cliente. (TGT-47272)
* Se ha corregido un problema que provocaba que se mostrara un mensaje “Carga útil no válida” cuando un único cliente intentaba habilitar “Requerir autenticación”. (TGT-47195)
* Se han actualizado varias cadenas localizadas en la IU de [!DNL Target].

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
