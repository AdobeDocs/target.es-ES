---
keywords: informes;segmentación automática;segmentación automática;AT;informe
description: Obtenga información sobre cómo interpretar el informe Resumen de segmentación automática en Adobe Target. Puede cambiar a los informes Segmentos automatizados y Atributos importantes desde este informe.
title: ¿Cómo utilizo el informe Resumen de segmentación automática?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 52%

---

# Informe Resumen de segmentación automática

Información sobre cómo interpretar los informes de [!UICONTROL Auto-Target Summary] en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).

Para mostrar los informes de [!UICONTROL Auto-Target Summary]:

1. En la página [!UICONTROL Activities], haga clic en la actividad [!UICONTROL Auto-Target] que desee.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] y [!UICONTROL Activity Source].

1. Haga clic en la ficha [!UICONTROL Reports] y, a continuación, haga clic en el icono deseado:

   * Visualización de tabla. 
   * Visualización de gráfico
   * Segmentos automatizados
   * Atributos importantes

## Visualización de tabla. 

La siguiente ilustración muestra el aspecto habitual de un informe de resumen en [!UICONTROL Table View] cuando se visualiza el informe de una actividad [!UICONTROL Auto-Target]:

![Informe de vista de tabla de segmentación automática](/help/main/c-reports/assets/at-table-view.png)

Algunas sugerencias y consideraciones al interpretar sus informes de [!UICONTROL Auto-Target]:

* Las distintas filas de la tabla le ayudan a comprender el rendimiento de la actividad.

   * Las dos filas superiores de la tabla en la página de informes muestran los resultados de una prueba A/B entre los visitantes que fueron asignados al control (es decir, experiencias servidas al azar) y los visitantes que fueron asignados al algoritmo de personalización. Esta información se puede usar para medir cómo se realizó el algoritmo de personalización en comparación con el control servido al azar.
   * Las filas restantes muestran resultados de nivel de experiencia. Para cada experiencia, hay una comparación entre la respuesta promedio de los visitantes a quienes se les mostró esa experiencia como un control servido aleatoriamente, y la respuesta promedio de los visitantes a quienes se les mostró la experiencia usando el algoritmo de personalización.

* El icono de verificación verde junto a cada experiencia en el informe indica que para dicha experiencia se ha generado un modelo personalizado de aprendizaje automático. El icono del reloj indica que no se ha servido tráfico suficiente para crear el modelo.

   * Debido a que el modelo se construye por experiencia, es posible ver un modelo para algunas experiencias con un cheque verde y otras con un icono de reloj.
   * En este caso, para aumentar la velocidad de la actividad con modelos creados para todas las experiencias, se envía tráfico adicional a las experiencias con modelos no construidos.
   * Debe haber al menos dos experiencias con modelos integrados (marca de verificación verde) para que comience la personalización.

* Comparar la tasa de conversión de la experiencia A con la de la experiencia B no es la comparación correcta en [!UICONTROL Auto-Target]. La pregunta es si la experiencia A rinde mejor cuando se sirve de una manera inteligente en lugar de aleatoria (en otras palabras, frente al control). Los profesionales del marketing también deben tener precaución al interpretar los aumentos de las experiencias individuales porque el algoritmo de personalización está intentando optimizar la métrica del éxito sobre toda la actividad, no sobre cada experiencia individual.
* Las experiencias con el alza más elevada se pueden considerar como las de mayor diferenciación dentro de la población. Es decir, el algoritmo ha encontrado la experiencia que más gusta a un segmento.
* Las distintas columnas de la tabla muestran el número de visitas, la tasa de conversión, el alza promedio y el nivel de confianza, así como la confianza. Para obtener más información, consulte [Cálculos estadísticos en Pruebas A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Visualización de gráfico

La siguiente ilustración muestra el aspecto habitual de un informe de resumen en [!UICONTROL Graph View] cuando se visualiza el informe de una actividad [!UICONTROL Auto-Target]:

![Informe de vista de gráfico de segmentación automática](/help/main/c-reports/assets/at-graph-view.png)

Como se muestra a continuación, puede utilizar las dos listas desplegables para elegir las métricas deseadas, la metodología de contabilización y más. Consulte [Resumen de configuración de informes](/help/main/c-reports/c-report-settings/report-settings.md) para obtener más información:

![Informe de vista de gráfico de segmentación automática](/help/main/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Haga clic en el icono [!UICONTROL Automated Segments]. Este informe muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

![Icono de segmentos automatizados](/help/main/c-reports/assets/icon-automated-sements.png)

Para obtener más información, consulte [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Haga clic en el icono [!UICONTROL Important Attributes]. Este informe muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

![Icono de atributos importantes](/help/main/c-reports/assets/icon-important-attributes.png)

Para obtener más información, consulte [Informe sobre atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
