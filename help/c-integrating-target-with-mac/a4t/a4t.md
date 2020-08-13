---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe “Analytics for Target” (A4T) es una integración de soluciones cruzadas que le permite crear actividades basadas en las métricas de conversión y los segmentos de audiencia de Analytics. Esta integración le permite utilizar informes de Analytics para examinar sus resultados. Si usa Analytics como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basarán en la recopilación de datos de Analytics.
title: Adobe Analytics como fuente de informes para Adobe Target (A4T)
feature: a4t general
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 49%

---


# Adobe Analytics como fuente de informes para Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que permite crear actividades basadas en métricas de [!DNL Analytics] conversión y segmentos de audiencia. The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## Información general de A4T {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. No es necesario especificarlo todo antes de ejecutar la actividad.
* Disponer de una única fuente de datos elimina la variación derivada de la recopilación de datos de dos sistemas distintos.
* Your existing [!DNL Analytics] implementation collects all required data. No es necesario implementar mboxes en páginas con el único objetivo de recopilar datos para informes. Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Rellene [este formulario](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. Este complemento se considera obsoleto, pero aún se ofrece asistencia técnica para aquellos clientes que todavía lo usan.

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Se incluyen todas las métricas, incluida cualquier métrica de cliente o calculada que esté integrada en [!DNL Analytics].

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Tenga en cuenta los siguientes puntos cuando vaya a utilizar A4T:

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [Póngase en contacto con su representante de cuentas](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si necesita alguna de estas soluciones.
* La fuente de informes se establece por actividad. [!DNL Target][!DNL Target] continuará recopilando datos para usarlos en los informes y los datos de seguirán estando disponibles (si prefiere que las actividades se basen en datos recopilados por [!DNL Target].
* Debe usar una de las dos fuentes de informes. No puede recopilar datos de una única actividad desde ambas fuentes.
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. Sin embargo, su métrica de objetivos se puede basar en una llamada de mbox. For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   En algunas situaciones, la llamada de clasificación de [!DNL Target] a [!DNL Analytics] podría fallar y las actividades no muestran datos en [!DNL Analytics]. Si esto sucede, consulte [Resolución de problemas de la integración de Analytics y Destinatario (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). También puede [ponerse en contacto con Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obtener más ayuda.

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| Tipos de actividad | Compatible con A4T | Notas, si corresponde |
|--- |--- |--- |
| Actividad A/B con división de tráfico manual | Sí |  |
| Actividad A/B con asignación automática | Sí | Consulte Compatibilidad [de Analytics para Destinatario (A4T) con actividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)de asignación automática. |
| Actividad A/B con segmentación automática | No |  |
| Segmentación de experiencias (XT) | Sí |  |
| Prueba multivariable (MVT) | Sí | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| Actividad de personalización automatizada (AP) | No |  |
| Actividad de Recommendations | Sí |  |
| Aplicación móvil | Sí | Compatible con el SDK de Mobile Services, versión 4.13.1 o posterior.  Para obtener más información, consulte la [documentación de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html). |
| Correo electrónico | No |  |
| API de envío del servidor | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK de NodeJS | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Integración de servicios en la nube AEM 6.1 (o anterior) | No |  |
| Integración de servicios en la nube AEM 6.2 (o posterior) | Sí | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| Cualquier actividad que utilice una oferta de redireccionamiento | Sí | Existen requisitos mínimos más estrictos para utilizar ofertas de redireccionamiento con A4T. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sí |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>Puede usar la lista desplegable de [!UICONTROL Fuente de informes] situada en la parte superior de la página [!UICONTROL Actividades] para mostrar solo las actividades que utilizan [!DNL Analytics] como fuente de informes.

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Métrica de informes] muestra las métricas de objetivo de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph1.png)

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Audiencia] muestra las audiencias de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph2.png)

En la ilustración siguiente, se muestra la [!UICONTROL Visualización de tabla] de un informe de A4T:

![](assets/a4t_report_table.png)

Para ver el informe en [!DNL Analytics] en lugar de en [!DNL Target], haga clic en **[!UICONTROL Ver en Analytics]** en la parte superior del informe.

## Tutorial Analytics &amp; Target: Best Practices for Analysis (en inglés){#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos tratados en este tema.

### Distintivo de ![información general de Analytics para Destinatario (A4T) (4:32)](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* Explicar qué es A4T y por qué debería utilizarlo
* Explicar cómo funciona A4T
* Entender los requisitos necesarios antes de utilizar A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Distintivo ![Tutorial de Analytics/Integración de Destinatario (A4T) (40:33)](/help/assets/tutorial.png)

Este vídeo es una grabación de “[Horario de oficina](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo configurar y validar que la integración está funcionando
* Cómo funciona la integración
* Obtenga información sobre los informes ideales para su uso en Analytics
* Respuestas a preguntas más frecuentes sobre A4T

[Horas de oficina de Analytics/Integración de Destinatario (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)