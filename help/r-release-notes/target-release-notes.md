---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7cb6baeb7ef9e9cf0efb76866a3eae8dfd38af34
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 67%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 18 de octubre de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.3 (19 de octubre de 2021)

En esta versión de mantenimiento se incluyen las siguientes mejoras, correcciones y cambios:

* Se han corregido problemas que evitaban que los clientes abrieran la variable [!UICONTROL A4T] panel en [!DNL Analysis Workspace] haciendo clic en el botón [!UICONTROL Ver en Analytics] botón [!DNL Target] informes de actividad. (TGT-42099, TGT-42100)
* Se ha corregido un problema que hacía que la variable [!UICONTROL Editar diseño] botón para no mostrarse durante la edición [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] Actividades (XT) utilizando el [!UICONTROL Compositor de experiencias basadas en formularios]. (TGT-41980)
* Se ha corregido un problema que impedía que la variable [!UICONTROL Compatible] casilla de verificación que aparece en la selección de criterios al crear un nuevo [!UICONTROL Recommendations] actividad. (TGT-42053)
* Se ha corregido un mensaje de error incorrecto que se mostraba al no poder seleccionar [!DNL Analytics] como fuente de informes (A4T) debido a la falta de [!DNL Analytics] permisos. (TGT-41954)
* Se han implementado varias correcciones de accesibilidad para mejorar la navegación mediante el teclado en el [!DNL Target] IU.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
