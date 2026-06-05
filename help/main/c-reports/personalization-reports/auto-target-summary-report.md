---
keywords: informes;segmentación automática;segmentación automática;AT;informe
description: Obtenga información sobre cómo interpretar el informe Resumen de segmentación automática en Adobe Target. Puede cambiar a los informes Segmentos automatizados y Atributos importantes desde este informe.
title: ¿Cómo utilizo el informe Resumen de segmentación automática?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
TQID: https://experienceleague.adobe.com/de9ST0undYRSL-BMmwEhvbU7PsfHgYieNAWY-qsQ-Z8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 35%

---

# [!UICONTROL Informe Resumen de segmentación automática]

Información sobre cómo interpretar los informes [!UICONTROL Resumen de segmentación automática] en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Segmentación automática] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).

Para mostrar los informes de [!UICONTROL Resumen de segmentación automática]:

1. En la página [!UICONTROL Actividades], haga clic en la actividad [!UICONTROL Segmentación automática] que desee.

   Si tiene muchas actividades, haga clic en el icono Filtro (![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Source de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Source de actividades].

1. Haga clic en la ficha **[!UICONTROL Informes]** y luego haga clic en el icono que desee:

   * **[!UICONTROL Vista de tabla]** ( ![icono de Vista de tabla](/help/main/assets/icons/Table.svg) )
   * **[!UICONTROL Visualización de gráfico]** ( ![Icono de Visualización de gráfico](/help/main/assets/icons/GraphTrend.svg) )
   * **[!UICONTROL Segmentos automatizados]** ( ![Informe de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) )
   * [!UICONTROL Atributos importantes]** ( ![icono de Atributos importantes](/help/main/assets/icons/ViewList.svg) )

## Visualización de tabla.

Algunas sugerencias y consideraciones al interpretar sus informes de [!UICONTROL Segmentación automática]:

* Las distintas filas de la tabla le ayudan a comprender el rendimiento de la actividad.

   * Las dos filas principales de la tabla de la página de creación de informes muestran los resultados de una prueba A/B entre los visitantes asignados al control (es decir, experiencias servidas aleatoriamente) y los visitantes asignados al algoritmo de personalización. Esta información se puede utilizar para medir el rendimiento del algoritmo de personalización en comparación con el control servido de forma aleatoria.
   * Las filas restantes muestran resultados de nivel de experiencia. Para cada experiencia, hay una comparación entre la respuesta promedio de los visitantes a quienes se les mostró esa experiencia como un control servido aleatoriamente, y la respuesta promedio de los visitantes a quienes se les mostró la experiencia usando el algoritmo de personalización.

* El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo.

   * Debido a que el modelo se construye por experiencia, es posible ver un modelo para algunas experiencias con un cheque verde y otras con un icono de reloj.
   * En este caso, para aumentar la velocidad de la actividad con modelos creados para todas las experiencias, se envía tráfico adicional a las experiencias con modelos no construidos.
   * Debe haber al menos dos experiencias con modelos creados (marca de verificación verde) para que comience la personalización.

* Comparar la tasa de conversión de la experiencia A con la de la experiencia B no es la comparación correcta en [!UICONTROL Segmentación automática]. La pregunta es si la experiencia A rinde mejor cuando se sirve de una manera inteligente en lugar de aleatoria (en otras palabras, frente al control). Los profesionales del marketing también deben tener precaución al interpretar los aumentos de las experiencias individuales porque el algoritmo de personalización está intentando optimizar la métrica del éxito sobre toda la actividad, no sobre cada experiencia individual.
* Las experiencias con el alza más elevada se pueden considerar como las de mayor diferenciación dentro de la población. Es decir, el algoritmo ha encontrado un segmento que le gusta más esa experiencia en particular.
* Las distintas columnas de la tabla muestran el número de visitas, la tasa de conversión, el alza promedio y el nivel de confianza, así como la confianza. Para obtener más información, consulte [Cálculos estadísticos en Pruebas A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Visualización de gráfico

Utilice las dos listas desplegables para elegir las métricas deseadas, la metodología de recuento, etc. Consulte [Resumen de configuración de informes](/help/main/c-reports/c-report-settings/report-settings.md) para obtener más información:

## Segmentos automatizados

Este informe muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad.

Para obtener más información, consulte el [informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Este informe muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

Para obtener más información, consulte el [informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
