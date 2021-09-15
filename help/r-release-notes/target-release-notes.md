---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 41%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 14 de septiembre de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.9.1 (14 de septiembre de 2021)

En esta versión de mantenimiento se incluyen las siguientes mejoras, correcciones y cambios.

* Se han corregido problemas que evitaban que los clientes iniciaran sesión en el [!UICONTROL Compositor de experiencias visuales] (VEC) debido a las nuevas políticas de seguridad para cookies de terceros en algunos exploradores web. Este problema se trató en &quot;Páginas que no se cargan en el Compositor de experiencias visuales (VEC) o el Compositor de experiencias mejorado (EEC) al usar Google Chrome versión 80+&quot; en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Se ha corregido un problema que provocaba que los nombres de oferta en el VEC mostraran la ruta de la oferta en lugar del nombre descriptivo de la oferta. (TGT-41300)
* Los nombres de experiencia ahora se reflejan en [!DNL Analysis Workspace] para actividades A4T (TGT-38674)
* Se ha corregido un problema en [!DNL Recommendations] que producía cambios erróneos en el ID de entidad en una promoción de una actividad duplicada en la actividad original. (TGT-41482)
* Se ha corregido un problema que impedía que el botón &quot;Editar criterios&quot; se mostrara correctamente en la página [!UICONTROL Experiencias] de las actividades [!DNL Recommendations] del VEC. (TGT-39512)
* Se ha corregido un problema que impedía la sincronización de actividades cuando se duplicaban y copiaban en un espacio de trabajo de prueba. (TGT-40686)
* Se ha corregido un problema que impedía realizar modificaciones en un selector con [fragmentos de experiencia](/help/c-experiences/c-manage-content/aem-experience-fragments.md) al usar &quot;[!UICONTROL Insertar después]&quot; en el VEC. (TGT-41802)
* Se ha corregido un problema que impedía que el contenido JSON vacío en una oferta se enviara al servidor. [!DNL Target] ahora envía el objeto JSON aunque esté vacío. (TGT-41555)
* Se ha corregido un problema que provocaba que se abrieran los informes [!DNL Analytics] heredados en lugar de [!DNL Analysis Workspace] cuando los clientes hacían clic en &quot;[!UICONTROL Ver en Analytics]&quot; mientras visualizaban un informe. (TGT-41867)
* Se ha añadido una aclaración adicional al mensaje de interfaz de usuario mostrado cuando un cliente intenta seleccionar [!DNL Analytics] como fuente de informes (A4T) para una actividad [!UICONTROL Automated Personalization]. El mensaje indica que, &quot;[!DNL Target] es la única fuente admitida para las actividades [!UICONTROL Automated Personalization]&quot;. (TGT-41954)
* Se ha añadido una aclaración adicional al mensaje de error cuando los clientes intentan separar hosts con &quot;nueva línea&quot; en lugar de comas. (TGT-40671)
* Se ha corregido un problema que provocaba que las fechas &quot;[!UICONTROL Última actualización]&quot; de algunas actividades difieran de la IU en inglés para clientes españoles y japoneses (al ver la IU en español y japonés). (TGT-38980)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
