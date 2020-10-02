---
keywords: traffic estimator;automated personalization;ap
description: El estimador de tráfico proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la actividad de Adobe Target tenga éxito.
title: Calcular el tráfico necesario para realizar una prueba con éxito
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: df9cb5c4a3cd44917ee9136300e4ad68f922d3c9
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 25%

---


# ![PREMIUM](/help/assets/premium.png) Estimar el tráfico necesario para realizar una prueba con éxito{#estimate-the-traffic-required-for-success}

The [!UICONTROL Traffic Estimator] provides feedback that lets you know whether you have sufficient traffic for your [!DNL Adobe Target] activity to succeed.

Because an [!UICONTROL Automated Personalization] activity uses multiple offer combinations, it is important to know how much traffic is required to provide meaningful results. The [!UICONTROL Traffic Estimator] uses statistics about your page and the number of experiences being tested to estimate the amount of traffic and the test duration needed to make the activity successful.

The [!UICONTROL Traffic Estimator] determines if there is enough traffic to generate personalized models, by comparing the estimated page impressions and typical conversion rate for the pages. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Esto ofrece tiempo suficiente para obtener el contenido personalizado y conocer qué contenido se publicará.

Remember that [!DNL Target] randomly serves experiences until the personalization algorithms are built. The checkmark icon beside each offer shows when the model for that offer is ready and [!DNL Target] is able to begin delivering personalized content. Ya que se espera un alza solo después de que los modelos estén listos, la indicación visual permite establecer la expectativa adecuada. Use the [!UICONTROL Traffic Estimator] in the [!UICONTROL Visual Experience Composer] (VEC) to get a guideline of when the models will be ready.

## Uso del estimador de tráfico

1. From the [!UICONTROL Visual Experience Composer], click **[!UICONTROL Traffic]**.

   ![Icono de tráfico](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   The [!UICONTROL Traffic Estimator] opens. You can click **[!UICONTROL Traffic]** again to hide the [!UICONTROL Traffic Estimator].

   ![](assets/ap_est.png)

1. Proporcione la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   * **Número de Ofertas**: Se calcula automáticamente en función del número de experiencias que se crean como parte de la actividad después de cualquier exclusión.
   * **Tasa de conversión típica**: la tasa de conversión se expresa como porcentaje según los datos o las estimaciones anteriores procedentes del sistema de Analytics.
   * **Visitas estimadas por día**: Es el número de visitas diarias de visitantes que pueden realizar la vista de la actividad, según los criterios de objetivo. Esta cifra puede estar basada en los datos de Analytics. Tenga en cuenta que este número debe ser las visitas, no los visitantes únicos.
   * **Duración de la prueba**: número de días durante los cuales quiere ejecutar la actividad.

   The [!UICONTROL Traffic Estimato]r uses these statistics to determine what adjustments are needed to run a successful test.

   Near the top of the [!UICONTROL Traffic Estimator], the values you entered are calculated and the results are shown.

   ![](assets/ap_est_no.png)

   Al cambiar estos números, también cambian las estimaciones. For example, if you are testing a large number of combinations and your conversion rate and impressions are too low, the [!UICONTROL Traffic Estimator] shows how long the test will need to run to be successful. Or, if your traffic is low, the [!UICONTROL Traffic Estimator] might suggest a lower number of offer combinations so you can run the test the desired number of days.

   Si no tiene tráfico suficiente, puede hacer una o todas las siguientes acciones:

   * Consider using an [Auto-Target](/help/c-activities/auto-target-to-optimize.md) activity instead of [!UICONTROL Automated Personalization] to create experiences with several offer changes in one experience variation.
   * Reduce the number of offer combinations within your [!UICONTROL Automated Personalization] activity.
   * Incremente la duración de la actividad.

   Adjust the numbers until the [!UICONTROL Traffic Estimator] says you have sufficient traffic, then design your test accordingly.

   ![](assets/ap_est_yes.png)

   If the traffic is sufficient, the [!UICONTROL Traffic] icon shows a green check. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.

## Preguntas más frecuentes sobre el estimador de tráfico

Tenga en cuenta las siguientes preguntas más frecuentes cuando trabaje con el estimador [!UICONTROL de tráfico]:

### ¿Por qué [!DNL Target] no se crean modelos personalizados cuando la actividad AP tiene tráfico suficiente?

En determinadas circunstancias, el tráfico puede ser lo suficientemente grande como para crear un modelo personalizado, pero ese tráfico podría informar [!DNL Target] que no hay ninguna diferencia significativa entre el modelo personalizado y el aleatorio. Aunque el modelo está integrado [!DNL Target] y probado, no se implementará porque no es significativamente mejor que el aleatorio.

Una posible razón para que el modelo no sea mejor que el aleatorio podría ser que las ofertas no son significativamente diferentes entre sí. Si este es el caso, puede intentar que las ofertas sean más distintas visualmente si los mensajes son similares o puede intentar cambiar los mensajes en sí.
