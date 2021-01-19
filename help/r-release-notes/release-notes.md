---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
feature: Release Notes
translation-type: tm+mt
source-git-commit: 2dce7bbe94f20ad6f6732dfc3abceb69058a1f75
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 36%

---


# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Destinatario, los SDK, la biblioteca de JavaScript (at.js) y otros cambios en la plataforma, cuando corresponde.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado. Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios.
>
>* **Adobe Experience Platform Web SDK**: El  [!UICONTROL Adobe Experience Platform Web ] SDK le permite interactuar con los distintos servicios de la red  [!DNL Experience Cloud] (incluido  [!DNL Target]) a través de Adobe Experience Edge Network. Si decide migrar a [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) en la *Guía del SDK web*.
   >
   >
* **at.js**: La biblioteca JavaScript de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página. Si decide migrar a at.js, consulte [Cómo funciona At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Aunque actualmente se admite mbox.js (hasta el 31 de marzo de 2021), no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. Al trasladar a todos los clientes al [!UICONTROL SDK web de Adobe Experience Platform] o at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta del soporte que espera de Adobe.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

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

## at.js 2.4.0 (14 de enero de 2021)

Esta versión de at.js es una versión de mantenimiento que incluye las siguientes correcciones:

* Añade la compatibilidad con ID de plataforma/perfil unificado en ID de cliente de API de envío.
* Corrige la inyección de etiquetas de estilo no válida.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas [ de la versión de ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)Experience Cloud. |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
