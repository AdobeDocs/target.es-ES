---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de Adobe Target, incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: ' Notas de la versión '
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---


# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen notas de la versión de API de Target, SDK, la biblioteca JavaScript (at.js) y otros cambios de plataforma, cuando corresponde.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: El 31 de marzo de 2021, ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Target Standard/Premium 21.1.1 (19 de enero de 2021). 

Esta versión de mantenimiento contiene las siguientes mejoras, correcciones y cambios.

Los números entre paréntesis son para uso interno de [!DNL Adobe].

* Se ha añadido una advertencia al seleccionar una métrica [!DNL Adobe Analytics] al usar [!UICONTROL Analytics como fuente de informes] (A4T) en una actividad de [!UICONTROL Segmentación automática]. [!UICONTROL Los modelos de ] segmentación automática están optimizados para funcionar con métricas binarias (basadas en conversión). La selección de una métrica continua, como los ingresos, puede tener resultados subóptimos y los informes de [!UICONTROL Perspectivas de personalización] pueden no ser precisos. (TGT-38926)
* Se ha agregado un icono de estado en el informe [!UICONTROL Resumen de segmentación automática] para las actividades de [!UICONTROL Segmentación automática] que utilizan A4T. El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo. (TGT-38925)
* Los informes [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes] para actividades de [!UICONTROL Segmentación automática] que utilizan métricas de conversión de A4T y [!DNL Analytics] se generan y tienen el mismo aspecto que al usar [!DNL Target] como fuente de informes. (TGT-38931)
* Se ha agregado una opción de filtrado de entorno a la lista [!UICONTROL Recommendations] [!UICONTROL Colecciones]. (TGT-38353)
* Se ha corregido un problema que provocaba que se mostrara un recuento incorrecto del producto en las colecciones [!UICONTROL Recommendations]. (TGT-39162)
* Se ha agregado un filtro [!UICONTROL Última actualización] a [!UICONTROL Recomendaciones] [!UICONTROL Búsqueda en el catálogo]. (TGT-38340)
* Se ha corregido un problema en [!UICONTROL Recommendations] que hacía que la página [!UICONTROL Crear secuencia] se bloqueara después de cambiar el sector vertical. (TGT-38160)
* Se ha corregido un problema que impedía guardar la actividad si Device Co-op estaba habilitado y el usuario cambiaba de [!DNL Target] como fuente de informes a [!DNL Analytics] (A4T). (TGT-38163)
* Se ha corregido un problema que impedía a los usuarios eliminar una audiencia de una oferta en una actividad de [!UICONTROL Personalización automatizada] (AP). (TGT-39058)
* Se ha corregido un problema que provocaba que se mostrara un lapso de tiempo incorrecto (fechas de inicio y finalización) en las tarjetas [!UICONTROL Información de audiencia] para algunos clientes. (TGT-39150)
* Se ha corregido un problema que impedía que algunos clientes vieran la lista de actividades en el [!UICONTROL espacio de trabajo predeterminado]. (TGT-38526)

## at.js 2.4.0 (14 de enero de 2021)

Esta versión de at.js es de mantenimiento e incluye las siguientes correcciones:

* Añade compatibilidad con el perfil unificado/ID de plataforma a customerIds de la API de envío.
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
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas de la versión de  [Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
