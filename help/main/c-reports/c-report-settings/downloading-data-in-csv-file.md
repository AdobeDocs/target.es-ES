---
keywords: informes;informes de descargas;csv;métricas de éxito;detalles de pedidos
description: Aprenda a descargar datos de actividades de Adobe [!DNL Target] en formato CVS para importarlos rápidamente a Excel, Access u otros programas de análisis de datos.
title: ¿Cómo se descargan datos de informes en un archivo CSV?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 34%

---

# Descarga de datos en un archivo CSV

Descargue datos en formato .csv para poder importarlos rápidamente a [!DNL Excel], [!DNL Access] u otros programas de análisis de datos.

Para descargar datos en un archivo CSV:

1. Haga clic en **[!UICONTROL Activities]** y luego en una actividad de la lista.

   Si tiene muchas actividades, haga clic en el icono Filtro ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] y [!UICONTROL Activity Source].

1. Haga clic en la ficha **[!UICONTROL Reports]**.
1. Haga clic en el icono **[!UICONTROL Download]** ( ![Icono de descarga](/help/main/assets/icons/Download.svg) ) y, a continuación, seleccione un tipo de informe que quiera descargar para analizarlo en Excel y otras herramientas.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

El informe [!UICONTROL Success Metrics] muestra información sobre las métricas de éxito y las siguientes métricas que no están disponibles en la interfaz de usuario de [!DNL Target]:

* Promedio de tiempo de la conversión (en horas), con lo cual podrá saber cuánto tarda el visitante promedio en alcanzar el punto de conversión
* Suma de los ingresos (al cuadrado) para los cálculos de confianza estadística sin conexión

Los datos se guardan hasta que finaliza la actividad.

>[!NOTE]
>
>El informe CSV solo incluye datos sin procesar y no incluye métricas calculadas como los ingresos por visitante, el alza o la confianza, utilizadas para las pruebas A/B. Para calcular estas métricas calculadas, descargue el archivo de Excel [!DNL Target] [Calculadora de confianza completa](/help/main/assets/complete_confidence_calculator.xlsx) para escribir el valor de la actividad o revise [cálculos estadísticos en pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

El informe [!UICONTROL Order Details] muestra información sobre sus pedidos, incluidos:

* Hora y fecha del pedido
* Cantidad de pedido (si insertó un mbox de realización de pedido)

  El informe [!UICONTROL Order Details] solo funciona si tiene pedidos.

* Indicador de pedido (pedidos duplicados o extremos)

  Un pedido se marca como extremo si tiene más de +/- 3 desviaciones estándar del valor de pedido promedio. Este cálculo utiliza el último mes de datos (hasta el momento en que se realizó el cálculo). Los pedidos extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes. Para obtener más información, consulte [Exclusión de pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID del producto

  La longitud total de los ID de producto, concatenados con comas, no debe superar los 255 caracteres o los ID no se mostrarán correctamente en el informe. Por ejemplo, si su pedido tenía productos con ID “aa, bb”, la longitud total sería “aa,bb” = 5.

* Experiencia

  En el informe [!UICONTROL Order Details] para las actividades [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT) y [!UICONTROL Multivariate Test] (MVT), la columna [!UICONTROL Experience] contiene la experiencia `localId`. Este es el valor que resulta de `$campaign.recipe.id` en los token de la oferta.

  No hay una columna [!UICONTROL Experience] para las actividades [!UICONTROL Automated Personalization] (AP). La columna actual [!UICONTROL Algorithm Name] se ha reemplazado con la terminología &quot;Control&quot; contra &quot;Objetivos&quot;, como se muestra en otras partes de [!DNL Target].

  No hubo ningún impacto en [!UICONTROL Recommendations] actividades.

>[!NOTE]
>
>* Los datos de informe de pedido incluyen cuatro semanas de datos para el entorno (grupo de hosts) predeterminado y dos semanas para todos los demás.
>* Las métricas de ingresos establecidas en &quot;[!UICONTROL Increment count and keep the user in the activity]&quot; registran los detalles de pedido únicamente para el primer pedido realizado por el mismo visitante. Todos los pedidos subsiguientes aumentan el recuento de conversiones, pero no agregan ingresos a RPV/AOV/Sales y no se incluyen en el informe [!UICONTROL Order Details].

## Prácticas recomendadas  

* Para registrar un registro de pedido, se debe pasar el parámetro `orderTotal`.
* Los valores pasados a través del parámetro de mbox `ProductPurchasedId` se enumeran en el informe [!UICONTROL Order Details].
* La práctica recomendada es incluir un `orderID` y un `orderTotal`. Esto permite ignorar automáticamente los pedidos duplicados.

## Advertencias  {#section_49B9590904A645B18E694B4EFFFC1DEF}

La siguiente información se aplica a la opción [!UICONTROL Download]:

* Puede descargar ambos informes para las actividades [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], [!UICONTROL Experience Targeting] y [!UICONTROL Multivariate]. No puede descargar el informe [!UICONTROL Success Metrics] para [!UICONTROL Recommendations] actividades.
* La opción [!UICONTROL Download] no está disponible para las actividades [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] creadas antes de [!DNL Target] versión 15.7.1 (julio de 2015).
* Las experiencias que no tienen datos asociados no se registran en el informe descargado.
* Las audiencias aplicadas en la interfaz de usuario de informes [!DNL Target] no se transfieren al informe de descarga.
* Los informes generados para su descarga como archivos .csv son incoherentes si la actividad utiliza más de una métrica. El informe descargable se genera solo en función de la configuración del informe y considera el mismo valor para cualquier otra métrica utilizada. La fuente de verdad es siempre el informe mostrado en la IU de [!DNL Target].
