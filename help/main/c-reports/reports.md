---
keywords: informes;bloquear dirección ip;bloquear visitante de dirección ip;descargar informes;csv;informes
description: Optimice sus actividades dominando las características de los informes de  [!DNL Adobe Target] para mejorar la toma de decisiones y aumentar el retorno de la inversión.
title: ¿Cómo veo los informes?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: bd65cb9339dbe4b79d26c314cfb81d1fc7226fd2
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 26%

---

# Informes

Los informes proporcionan información sobre el progreso y los resultados de las actividades [!DNL Adobe Target] que le ayudan a tomar decisiones basadas en los datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una actividad, mostrar qué experiencia u oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes.

## Mostrar un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Activities]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede hacer clic en el icono Filtro ( ![icono Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Method] y [!UICONTROL Activity Source].

   Por ejemplo, podría seleccionar [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] de la lista desplegable [!UICONTROL Type] y [!UICONTROL Live] de la lista desplegable [!UICONTROL Status] para mostrar solamente las actividades [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] que están en estado activo.

   La siguiente ilustración muestra la lista desplegable [!UICONTROL Type] con dos tipos seleccionados: [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting]. Tenga en cuenta que los tres tipos de pruebas A/B (Manual, [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) están seleccionados de forma predeterminada. Puede anular la selección de uno o más tipos según sea necesario.

   ![Filtrar informes por tipo](/help/main/c-reports/assets/report-filters-refresh.png)

1. Haga clic en la actividad deseada de la lista para mostrar su página [!UICONTROL Overview].

1. Haga clic en la ficha **[!UICONTROL Reports]** en el carril izquierdo.

   ![Informe A/B](/help/main/c-reports/assets/reports-refresh.png)

   En todos los informes se incluye una leyenda para ayudarle a entender el informe.

   La leyenda muestra la siguiente información:

   * El estado de la actividad, incluido el intervalo de fechas en que se ejecutó.
   * La [experiencia ganadora prevista](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (si está disponible).

   >[!NOTE]
   >
   >Los resultados de las experiencias aparecen después de que por lo menos un visitante haya visto la experiencia.

1. (Opcional) [Configure el informe](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) haciendo clic en el icono Configuración de informe ( ![icono Configuración de informe](/help/main/assets/icons/Setting.svg) ).
1. (Opcional) Haga clic en el icono Descargar informes ( ![icono Descargar informes](/help/main/assets/icons/Download.svg) ) para [descargar el informe en formato CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para su análisis en Excel y otras herramientas.

   Las opciones disponibles son las siguientes:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Opcional) Haga clic en los iconos **[!UICONTROL Table View]** ( ![icono de Visualización de tabla](/help/main/assets/icons/Table.svg) ) y **[!UICONTROL Graph View]** ( ![icono de Visualización de gráfico](/help/main/assets/icons/GraphTrend.svg) ) para cambiar entre los formatos de los informes.

   Según el tipo de informe seleccionado, otras vistas e informes podrían estar disponibles:

   | Tipo de informe | Ver |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Haga clic en los iconos **[!UICONTROL Automated Segments]** ( ![Informe de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) o **[!UICONTROL Important Attributes]** ( ![Icono de atributos importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>El informe [[!UICONTROL Automated Segments]](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra de qué manera los distintos visitantes responden de manera diferente a las ofertas y experiencias de su actividad [!UICONTROL Automated Personalization] o [!UICONTROL Auto-Target]. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad.</li><li>El informe [[!UICONTROL Important Attributes]](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Además de los [[!UICONTROL Automated Personalization Summary] informes](/help/main/c-reports/personalization-reports/reports-ap.md), puede hacer clic en los iconos **[!UICONTROL Automated Segments]** ( ![Informe de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) o **[!UICONTROL Important Attributes]** ( ![Icono de atributos importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>El informe [[!UICONTROL Automated Segments]](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra de qué manera los distintos visitantes responden de manera diferente a las ofertas y experiencias de su actividad [!UICONTROL Automated Personalization] o [!UICONTROL Auto-Target]. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad.</li><li>El informe [[!UICONTROL Important Attributes]](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Además del informe [[!UICONTROL Experience Performance]](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), puede hacer clic en el icono [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![icono de Contribución de ubicación](/help/main/assets/icons/LocationContribution.svg) ) para que el informe muestre la contribución por ubicación. |

## Información adicional para tipos de actividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar [!UICONTROL Auto-Allocate] informes](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprete los resultados de una actividad A/B de [!UICONTROL Auto-Allocate] examinando los indicadores importantes, incluidos el alza y la confianza, en la interfaz de usuario de [!DNL Target]. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Información sobre el informe [!UICONTROL Summary] para actividades de AT. Para obtener más información, consulte [[!UICONTROL Auto-Target Summary] Informe](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Información sobre los dos informes [!UICONTROL Personalization Insights] para actividades AT y AP: informe [!UICONTROL Automated Segments] e informe [!UICONTROL Important Attributes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos informes [!UICONTROL Automated Personalization Summary] para actividades AP: informe [!UICONTROL Activity Level] e informe [!UICONTROL Offer Level]. Para obtener más información, consulte [Informes de resumen de Personalización automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Información sobre los dos informes [!UICONTROL Personalization Insights] para actividades AT y AP: informe [!UICONTROL Automated Segments] e informe [!UICONTROL Important Attributes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Experience Performance] y [!UICONTROL Location Contribution]. Para obtener más información, consulte [Informe de rendimiento de experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics] como Source de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics] como origen de informes para [!DNL Target] (A4T). A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Información sobre la integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/customer-journey-analytics){target=_blank} y [!DNL Target] que proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización. |

## Bloquear datos de informes de direcciones IP especificadas

Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Esta opción resulta útil, por ejemplo, para bloquear los datos de informes de los visitantes internos.

[Póngase en contacto con Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar filtros IP. Este filtrado no se aplica cuando se usa [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.
