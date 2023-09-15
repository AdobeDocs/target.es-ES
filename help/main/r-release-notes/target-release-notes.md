---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b0bdb7d5004af73c6dff8323266ea4c58972fd80
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 77%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 15 de septiembre de 2023**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.3 (18 de septiembre de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha mejorado la [!UICONTROL Compositor de experiencias visuales] (VEC) para admitir Lightning DOM (componentes web). (TGT-45422)
* Se ha corregido un problema que provocaba que las acciones del VEC se aplicaran en el orden incorrecto. En algunos casos, el VEC aplicaba algunas modificaciones de forma asíncrona y añadir modificaciones adicionales a un elemento provocaba errores si ese elemento se mostraba después de un [!UICONTROL Insertar] acción. (TGT-45983)
* Se ha corregido un problema con el VEC [!UICONTROL Superposición] función, que ahora admite elementos en DOM sombreados. (TGT-45202 y TGT-45262)
* SPA Se ha corregido un problema que se producía al abrir una página Aplicación de una sola página () en el VEC y, a continuación, ir a [!UICONTROL Examinar] El modo hacía que las flechas Atrás y Adelante no funcionaran correctamente. (TGT-45956)
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

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
