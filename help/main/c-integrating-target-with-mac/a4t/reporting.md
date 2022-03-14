---
keywords: analytics para target, a4t, analytics como fuente de informes, analytics
description: Obtenga información sobre cómo usar Analytics para [!DNL Target] (A4T). A4T proporciona acceso a los informes de Analytics para [!DNL Target] actividades que utilizan métricas de Analytics y segmentos de audiencia.
title: ¿Cómo utilizo los informes en A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 34%

---

# Informes de A4T

Uso [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T) le proporciona acceso a [!DNL Analytics] informes para [!DNL Target] actividades.

Puede ver los informes de las actividades en ambas [!DNL Analytics] y [!DNL Target].

Para informar sobre las prácticas recomendadas usando [!DNL Analytics] para [!DNL Target], [visite este Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Ambas [!DNL Analytics] y [!DNL Target] los informes miden los participantes (las personas que participan en las pruebas), en lugar de los visitantes del sitio.

Cada vez que un visitante ve contenido de actividad en la página, [!DNL Target] realiza una llamada directa de servidor a servidor a [!DNL Analytics], incluida la actividad y experiencia que vio el visitante. [!DNL Target] llamadas también [!DNL Analytics] siempre que se realice la conversión. [!DNL Analytics][!DNL Analytics] agrega la conversión como un nuevo evento específico de , denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por [!DNL Analytics].

Cuando la variable [!UICONTROL Select] se utiliza y se ordena *Participantes*, solo se mostrarán en los informes las experiencias que hayan recibido participantes durante el período de tiempo seleccionado.

>[!NOTE]
>
>Informes con tecnología de [!DNL Target] tienen una latencia de cuatro minutos. Para las actividades ofrecidas por A4T, en ambas [!DNL Target] y [!DNL Analytics] , puede tardar hasta 24 horas después de guardar la actividad por primera vez para que los datos del informe se puedan desglosar por experiencias. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics   {#analytics}

En [!DNL Analytics], hay varias dimensiones y métricas disponibles una vez habilitada la integración de A4T.

### Dimensiones

* [!UICONTROL Analytics para Target] : ID principal que se transfiere a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Actividades de Target]
* [!UICONTROL Experiencias de Target]
* [!UICONTROL Actividad de Target] > [!UICONTROL Experiencia]
* [!UICONTROL 3er ID] - se puede ignorar

### Métricas

* [!UICONTROL Impresiones de actividad] - Coincide con el [!UICONTROL Participantes] en el [!DNL Target] informe.
* [!UICONTROL Conversiones de actividades] - Coincide con el [!UICONTROL Conversiones personalizadas] en el [!DNL Target] informe.

En [!DNL Analysis Workspace], use el [!UICONTROL Analytics para Target] para analizar su [!DNL Target] actividades y experiencias con alza y confianza. Para obtener más información, consulte [Panel de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es) en el *Guía de herramientas de Analytics*.

>[!IMPORTANT]
>
>Si su [!UICONTROL Actividades de Target] informe en [!DNL Analytics] enumera &quot;sin especificar&quot; en lugar de enumerar sus actividades, se requiere una actualización en la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

Para obtener información detallada y ejemplos, abra el [Analytics y Target: Prácticas recomendadas para el análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, proporcionado por Adobe Experience League.

## Informes en [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] se usa como fuente de informes, los informes de [!DNL Target] mostrar los datos recopilados de [!DNL Analytics]. El informe difiere en cierta medida de otro [!DNL Target] informes:

* La variable [!UICONTROL Audiencias] La lista muestra las audiencias disponibles para su [!DNL Analytics] grupo de informes.
* La variable [!UICONTROL Métrica] la lista muestra todas las métricas disponibles mediante [!DNL Analytics].

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

   Los números que aumentan se muestran como positivos en el informe, incluso cuando no se desea un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de que se haya iniciado la actividad o incluso después de que se haya completado la prueba. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic en para ver el [!DNL Analytics] informe directamente desde la página de informe de actividad.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Una prueba con [!DNL Analytics] uses [!DNL Adobe Analytics] segmentos en lugar de [!DNL Target] audiencias.

## Realización de cálculos sin conexión en Analytics for Adobe Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para obtener más información, véase [Realización de cálculos sin conexión en Analytics for Target (A4T)](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
