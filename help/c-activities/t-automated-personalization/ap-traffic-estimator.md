---
keywords: estimador de tráfico;personalización automatizada;ap;estimación de tráfico;segmentación automática
description: Utilice el estimador de tráfico de Adobe Target para determinar si tiene tráfico suficiente para que su actividad de Automated Personalization se realice correctamente.
title: ¿Cuánto tráfico se necesita para una actividad de éxito?
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 13%

---

# ![PREMIUM](/help/assets/premium.png) Estimar el tráfico necesario para realizar una prueba con éxito

El [!DNL Adobe Target] [!UICONTROL Estimador de tráfico] proporciona información que le permite saber si tiene tráfico suficiente para que su actividad [!UICONTROL Automated Personalization] tenga éxito.

Dado que una actividad de [!UICONTROL Automated Personalization] utiliza varias combinaciones de ofertas, es importante saber cuánto tráfico se necesita para proporcionar resultados significativos. El [!UICONTROL Estimador de tráfico] usa estadísticas sobre la página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesarios para que la actividad tenga éxito.

El [!UICONTROL Estimador de tráfico] determina si hay tráfico suficiente para generar modelos personalizados mediante la comparación de las impresiones de página estimadas y la tasa de conversión típica para las páginas. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Este proceso le permite disponer de tiempo suficiente para obtener contenido personalizado y saber qué contenido entregar.

Recuerde que [!DNL Target] proporciona experiencias de forma aleatoria hasta que se crean los algoritmos de personalización. El icono de marca de verificación junto a cada oferta muestra cuándo el modelo para esa oferta está listo y [!DNL Target] puede comenzar a enviar contenido personalizado. Ya que se espera un alza solo después de que los modelos estén listos, la indicación visual permite establecer la expectativa adecuada. Utilice el [!UICONTROL Estimador de tráfico] del [!UICONTROL Compositor de experiencias visuales] (VEC) para obtener instrucciones sobre cuándo están listos los modelos.

## Uso del estimador de tráfico

1. En el [!UICONTROL Compositor de experiencias visuales], haga clic en **[!UICONTROL Tráfico]**.

   ![Icono de tráfico](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   Se abre el [!UICONTROL Estimador de tráfico]. Puede volver a hacer clic en **[!UICONTROL Tráfico]** para ocultar el [!UICONTROL Estimador de tráfico].

   ![Interfaz de usuario del estimador de tráfico](assets/ap_est.png)

1. Especifique la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   | Métrica | Descripción |
   | --- | --- |
   | **[!UICONTROL Número de ofertas]** | Esta métrica se calcula automáticamente en función del número de experiencias que se crean como parte de la actividad, después de cualquier exclusión. |
   | **[!UICONTROL Tasa de conversión típica]** | Esta métrica se expresa como un porcentaje, en función de los datos o las estimaciones anteriores procedentes del sistema de Analytics. |
   | **[!UICONTROL Visitas estimadas por día]** | Esta métrica es el número de visitas por día de visitantes que pueden ver la actividad según los criterios de segmentación. Esta métrica se puede basar en los datos de análisis. Este número debe ser visitas, no visitantes únicos. |
   | **[!UICONTROL Duración de la prueba]** | Número de días durante los cuales quiere ejecutar la actividad. |

   El [!UICONTROL Estimador de tráfico] usa estas métricas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   Cerca de la parte superior del [!UICONTROL Estimador de tráfico], se calculan los valores introducidos y se muestran los resultados.

   ![Estimación de tráfico con valores y resultados mostrados](assets/ap_est_no.png)

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si está probando muchas combinaciones y la tasa de conversión y las impresiones son demasiado bajas, el [!UICONTROL Estimador de tráfico] muestra cuánto tiempo debe ejecutarse la prueba para que tenga éxito. O, si el tráfico es escaso, el [!UICONTROL Estimador de tráfico] podría sugerir un número menor de combinaciones de ofertas para que pueda ejecutar la prueba durante el número de días deseado.

   Si no tiene tráfico suficiente, tenga en cuenta lo siguiente:

   * Considere la posibilidad de utilizar una actividad de [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) en lugar de [!UICONTROL Automated Personalization] para crear experiencias con varios cambios de oferta en una variación de experiencia.
   * Reduzca el número de combinaciones de ofertas dentro de su actividad [!UICONTROL Automated Personalization].
   * Incremente la duración de la actividad.

   Ajuste los números hasta que el [!UICONTROL Estimador de tráfico] indique que tiene tráfico suficiente y, a continuación, diseñe la prueba en consecuencia.

   ![Estimador de tráfico que muestra un mensaje de tráfico suficiente](assets/ap_est_yes.png)

   Si el tráfico es suficiente, el icono [!UICONTROL Tráfico] muestra una marca de verificación verde. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.

## Preguntas más frecuentes sobre el estimador de tráfico

Tenga en cuenta las siguientes preguntas frecuentes mientras trabaja con el [!UICONTROL Estimador de tráfico]:

### ¿Por qué no se crean modelos personalizados aunque mi actividad AP tenga tráfico suficiente?

En determinadas circunstancias, el tráfico es lo suficientemente grande como para crear un modelo personalizado, pero ese tráfico podría informar a [!DNL Target] de que no hay diferencia significativa entre el modelo personalizado y el aleatorio. Aunque el modelo está construido en [!DNL Target] y probado, no se implementa porque el modelo no es mejor que aleatorio.

Una posible razón para que el modelo no sea mejor que aleatorio podría ser que las ofertas no son lo suficientemente diferentes entre sí. Si es así, puede intentar hacer que las ofertas sean más diferentes visualmente si la mensajería es similar o puede intentar cambiar la propia mensajería.
