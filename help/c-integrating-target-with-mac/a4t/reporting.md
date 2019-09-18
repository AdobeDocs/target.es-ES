---
description: El uso de Analytics como fuente de informes para Target (A4T) permite acceder a informes de Analytics para sus actividades de Target.
keywords: analytics for target, a4t, analytics como origen de informes
seo-description: El uso de Analytics como fuente de informes para Target (A4T) permite acceder a informes de Analytics para sus actividades de Target.
seo-title: Informes de A4T
solution: Target
subtopic: Prueba multivariable
title: Informes de A4T
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Informes de A4T{#a-t-reporting}

El uso de Analytics como fuente de informes para Target (A4T) permite acceder a informes de Analytics para sus actividades de Target.

Puede ver informes de las actividades tanto en Analytics como en Target Standard/Premium.

Para informar sobre las prácticas recomendadas utilizando Analytics for Target, [visite esta página de Adobe Spark](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Los informes tanto de Analytics como de Target miden los participantes (las personas que participan en las pruebas), en lugar de los visitantes del sitio.

Cada vez que un visitante ve contenido de actividades en la página, Target realiza una llamada directa de servidor a servidor a Analytics, en la que se incluye la actividad y la experiencia que vio el visitante. Target también realiza llamadas a Analytics cada vez que se realiza la conversión. Analytics agrega la conversión como un nuevo evento específico de Analytics, denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por Analytics.

Cuando se usa la operación Seleccionar y ordenar por *participantes*, solo se mostrarán en los informes las experiencias que reciban participantes durante el período de tiempo seleccionado.

>[!NOTE]
>
>Los informes ofrecidos por Target tienen una latencia de cuatro minutos. En el caso de las actividades ofrecidas por A4T, en los informes tanto de Target como de Analytics, después de guardar la actividad por primera vez se puede tardar hasta 24 horas en poder desglosar los datos del informe por experiencia. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics  {#section_F6884872DC864AE7913587FAED4CD11C}

En Analytics, en el menú de la izquierda, haga clic en **[!UICONTROL Target]** &gt; **[!UICONTROL Actividades de Target]**. En Target, los informes de actividad muestran automáticamente los datos, las métricas y los segmentos de Analytics. Los datos aparecen en estos informes aproximadamente una hora después de recopilarlos del sitio. Todas las métricas, las audiencias y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

En Analytics, utilice el informe de Actividades de Target para ver los resultados de su actividad de Target. Los informes de Test&amp;Target (solución anterior) ofrecen información sobre las integraciones de página de estilo del antiguo complemento Test&amp;Target, pero no incluyen los datos de Analytics for Target. En el informe Actividades, puede consultar la información sobre las experiencias de Target. Haga clic en **[!UICONTROL Métricas]** y seleccione el tipo de métrica **[!UICONTROL Target]**. Hay dos métricas disponibles para el informe:

* **Entradas de actividad:** coincide con el número de participantes en el informe de Target.
* **Conversiones de actividad:** coincide con el número de conversiones personalizadas en el informe de Target.

>[!NOTE]
>
>Los detalles de alza y confianza de Target también están disponibles en Analytics. Para obtener más información, consulte Alza y confianza [de](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) Target en la Guía *de componentes de* Analytics.

>[!IMPORTANT]
>
>Si el informe Actividades de Target en Analytics indica “sin especificar” en lugar de enumerar las actividades, se requiere una actualización en la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

## Informes en Target  {#section_C0D1F17F88374B6690BF904D7B83B42E}

Cuando se usa Analytics como fuente de informes, los informes en Target Standard muestran los datos recopilados de Analytics. El informe es algo distinto de otros informes de Target Standard:

* En la lista de audiencias se muestran las audiencias disponibles en el grupo de informes de Analytics.
* En la lista de métricas se muestran todas las métricas disponibles mediante Analytics.

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en Analytics..

   Tenga en cuenta que cualquier número que aumente se muestra como positivo en el informe, aun cuando realmente no se desee un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o la audiencia al informe en Target después de haber iniciado la prueba, o incluso después de que se haya completado la prueba. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic para ver el informe de Analytics completo directamente desde la página de informes de la actividad.

## Informes en Analysis Workspace {#reports-in-analysis-workspace}

Puede utilizar [!DNL Adobe Analysis Workspace] para profundizar y visualizar los datos o descubrir la información oculta bajo la superficie.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Creación de actividades {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Las pruebas con Analytics usan segmentos de Adobe Analytics, en lugar de audiencias de Target Standard.

## Realización de cálculos sin conexión en Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para obtener más información, véase [Realización de cálculos sin conexión en Analytics for Target (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).