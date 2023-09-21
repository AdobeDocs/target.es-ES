---
keywords: estimador de tráfico;personalización automatizada;ap;estimar tráfico
description: Utilice el [!DNL Adobe Target] [!UICONTROL Estimador de tráfico] para determinar si tiene tráfico suficiente para su [!UICONTROL Automated Personalization] actividad para realizar correctamente.
title: La cantidad de tráfico necesario para un [!UICONTROL Automated Personalization] ¿Actividad?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 10%

---

# Calcular el tráfico necesario para realizar una prueba con éxito

El [!DNL Adobe Target] [!UICONTROL Estimador de tráfico] proporciona comentarios que le permiten saber si tiene tráfico suficiente para su [!UICONTROL Automated Personalization] La actividad (AP) debe realizarse correctamente.

Porque [!UICONTROL Automated Personalization] Las actividades de utilizan varias combinaciones de ofertas, por lo que es importante saber cuánto tráfico se requiere para proporcionar resultados significativos. El [!UICONTROL Estimador de tráfico] utiliza estadísticas sobre su página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesaria para que la actividad tenga éxito.

El [!UICONTROL Estimador de tráfico] determina si hay tráfico suficiente para generar modelos personalizados comparando las impresiones de página estimadas y la tasa de conversión típica de las páginas. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Este proceso permite tiempo suficiente para obtener contenido personalizado y aprender qué contenido entregar.

Recuerde que [!DNL Target] proporciona experiencias de forma aleatoria hasta que se crean los algoritmos de personalización. El icono de marca de verificación junto a cada oferta muestra cuándo el modelo de esa oferta está listo y [!DNL Target] puede empezar a enviar contenido personalizado. Dado que el alza solo se espera después de que los modelos estén listos, la indicación visual le permite establecer la expectativa correcta. Utilice el [!UICONTROL Estimador de tráfico] en el [!UICONTROL Compositor de experiencias visuales] (VEC) para obtener una guía de cuándo están listos los modelos.

## Uso del estimador de tráfico

1. Desde el [!UICONTROL Experiencias] página de la [!UICONTROL Compositor de experiencias visuales] en un [!UICONTROL Automated Personalization] actividad, haga clic en  **[!UICONTROL Tráfico]** icono.

   ![Icono de tráfico](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   El [!UICONTROL Estimador de tráfico] abre. Puede hacer clic en **[!UICONTROL Tráfico]** de nuevo para ocultar el [!UICONTROL Estimador de tráfico].

   ![Interfaz de usuario del estimador de tráfico](assets/ap_est.png)

1. Especifique la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   | Métrica | Descripción |
   | --- | --- |
   | **[!UICONTROL Número de ofertas]** | Esta métrica se calcula automáticamente según el número de experiencias que se crean como parte de la actividad, después de cualquier exclusión. |
   | **[!UICONTROL Tasa de conversión típica]** | Esta métrica se expresa como porcentaje según las estimaciones o los datos anteriores procedentes del sistema de análisis. |
   | **[!UICONTROL Visitas estimadas por día]** | Esta métrica es el número de visitas por día de visitantes que pueden ver la actividad según los criterios de segmentación. Esta métrica se puede basar en los datos de análisis. Este número debe ser visitas, no visitantes únicos. |
   | **[!UICONTROL Duración de la prueba]** | Número de días durante los cuales quiere ejecutar la actividad. |

   El [!UICONTROL Estimador de tráfico] utiliza estas métricas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   Cerca de la parte superior del [!UICONTROL Estimador de tráfico], los valores introducidos se calculan y se muestran los resultados.

   ![Estimación del tráfico con valores y resultados mostrados](assets/ap_est_no.png)

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si está probando muchas combinaciones y la tasa de conversión y las impresiones son demasiado bajas, la variable [!UICONTROL Estimador de tráfico] muestra cuánto tiempo debe durar la ejecución de la prueba para que tenga éxito. O, si el tráfico es bajo, la variable [!UICONTROL Estimador de tráfico] podría sugerir un número menor de combinaciones de ofertas para que pueda ejecutar la prueba el número deseado de días.

   Si no tiene tráfico suficiente, tenga en cuenta lo siguiente:

   * Considere utilizar un [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) actividad en lugar de [!UICONTROL Automated Personalization] para crear experiencias con varios cambios de oferta en una variación de experiencia.
   * Reduzca el número de combinaciones de ofertas dentro de su [!UICONTROL Automated Personalization] actividad.
   * Incremente la duración de la actividad.

   Ajuste los números hasta que [!UICONTROL Estimador de tráfico] indica que tiene tráfico suficiente y, a continuación, diseñe la prueba en consecuencia.

   ![Estimador de tráfico que muestra un mensaje de tráfico suficiente](assets/ap_est_yes.png)

   Si el tráfico es suficiente, la variable [!UICONTROL Tráfico] El icono muestra una marca de verificación verde. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.

## Preguntas más frecuentes sobre el estimador de tráfico

Tenga en cuenta las siguientes preguntas frecuentes al trabajar con [!UICONTROL Estimador de tráfico]:

### ¿Por qué los modelos personalizados no se crean aunque mi actividad de AP tenga tráfico suficiente?

En determinadas circunstancias, el tráfico es lo suficientemente grande como para crear un modelo personalizado, pero ese tráfico podría informar [!DNL Target] que no hay ninguna diferencia significativa entre el modelo personalizado y el aleatorio. Aunque el modelo esté integrado [!DNL Target] y probado, no se implementa porque el modelo no es mejor que random.

Una posible razón para que el modelo no sea mejor que aleatorio podría ser que las ofertas no son lo suficientemente diferentes entre sí. Si es así, puede intentar hacer que las ofertas sean más visualmente diferentes si la mensajería es similar, o puede intentar cambiar la mensajería en sí.
