---
description: El estimador de tráfico proporciona información que le permite conocer si tiene tráfico suficiente para que tenga éxito su actividad.
title: Calcular el tráfico necesario para realizar una prueba con éxito
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Estimar el tráfico necesario para realizar una prueba con éxito{#estimate-the-traffic-required-for-success}

El estimador de tráfico proporciona información que le permite conocer si tiene tráfico suficiente para que tenga éxito su actividad.

Debido a que la actividad de Personalización automatizada utiliza varias combinaciones de ofertas, es importante conocer cuánto tráfico es necesario para obtener resultados significativos. El estimador de tráfico usa datos estadísticos sobre su página y el número de experiencias que se están probando para calcular la cantidad de tráfico y la duración de la prueba necesarios para que la actividad se realice con éxito.

El estimador de tráfico determina si hay suficiente tráfico para generar modelos personalizados, mediante la comparación de la estimación de impresiones de página y la tasa de conversión típica para las páginas. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Esto ofrece tiempo suficiente para obtener el contenido personalizado y conocer qué contenido se publicará.

Recuerde que Target ofrece experiencias aleatoriamente hasta que se crean los algoritmos de personalización. El icono de marca de verificación junto a cada oferta muestra cuándo está listo el modelo para esa oferta y Target puede comenzar a entregar contenido personalizado. Ya que se espera un alza solo después de que los modelos estén listos, la indicación visual permite establecer la expectativa adecuada. Use el estimador de tráfico en el Compositor de experiencias visuales (VEC) para obtener instrucciones sobre cuándo estarán listos los modelos.

1. En el Compositor de experiencias, haga clic en **[!UICONTROL Tráfico]**.

   ![Icono de tráfico](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   Se abre el estimador de tráfico. Para ocultarlo, puede volver a hacer clic en **[!UICONTROL Estimador de tráfico]**.

   ![](assets/ap_est.png)

1. Proporcione la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   * Número de combinaciones de contenido: se calcula automáticamente según el número de experiencias que se crean como parte de la actividad después de cualquier exclusión.
   * Tasa de conversión típica: la tasa de conversión se expresa como porcentaje según los datos o las estimaciones anteriores procedentes del sistema de Analytics.
   * Visitas estimadas por día: es el número de visitas por día de visitantes que pueden ver la actividad según los criterios de segmentación. Esta cifra puede estar basada en los datos de Analytics. Tenga en cuenta que este número debe ser las visitas, no los visitantes únicos.
   * Duración de la prueba: número de días durante los cuales quiere ejecutar la actividad.

   El estimador de tráfico utiliza estas estadísticas para determinar qué ajustes se necesitan para ejecutar una prueba con éxito.

   Cerca de la parte superior del estimador de tráfico, se calculan los valores que ha indicado y se muestran los resultados.

   ![](assets/ap_est_no.png)

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si va a probar un gran número de combinaciones y la tasa de conversión y las impresiones son demasiado bajas, el estimador de tráfico muestra el tiempo que deberá ejecutarse la prueba para que tenga éxito. O, si el tráfico es escaso, es posible que el estimador de tráfico sugiera un menor número de combinaciones de ofertas para poder ejecutar la prueba durante el número de días que desee.

   Si no tiene tráfico suficiente, puede hacer una o todas las siguientes acciones:

   * Puede usar la segmentación automática en lugar de la personalización automatizada para crear experiencias con varios cambios de oferta en una variación de experiencia.
   * Reduzca el número de combinaciones de ofertas dentro de su actividad de personalización automatizada.
   * Incremente la duración de la actividad.

   Ajuste las cifras hasta que el estimador de tráfico le indique que tiene tráfico suficiente y, después, diseñe la prueba según corresponda.

   ![](assets/ap_est_yes.png)

   Si hay suficiente tráfico, el icono Tráfico muestra una marca de verificación verde. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.
