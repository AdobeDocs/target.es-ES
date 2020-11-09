---
keywords: reports;auto-target;auto target;AT;report
description: Información sobre cómo interpretar el informe Resumen de Destinatario automático en Adobe Target.
title: Informe Resumen de segmentación automática
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 57%

---


# ![Informe Resumen de Destinatario automático de PREMIUM](/help/assets/premium.png){#auto-target-summary-report}

Information about how to interpret the [!UICONTROL Auto-Target Summary] reports in [!DNL Adobe Target].

>[!NOTE]
>
>La [!UICONTROL segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una licencia de [Target Premium](/help/c-intro/intro.md#premium).

Para mostrar los informes Resumen [!UICONTROL de Destinatario] automático:

1. En la página [!UICONTROL Actividades] , haga clic en la actividad de Destinatario  automático que desee.

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], and [!UICONTROL Activity Source] drop-down lists.

1. Haga clic en la ficha [!UICONTROL Informes] y, a continuación, haga clic en el icono que desee:

   * Visualización de tabla. 
   * Visualización de gráfico
   * Segmentos automatizados
   * Atributos importantes

## Visualización de tabla. 

La ilustración siguiente muestra el aspecto que tiene un informe de resumen típico en la Vista [!UICONTROL de] tabla al ver un informe de actividad de Destinatario  automático:

![Informe de vista de tabla de Destinatario automático](/help/c-reports/assets/at-table-view.png)

Some tips and considerations as you interpret your [!UICONTROL Auto-Target] reports:

* Las distintas filas de la tabla le ayudan a comprender el rendimiento de la actividad.

   * Las dos filas superiores de la tabla en la página de informes muestran los resultados de una prueba A/B entre los visitantes que fueron asignados al control (es decir, experiencias servidas al azar) y los visitantes que fueron asignados al algoritmo de personalización. Esta información se puede usar para medir cómo se realizó el algoritmo de personalización en comparación con el control servido al azar.
   * Las filas restantes muestran resultados de nivel de experiencia. Para cada experiencia, hay una comparación entre la respuesta promedio de los visitantes a quienes se les mostró esa experiencia como un control servido aleatoriamente, y la respuesta promedio de los visitantes a quienes se les mostró la experiencia usando el algoritmo de personalización.

* El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo.

   * Debido a que el modelo se construye por experiencia, es posible ver un modelo para algunas experiencias con un cheque verde y otras con un icono de reloj.
   * En este caso, para aumentar la velocidad de la actividad con modelos creados para todas las experiencias, se envía tráfico adicional a las experiencias con modelos no construidos.
   * Debe haber al menos dos experiencias con modelos integrados (marca de verificación verde) para que comience la personalización.

* Comparing the conversion rate of experience A with that of experience B is not the right comparison in [!UICONTROL Auto-Target]. La pregunta es si la experiencia A rinde mejor cuando se sirve de una manera inteligente en lugar de aleatoria (en otras palabras, frente al control). Los profesionales del marketing también deben tener precaución al interpretar los aumentos de las experiencias individuales porque el algoritmo de personalización está intentando optimizar la métrica del éxito sobre toda la actividad, no sobre cada experiencia individual.
* Las experiencias con el alza más elevada se pueden considerar como las de mayor diferenciación dentro de la población. Es decir, el algoritmo ha encontrado la experiencia que más gusta a un segmento.
* Las distintas columnas de la tabla muestran el número de visitas, la tasa de conversión, el alza promedio y el nivel de confianza, y la confianza. Para obtener más información, consulte [Promedio de alza, límites de alza e intervalo de confianza](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Visualización de gráfico

La ilustración siguiente muestra el aspecto que tiene un informe de resumen típico en la Vista [!UICONTROL de] gráficos al ver un informe de actividad de Destinatario  automático:

![Informe de vista de gráficos de Destinatario automático](/help/c-reports/assets/at-graph-view.png)

Como se muestra a continuación, puede utilizar las dos listas desplegables para elegir las métricas deseadas, la metodología de recuento y mucho más. Consulte Información general sobre la configuración [de informes](/help/c-reports/c-report-settings/report-settings.md) para obtener más información:

![Informe de vista de gráficos de Destinatario automático](/help/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Haga clic en el icono Segmentos  automatizados. Este informe muestra cómo los diferentes visitantes responden de manera diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

![Icono de segmentos automatizados](/help/c-reports/assets/icon-automated-sements.png)

Para obtener más información, consulte el informe [Segmentos](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatizados.

## Atributos importantes

Haga clic en el icono Atributos  importantes. Este informe muestra cómo, en diferentes actividades, los diferentes atributos son más (o menos) importantes para la forma en que el modelo decide personalizar. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

![Icono de atributos importantes](/help/c-reports/assets/icon-important-attributes.png)

Para obtener más información, consulte el informe [Atributos](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importantes.
