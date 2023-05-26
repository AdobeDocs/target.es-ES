---
keywords: informes;bloquear dirección ip;bloquear visitante de dirección ip;descargar informes;csv;informes
description: Aprenda a utilizar las funciones de creación de informes en Adobe [!DNL Target] para examinar el rendimiento de sus actividades. Tome mejores decisiones según sus datos para aumentar el retorno de la inversión.
title: ¿Cómo veo los informes?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 63%

---

# Informes

Los informes proporcionan información sobre el progreso y los resultados de su [!DNL Adobe Target] actividades que le ayudan a tomar decisiones basadas en sus datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una actividad, mostrar qué experiencia de oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes.

## Mostrar un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Actividades]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Fuente de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Fuente de la actividad].

   Por ejemplo, podría seleccionar [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] en la lista desplegable [!UICONTROL Tipo] y elegir [!UICONTROL Activo] en la lista desplegable [!UICONTROL Estado] para mostrar solo las pruebas A/B y actividades de Segmentación de experiencias que tengan este estado.

   En la ilustración siguiente vemos la lista desplegable [!UICONTROL Tipo] con dos tipos marcados:  [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias]. Tenga en cuenta que los tres tipos de pruebas A/B (Manual, [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) están seleccionados de forma predeterminada. Puede anular la selección de uno o más tipos según sea necesario.

   ![Filtrar informes por tipo](/help/main/c-reports/assets/report_filters-new.png)

1. Haga clic en la pestaña **[!UICONTROL Informes]**.

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

   * [!UICONTROL Exportar informes a CSV]
   * [!UICONTROL Exportar detalles del pedido a un archivo .csv]

1. (Opcional) Haga clic en los iconos **[!UICONTROL Visualización de tabla]** y **[!UICONTROL Visualización de gráfico]** para cambiar entre los formatos de los informes.

   ![Iconos de vista de tabla y gráfico](/help/main/c-reports/assets/table-and-graph-icons.png)

   Según el tipo de informe seleccionado, otras vistas e informes podrían estar disponibles:

   | Tipo de informe | Ver |
   | --- | --- |
   | [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Haga clic en **[!UICONTROL Segmentos automatizados]** o **[!UICONTROL Atributos importantes]** iconos.<ul><li>El [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>El [Informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Además de las [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md), puede hacer clic en **[!UICONTROL Segmentos automatizados]** o **[!UICONTROL Atributos importantes]** iconos.<ul><li>El [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>El [Informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) Muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Prueba multivariada](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Además de las [Informe Rendimiento de las experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), puede hacer clic en [Contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) para que el informe muestre la contribución por ubicación. |

## Información adicional para tipos de actividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretación de informes de asignación automática](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interpretación de los resultados de un [!UICONTROL Asignación automática] actividad A/B mediante el examen de indicadores importantes, incluidos el alza y la confianza, en la [!DNL Target] IU. |
| [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Información sobre el informe [!UICONTROL Resumen] para las actividades de AT. Para obtener más información, consulte [Informe Resumen de segmentación automática](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalización automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos informes de [!UICONTROL Resumen de personalización automatizada] para actividades AP: informe de [!UICONTROL Nivel de actividad] e informe de [!UICONTROL Nivel de oferta]. Para obtener más información, consulte [Informes de resumen de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Rendimiento de las experiencias] y [!UICONTROL Contribución de ubicación]. Para obtener más información, consulte [Informe de rendimiento de las experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como fuente de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics]como origen de informes para [!DNL Target]. A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |

## Bloquear datos de informes de direcciones IP especificadas

Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Esto resulta útil, por ejemplo, para bloquear los datos de informes de los visitantes internos.

[Póngase en contacto con ClientCare para configurar filtros IP. ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Este filtrado no se aplica al usar  [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.
