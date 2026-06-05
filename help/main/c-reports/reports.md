---
keywords: informes;bloquear dirección ip;bloquear visitante de dirección ip;descargar informes;csv;informes
description: Optimice sus actividades dominando las características de los informes de  [!DNL Adobe Target] para mejorar la toma de decisiones y aumentar el retorno de la inversión.
title: ¿Cómo veo los informes?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
TQID: https://experienceleague.adobe.com/aRp-t-Z-Hfu5O01RqfxnKyHHL2suM2ahkteDQJShGQI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 947
ht-degree: 24%

---

# Informes

Los informes proporcionan información sobre el progreso y los resultados de las actividades [!DNL Adobe Target] que le ayudan a tomar decisiones basadas en los datos. Los datos del informe pueden ayudarle a decidir cuándo finalizar una actividad, mostrar qué experiencia u oferta es la ganadora y proporcionar las perspectivas o los datos que necesite para determinar las acciones siguientes.

## Mostrar un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Actividades]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede hacer clic en el icono Filtro ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Source de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas], [!UICONTROL Método de decisión] y [!UICONTROL Source de actividades].

   Por ejemplo, podría seleccionar [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] de la lista desplegable [!UICONTROL Tipo] y [!UICONTROL Activo] de la lista desplegable [!UICONTROL Estado] para mostrar solo las actividades de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] que están en estado activo.

   La siguiente ilustración muestra la lista desplegable [!UICONTROL Tipo] con dos tipos seleccionados: [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias]. Tenga en cuenta que los tres tipos de pruebas A/B (Manual, [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) están seleccionados de forma predeterminada. Puede anular la selección de uno o más tipos según sea necesario.

   ![Filtrar informes por tipo](/help/main/c-reports/assets/report-filters-refresh.png)

1. Haga clic en la actividad que quiera de la lista para mostrar su página [!UICONTROL Información general].

1. Haga clic en la ficha **[!UICONTROL Informes]** en el carril izquierdo.

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

   * [!UICONTROL Exportar informes a CSV]
   * [!UICONTROL Exportar detalles del pedido a un archivo .csv]

1. (Opcional) Haga clic en los iconos **[!UICONTROL Visualización de tabla]** ( ![Icono de Visualización de tabla](/help/main/assets/icons/Table.svg) ) y **[!UICONTROL Visualización de gráfico]** ( ![Icono de Visualización de gráfico](/help/main/assets/icons/GraphTrend.svg) ) para cambiar entre los formatos de los informes.

   Según el tipo de informe seleccionado, otras vistas e informes podrían estar disponibles:

   | Tipo de informe | Ver |
   | --- | --- |
   | [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Haga clic en los iconos **[!UICONTROL Segmentos automatizados]** ( ![Informe de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) o **[!UICONTROL Atributos importantes]** ( ![Icono de Atributos importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>El informe [[!UICONTROL Segmentos automatizados]](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad de [!UICONTROL Automated Personalization] o [!UICONTROL Segmentación automática]. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad.</li><li>El informe [[!UICONTROL Atributos importantes]](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Además de los [[!UICONTROL informes de resumen de Automated Personalization]](/help/main/c-reports/personalization-reports/reports-ap.md), puede hacer clic en los iconos **[!UICONTROL Segmentos automatizados]** ( ![Informe de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) o **[!UICONTROL Atributos importantes]** ( ![Icono de Atributos importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>El informe [[!UICONTROL Segmentos automatizados]](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad de [!UICONTROL Automated Personalization] o [!UICONTROL Segmentación automática]. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad.</li><li>El informe [[!UICONTROL Atributos importantes]](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.</li></ul> |
   | [[!UICONTROL Prueba multivariada]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Además del informe [[!UICONTROL Rendimiento de la experiencia]](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), puede hacer clic en el icono [[!UICONTROL Contribución de ubicación]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![icono de Contribución de ubicación](/help/main/assets/icons/LocationContribution.svg) ) para que el informe muestre la contribución por ubicación. |

## Información adicional para tipos de actividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [[!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar [!UICONTROL asignación automática] informes](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprete los resultados de una actividad A/B de [!UICONTROL asignación automática] examinando los indicadores importantes, incluidos el alza y la confianza, en la interfaz de usuario de [!DNL Target]. |
| [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Información sobre el informe [!UICONTROL Resumen] para actividades de AT. Para obtener más información, consulte [[!UICONTROL Informe] de resumen de segmentación automática](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Información sobre los dos informes de [!UICONTROL Personalization Insights] para actividades de AT y AP: [!UICONTROL Informe de segmentos automatizados] e informe de [!UICONTROL atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos informes de [!UICONTROL Resumen de Automated Personalization] para actividades AP: informe de [!UICONTROL Nivel de actividad] e informe de [!UICONTROL Nivel de oferta]. Para obtener más información, consulte [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Información sobre los dos informes de [!UICONTROL Personalization Insights] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Prueba multivariada]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Rendimiento de la experiencia] e [!UICONTROL Contribución de ubicación]. Para obtener más información, consulte [Informe de rendimiento de experiencias](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics] como Source de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics] como origen de informes para [!DNL Target] (A4T). A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Información sobre la integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} y [!DNL Target] que proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización. |

## Bloquear datos de informes de direcciones IP especificadas

Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Esta opción resulta útil, por ejemplo, para bloquear los datos de informes de los visitantes internos.

[Póngase en contacto con Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar filtros IP. Este filtrado no se aplica cuando se usa [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.
