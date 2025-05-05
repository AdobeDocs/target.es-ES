---
keywords: analytics for target;a4t;analytics como fuente de informes;analytics
description: Aprenda a utilizar Analytics for [!DNL Target] (A4T). A4T proporciona acceso a los informes de Analytics para  [!DNL Target] actividades que usan métricas y segmentos de audiencia de Analytics.
title: ¿Cómo se utiliza la creación de informes en A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# Informes de A4T

Si usa [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T), tendrá acceso a [!DNL Analytics] informes para sus actividades [!DNL Target].

Puede ver informes de sus actividades en [!DNL Analytics] y [!DNL Target].

Para informar sobre las prácticas recomendadas usando [!DNL Analytics] para [!DNL Target], [visite esta Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Los informes [!DNL Analytics] y [!DNL Target] miden los participantes (las personas que entran en las pruebas), en lugar de los visitantes del sitio.

Cada vez que un visitante ve contenido de actividad en la página, [!DNL Target] realiza una llamada directa de servidor a servidor a [!DNL Analytics], que incluye la actividad y experiencia que vio el visitante. [!DNL Target] también llama a [!DNL Analytics] cada vez que se realiza la conversión. [!DNL Analytics] agrega la conversión como un nuevo evento [!DNL Analytics] específico denominado &quot;Conversión de actividad&quot;, del que se hace seguimiento junto con otros datos recopilados por [!DNL Analytics].

Cuando se usa la operación [!UICONTROL Select] y se ordenan los *participantes*, en los informes solo se muestran las experiencias que recibieron participantes durante el período de tiempo seleccionado.

>[!NOTE]
>
>Los informes con tecnología de [!DNL Target] tienen una latencia de cuatro minutos. En el caso de las actividades con tecnología A4T, tanto en los informes [!DNL Target] como en el [!DNL Analytics], pueden pasar hasta 24 horas desde que se guardó inicialmente la actividad antes de que los datos del informe se puedan desglosar por experiencias. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics   {#analytics}

En [!DNL Analytics], hay varias dimensiones y métricas disponibles después de habilitar la integración de A4T.

### Dimensiones

* [!UICONTROL Analytics for Target]: el ID principal que se pasa a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - se puede ignorar

### Métricas

* [!UICONTROL Activity Impressions] - Coincide con el número [!UICONTROL Entrants] en el informe [!DNL Target].
* [!UICONTROL Activity Conversions] - Coincide con el número [!UICONTROL Custom Conversions] en el informe [!DNL Target].

En [!DNL Analysis Workspace], use el panel [!UICONTROL Analytics for Target] para analizar con confianza las actividades y experiencias de [!DNL Target]. Para obtener más información, consulte el [Panel Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es) en la *Guía de herramientas de Analytics*.

>[!IMPORTANT]
>
>Si el informe [!UICONTROL Target Activities] de [!DNL Analytics] incluye &quot;sin especificar&quot; en lugar de incluir sus actividades, se requiere una actualización de la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

Para obtener información detallada y ejemplos, abra el tutorial [Analytics &amp; Target: Prácticas recomendadas de análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) proporcionado por Adobe Experience League.

## Informes en [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

Cuando se usa [!DNL Analytics] como origen de informes, los informes de [!DNL Target] muestran los datos recopilados de [!DNL Analytics]. El informe difiere un poco de otros [!DNL Target] informes:

* La lista [!UICONTROL Audiences] muestra las audiencias disponibles para el grupo de informes [!DNL Analytics].
* La lista [!UICONTROL Metric] muestra todas las métricas disponibles mediante [!DNL Analytics].

  Todas las métricas están disponibles, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

  Los números que aumentan se muestran como positivos en el informe, incluso cuando no se desea un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de que se haya iniciado la actividad, o incluso después de que la prueba haya finalizado. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic para ver el informe completo de [!DNL Analytics] directamente desde la página del informe de actividad.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Settings]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Una prueba con [!DNL Analytics] usa [!DNL Adobe Analytics] segmentos en lugar de [!DNL Target] audiencias.

## Realización de cálculos sin conexión en Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Puede realizar cálculos sin conexión de los intervalos de confianza para A4T mediante el archivo de Excel [!DNL Target] [Calculadora de confianza completa](/help/main/assets/complete_confidence_calculator.xlsx), pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para A4T, utilizamos un cálculo [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para variables continuas (en lugar de métricas binarias). En Analytics, siempre se realiza un seguimiento de los visitantes y se cuenta toda acción realizada. Por tanto, si el visitante realiza varias compras o visita varias veces una métrica de éxito, todas estas visitas adicionales se cuentan. Esto convierte la métrica en una variable continua. Para realizar el cálculo de la prueba t de Welch, se requiere la &quot;suma de los cuadrados&quot; para calcular la varianza, que se utiliza en el denominador de la estadística t. [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explica los detalles de las fórmulas matemáticas utilizadas. La suma de los cuadrados se puede recuperar de [!DNL Analytics]. Para obtener datos de la suma de los cuadrados, debe realizar una exportación en el nivel de visitante de la métrica que desea optimizar durante un periodo de muestra.

Por ejemplo, si está optimizando las vistas de página por visitante, exportaría una muestra del número total de vistas de página por visitante durante un lapso de tiempo especificado, tal vez un par de días (unos pocos miles de puntos de datos es todo lo que necesita). A continuación, elevaría al cuadrado cada valor y sumaría los totales (en este caso, el orden de las operaciones es esencial). Este valor “suma de los cuadrados” se utiliza en la calculadora de confianza completa. Para estos valores, utilice la sección “ingresos” de dicha hoja de cálculo.

**Para utilizar a este respecto la función de exportación de datos de [!DNL Analytics]:**

1. Iniciar sesión en [!DNL Adobe Analytics].
1. Haga clic en **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. En la ficha **[!UICONTROL Data Warehouse Request]**, rellene los campos.

   Para obtener más información acerca de cada campo, consulte &quot;Descripciones de Data Warehouse&quot; en [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=es).

   | Campo | Instrucciones |
   |--- |--- |
   | Nombre de la solicitud | Especifica un nombre para su solicitud. |
   | Fecha de informes | Especifica un periodo de tiempo y una granularidad.<br>Como práctica recomendada, elija no más de una hora o un día de datos para la primera solicitud.  Los archivos del Data Warehouse tardan más en procesarse cuanto mayor es el periodo solicitado, por lo que siempre se recomienda solicitar primero un periodo corto para garantizar que el archivo devuelva el resultado esperado. A continuación, vaya a Solicitar administrador, duplique la solicitud y solicite más datos esta vez. Además, si establece la granularidad en cualquier valor distinto de &quot;Ninguno&quot;, el tamaño del archivo aumentará de forma drástica.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segmentos disponibles | Aplique un segmento, según sus necesidades. |
   | Desgloses | Seleccione las dimensiones que desee: Estándar está listo para usar (OOTB), mientras que Personalizado incluye eVars y props. Se recomienda utilizar &quot;ID de visitante&quot; si se necesita información en este nivel, en lugar de &quot;ID de visitante de Experience Cloud&quot;.<ul><li>El ID de visitante es el ID último utilizado por Analytics. Será AID (en el caso de un cliente heredado) o MID (si el cliente es nuevo o si borró las cookies desde el inicio del servicio ID de visitante de MC).</li><li>El ID de visitante de Experience Cloud solo se establecerá para clientes nuevos o que hayan borrado las cookies desde el inicio del servicio ID de visitante de MC.</li></ul> |
   | Métricas | Seleccione las métricas que desee. Estándar es el valor predeterminado, mientras que Personalizado incluye eventos personalizados. |
   | Vista previa del informe | Revise la configuración antes de programar el informe.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Programar envío | Escriba una dirección de correo electrónico a la que enviar el archivo, asigne un nombre al archivo y seleccione [!UICONTROL Send Immediately].<br>Nota: el archivo se puede enviar a través de FTP en [!UICONTROL Advanced Delivery Options]<br>![Programar envío](/help/main/c-reports/assets/datawarehouse3.png). |

1. Haga clic en **[!UICONTROL Request this Report]**.

   El envío de archivos puede tardar hasta 72 horas, dependiendo de la cantidad de datos solicitados. Puede comprobar el progreso de su solicitud en cualquier momento haciendo clic en [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Si desea volver a solicitar datos que ha solicitado anteriormente, puede duplicar una solicitud antigua de [!UICONTROL Request Manager] según sea necesario.

Para obtener más información sobre el [!DNL Data Warehouse], vea los siguientes vínculos en la documentación de ayuda de [!DNL Analytics]:

* [Crear una solicitud de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=es)
* [prácticas recomendadas de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=es)
