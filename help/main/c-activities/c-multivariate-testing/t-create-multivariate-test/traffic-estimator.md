---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Aprenda a utilizar el estimador de tráfico para saber si cuenta con tráfico suficiente para que la actividad de  [!DNL Adobe Target] [!UICONTROL Prueba multivariada] se realice correctamente.
title: ¿Cuánto tráfico se necesita para una actividad de [!UICONTROL Prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 19%

---

# Calcular el tráfico necesario para una actividad [!UICONTROL Prueba multivariable] correcta

Dado que una prueba multivariable compara varias experiencias, es importante conocer cuánto tráfico se requiere para proporcionar resultados significativos. El [!UICONTROL Estimador de tráfico] usa estadísticas sobre tu página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesaria para que esta sea exitosa.

El [!UICONTROL estimador de tráfico] predice el tamaño de muestra necesario para garantizar lo siguiente:

* 95% de confianza. Esta estadística significa que la probabilidad de informar de un falso positivo si no hay un alza real es del 5 % (100 %: nivel de confianza).
* 80% de potencia estadística. Esta estadística significa que la prueba tiene una probabilidad del 80 % de detectar un alza real del 25 % o más.
* 25% de elevación mínima detectable de forma fiable. [!DNL Target] calcula la cantidad de tráfico necesario para tener un 80% de probabilidades de detectar un alza real del 25% o más.

La prueba utiliza la corrección de Bonferroni para corregir varias comparaciones. Se sabe que este método es conservador, así que para equilibrarlo se aplica un alza mínima fiable detectable que es relativamente grande.

El [!UICONTROL Estimador de tráfico] también proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la prueba que diseñó se realice correctamente.

1. En la página [!UICONTROL Experiencias] del [!UICONTROL Compositor de experiencias visuales] de una actividad [!UICONTROL Multivariable], haga clic en el icono **[!UICONTROL Tráfico]** (![icono Estimador de tráfico](/help/main/assets/icons/Gauge2.svg) ) en la esquina superior izquierda de la página [!UICONTROL Experiencias].

   Se abre [!UICONTROL Estimador de tráfico].

   ![Interfaz de usuario del estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Puede hacer clic de nuevo en el icono para ocultar [!UICONTROL Estimador de tráfico].

   Cerca de la parte superior de [!UICONTROL Estimador de tráfico], los valores que ingresaste se calcularán y se mostrarán los resultados.

1. (Condicional) Proporcione la tasa de conversión típica, la estimación de visitantes al día y la duración de la prueba.

   * **[!UICONTROL Número de combinaciones de contenido]**: se calcula automáticamente según el número de experiencias que se crean como parte de la actividad después de cualquier exclusión.
   * **[!UICONTROL Tasa de conversión típica]**: la tasa de conversión se expresa como porcentaje según los datos o las estimaciones anteriores procedentes del sistema de Analytics.
   * **[!UICONTROL Visitantes estimados por día]**: Este es el número de visitantes que tienen probabilidades de ver esta página según los criterios de segmentación. Esta cifra puede estar basada en los datos de Analytics.
   * **[!UICONTROL Duración de la prueba]**: El número de días durante los cuales quiere ejecutar la actividad.

   El [!UICONTROL estimador de tráfico] usa estas estadísticas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si está probando muchas experiencias y la tasa de conversión y las impresiones son demasiado bajas, [!UICONTROL Estimador de tráfico] muestra cuánto tiempo debe durar la prueba para que sea satisfactoria. O, si el tráfico es bajo, [!UICONTROL Estimador de tráfico] podría sugerir un número menor de experiencias para que pueda ejecutar la prueba el número deseado de días.

   Si no tiene tráfico suficiente, puede hacer una de estas acciones, o las dos:

   * Reduzca el número de combinaciones de las ofertas y el número de ubicaciones.
   * Aumentar la duración de la prueba.

   Ajuste los números hasta que el [!UICONTROL Estimador de tráfico] indique que tiene tráfico suficiente y luego diseñe la prueba en consecuencia.
