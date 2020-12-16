---
keywords: traffic estimator;automated personalization;ap
description: El estimador de tráfico proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la actividad de Adobe Target tenga éxito.
title: Calcular el tráfico necesario para realizar una prueba con éxito
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 25%

---


# ![PREMIUM](/help/assets/premium.png) Estimar el tráfico necesario para realizar una prueba con éxito{#estimate-the-traffic-required-for-success}

El [!UICONTROL Estimador de tráfico] proporciona información que le permite saber si tiene tráfico suficiente para que su actividad [!DNL Adobe Target] tenga éxito.

Dado que una actividad [!UICONTROL Automated Personalization] utiliza múltiples combinaciones de ofertas, es importante saber cuánto tráfico se necesita para proporcionar resultados significativos. El [!UICONTROL Estimador de tráfico] utiliza estadísticas sobre la página y el número de experiencias que se están probando para calcular la cantidad de tráfico y la duración de la prueba necesarios para que la actividad tenga éxito.

El [!UICONTROL Estimador de tráfico] determina si hay tráfico suficiente para generar modelos personalizados, comparando las impresiones de página estimadas y la tasa de conversión típica de las páginas. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Esto ofrece tiempo suficiente para obtener el contenido personalizado y conocer qué contenido se publicará.

Recuerde que [!DNL Target] proporciona experiencias de forma aleatoria hasta que se crean los algoritmos de personalización. El icono de marca de verificación que aparece junto a cada oferta muestra cuándo está listo el modelo para esa oferta y [!DNL Target] puede empezar a entregar contenido personalizado. Ya que se espera un alza solo después de que los modelos estén listos, la indicación visual permite establecer la expectativa adecuada. Use el [!UICONTROL Estimador de tráfico] del [!UICONTROL Compositor de experiencias visuales] (VEC) para obtener una guía de cuándo estarán listos los modelos.

## Uso del estimador de tráfico

1. En el [!UICONTROL Compositor de experiencias visuales], haga clic en **[!UICONTROL Tráfico]**.

   ![Icono de tráfico](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   Se abre el [!UICONTROL Estimador de tráfico]. Puede volver a hacer clic en **[!UICONTROL Tráfico]** para ocultar el [!UICONTROL Estimador de tráfico].

   ![](assets/ap_est.png)

1. Proporcione la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   * **Número de Ofertas**: Se calcula automáticamente en función del número de experiencias que se crean como parte de la actividad después de cualquier exclusión.
   * **Tasa de conversión típica**: la tasa de conversión se expresa como porcentaje según los datos o las estimaciones anteriores procedentes del sistema de Analytics.
   * **Visitas estimadas por día**: Es el número de visitas diarias de visitantes que pueden realizar la vista de la actividad, según los criterios de objetivo. Esta cifra puede estar basada en los datos de Analytics. Tenga en cuenta que este número debe ser las visitas, no los visitantes únicos.
   * **Duración de la prueba**: número de días durante los cuales quiere ejecutar la actividad.

   La [!UICONTROL Estimación de tráfico]r utiliza estas estadísticas para determinar qué ajustes son necesarios para ejecutar una prueba exitosa.

   Cerca de la parte superior del [!UICONTROL Estimador de tráfico], se calculan los valores introducidos y se muestran los resultados.

   ![](assets/ap_est_no.png)

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo: si está probando un gran número de combinaciones y la tasa de conversión y las impresiones son demasiado bajas, el [!UICONTROL Estimador de tráfico] muestra cuánto tiempo tendrá que ejecutarse la prueba para que tenga éxito. O bien, si el tráfico es bajo, el [!UICONTROL Estimador de tráfico] puede sugerir un número menor de combinaciones de ofertas para que pueda ejecutar la prueba el número deseado de días.

   Si no tiene tráfico suficiente, puede hacer una o todas las siguientes acciones:

   * Considere utilizar una actividad [Destinatario automático](/help/c-activities/auto-target/auto-target-to-optimize.md) en lugar de [!UICONTROL Automated Personalization] para crear experiencias con varios cambios de oferta en una variación de experiencia.
   * Reduzca el número de combinaciones de ofertas dentro de su actividad [!UICONTROL Automated Personalization].
   * Incremente la duración de la actividad.

   Ajuste los números hasta que el [!UICONTROL Estimador de tráfico] indique que tiene tráfico suficiente y luego diseñe la prueba en consecuencia.

   ![](assets/ap_est_yes.png)

   Si el tráfico es suficiente, el icono [!UICONTROL Tráfico] muestra una marca de verificación verde. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.

## Preguntas más frecuentes sobre el estimador de tráfico

Tenga en cuenta las siguientes preguntas más frecuentes cuando trabaje con el [!UICONTROL Estimador de tráfico]:

### ¿Por qué [!DNL Target] no genera modelos personalizados cuando mi actividad AP tiene tráfico suficiente?

En determinadas circunstancias, el tráfico puede ser lo suficientemente grande como para que se cree un modelo personalizado, pero ese tráfico podría informar [!DNL Target] de que no hay ninguna diferencia significativa entre el modelo personalizado y el aleatorio. Aunque el modelo está integrado [!DNL Target] y se ha probado, no se implementará porque no es significativamente mejor que el aleatorio.

Una posible razón para que el modelo no sea mejor que el aleatorio podría ser que las ofertas no son significativamente diferentes entre sí. Si este es el caso, puede intentar que las ofertas sean más distintas visualmente si los mensajes son similares o puede intentar cambiar los mensajes en sí.
