---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Aprenda a utilizar el estimador de tráfico que le permite saber si tiene tráfico suficiente para que la actividad  [!DNL Adobe Target] [!UICONTROL Multivariate Test] se realice correctamente.
title: ¿Cuánto tráfico se necesita para una actividad de [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
hide: true
hidefromtoc: true
source-git-commit: 4805da617962e29794bd3af16138f3887ad250d0
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# Calcular el tráfico necesario para una actividad [!UICONTROL Multivariate Test] correcta

Dado que una prueba multivariable compara varias experiencias, es importante conocer cuánto tráfico se requiere para proporcionar resultados significativos. [!UICONTROL Traffic Estimator] usa estadísticas sobre su página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesaria para que esta se realice correctamente.

El [!UICONTROL Traffic Estimator] predice el tamaño de muestra necesario para garantizar lo siguiente:

* 95% de confianza. Esta estadística significa que la probabilidad de informar de un falso positivo si no hay un alza real es del 5 % (100 %: nivel de confianza).
* 80% de potencia estadística. Esta estadística significa que la prueba tiene una probabilidad del 80 % de detectar un alza real del 25 % o más.
* 25% de elevación mínima detectable de forma fiable. [!DNL Target] calcula la cantidad de tráfico necesario para tener un 80% de probabilidades de detectar un alza real del 25% o más.

La prueba utiliza la corrección de Bonferroni para corregir varias comparaciones. Se sabe que este método es conservador, así que para equilibrarlo se aplica un alza mínima fiable detectable que es relativamente grande.

El [!UICONTROL Traffic Estimator] también proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la prueba que diseñó se realice correctamente.

1. Desde la página [!UICONTROL Experiences] de [!UICONTROL Visual Experience Composer] en una actividad [!UICONTROL Multivariate], haga clic en el icono **[!UICONTROL Traffic]** ( ![icono Estimador de tráfico](/help/main/assets/icons/Gauge2.svg) ) en la esquina superior izquierda de la página [!UICONTROL Experiences].

   Se abre [!UICONTROL Traffic Estimator].

   ![Interfaz de usuario del estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Para ocultar [!UICONTROL Traffic Estimator], vuelva a hacer clic en el icono.

   Cerca de la parte superior de [!UICONTROL Traffic Estimator], los valores especificados se calculan y se muestran los resultados.

1. (Condicional) Proporcione la tasa de conversión típica, la estimación de visitantes al día y la duración de la prueba.

   * **[!UICONTROL Number of Content Combinations]**: se calcula automáticamente según el número de experiencias que se crean como parte de la actividad después de cualquier exclusión.
   * **[!UICONTROL Typical Conversion Rate]**: la tasa de conversión se expresa como porcentaje según los datos o las estimaciones anteriores procedentes del sistema de Analytics.
   * **[!UICONTROL Estimated Visitors Per Day]**: es el número de visitantes que tienen probabilidades de ver esta página según los criterios de segmentación. Esta cifra puede estar basada en los datos de Analytics.
   * **[!UICONTROL Test Duration]**: número de días durante los cuales quiere ejecutar la actividad.

   [!UICONTROL Traffic Estimator] usa estas estadísticas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si está probando muchas experiencias y la tasa de conversión y las impresiones son demasiado bajas, [!UICONTROL Traffic Estimator] muestra durante cuánto tiempo debe ejecutarse la prueba para que tenga éxito. O bien, si el tráfico es bajo, [!UICONTROL Traffic Estimator] podría sugerir un número menor de experiencias para que pueda ejecutar la prueba el número deseado de días.

   Si no tiene tráfico suficiente, puede hacer una de estas acciones, o las dos:

   * Reduzca el número de combinaciones de las ofertas y el número de ubicaciones.
   * Aumentar la duración de la prueba.

   Ajuste los números hasta que [!UICONTROL Traffic Estimator] indique que tiene tráfico suficiente y, a continuación, diseñe la prueba según corresponda.
