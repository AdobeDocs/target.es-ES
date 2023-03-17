---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 59%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 14 de marzo de 2023**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Estándar/Premium 22.15.1 (8 y 9 de marzo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **8 de marzo**: región de las Américas
* **9 de marzo**: región de Europa, Oriente Medio y África (EMEA)
* **9 de marzo**: región Asia-Pacífico (APAC)

>[!NOTE]
>
>Debido a problemas que se han solucionado desde entonces, las métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]&quot; que se lanzó el 8 y 9 de marzo se ha eliminado temporalmente. Después de realizar más pruebas internas, la función se volverá a publicar en las próximas semanas.

Esta versión incluye las siguientes correcciones:

* Actualizaciones para la creación de componentes web personalizados con la variable [!UICONTROL Compositor de experiencias visuales] (VEC):

   * Se ha corregido la selección de elementos DOM de sombra en el VEC mejorando el proceso de creación para que no haya dependencia en el [!DNL Target] tipo de implementación al crear la raíz de sombra. Ahora, seleccionar los elementos DOM de sombra en el VEC debería funcionar para cualquier sitio web.
   * Se ha corregido un problema que impedía cargar elementos de HTML usando #Shadow DOM en el VEC. (TGT-35801)
   * Se corrigieron problemas de VEC con sitios web SPA que utilizan ShadowDOM. (TGT-43169)
   * Se ha corregido un problema con el objetivo de optimización: &quot;se hizo clic en un elemento&quot; que no identificaba correctamente el selector de CSS en ShadowDOM.

>[!NOTE]
>
>Para garantizar la entrega de los cambios creados en el VEC, asegúrese de que está utilizando un [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) con una versión buena a la 2.8.

**Problema conocido**: Rastreo de clics en un elemento raíz de la sombra al utilizar [!DNL Adobe Experience Platform Web SDK] no funciona correctamente. (TNT-47012)

## Versión 2.10.2 de at.js (7 de marzo de 2023)

* Se ha corregido un problema que provocaba que la función `trackEvent` devolviera siempre un error.

Para obtener información sobre todas las versiones de at.js, consulte [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
