---
keywords: analytics para target, a4t, analytics como fuente de informes, analytics
description: Aprenda a utilizar Analytics para Target (A4T). A4T proporciona acceso a los informes de Analytics para las actividades de Target que usan métricas de Analytics y segmentos de audiencia.
title: ¿Cómo utilizo los informes en A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 7b2d5251275f42da66d09370501d0882671d5cca
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 33%

---


# Informes de A4T{#a-t-reporting}

El uso de [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T) le permite acceder a [!DNL Analytics] informes para sus actividades [!DNL Target].

Puede ver los informes de las actividades tanto en [!DNL Analytics] como en [!DNL Target].

Para informar sobre las prácticas recomendadas utilizando [!DNL Analytics] para [!DNL Target], [visite este Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Los informes [!DNL Analytics] y [!DNL Target] miden los participantes (las personas que participan en las pruebas), en lugar de los visitantes del sitio.

Cada vez que un visitante ve contenido de actividad en la página, [!DNL Target] realiza una llamada directa de servidor a servidor a [!DNL Analytics], incluida la actividad y experiencia que vio el visitante. [!DNL Target] también llama  [!DNL Analytics] cada vez que se realiza la conversión. [!DNL Analytics][!DNL Analytics] agrega la conversión como un nuevo evento específico de , denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por [!DNL Analytics].

Cuando se utiliza la operación [!UICONTROL Select] y se ordena por *Entrantes*, solo se muestran en los informes las experiencias que recibieron participantes durante el período de tiempo seleccionado.

>[!NOTE]
>
>Los informes ofrecidos por [!DNL Target] tienen una latencia de cuatro minutos. Para las actividades ofrecidas por A4T, tanto en los informes [!DNL Target] como [!DNL Analytics], puede tardar hasta 24 horas después de que la actividad se guarde inicialmente antes de que los datos del informe se puedan desglosar por experiencias. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics    {#analytics}

En [!DNL Analytics], hay varias dimensiones y métricas disponibles después de activar la integración con A4T.

### Dimensiones

* [!UICONTROL Analytics para Target] : el ID principal que se transfiere a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Actividades de Target]
* [!UICONTROL Experiencias de Target]
* [!UICONTROL Actividad]  de Target >  [!UICONTROL Experiencia]
* [!UICONTROL 3er ID] : se puede ignorar

### Métricas

* [!UICONTROL Impresiones de actividad] : coincide con el número de   participantes en el  [!DNL Target] informe.
* [!UICONTROL Conversiones de actividad] : coincide con el número de  [!UICONTROL conversiones ] personalizadas del  [!DNL Target] informe.

En [!DNL Analysis Workspace], utilice el panel [!UICONTROL Analytics for Target] para analizar las actividades y experiencias de [!DNL Target] con alza y confianza. Para obtener más información, consulte el [Panel de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) en la *Guía de herramientas de Analytics*.

>[!IMPORTANT]
>
>Si el informe [!UICONTROL Actividades de Target] de [!DNL Analytics] indica &quot;sin especificar&quot; en lugar de enumerar las actividades, se requiere una actualización en la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

Para obtener información detallada y ejemplos, abra [Analytics &amp; Target: Tutorial Prácticas recomendadas de análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por Adobe Experience League.

## Informes en Target    {#section_C0D1F17F88374B6690BF904D7B83B42E}

Cuando se utiliza [!DNL Analytics] como fuente de informes, los informes de [!DNL Target] muestran los datos recopilados de [!DNL Analytics]. El informe difiere un poco de otros [!DNL Target] informes:

* La lista [!UICONTROL Audiencias] muestra las audiencias disponibles para el grupo de informes [!DNL Analytics].
* La lista [!UICONTROL Métrica] muestra cada métrica disponible a través de [!DNL Analytics].

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

   Los números que aumentan se muestran como positivos en el informe, incluso cuando no se desea un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de iniciar la actividad o incluso después de que se haya completado la prueba. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic en para ver el informe completo [!DNL Analytics] directamente desde la página del informe de actividad.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Una prueba con [!DNL Analytics] utiliza segmentos [!DNL Adobe Analytics] en lugar de [!DNL Target] audiencias.

## Realización de cálculos sin conexión en Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para obtener más información, véase [Realización de cálculos sin conexión en Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
