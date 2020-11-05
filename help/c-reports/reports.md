---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Los informes proporcionan información sobre el rendimiento de las actividades de Adobe Target
title: Informes
feature: reports
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 66%

---


# Informes{#reports}

Reports provide information about the progress and results of your [!DNL Adobe Target] activities that help you make decisions based on your data. Los datos de los informes pueden ayudarle a decidir cuándo finalizar una actividad, mostrar qué experiencia de oferta es la ganadora y proporcionar perspectivas o conocimientos que necesita para determinar las siguientes acciones.

## Mostrar un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Actividades]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Fuente de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Fuente de la actividad].

   Por ejemplo, podría seleccionar [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] en la lista desplegable [!UICONTROL Tipo] y elegir [!UICONTROL Activo] en la lista desplegable [!UICONTROL Estado] para mostrar solo las pruebas A/B y actividades de Segmentación de experiencias que tengan este estado.

   En la ilustración siguiente vemos la lista desplegable [!UICONTROL Tipo] con dos tipos marcados:  [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting]. Tenga en cuenta que los tres tipos de pruebas A/B (Manual, [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md)) están seleccionados de forma predeterminada. Puede anular la selección de uno o más tipos según sea necesario.

   ![Filtrar informes por tipo](/help/c-reports/assets/report_filters-new.png)

1. Haga clic en la pestaña **[!UICONTROL Informes]**.

   En todos los informes se incluye una leyenda para ayudarle a entender el informe.

   ![Leyenda del informe](/help/c-reports/assets/report_menu_bar-new.png)

   La leyenda muestra la siguiente información:

   * El estado de la actividad, incluido el intervalo de fechas en que se ejecutó.
   * The [projected winning experience](/help/c-activities/automated-traffic-allocation/determine-winner.md) (if available).

   >[!NOTE]
   >
   >Los resultados de las experiencias aparecen después de que por lo menos un visitante haya visto la experiencia.

1. (Opcional) [Configure el informe](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) como desee.
1. (Opcional) [Descargue el informe en formato CSV](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) para su análisis con Excel y otras herramientas.

   Las opciones disponibles son las siguientes:

   * [!UICONTROL Exportar informes a CSV]
   * [!UICONTROL Exportar detalles del pedido a un archivo .csv]

1. (Opcional) Haga clic en los iconos **[!UICONTROL Visualización de tabla]** y **[!UICONTROL Visualización de gráfico]** para cambiar entre los formatos de los informes.

   ![Iconos de vista de tabla y gráfico](/help/c-reports/assets/table-and-graph-icons.png)

   Según el tipo de informe seleccionado, podrían estar disponibles otras vistas e informes:

   | Tipo de informe | Ver |
   | --- | --- |
   | [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) | Haga clic en los iconos **[!UICONTROL Segmentos]** automatizados o Atributos **** importantes.<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) shows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Además de los informes [Resumen de](/help/c-reports/reports-ap.md)Automated Personalization, puede hacer clic en los iconos Segmentos **** automatizados o Atributos **** importantes.<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Además del informe [Rendimiento de la](/help/c-reports/experience-performance-report.md)experiencia, puede hacer clic en el icono Contribución [de](/help/c-reports/location-contribution-report.md) ubicación para cambiar el informe y mostrar la contribución por ubicación. |

## Additional reporting information for specific activity types {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar informes de asignación automática](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Interprete los resultados de una actividad A/B de asignación [!UICONTROL automática] examinando indicadores importantes, incluidos el alza y la confianza, en la [!DNL Target] interfaz de usuario. |
| [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) | Información sobre el informe [!UICONTROL Resumen] para las actividades de AT. Para obtener más información, consulte [Informe Resumen de segmentación automática](/help/c-reports/auto-target-summary-report.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos informes de [!UICONTROL Resumen de personalización automatizada] para actividades AP: informe de [!UICONTROL Nivel de actividad] e informe de [!UICONTROL Nivel de oferta]. Para obtener más información, consulte [Informes de resumen de Personalización automatizada](/help/c-reports/reports-ap.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Rendimiento de las experiencias] y [!UICONTROL Contribución de ubicación]. Para obtener más información, consulte [Informe de rendimiento de las experiencias](/help/c-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como fuente de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics]como origen de informes para [!DNL Target]. A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Bloquear datos de sistema de informes de direcciones IP especificadas

Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Esto resulta útil, por ejemplo, para bloquear datos de sistema de informes de sus visitantes internos.

[Póngase en contacto con ClientCare para configurar filtros IP. ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Este filtrado no se aplica al usar  [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.
