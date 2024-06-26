---
keywords: informes;bloquear dirección ip;bloquear visitante de dirección ip;descargar informes;csv;informes
description: Aprenda a utilizar las funciones de creación de informes en Adobe [!DNL Target] para examinar el rendimiento de sus actividades. Tome mejores decisiones según sus datos para aumentar el retorno de la inversión.
title: ¿Cómo veo los informes?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 41%

---

# Informes

Los informes proporcionan información sobre el progreso y los resultados de su [!DNL Adobe Target] actividades que le ayudan a tomar decisiones basadas en sus datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una actividad, mostrar qué experiencia de oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes.

## Mostrar un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Activities]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en la [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], y [!UICONTROL Activity Source] listas desplegables.

   Por ejemplo, puede seleccionar [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] desde el [!UICONTROL Type] lista desplegable y [!UICONTROL Live] desde el [!UICONTROL Status] lista desplegable para mostrar solo las pruebas A/B y las actividades de segmentación de experiencias que están en estado activo.

   La siguiente ilustración muestra el [!UICONTROL Type] lista desplegable con dos tipos seleccionados: [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting]. Tenga en cuenta que los tres tipos de pruebas A/B (Manual, [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) están seleccionados de forma predeterminada. Puede anular la selección de uno o más tipos según sea necesario.

   ![Filtrar informes por tipo](/help/main/c-reports/assets/report_filters-new.png)

1. Haga clic en **[!UICONTROL Reports]** pestaña.

   En todos los informes se incluye una leyenda para ayudarle a entender el informe.

   ![Leyenda del informe](/help/main/c-reports/assets/report_menu_bar-new.png)

   La leyenda muestra la siguiente información:

   * El estado de la actividad, incluido el intervalo de fechas en que se ejecutó.
   * El [experiencia ganadora prevista](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (si está disponible).

   >[!NOTE]
   >
   >Los resultados de las experiencias aparecen después de que por lo menos un visitante haya visto la experiencia.

1. (Opcional) [Configure el informe](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) como desee.
1. (Opcional) [Descargue el informe en formato CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para su análisis con Excel y otras herramientas.

   Las opciones disponibles son las siguientes:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Opcional) Haga clic en **[!UICONTROL Table View]** y **[!UICONTROL Graph View]** iconos para cambiar entre formatos de informes.

   ![Iconos de vista de tabla y gráfico](/help/main/c-reports/assets/table-and-graph-icons.png)

   Según el tipo de informe seleccionado, otras vistas e informes podrían estar disponibles:

   | Tipo de informe | Ver |
   | --- | --- |
   | [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Haga clic en **[!UICONTROL Automated Segments]** o **[!UICONTROL Important Attributes]** iconos.<ul><li>El [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>El [Informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Además de las [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md), puede hacer clic en **[!UICONTROL Automated Segments]** o **[!UICONTROL Important Attributes]** iconos.<ul><li>El [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>El [Informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) Muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Prueba multivariada](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Además de las [Informe Rendimiento de las experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), puede hacer clic en [Contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) para que el informe muestre la contribución por ubicación. |

## Información adicional para tipos de actividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretación de informes de asignación automática](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interpretación de los resultados de un [!UICONTROL Auto-Allocate] actividad A/B mediante el examen de indicadores importantes, incluidos el alza y la confianza, en la [!DNL Target] IU. |
| [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Información acerca de [!UICONTROL Summary] Informe de actividades de AT. Para obtener más información, consulte [Informe Resumen de segmentación automática](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Información sobre los dos [!UICONTROL Personalization Insights] Informes de actividades de AT y AP: [!UICONTROL Automated Segments] informe y [!UICONTROL Important Attributes] informe. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalización automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos [!UICONTROL Automated Personalization Summary] Informes de actividades AP: [!UICONTROL Activity Level] informe y [!UICONTROL Offer Level] informe. Para obtener más información, consulte [Informes de resumen de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Información sobre los dos [!UICONTROL Personalization Insights] Informes de actividades de AT y AP: [!UICONTROL Automated Segments] informe y [!UICONTROL Important Attributes] informe. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Experience Performance] informe y [!UICONTROL Location Contribution] informe. Para obtener más información, consulte [Informe de rendimiento de las experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como fuente de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics]como origen de informes para [!DNL Target]. A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Información sobre la integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} y [!DNL Target] que proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización. |

## Bloquear datos de informes de direcciones IP especificadas

Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Esto resulta útil, por ejemplo, para bloquear los datos de informes de los visitantes internos.

[Contactar con Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar filtros IP. Este filtrado no se aplica al utilizar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.
