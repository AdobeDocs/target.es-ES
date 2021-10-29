---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 89b995f20491fe0a51c91f8a1fe7e6b1ccc7f974
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 68%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 28 de octubre de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Versión 2.7.0 de at.js (28 de octubre de 2021)

Esta versión contiene la siguiente mejora:

* Se ha agregado compatibilidad con [Componentes web](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Esta versión de at.js es necesaria para crear y probar experiencias y ofertas personalizadas en elementos personalizados y en elementos dentro de elementos personalizados. Esta funcionalidad se incluye en la variable [!DNL Target Standard/Premium] Versión 21.10.5.

## [!DNL Target Standard/Premium] 21.10.5 (28 de octubre de 2021)

Esta versión de mantenimiento contiene las siguientes mejoras:

| Función | Detalles |
| --- | --- |
| [!UICONTROL Compositor de experiencias visuales] (VEC) | Se ha agregado compatibilidad con [Componentes web](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Las experiencias y ofertas personalizadas se pueden crear y probar en elementos personalizados y en elementos dentro de elementos personalizados.<br>Para obtener más información, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom). |

## [!DNL Target Standard/Premium] 21.10.4 (21 de octubre de 2021)

Esta versión de mantenimiento contiene las siguientes mejoras:

| Función | Detalles |
| --- | --- |
| Recommendations basado en el carro de compras | Se ha agregado una nueva familia de algoritmos para ofrecer recomendaciones basadas en el contenido del carro de compras del visitante.<br>Para obtener más información, consulte &quot;Basado en el carro de compras&quot; en [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) y &quot;Adiciones al carro de compras/Vistas del carro de compras/Páginas de cierre de compra&quot; y &quot;Excluir elementos que ya están en el carro de compras del visitante&quot; en [Planificar e implementar Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 de octubre de 2021)

En esta versión de mantenimiento se incluyen las siguientes mejoras, correcciones y cambios:

* Se han corregido problemas que evitaban que los clientes abran el panel [!UICONTROL A4T] en [!DNL Analysis Workspace] al hacer clic en el botón [!UICONTROL Ver en Analytics] en la creación de informes de actividad de [!DNL Target]. (TGT-42099, TGT-42100)
* Se ha corregido un problema que hacía que el botón [!UICONTROL Editar diseño] no se mostrase durante la edición de actividades de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) al utilizar el [!UICONTROL Compositor de experiencias basadas en formularios]. (TGT-41980)
* Se ha corregido un problema que impedía que la casilla de verificación [!UICONTROL Compatible] apareciese en la selección de criterios al crear una nueva actividad de [!UICONTROL Recommendations]. (TGT-42053)
* Se ha corregido un mensaje de error incorrecto que se mostraba al no poder seleccionar [!DNL Analytics] como fuente de creación de informes (A4T) debido a la falta de permisos de [!DNL Analytics]. (TGT-41954)
* Se han implementado varias correcciones de accesibilidad para mejorar la navegación mediante el teclado en la IU de [!DNL Target].

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
