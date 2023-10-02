---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 159cf7595878e0412f249a52dc979e0824c717eb
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 75%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 2 de octubre de 2023**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.4 (fecha por determinar)

Esta versión incluye las siguientes mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| [!UICONTROL Actividades] Actualización de IU<P>y<P>[!UICONTROL Fuentes] Actualización de IU | Como parte de [!DNL Adobe Target] esfuerzo continuo del equipo de para mejorar la experiencia del usuario de [!DNL Target] usuarios, esta versión actualiza el [!UICONTROL Actividades] y [!DNL Recommendations] [!UICONTROL Fuentes] páginas en la [!DNL Target] IU. Esta actualización unifica y estandariza los patrones de diseño que anteriormente eran incoherentes, a la vez que añade nuevas mejoras.<P>Para obtener más información, consulte [Actividades](/help/main/c-activities/activities.md) y [Fuentes](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] modelo de implementación | El *Patrón de implementación de Recommendations con at.js* Los artículos de le ayudan a comprender y crear sus [!DNL Adobe Target Recommendations] al usar la biblioteca JavaScript at.js.<P>Para obtener más información, consulte [Información general sobre el patrón de implementación de Recommendations con at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} en el *Guía para desarrolladores de Adobe Target*. |

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

## [!DNL Target] Standard/Premium 23.5.2 (fecha por determinar)

Esta versión incluye las siguientes mejoras y correcciones:

* Selección de criterios de optimización habilitada para [!DNL Adobe Analytics] métricas.
* Se habilitó la sincronización de audiencias externas mediante trabajos de Sling.
* Se ha corregido un problema en el cual los grupos de informes SC que contenían un carácter de punto en el nombre no eran compatibles.
* Funcionalidad habilitada para permitir que los clientes eliminen y editen audiencias integradas.

## [!DNL Target] Standard/Premium 23.5.3 (fecha por determinar)

Esta versión incluye las siguientes mejoras:

| Función | Detalles |
|--- |--- |
| [!UICONTROL Modo de control de calidad] para actividades de [!UICONTROL Automated Personalization] | [!DNL Adobe Target] [!UICONTROL Modo de control de calidad] ya está disponible para actividades de [!UICONTROL Automated Personalization], reemplazar la funcionalidad [!UICONTROL Previsualizar vínculos].<P>Para obtener más información, consulte [Control de calidad de las actividades.](/help/main/c-activities/c-activity-qa/activity-qa.md) |

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
