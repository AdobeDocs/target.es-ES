---
keywords: informes;informes de descargas;csv;métricas de éxito;detalles de pedidos
description: Obtenga información sobre cómo descargar datos desde Adobe [!DNL Target] actividades en formato CVS para una importación rápida a Excel, Access u otros programas de análisis de datos.
title: ¿Cómo se descargan datos de informes en un archivo CSV?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

---

# Descarga de datos en un archivo CSV

Descargue datos en formato .csv para poder importarlos rápidamente a Excel, Access o cualquier otro programa de análisis de datos.

Para descargar datos en un archivo CSV:

1. Haga clic en **[!UICONTROL Actividades]** y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Fuente de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Fuente de la actividad].

1. Haga clic en la pestaña **[!UICONTROL Informes]**.
1. Haga clic en el icono **[!UICONTROL Descargar]** y, a continuación, seleccione un tipo de informe que quiera descargar para analizarlo en Excel y otras herramientas.

   * [!UICONTROL Exportar informes a CSV]
   * [!UICONTROL Exportar detalles del pedido a un archivo .csv]

   ![Descargar opciones](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL Exportar informes a CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

El [!UICONTROL Métricas de éxito] Este informe muestra información sobre las métricas de éxito y las siguientes métricas que no están disponibles en el [!DNL Target] IU:

* Promedio de tiempo de la conversión (en horas), con lo cual podrá saber cuánto tarda el visitante promedio en alcanzar el punto de conversión
* Suma de los ingresos (al cuadrado) para los cálculos de confianza estadística sin conexión

Los datos se guardan hasta que finaliza la actividad.

>[!NOTE]
>
>El informe CSV solo incluye datos sin procesar y no incluye métricas calculadas como los ingresos por visitante, el alza o la confianza, utilizadas para las pruebas A/B. Para calcular estas métricas, descargue el [!DNL Target] [Calculadora de confianza completa](/help/main/assets/complete_confidence_calculator.xlsx) Archivo de Excel para introducir el valor de la actividad o revisar [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Exportar detalles del pedido a un archivo .csv] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

El [!UICONTROL Detalles del pedido] Este informe muestra información sobre sus pedidos, incluidos:

* Hora y fecha del pedido
* Cantidad de pedido (si insertó un mbox de realización de pedido)

   El [!UICONTROL Detalles del pedido] El informe solo funciona si tiene pedidos.

* Indicador de pedido (pedidos duplicados o extremos)

   Un pedido se marca como extremo si tiene más de +/- 3 desviaciones estándar del valor de pedido promedio. Este cálculo utiliza el último mes de datos (hasta el momento en que se realizó el cálculo). Los pedidos extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes. Para obtener más información, consulte [Exclusión de pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID del producto

   La longitud total de los ID de producto, concatenados con comas, no debe superar los 255 caracteres o los ID no se mostrarán correctamente en el informe. Por ejemplo, si su pedido tenía productos con ID “aa, bb”, la longitud total sería “aa,bb” = 5.

* Experiencia

   En el informe [!UICONTROL Detalles del pedido] para las actividades [!UICONTROL Prueba A/B], [!UICONTROL Segmentación de experiencias] (XT) y [!UICONTROL Prueba multivariable] (MVT), la columna [!UICONTROL Experiencia] contiene la experiencia `localId`. Este es el valor que resulta de `$campaign.recipe.id` en los token de la oferta.

   No existe la columna [!UICONTROL Experiencia] para las actividades de [!UICONTROL Personalización automatizada] (AP). La columna [!UICONTROL Nombre de algoritmo] actual ha sido sustituida con la terminología “Control” contra “Objetivos”, como se muestra en otras partes en [!DNL Target].

   Esto no afecta a las actividades de [!UICONTROL Recommendations].

>[!NOTE]
>
>* Los datos de informe de pedido incluyen cuatro semanas de datos para el entorno (grupo de hosts) predeterminado y dos semanas para todos los demás.
>* Métricas de ingresos configuradas como &quot;[!UICONTROL Incrementar el recuento y mantener al usuario en la actividad]&quot; registrar detalles de pedidos solo para el primer pedido realizado por el mismo visitante. Todos los pedidos subsiguientes aumentan el recuento de conversiones, pero no añaden ingresos a RPV/AOV/Sales y no se incluyen en la [!UICONTROL Detalles del pedido] informe.


## Prácticas recomendadas  

* Para registrar un registro de pedido, la variable `orderTotal` se debe pasar el parámetro.
* Los valores que se pasan mediante el parámetro de mbox `ProductPurchasedId` aparecen ahora recogidos en el informe de detalles del pedido.
* La práctica recomendada es incluir un `orderID` y un `orderTotal`. Esto permite ignorar automáticamente los pedidos duplicados.

## Advertencias  {#section_49B9590904A645B18E694B4EFFFC1DEF}

La siguiente información se aplica a [!UICONTROL Descargar] opción:

* Puede descargar ambos informes para [!UICONTROL Prueba A/B], [!UICONTROL Automated Personalization], [!UICONTROL Segmentación de experiencias], y [!UICONTROL Multivariado] actividades. No puede descargar el [!UICONTROL Métricas de éxito] informe para [!UICONTROL Recommendations] actividades.
* El [!UICONTROL Descargar] La opción no está disponible para [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] actividades creadas anteriormente [!DNL Target] versión 15.7.1 (julio de 2015).
* Las experiencias que no tienen datos asociados no se registran en el informe descargado.
* Audiencias aplicadas en [!DNL Target] La interfaz de usuario de creación de informes no se transfiere al informe de descarga.
* Los informes generados para su descarga como archivos .csv son incoherentes si la actividad utiliza más de una métrica. El informe descargable se genera solo en función de la configuración del informe y considera el mismo valor para cualquier otra métrica utilizada. La fuente de verdad es siempre el informe mostrado en la IU de [!DNL Target].
