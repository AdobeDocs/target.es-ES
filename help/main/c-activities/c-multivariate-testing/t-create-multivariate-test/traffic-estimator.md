---
keywords: estimación de tráfico;estimador de tráfico;estimación;tráfico;confianza;potencia estadística;alza;bonferroni;tasa de conversión;visitantes por día;duración
description: Aprenda a utilizar el estimador de tráfico para saber si cuenta con tráfico suficiente para que la actividad de [!DNL Adobe Target] [!UICONTROL Prueba multivariable] se realice correctamente.
title: ¿Cuánto tráfico se necesita para una actividad de [!UICONTROL Prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: 'https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 8%
---
# Calcular el tráfico necesario para una actividad [!UICONTROL Prueba multivariable] correcta {#traffic-estimator}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a usar el **[!UICONTROL Estimador de tráfico]** para comprobar si su actividad de **[!UICONTROL Prueba multivariable]** tiene tráfico suficiente para tener éxito.

>[!ENDSHADEBOX]

Una prueba multivariable compara varias experiencias, por lo que es importante saber cuánto tráfico se necesita para proporcionar resultados significativos. El **[!UICONTROL Estimador de tráfico]** usa estadísticas sobre tu página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesaria para que esta sea exitosa. También proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la prueba se realice correctamente.

El **[!UICONTROL estimador de tráfico]** predice el tamaño de muestra necesario para garantizar lo siguiente:

* **95% de confianza.** Esta estadística significa que la probabilidad de informar de un falso positivo si no hay un alza real es del 5 % (100 %: nivel de confianza).
* **80% de potencia estadística.** Esta estadística significa que la prueba tiene una probabilidad del 80 % de detectar un alza real del 25 % o más.
* **25% de alza mínima detectable de forma fiable.** [!DNL Target] calcula la cantidad de tráfico necesario para tener un 80% de probabilidades de detectar un alza real del 25% o más.

La prueba utiliza la corrección de Bonferroni para corregir varias comparaciones. Se sabe que este método es conservador, así que para equilibrarlo se aplica un alza mínima fiable detectable que es relativamente grande.

## Uso del estimador de tráfico {#use-traffic-estimator}

Mientras diseña una **[!UICONTROL Prueba multivariable]**, el **[!UICONTROL Estimador de tráfico]** le permite comprobar si el tráfico a su página es suficiente para la cantidad de experiencias que planea probar. Si ejecuta esta comprobación antes de iniciar la prueba, evitará tener que realizar una prueba que no llegue a suficientes visitantes para generar resultados significativos. También le mostrará cómo ajustar el número de combinaciones o la duración de la prueba si el tráfico no es suficiente.

1. En la página **[!UICONTROL Experiencias]** del **[!UICONTROL Compositor de experiencias visuales]** de una actividad **[!UICONTROL Multivariable]**, haga clic en el icono **[!UICONTROL Tráfico]** ( ![icono Estimador de tráfico](/help/main/assets/icons/Gauge2.svg) ) en la esquina superior izquierda de la página.

   Se abre **[!UICONTROL Estimador de tráfico]**. Para ocultarlo, vuelva a hacer clic en el icono.

   ![Interfaz de usuario del estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Cerca de la parte superior de **[!UICONTROL Estimador de tráfico]**, los valores que ingresó se calculan y se muestran los resultados.

1. (Opcional) Proporcione la tasa de conversión típica, la estimación de visitantes al día y la duración de la prueba.

   El **[!UICONTROL estimador de tráfico]** usa estas estadísticas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   | Métrica | Descripción |
   | --- | --- |
   | **[!UICONTROL Número de combinaciones de contenido]** | Esta métrica se calcula automáticamente, en función del número de experiencias que se crean como parte de la actividad, después de cualquier exclusión. |
   | **[!UICONTROL Tasa de conversión típica]** | Esta métrica se expresa como porcentaje según las estimaciones o los datos anteriores procedentes del sistema de análisis. |
   | **[!UICONTROL Visitantes estimados por día]** | Esta métrica es el número de visitantes que tienen probabilidades de ver esta página según los criterios de segmentación. Este número podría basarse en los datos de análisis. |
   | **[!UICONTROL Duración de la prueba]** | Número de días durante los cuales quiere ejecutar la actividad. |

1. Revise los resultados. Al cambiar estos números, también cambian las estimaciones.

   Por ejemplo, si está probando muchas experiencias y la tasa de conversión y las impresiones son demasiado bajas, **[!UICONTROL Estimador de tráfico]** muestra cuánto tiempo debe durar la prueba para que sea satisfactoria. O, si el tráfico es bajo, **[!UICONTROL Estimador de tráfico]** podría sugerir un número menor de experiencias para que pueda ejecutar la prueba durante el número de días deseado.

1. Si no tiene tráfico suficiente, siga uno o ambos de estos procedimientos:

   * Reduzca el número de combinaciones de las ofertas y el número de ubicaciones.
   * Aumentar la duración de la prueba.

1. Ajuste los números hasta que **[!UICONTROL Estimador de tráfico]** indique que tiene tráfico suficiente y luego diseñe la prueba en consecuencia.
