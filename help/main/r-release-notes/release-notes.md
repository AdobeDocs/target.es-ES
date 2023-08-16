---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Adobe Target] Actualización de infraestructura de Edge planificada {#edge}

La actualización de la infraestructura de Edge planificada requiere IP o dominios adicionales para poder incluirlos en la lista de permitidos. Revise e incluya en la lista de permitidos los dominios NAT e IP para implementaciones de Edge 41-48. Las actualizaciones de la infraestructura comienzan el 9 de agosto de 2023.

Para obtener más información, consulte [Inclusión en la lista de permitidos de los nodos de Edge de Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=es){target=_blank} en la *Guía para desarrolladores de Adobe Target*.

## [!DNL Target] Estándar/Premium 23.8.1 (9 de agosto de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que, a veces, impedía que las actividades se sincronizaran correctamente, tal como se muestra en la columna [!UICONTROL Estado] de la página de la lista [!UICONTROL Actividad]. (TGT-46010 y TGT-44831)
* Se ha corregido un problema que, a veces, impedía que el vínculo “[!UICONTROL Ver en Analytics]” se mostrara en la página [!UICONTROL Informes] de actividades que utilizan [!UICONTROL Analytics for Target] (A4T) como fuente de informes. (TGT-45808)
* Se ha ajustado la presentación de los valores en las tablas para que se muestren como porcentajes en lugar de números con decimales. Por ejemplo, 8 % en lugar de .08. (TGT-45548)
* Se ha corregido un problema que impedía que los clientes usaran el enfoque del teclado para pasar al siguiente elemento de la página [!UICONTROL Objetivos y configuración] para las actividades [!UICONTROL Segmentación de experiencias] (XT). (TGT-44526)
* Se ha corregido un problema que provocaba una pérdida de enfoque del teclado después de abrir “[!UICONTROL Añadir públicos]” al crear una actividad. (TGT-44525)

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
