---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8da8daf7da0cfe3e4936cb48b4c594c464708775
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.9.1 (del 6 al 11 de septiembre de 2023)

Esta versión está disponible según la siguiente programación escalonada:

* **6 de septiembre**: región de América
* **7 de septiembre**: región de Europa, Oriente Medio y África (EMEA)
* **11 de septiembre**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que generaba datos de informes incoherentes en la variable [!DNL Target] La interfaz de usuario y [!DNL Adobe Analytics] IU para [!UICONTROL Asignación automática] actividades que utilizan [!UICONTROL Analytics for Target] (A4T) como fuente de informes. (TGT-46112)
* Se ha aumentado el tiempo de espera para las llamadas del PUT a la API de envío de Target a 15 segundos para evitar errores de tiempo de espera. (TGT-46091)
* Se ha corregido un problema que mostraba el nombre de informe incorrecto al cambiar entre las variables [!UICONTROL Visualización en tabla] y el [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes] informes. (TGT-46040)
* Se ha mejorado la [!UICONTROL Compositor de experiencias visuales] (VEC) para admitir Lightning DOM (componentes web). (TGT-45422)
* Se ha corregido un problema que provocaba que las acciones del VEC se aplicaran en el orden incorrecto. En algunos casos, el VEC aplicaba algunas modificaciones de forma asíncrona y añadir modificaciones adicionales a un elemento provocaba errores si ese elemento se mostraba después de un [!UICONTROL Insertar] acción. (TGT-45983)
* SPA Se ha corregido un problema que se producía al abrir una página de aplicación de una sola página () en el VEC y, a continuación, ir al modo Examinar, provocaba que las flechas Atrás y Adelante no funcionaran correctamente. (TGT-45956)
* SPA Se ha corregido un problema que impedía que la dirección URL se actualizara de forma coherente al navegar por un sitio web de aplicación de una sola página (). (TGT-45417)

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
