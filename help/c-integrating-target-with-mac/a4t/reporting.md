---
keywords: analytics for target, a4t, analytics como origen de informes
description: Aprenda a utilizar Analytics para Destinatario (A4T). A4T proporciona acceso a los informes de Analytics para actividades de Destinatario que utilizan métricas de Analytics y segmentos de audiencia.
title: ¿Cómo se usa Sistema de informes en A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 37%

---


# Informes de A4T{#a-t-reporting}

El uso de [!DNL Analytics] como fuente de sistema de informes para [!DNL Target] (A4T) le permite acceder a [!DNL Analytics] informes para sus [!DNL Target] actividades.

Puede vista de informes para sus actividades en [!DNL Analytics] y [!DNL Target].

Para conocer las optimizaciones de sistema de informes que utilizan [!DNL Analytics] para [!DNL Target], [visite esta página de Adobe Spark](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Los informes [!DNL Analytics] y [!DNL Target] miden los participantes (las personas que ingresan a las pruebas), en lugar de los visitantes al sitio.

Cada vez que un visitante ve contenido de actividad en la página, [!DNL Target] realiza una llamada directa de servidor a servidor a [!DNL Analytics], incluyendo la actividad y experiencia que vio el visitante. [!DNL Target] también llama  [!DNL Analytics] cada vez que se realiza la conversión. [!DNL Analytics][!DNL Analytics] agrega la conversión como un nuevo evento específico de , denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por [!DNL Analytics].

Cuando se utiliza la operación [!UICONTROL Seleccionar] y se ordena en *Participantes*, en los informes solo se muestran las experiencias que recibieron participantes durante el período de tiempo seleccionado.

>[!NOTE]
>
>Los informes proporcionados por [!DNL Target] tienen una latencia de cuatro minutos. En el caso de actividades con tecnología A4T, tanto en los informes [!DNL Target] como [!DNL Analytics], puede tardar hasta 24 horas después de guardar la actividad por primera vez antes de que los datos del informe se puedan desglosar por experiencias. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics    {#analytics}

En [!DNL Analytics], hay varias dimensiones y métricas disponibles después de habilitar la integración de A4T.

### Dimensiones

* [!UICONTROL Analytics para Destinatario] : el ID principal que se pasa a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Actividades de Target]
* [!UICONTROL Experiencias de Target]
* [!UICONTROL Actividad]  destinatario>  [!UICONTROL Experiencia]
* [!UICONTROL 3er ID] : se puede ignorar

### Métricas

* [!UICONTROL Impresiones]  de actividad: coincide con el número de   participantes del  [!DNL Target] informe.
* [!UICONTROL Conversiones]  de actividad: coincide con el número de  [!UICONTROL conversiones ] personalizadas del  [!DNL Target] informe.

En [!DNL Analysis Workspace], utilice el panel [!UICONTROL Análisis para Destinatario] para analizar sus actividades [!DNL Target] y experiencias con alza y confianza. Para obtener más información, consulte el [Panel Análisis para Destinatario (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) en la *Guía de herramientas de Analytics*.

>[!IMPORTANT]
>
>Si su [!UICONTROL informe de Actividades de Destinatario] en listas [!DNL Analytics] &quot;no especificadas&quot; en lugar de enumerar sus actividades, se requiere una actualización en la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

Para obtener información detallada y ejemplos, abra el [Destinatario y análisis: Tutorial de Prácticas recomendadas para la Análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por Adobe Experience League.

## Informes en Target    {#section_C0D1F17F88374B6690BF904D7B83B42E}

Cuando [!DNL Analytics] se utiliza como fuente de sistema de informes, los informes de [!DNL Target] muestran los datos recopilados de [!DNL Analytics]. El informe difiere un poco de otros [!DNL Target] informes:

* La lista [!UICONTROL Audiencias] muestra las audiencias disponibles para su grupo de informes [!DNL Analytics].
* La lista [!UICONTROL Métrica] muestra todas las métricas disponibles a través de [!DNL Analytics].

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

   Tenga en cuenta que cualquier número que aumente se muestra como positivo en el informe, aun cuando realmente no se desee un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o audiencia al informe en [!DNL Target] después de que se haya iniciado la actividad o incluso después de que la prueba se haya completado. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic para vista del [!DNL Analytics] informe completo directamente desde la página del informe de actividad.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Una prueba con [!DNL Analytics] utiliza [!DNL Adobe Analytics] segmentos en lugar de [!DNL Target] audiencias.

## Realización de cálculos sin conexión para Analytics para Destinatario (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para obtener más información, véase [Realización de cálculos sin conexión en Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
