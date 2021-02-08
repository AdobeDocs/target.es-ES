---
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Adobe Target, incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la próxima versión?
feature: Release Notes
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 26%

---


# Notas de la versión de Target (versión previa)

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización:14 de enero de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
