---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e15709ac2a34a96dbc632c71f400c2575d74cf4
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 75%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.9.4 (del 2 al 4 de octubre de 2023)

Esta versión está disponible según la siguiente programación escalonada:

* **2 de octubre**: región de Europa, Oriente Medio y África (EMEA)
* **3 de octubre**: región de América
* **4 de octubre**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| [!UICONTROL Actividades] Actualización de IU<P>y<P>[!UICONTROL Fuentes] Actualización de IU | Como parte de [!DNL Adobe Target] esfuerzo continuo del equipo de para mejorar la experiencia del usuario de [!DNL Target] usuarios, esta versión actualiza el [!UICONTROL Actividades] y [!DNL Recommendations] [!UICONTROL Fuentes] páginas en la [!DNL Target] IU. Esta actualización unifica y estandariza los patrones de diseño que anteriormente eran incoherentes, a la vez que añade nuevas mejoras.<P>Para obtener más información, consulte [Actividades](/help/main/c-activities/activities.md) y [Fuentes](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] modelo de implementación | El *Patrón de implementación de Recommendations con at.js* Los artículos de le ayudan a comprender y crear sus [!DNL Adobe Target Recommendations] al usar la biblioteca JavaScript at.js.<P>Para obtener información general sobre los patrones de Target, consulte [Información general sobre patrones de implementación](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank} en el *Guía para desarrolladores de Adobe Target*.<P>El nuevo patrón de implementación de Recommendations se compone de los siguientes artículos:<ul><li>[Información general sobre el patrón de implementación de Recommendations con at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[Inicializar SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[Configuración de la recopilación de datos](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[Procesar experiencias](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=en){target=_blank}</li><li>[Notificar [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=en){target=_blank}</li></ul></ul> |

* Añadido [!UICONTROL Compositor de experiencias visuales] Mejoras de (VEC) para marcos dinámicos. (TGT-44064)
* Se ha corregido un problema que provocaba que la fecha seleccionada en la `getViewInAnalyticsId` Solicitud de no actualización correcta. Esta corrección ayuda a volver a calcular el [!DNL Analytics] vínculo en creación de informes cuando se cambia la configuración del informe de intervalo de fechas y métricas. (TGT-46246)

## [!DNL Target] Standard/Premium 23.9.3 (18 de septiembre de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha mejorado el [!UICONTROL Compositor de experiencias visuales] (VEC) para admitir Lightning Web Components (Light DOM). (TGT-45422)
* Se ha corregido un problema que provocaba que las acciones del VEC se aplicaran en el orden incorrecto. En algunos casos, el VEC aplicaba algunas modificaciones de forma asíncrona y al añadir modificaciones adicionales a un elemento se producían errores si ese elemento se mostraba después de una acción [!UICONTROL Insertar]. También corrige la URL del VEC que ahora se actualiza al hacer clic en los vínculos de anclaje. (TGT-45983)
* Se ha corregido un problema con la función [!UICONTROL Superposición] del VEC, que ahora admite elementos en Shadow DOMs. (TGT-45202 y TGT-45262)
* Se ha corregido un problema que se producía cuando al abrir una página de aplicación de una sola página (SPA) en el VEC y, a continuación, ir al modo [!UICONTROL Examinar] las flechas Atrás y Adelante no funcionaban correctamente. (TGT-45956)
* Se ha corregido un problema que impedía que algunas páginas web se cargaran en el VEC. (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (12-14 de septiembre de 2023)

Esta versión está disponible según la siguiente programación escalonada:

* **12 de septiembre**: región de América
* **13 de septiembre**: región Asia-Pacífico (APAC)
* **14 de septiembre**: región de Europa, Oriente Medio y África (EMEA)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha cambiado la API [!DNL Analytics] a la nueva versión 2.0 de API [!DNL Analytics]. (TGT-45345)
* Se han corregido problemas que afectaban a [!UICONTROL Automated Personalization] (AP) para algunos clientes, incluida la sincronización oportuna de la actividad en [!DNL Target] backend y ofrecer la experiencia esperada en los vínculos de vista previa. (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (6-11 de septiembre de 2023)

Esta versión está disponible según la siguiente programación escalonada:

* **6 de septiembre**: región de América
* **7 de septiembre**: región de Europa, Oriente Medio y África (EMEA)
* **11 de septiembre**: región Asia-Pacífico (APAC)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que generaba datos de creación de informes incoherentes en la IU de [!DNL Target] y de [!DNL Adobe Analytics] para las actividades de [!UICONTROL Asignación automática] que utilizan [!UICONTROL Analytics para Target] (A4T) como fuente de creación de informes. (TGT-46112)
* Se ha aumentado el tiempo de espera para las llamadas PUT a la API de entrega de Target a 15 segundos para evitar errores de tiempo de espera. (TGT-46091)
* Se ha corregido un problema que impedía que la dirección URL se actualizara de forma coherente al navegar por un sitio web de aplicación de una sola página (SPA). (TGT-45417)

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
