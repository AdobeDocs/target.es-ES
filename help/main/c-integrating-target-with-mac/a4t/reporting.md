---
keywords: analytics for target;a4t;analytics como fuente de informes;analytics
description: Aprenda a utilizar Analytics para [!DNL Target] (A4T). A4T proporciona acceso a informes de Analytics para [!DNL Target] actividades que utilizan métricas de Analytics y segmentos de audiencia.
title: ¿Cómo se utiliza la creación de informes en A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 48%

---

# Informes de A4T

Uso de [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T) le permite acceder a [!DNL Analytics] informes para su [!DNL Target] actividades.

Puede ver informes de sus actividades en ambos [!DNL Analytics] y [!DNL Target].

Para informar sobre las prácticas recomendadas utilizando [!DNL Analytics] para [!DNL Target], [visite este Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Información general {#section_035A62D65608423285D8A5A54731E2C5}

Ambos [!DNL Analytics] y [!DNL Target] Los informes miden los participantes (las personas que entran en las pruebas), en lugar de los visitantes del sitio.

Cada vez que un visitante ve contenido de actividad en la página, [!DNL Target] realiza una llamada directa de servidor a servidor a [!DNL Analytics], incluida la actividad y experiencia que vio el visitante. [!DNL Target] también llama a [!DNL Analytics] siempre que se realice la conversión. [!DNL Analytics][!DNL Analytics] agrega la conversión como un nuevo evento específico de , denominado “Conversión de actividad”, del que se hace seguimiento junto con el resto de los datos recopilados por [!DNL Analytics].

Si la variable [!UICONTROL Seleccionar] se utiliza la operación y se ordena según *Participantes*, en los informes solo se mostrarán las experiencias que hayan recibido participantes durante el periodo de tiempo seleccionado.

>[!NOTE]
>
>Informes con tecnología [!DNL Target] tienen una latencia de cuatro minutos. Para actividades con tecnología A4T, en [!DNL Target] y [!DNL Analytics] de informes, pueden pasar hasta 24 horas desde que se guardó inicialmente la actividad antes de que los datos del informe se puedan desglosar por experiencias. Los datos recopilados en esas primeras 24 horas siguen siendo precisos y se asignan a la experiencia adecuada.

## Informes en Analytics   {#analytics}

Entrada [!DNL Analytics]Sin embargo, hay varias dimensiones y métricas disponibles después de habilitar la integración de A4T.

### Dimensiones

* [!UICONTROL Analytics for Target] : el ID principal que se pasa a través de la integración. El formato de esta dimensión es `Activity ID:Experience ID:3rd ID`. Las dimensiones siguientes son clasificaciones de esta dimensión.
* [!UICONTROL Actividades de Target]
* [!UICONTROL Experiencias de Target]
* [!UICONTROL Actividad de Target] > [!UICONTROL Experiencia]
* [!UICONTROL 3er ID] - se puede ignorar

### Métricas

* [!UICONTROL Impresiones de actividad] - Coincide con [!UICONTROL Participantes] número en la [!DNL Target] informe.
* [!UICONTROL Conversiones de actividades] - Coincide con [!UICONTROL Conversiones personalizadas] número en la [!DNL Target] informe.

Entrada [!DNL Analysis Workspace], use el [!UICONTROL Analytics for Target] panel para analizar su [!DNL Target] actividades y experiencias con alza y confianza. Para obtener más información, consulte [Panel de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es) en el *Guía de herramientas de Analytics*.

>[!IMPORTANT]
>
>Si su [!UICONTROL Actividades de Target] informar en [!DNL Analytics] enumera &quot;sin especificar&quot; en lugar de enumerar las actividades, se requiere una actualización de la cuenta aprovisionada. Póngase en contacto con el Servicio de atención al cliente para resolver este problema.

Para obtener información detallada y ejemplos, abra el [Analytics &amp; Target: prácticas recomendadas de análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial proporcionado por Adobe Experience League.

## Informes en [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

Cuándo [!DNL Analytics] se utiliza como fuente de informes, informa en [!DNL Target] mostrar los datos recopilados de [!DNL Analytics]. El informe difiere un poco de otros [!DNL Target] informes:

* El [!UICONTROL Audiencias] muestra las audiencias disponibles para su [!DNL Analytics] grupo de informes.
* El [!UICONTROL Métrica] La lista muestra todas las métricas disponibles a través de [!DNL Analytics].

   Cada métrica está disponible, incluida cualquier métrica personalizada o calculada que esté integrada en [!DNL Analytics].

   Los números que aumentan se muestran como positivos en el informe, incluso cuando no se desea un aumento. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de que la actividad se haya iniciado o incluso después de que se haya completado la prueba. No tiene por qué saber exactamente lo que quiere medir de antemano.

Haga clic para ver el [!DNL Analytics] informe directamente desde la página informe de actividad.

## Creación de actividad {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante la creación de la actividad, debe especificar un objetivo para la actividad en la página [!UICONTROL Ajustes]. Este objetivo se convierte en la métrica predeterminada para el informe y siempre se enumera como la primera opción en el selector de métricas. No se pueden seleccionar segmentos para informes como lo haría para una actividad normal de Target. Una prueba con [!DNL Analytics] utiliza [!DNL Adobe Analytics] segmentos en lugar de [!DNL Target] audiencias.

## Realización de cálculos sin conexión en Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Puede realizar cálculos sin conexión para los intervalos de confianza y confianza para A4T mediante la variable [!DNL Target] [Calculadora de confianza completa](/help/main/assets/complete_confidence_calculator.xlsx) Archivo de Excel, pero requiere un paso con exportaciones de datos en [!DNL Analytics].

Para A4T, utilizamos un [Prueba T de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} cálculo para variables continuas (en lugar de métricas binarias). En Analytics, siempre se realiza un seguimiento de los visitantes y se cuenta toda acción realizada. Por tanto, si el visitante realiza varias compras o visita varias veces una métrica de éxito, todas estas visitas adicionales se cuentan. Esto convierte la métrica en una variable continua. Para realizar el cálculo de la prueba t de Welch, se requiere la &quot;suma de los cuadrados&quot; para calcular la varianza, que se utiliza en el denominador de la estadística t. [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explica los detalles de las fórmulas matemáticas utilizadas. La suma de los cuadrados se puede recuperar de [!DNL Analytics]. Para obtener datos de la suma de los cuadrados, debe realizar una exportación en el nivel de visitante de la métrica que desea optimizar durante un periodo de muestra.

Por ejemplo, si está optimizando las vistas de página por visitante, exportaría una muestra del número total de vistas de página por visitante durante un lapso de tiempo especificado, tal vez un par de días (unos pocos miles de puntos de datos es todo lo que necesita). A continuación, elevaría al cuadrado cada valor y sumaría los totales (en este caso, el orden de las operaciones es esencial). Este valor “suma de los cuadrados” se utiliza en la calculadora de confianza completa. Para estos valores, utilice la sección “ingresos” de dicha hoja de cálculo.

**Para utilizar a este respecto la función de exportación de datos de [!DNL Analytics]:**

1. Iniciar sesión en [!DNL Adobe Analytics].
1. Haga clic en **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]**.
1. En la pestaña **[!UICONTROL Solicitud de Data Warehouse]**, rellene los campos.

   Para obtener más información acerca de cada campo, consulte &quot;Descripciones de Data Warehouse&quot; en [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Campo | Instrucciones |
   |--- |--- |
   | Nombre de la solicitud | Especifica un nombre para su solicitud. |
   | Fecha de informes | Especifica un periodo de tiempo y una granularidad.<br>Como práctica recomendada, elija no más de una hora o un día de datos para la primera solicitud.  Los archivos del Data Warehouse tardan más en procesarse cuanto mayor es el periodo solicitado, por lo que siempre se recomienda solicitar primero un periodo corto para garantizar que el archivo devuelva el resultado esperado. A continuación, vaya a Solicitar administrador, duplique la solicitud y solicite más datos esta vez. Además, si establece la granularidad en cualquier valor distinto de &quot;Ninguno&quot;, el tamaño del archivo aumentará de forma drástica.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segmentos disponibles | Aplique un segmento, según sus necesidades. |
   | Desgloses | Seleccione las dimensiones que desee:     Estándar es el valor predeterminado, mientras que Personalizado incluye eVars y props. Se recomienda utilizar &quot;ID de visitante&quot; si se necesita información en este nivel, en lugar de &quot;ID de visitante de Experience Cloud&quot;.<ul><li>El ID de visitante es el ID último utilizado por Analytics. Será AID (en el caso de un cliente heredado) o MID (si el cliente es nuevo o si borró las cookies desde el inicio del servicio ID de visitante de MC).</li><li>El ID de visitante de Experience Cloud solo se establecerá para clientes nuevos o que hayan borrado las cookies desde el inicio del servicio ID de visitante de MC.</li></ul> |
   | Métricas | Seleccione las métricas que desee. Estándar es el valor predeterminado, mientras que Personalizado incluye eventos personalizados. |
   | Vista previa del informe | Revise la configuración antes de programar el informe.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Programar envío | Introduzca una dirección de correo electrónico a la que enviar el archivo, asigne un nombre a este y, a continuación, seleccione [!UICONTROL Enviar inmediatamente].<br>Nota: El archivo se puede enviar mediante FTP desde [!UICONTROL Opciones de envío avanzadas]<br>![Programar envío](/help/main/c-reports/assets/datawarehouse3.png). |

1. Haga clic en **[!UICONTROL Solicitar este informe]**.

   El envío de archivos puede tardar hasta 72 horas, dependiendo de la cantidad de datos solicitados. Puede comprobar el progreso de la solicitud en cualquier momento haciendo clic en [!UICONTROL Herramientas] > [!UICONTROL Data Warehouse] > [!UICONTROL Solicitar administrador].

   Si desea volver a solicitar datos que ya ha solicitado anteriormente, puede duplicar una solicitud antigua de [!UICONTROL Administrador de solicitudes] según sea necesario.

Para obtener más información sobre el [!DNL Data Warehouse], vea los siguientes vínculos en la documentación de ayuda de [!DNL Analytics]:

* [Crear una solicitud del Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Prácticas recomendadas de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
