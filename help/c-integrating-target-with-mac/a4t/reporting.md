---
keywords: analytics for target;a4t;analytics as the reporting source
description: El uso de Analytics como fuente de informes para Target (A4T) permite acceder a informes de Analytics para sus actividades de Target.
title: Informes de A4T
feature: a4t reports
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 40%

---


# Informes de A4T{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] también llama [!DNL Analytics] cada vez que se realiza la conversión. [!DNL Analytics][!DNL Analytics] agrega la conversión como un nuevo evento específico de , denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por [!DNL Analytics].

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics   {#analytics}

En [!DNL Analytics], hay varias dimensiones y métricas disponibles después de habilitar la integración de A4T.

### Dimensiones

* [!UICONTROL Analytics para Destinatario] : el ID principal que se pasa a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Actividades de Target]
* [!UICONTROL Experiencias de Target]
* [!UICONTROL Actividad] de destinatario > [!UICONTROL Experiencia]
* [!UICONTROL 3er ID] : se puede ignorar

### Métricas

* [!UICONTROL Impresiones] de actividad: coincide con el número de [!UICONTROL participantes] en el [!DNL Target] informe.
* [!UICONTROL Conversiones] de actividad: coincide con el número de conversiones  personalizadas del [!DNL Target] informe.

En [!DNL Analysis Workspace], utilice el panel [!UICONTROL Analytics para Destinatario] para analizar sus [!DNL Target] actividades y experiencias con alza y confianza. Para obtener más información, consulte Panel [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics para Destinatario (A4T) en la Guía *de herramientas de* Analytics.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Informes en Target   {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

   Tenga en cuenta que cualquier número que aumente se muestra como positivo en el informe, aun cuando realmente no se desee un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. No tiene por qué saber exactamente lo que quiere medir de antemano.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para obtener más información, véase [Realización de cálculos sin conexión en Analytics for Target (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
