---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 4395caa7e40717c59067eaedff5e53776768eda9
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 92%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Eliminación del atributo de público del explorador de iPad e iPhone (30 de abril de 2024)

| Eliminación | Detalles |
|--- |--- |
| [!DNL iPad] y [!DNL iPhone] se van a eliminar del [atributo de explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) que se utiliza para crear públicos.<p>Fecha de eliminación:<P>Martes, 30 de abril de 2024 | [!DNL Adobe Target] le permite [segmentar en función de varios atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que utilizan un [explorador específico u opciones del explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) cuando visitan su página.<P><B>A partir del 30 de abril de 2024, iPad e iPhone se eliminarán de la lista desplegable de tipos de [!UICONTROL explorador] disponibles al crear categorías para públicos.</b><P>Audiencias integradas creadas con [!DNL Target] Las interfaces de usuario, como &quot;Explorador: iPad&quot; y &quot;Explorador: iPhone&quot;, se moverán automáticamente a la nueva definición de audiencia.<p>Para ver ejemplos de configuraciones alternativas que deben cambiarse manualmente, consulte [Obsolescencia de iPad y iPhone a partir del atributo de audiencia del explorador (30 de abril de 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

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

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| [Cambios de la documentación](/help/main/r-release-notes/doc-change.md) | Vea información detallada sobre las actualizaciones que se realizaron en esta guía y que no se incluyen en estas notas de la versión. |
| [Notas de la versión para versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium. |
| [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es){target=_blank} | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud. |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
