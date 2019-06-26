---
description: Descargue datos en formato .csv para poder importarlos rápidamente a Excel, Access o cualquier otro programa de análisis de datos.
keywords: informes;informes de descargas;csv;métricas de éxito;detalles de pedidos
seo-description: Descargue datos en formato .csv para poder importarlos rápidamente a Excel, Access o cualquier otro programa de análisis de datos.
seo-title: Descarga de datos en un archivo CSV
solution: Target
subtopic: Prueba multivariable
title: Descarga de datos en un archivo CSV
topic: Standard
uuid: 9ac151e1-45a9-4d46-b23b-e7c9ae518253
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Descarga de datos en un archivo CSV{#downloading-data-in-a-csv-file}

Descargue datos en formato .csv para poder importarlos rápidamente a Excel, Access o cualquier otro programa de análisis de datos.

Para descargar datos en un archivo CSV:

1. Haga clic en [!DNL Activities] y luego en una actividad de la lista.

   Si tiene muchas actividades, puede filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Fuente de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Fuente de la actividad].

1. Haga clic en la pestaña **[!UICONTROL Informes].**
1. Haga clic en el icono [!UICONTROL Descargar] y, a continuación, seleccione un tipo de informe que quiera descargar para analizarlo en Excel y otras herramientas.

## Exportar informes a CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

El informe de métricas de éxito muestra información sobre las métricas de éxito, así como las siguientes métricas que no están disponibles en la interfaz de usuario de Target.

* Promedio de tiempo de la conversión (en horas), con lo cual podrá saber cuánto tarda el visitante promedio en alcanzar el punto de conversión
* Suma de los ingresos (al cuadrado) para los cálculos de confianza estadística sin conexión

Los datos se guardan hasta que finaliza la actividad.

>[!NOTE]
>
>El informe CSV solo incluye datos sin procesar y no incluye métricas calculadas como los ingresos por visitante, el alza o la confianza, utilizadas para las pruebas A/B. Para calcular estas métricas, descargue el archivo de Excel [Calculadora de confianza completa de Target](https://marketing.adobe.com/resources/help/en_US/target/target/complete_confidence_calculator.xlsx) para introducir el valor de la actividad o revisar los [cálculos estadísticos usados por Target](https://marketing.adobe.com/resources/help/en_US/target/target/statistical-calculations.pdf).

## Exportar detalles del pedido a un archivo .csv {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

El informe de detalles del pedido (conocido como el informe de auditoría en [!DNL Target Classic]) muestra información sobre sus pedidos, incluyendo datos como:

* Hora y fecha del pedido
* Cantidad de pedido (si insertó un mbox de realización de pedido)

   El informe de detalles del pedido solo funciona si tiene pedidos.

* Indicador de pedido (pedidos duplicados o extremos)

   Un pedido se marca como extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo). Los pedidos extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes. Para obtener más información, consulte [Exclusión de pedidos extremos](../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID del producto

   La longitud total de los ID de producto, concatenados con comas, no debe superar los 255 caracteres. En caso contrario, no se mostrarán adecuadamente en el informe. Por ejemplo, si su pedido tenía productos con ID “aa, bb”, la longitud total sería “aa,bb” = 5.

* Experiencia

   En el informe [!UICONTROL Detalles del pedido] para las actividades [!UICONTROL Prueba A/B], [!UICONTROL Segmentación de experiencias] (XT) y [!UICONTROL Prueba multivariable] (MVT), la columna [!UICONTROL Experiencia] contiene la experiencia `localId`. Este es el valor que resulta de `$campaign.recipe.id` en los token de la oferta.

   No existe la columna [!UICONTROL Experiencia] para las actividades de [!UICONTROL Personalización automatizada] (AP). La columna [!UICONTROL Nombre de algoritmo] actual ha sido sustituida con la terminología “Control” contra “Objetivos”, como se muestra en otras partes en [!DNL Target].

   Esto no afecta a las actividades de [!UICONTROL Recommendations].

>[!NOTE]
>
>* Los datos de informe de pedido incluyen cuatro semanas de datos para el entorno (grupo de hosts) predeterminado y dos semanas para todos los demás.
>* Las métricas de ingresos establecidas en “Aumentar recuento y mantener al usuario en la actividad” registran los detalles de pedido únicamente para el primer pedido realizado por el mismo visitante. Todos los pedidos posteriores aumentan el contador de conversión, pero no añaden ingresos a RPV/AOV/Sales y no se incluyen en el informe Detalles del pedido.


## Prácticas recomendadas

* Para registrar un registro de pedido, se deberá pasar el parámetro `orderTotal`.
* Los valores que se pasan mediante el parámetro de mbox `ProductPurchasedId` aparecen ahora recogidos en el informe de detalles del pedido.
* Una práctica recomendada es incluir un `orderID`, así como un `orderTotal`. Esto permite ignorar automáticamente los pedidos duplicados.

## Advertencias  {#section_49B9590904A645B18E694B4EFFFC1DEF}

La información siguiente se refiere a la opción Descargar:

* Puede descargar informes para las actividades A/B, Personalización automatizada, Segmentación de experiencias y multivariable. No puede descargar el informe de métricas de éxito para actividades de Recommendations.
* La opción Descargar no está disponible para actividades A/B ni Segmentación de experiencias creadas antes de la versión 15.7.1 de Target (julio de 2015).
* Las experiencias que no tienen datos asociados no se registran en el informe descargado.
* Las audiencias aplicadas en la interfaz de usuario de informes de Target no se transmiten al informe de descarga.
