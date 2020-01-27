---
keywords: reports;auto-target;auto target;AT
description: Información sobre la interpretación del informe Resumen de segmentación automática.
title: Informe Resumen de segmentación automática
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 3faba3d3158bed69ae5d756fb70c97d17110c1d8

---


# Informe Resumen de segmentación automática{#auto-target-summary-report}

Información sobre cómo interpretar los informes de resumen de segmentación automática.

Para mostrar los informes de resumen de segmentación automática:

1. En la página [!UICONTROL Actividades] , haga clic en la actividad de segmentación automática que desee.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables Tipo, Estado, Propiedad, Origen de informes, Compositor de experiencias, Tipo de métricas y Origen de actividad.

1. Haga clic en la pestaña [!UICONTROL Informes].

## Visualización de tabla. 

La siguiente ilustración muestra el aspecto que tiene un informe de resumen típico en la &quot;vista de tabla&quot; al usar la segmentación automática:

![Informe de vista de tabla de segmentación automática](/help/c-reports/assets/at-table-view.png)

Algunos consejos y consideraciones a medida que interpreta sus informes de segmentación automática:

* Las distintas filas de la tabla permiten conocer el rendimiento de la actividad.

   * Las dos filas superiores de la tabla en la página de informes muestran los resultados de una prueba A/B entre los visitantes que fueron asignados al control (es decir, experiencias servidas al azar) y los visitantes que fueron asignados al algoritmo de personalización. Esta información se puede usar para medir cómo se realizó el algoritmo de personalización en comparación con el control servido al azar.
   * Las filas restantes muestran resultados de nivel de experiencia. Para cada experiencia, hay una comparación entre la respuesta promedio de los visitantes a quienes se les mostró esa experiencia como un control servido aleatoriamente, y la respuesta promedio de los visitantes a quienes se les mostró la experiencia usando el algoritmo de personalización.

* El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo.

   * Debido a que el modelo se construye por experiencia, es posible ver un modelo para algunas experiencias con un cheque verde y otras con un icono de reloj.
   * En este caso, para aumentar la velocidad de la actividad con modelos creados para todas las experiencias, se envía tráfico adicional a las experiencias con modelos no construidos.
   * Debe haber al menos dos experiencias con modelos integrados (marca de verificación verde) para que comience la personalización.

* Comparar la tasa de conversión de la experiencia A con la de la experiencia B no es lo adecuado en la segmentación automática. La pregunta es si la experiencia A rinde mejor cuando se sirve de una manera inteligente en lugar de aleatoria (en otras palabras, frente al control). Los profesionales del marketing también deben tener precaución al interpretar los aumentos de las experiencias individuales porque el algoritmo de personalización está intentando optimizar la métrica del éxito sobre toda la actividad, no sobre cada experiencia individual.
* Las experiencias con el alza más elevada se pueden considerar como las de mayor diferenciación dentro de la población. Es decir, el algoritmo ha encontrado la experiencia que más gusta a un segmento.
* Las distintas columnas de la tabla muestran el número de visitas, la tasa de conversión, el alza promedio y el nivel de confianza, y la confianza. Para obtener más información, consulte [Promedio de alza, límites de alza e intervalo de confianza](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Visualización de gráfico

La siguiente ilustración muestra el aspecto que tiene un informe de resumen típico en la &quot;vista de gráfico&quot; al usar la segmentación automática:

![Informe de vista de gráfico de segmentación automática](/help/c-reports/assets/at-graph-view.png)

Como se muestra a continuación, puede utilizar las dos listas desplegables para elegir las métricas deseadas, la metodología de recuento y mucho más. Consulte Información general sobre la configuración [de informes](/help/c-reports/c-report-settings/report-settings.md) para obtener más información:

![Informe de vista de gráfico de segmentación automática](/help/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Haga clic en el icono Segmentos automatizados. Este informe muestra cómo los distintos visitantes responden de manera diferente a las ofertas o experiencias de su actividad de AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

![Icono de segmentos automatizados](/help/c-reports/assets/icon-automated-sements.png)

Para obtener más información, consulte el informe [Segmentos](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatizados.

## Atributos importantes

Haga clic en el icono Atributos importantes. Este informe muestra cómo, en diferentes actividades, los diferentes atributos son más (o menos) importantes para la forma en que el modelo decide personalizar. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

![Icono de atributos importantes](/help/c-reports/assets/icon-important-attributes.png)

Para obtener más información, consulte el informe [Atributos](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importantes.
