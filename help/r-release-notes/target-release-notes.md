---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de DNL Adobe Target.
title: Notas de evaluación de Adobe Target
feature: Release Notes
translation-type: tm+mt
source-git-commit: ec8aa3c2f6eca3c1f8002526cc2d2f15365f9671
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 19%

---


# Notas de la versión de Target (versión previa)

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización:12 de enero de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado. Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios.
>
>* **Adobe Experience Platform Web SDK**: El  [!UICONTROL Adobe Experience Platform Web ] SDK le permite interactuar con los distintos servicios de la red  [!DNL Experience Cloud] (incluido  [!DNL Target]) a través de Adobe Experience Edge Network. Si decide migrar a [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) en la *Guía del SDK web*. Consulte [información general de Destinatario](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) para obtener información específica de [!DNL Target].
   >
   >
* **at.js**: La biblioteca JavaScript de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página. Si decide migrar a at.js, consulte [Cómo funciona At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Aunque actualmente se admite mbox.js (hasta el 31 de marzo de 2021), no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. Al trasladar a todos los clientes al [!UICONTROL SDK web de Adobe Experience Platform] o at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta del soporte que espera de Adobe.

## Target Standard/Premium 21.1.1 (19 de enero de 2021). 

Esta versión de mantenimiento contiene las siguientes mejoras, correcciones y cambios.

Los números entre paréntesis son para uso interno de [!DNL Adobe].

* Se añadió una advertencia al seleccionar una métrica [!DNL Adobe Analytics] al utilizar [!UICONTROL Analytics como fuente de sistema de informes] (A4T) en una actividad [!UICONTROL Destinatario automático]. [!UICONTROL Los modelos de ] segmentación automática están optimizados para funcionar con métricas binarias (basadas en conversión). La selección de una métrica continua, como los ingresos, podría tener resultados subóptimos y los informes [!UICONTROL Perspectivas de personalización] podrían no ser precisos. (TGT-38926)
* Se añadió un icono de estado en el informe [!UICONTROL Resumen de Destinatario automático] para actividades [!UICONTROL Destinatario automático] que utilizan A4T. El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo. (TGT-38925)
* Los informes [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes] para actividades [!UICONTROL Destinatario automático] que utilizan métricas de conversión A4T y [!DNL Analytics] se generan y tienen el mismo aspecto que cuando se utiliza [!DNL Target] como fuente de sistema de informes. (TGT-38931)
* Se ha añadido una opción de filtrado de entornos en la lista [!UICONTROL Recommendations] [!UICONTROL Collections]. (TGT-38353)
* Se ha corregido un problema que hacía que se mostrara un recuento de productos incorrecto en las colecciones [!UICONTROL Recommendations]. (TGT-39162)
* Se ha añadido un filtro [!UICONTROL Última actualización] en [!UICONTROL Recommendations] [!UICONTROL Búsqueda en el catálogo]. (TGT-38340)
* Se corrigió un problema en [!UICONTROL Recommendations] que ocasionaba que la página [!UICONTROL Crear secuencia] se bloqueara después de cambiar la vertical del sector. (TGT-38160)
* Se ha corregido un problema que impedía guardar la actividad si Device Co-op estaba habilitado y el usuario cambiaba de [!DNL Target] como origen de sistema de informes a [!DNL Analytics] (A4T). (TGT-38163)
* Se ha corregido un problema que impedía a los usuarios quitar una audiencia de una oferta en una actividad [!UICONTROL Automated Personalization] (AP). (TGT-39058)
* Se corrigió un problema que ocasionaba que el intervalo de tiempo incorrecto (fechas de inicio y finalización) se mostrara en [!UICONTROL tarjetas de información de Audiencia] para algunos clientes. (TGT-39150)
* Se ha corregido un problema que impedía a algunos clientes ver la lista de actividades en el [!UICONTROL espacio de trabajo predeterminado]. (TGT-38526)
* Se han aumentado los límites de tamaño de las ofertas en la interfaz de usuario y la API [!DNL Target] a 1 MB. (TGT-38304)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
