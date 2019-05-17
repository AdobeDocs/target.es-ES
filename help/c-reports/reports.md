---
description: Los informes proporcionan información sobre el rendimiento de sus actividades.
keywords: informes;bloquear dirección ip;bloquear visitante de dirección ip;descargar informes;csv
seo-description: Los informes proporcionan información sobre el rendimiento de sus actividades
seo-title: Informes
solution: Target
subtopic: Prueba multivariable
title: Informes
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Informes{#reports}

Los informes proporcionan información sobre el rendimiento de sus actividades.

>[!NOTE]
>
>Puede bloquear a visitantes de direcciones IP específicas para que no se cuenten en los informes. Póngase en contacto con ClientCare para configurar filtros IP. Este filtrado no se aplica al usar   [Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como fuente de informes.

## Información sobre la creación de informes para tipos de actividad específicos {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Además de la información general sobre informes de este tema y sus apartados, en otras partes de esta guía puede encontrar información adicional específica para determinados tipos de actividad:

| Tipo de actividad | Detalles |
|--- |--- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Para comprender el alza y la confianza y los enfoques estadísticos utilizados en[!DNL Target], consulte [Planificación de una prueba A/B](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Segmentación automática](/help/c-activities/auto-target-to-optimize.md) | Información sobre el informe [!UICONTROL Resumen] para las actividades de AT. Para obtener más información, consulte [Informe Resumen de segmentación automática](/help/c-reports/auto-target-summary-report.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Información sobre los dos informes de [!UICONTROL Resumen de personalización automatizada] para actividades AP: informe de [!UICONTROL Nivel de actividad] e informe de [!UICONTROL Nivel de oferta]. Para obtener más información, consulte [Informes de resumen de Personalización automatizada](/help/c-reports/reports-ap.md).<br>Información sobre los dos informes de [!UICONTROL Perspectivas de personalización] para actividades de AT y AP: [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]. Para obtener más información, consulte [Informes de perspectivas de personalización](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Información sobre los dos informes para actividades MVT: [!UICONTROL Rendimiento de las experiencias] y [!UICONTROL Contribución de ubicación]. Para obtener más información, consulte [Informe de rendimiento de las experiencias](/help/c-reports/experience-performance-report.md) (MVT) e [Informe de contribución de ubicación](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como fuente de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Información sobre el uso de [!DNL Adobe Analytics]como origen de informes para [!DNL Target]. A4T le proporciona acceso a los [!DNL Analytics]informes para sus actividades [!DNL Target]. Para obtener más información, consulte [Informes de Analytics para Target (A4T)](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Visualización de un informe {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Haga clic en **[!UICONTROL Actividades]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Fuente de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Fuente de la actividad].

   Por ejemplo, podría seleccionar [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] en la lista desplegable [!UICONTROL Tipo] y elegir [!UICONTROL Activo] en la lista desplegable [!UICONTROL Estado] para mostrar solo las pruebas A/B y actividades de Segmentación de experiencias que tengan este estado.

   En la ilustración siguiente vemos la lista desplegable [!UICONTROL Tipo] con dos tipos marcados:

   ![](assets/report_filters.png)

1. Haga clic en la pestaña **[!UICONTROL Informes].**

   En todos los informes se incluye una leyenda para ayudarle a entender el informe.

   ![](assets/report_menu_bar.png)

   La leyenda muestra la siguiente información:

   * El estado de la actividad, incluido el intervalo de fechas en que se ejecutó.
   * La experiencia ganadora prevista.
   * La fuente de la actividad, como [!DNL Adobe Target] o [!DNL Adobe Target Classic].
   >[!NOTE]
   >
   >Los resultados de las experiencias aparecen después de que por lo menos un visitante haya visto la experiencia.

1. (Opcional) [Configure el informe](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) como desee.
1. (Opcional) [Descargue el informe en formato CSV](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) para su análisis con Excel y otras herramientas.

   Las opciones disponibles son las siguientes:

   * [!UICONTROL Exportar informes a CSV]
   * [!UICONTROL Exportar detalles del pedido a un archivo .csv]

1. (Opcional) Haga clic en los iconos **[!UICONTROL Visualización de tabla]** y **Visualización de gráfico]para cambiar entre los formatos de los informes.[!UICONTROL **

   Solo para las pruebas multivariable, haga clic en el icono de **[!UICONTROL Contribución de ubicación]** ( ![icono de Contribución de ubicación](assets/icon_location_contribution.png)) para que el informe muestre la contribución por ubicación.
