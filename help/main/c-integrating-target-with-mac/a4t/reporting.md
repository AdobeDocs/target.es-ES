---
keywords: analytics para target, a4t, analytics como fuente de informes, analytics
description: Obtenga información sobre cómo usar Analytics para [!DNL Target] (A4T). A4T proporciona acceso a los informes de Analytics para [!DNL Target] actividades que utilizan métricas de Analytics y segmentos de audiencia.
title: ¿Cómo utilizo los informes en A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 493ecd762b5228d33377ac8263b90a0f9c73127e
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 49%

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

## Realización de cálculos sin conexión en Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics].

Para A4T se usa un [Prueba T de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test)Cálculo de {target=_blank} para variables continuas (en lugar de métricas binarias). En Analytics, siempre se realiza un seguimiento de los visitantes y se cuenta toda acción realizada. Por tanto, si el visitante realiza varias compras o visita varias veces una métrica de éxito, todas estas visitas adicionales se cuentan. Esto convierte la métrica en una variable continua. Para realizar el cálculo de la prueba T de Welch, se necesita la &quot;suma de los cuadrados&quot; para calcular la varianza, que se utiliza en el denominador de la estadística t. [Cálculos estadísticos en pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explica los detalles de las fórmulas matemáticas utilizadas. La suma de los cuadrados se puede recuperar de [!DNL Analytics]. Para obtener datos de la suma de los cuadrados, debe realizar una exportación en el nivel de visitante de la métrica que desea optimizar durante un periodo de muestra.

Por ejemplo, si está optimizando las vistas de página por visitante, exportaría una muestra del número total de vistas de página por visitante durante un lapso de tiempo especificado, tal vez un par de días (solo necesita unos cuantos miles de puntos de datos). A continuación, elevaría al cuadrado cada valor y sumaría los totales (en este caso, el orden de las operaciones es esencial). Este valor “suma de los cuadrados” se utiliza en la calculadora de confianza completa. Para estos valores, utilice la sección “ingresos” de dicha hoja de cálculo.

**Para utilizar a este respecto la función de exportación de datos de [!DNL Analytics]:**

1. Iniciar sesión en [!DNL Adobe Analytics].
1. Haga clic en **[!UICONTROL Herramientas]** > **[!UICONTROL Data Warehouse]**.
1. En la pestaña **[!UICONTROL Solicitud de Data Warehouse]**, rellene los campos.

   Para obtener más información acerca de cada campo, consulte &quot;Descripciones de Data Warehouse&quot; en [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Campo | Instrucciones |
   |--- |--- |
   | Nombre de la solicitud | Especifica un nombre para su solicitud. |
   | Fecha de informes | Especifica un periodo de tiempo y una granularidad.<br>Como práctica recomendada, elija no más de una hora o un día de datos para la primera solicitud.  Los archivos del Data Warehouse tardan más en procesarse cuanto mayor es el periodo solicitado, por lo que siempre se recomienda solicitar primero un periodo corto para garantizar que el archivo devuelva el resultado esperado. A continuación, vaya a Solicitar administrador, duplique la solicitud y solicite más datos esta vez. Además, si cambia la granularidad a cualquier valor distinto de &quot;Ninguno&quot;, el tamaño del archivo aumentará de forma drástica.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segmentos disponibles | Aplique un segmento, según sus necesidades. |
   | Desgloses | Seleccione las dimensiones que desee:     Estándar es el valor predeterminado, mientras que Personalizado incluye eVars y props. Se recomienda usar &quot;ID de visitante&quot; si se necesita información en el nivel de ID de visitante, en lugar de &quot;ID de visitante de Experience Cloud&quot;.<ul><li>El ID de visitante es el ID último utilizado por Analytics. Será AID (en el caso de un cliente heredado) o MID (si el cliente es nuevo o si borró las cookies desde el inicio del servicio ID de visitante de MC).</li><li>El ID de visitante de Experience Cloud solo se establecerá para clientes nuevos o que hayan borrado las cookies desde el inicio del servicio ID de visitante de MC.</li></ul> |
   | Métricas | Seleccione las métricas que desee. Estándar es el valor predeterminado, mientras que Personalizado incluye eventos personalizados. |
   | Vista previa del informe | Revise la configuración antes de programar el informe.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Programar envío | Introduzca una dirección de correo electrónico a la que enviar el archivo, asigne un nombre a este y, a continuación, seleccione [!UICONTROL Enviar inmediatamente].<br>Nota: El archivo se puede enviar mediante FTP desde [!UICONTROL Opciones de envío avanzadas]<br>![Programar envío](/help/main/c-reports/assets/datawarehouse3.png). |

1. Haga clic en **[!UICONTROL Solicitar este informe]**.

   El envío de archivos puede tardar hasta 72 horas, dependiendo de la cantidad de datos solicitados. Puede comprobar el progreso de la solicitud en cualquier momento haciendo clic en [!UICONTROL Herramientas] > [!UICONTROL Data Warehouse] > [!UICONTROL Solicitar administrador].

   Si desea volver a solicitar los datos que ha solicitado anteriormente, puede duplicar una solicitud antigua desde la [!UICONTROL Administrador de solicitudes] según sea necesario.

Para obtener más información sobre el [!DNL Data Warehouse], vea los siguientes vínculos en la documentación de ayuda de [!DNL Analytics]:

* [Crear una solicitud del Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [prácticas recomendadas de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
