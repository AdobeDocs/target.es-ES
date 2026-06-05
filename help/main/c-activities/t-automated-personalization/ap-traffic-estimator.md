---
keywords: estimador de tráfico;personalización automatizada;ap;estimar tráfico
description: Use el [!UICONTROL Estimador de tráfico] para saber si tiene tráfico suficiente para que una actividad de [!UICONTROL Automated Personalization] se realice correctamente.
title: ¿Cuánto tráfico es necesario para una actividad [!UICONTROL Automated Personalization] correcta?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 794
ht-degree: 8%

---

# Calcular el tráfico necesario para realizar una prueba con éxito

El [!DNL Adobe Target] [!UICONTROL estimador de tráfico] proporciona comentarios que le permiten saber si tiene tráfico suficiente para que la actividad de [!UICONTROL Automated Personalization] (AP) se realice correctamente.

Dado que las actividades de [!UICONTROL Automated Personalization] utilizan varias combinaciones de ofertas, es importante saber cuánto tráfico se requiere para proporcionar resultados significativos. El [!UICONTROL Estimador de tráfico] usa estadísticas sobre tu página y el número de experiencias que se están probando para estimar la cantidad de tráfico y la duración de la prueba necesaria para que la actividad tenga éxito.

El [!UICONTROL estimador de tráfico] determina si hay tráfico suficiente para generar modelos personalizados al comparar las impresiones de página estimadas y la tasa de conversión típica de las páginas. Para lograr una actividad con éxito, lo ideal es que el tamaño de muestra correcto garantice que el contenido personalizado esté listo dentro del 50 % de la duración de la actividad o en 14 días, lo que sea menos. Este proceso permite tiempo suficiente para obtener contenido personalizado y aprender qué contenido entregar.

Recuerde que [!DNL Target] proporciona experiencias de forma aleatoria hasta que se crean los algoritmos de personalización. El icono de marca de verificación al lado de cada oferta muestra cuándo el modelo de esa oferta está listo y [!DNL Target] puede empezar a entregar contenido personalizado. Dado que el alza solo se espera después de que los modelos estén listos, la indicación visual le permite establecer la expectativa correcta. Use el [!UICONTROL Estimador de tráfico] en el [!UICONTROL Compositor de experiencias visuales] (VEC) para obtener una guía de cuándo los modelos están listos.

## Uso del estimador de tráfico

1. En la página [!UICONTROL Experiencias] del [!UICONTROL Compositor de experiencias visuales] en una actividad de [!UICONTROL Automated Personalization], haga clic en el icono **[!UICONTROL Tráfico]** ( ![icono Estimador de tráfico](/help/main/assets/icons/Gauge2.svg) ) en la esquina superior izquierda de la página [!UICONTROL Experiencias].

   Se abre [!UICONTROL Estimador de tráfico].

   ![Interfaz de usuario del estimador de tráfico](assets/ap-est.png)

   Puede hacer clic de nuevo en el icono para ocultar [!UICONTROL Estimador de tráfico].

1. Especifique la tasa de conversión típica (o la tasa de conversión que espera de esta actividad), las impresiones de actividad estimadas por día y la duración de la prueba.

   | Métrica | Descripción |
   | --- | --- |
   | **[!UICONTROL Número de ofertas]** | Esta métrica se calcula automáticamente según el número de experiencias que se crean como parte de la actividad, después de cualquier exclusión. |
   | **[!UICONTROL Tasa de conversión típica]** | Esta métrica se expresa como porcentaje según las estimaciones o los datos anteriores procedentes del sistema de análisis. |
   | **[!UICONTROL Visitas estimadas por día]** | Esta métrica es el número de visitas por día de visitantes que pueden ver la actividad según los criterios de segmentación. Esta métrica se puede basar en los datos de análisis. Este número debe ser visitas, no visitantes únicos. |
   | **[!UICONTROL Duración de la prueba]** | Número de días durante los cuales quiere ejecutar la actividad. |

   El [!UICONTROL estimador de tráfico] usa estas métricas para determinar qué ajustes son necesarios para ejecutar una prueba con éxito.

   Cerca de la parte superior de [!UICONTROL Estimador de tráfico], los valores que ingresaste se calcularán y se mostrarán los resultados.

   ![Estimación de tráfico con valores y resultados mostrados](assets/ap-est-no.png)

   Al cambiar estos números, también cambian las estimaciones. Por ejemplo, si está probando muchas combinaciones y la tasa de conversión y las impresiones son demasiado bajas, [!UICONTROL Estimador de tráfico] muestra cuánto tiempo debe durar la prueba para que sea satisfactoria. O, si el tráfico es bajo, el [!UICONTROL Estimador de tráfico] podría sugerir un número menor de combinaciones de ofertas para que pueda ejecutar la prueba el número deseado de días.

   Si no tiene tráfico suficiente, tenga en cuenta lo siguiente:

   * Considere la posibilidad de usar una actividad de [[!UICONTROL segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) en lugar de [!UICONTROL Automated Personalization] para crear experiencias con varios cambios en las ofertas en una variación de experiencia.
   * Reduzca la cantidad de combinaciones de ofertas dentro de su actividad [!UICONTROL Automated Personalization].
   * Incremente la duración de la actividad.

   Ajuste los números hasta que [!UICONTROL Estimador de tráfico] indique que tiene tráfico suficiente y luego diseñe la prueba en consecuencia.

   ![Estimador de tráfico que muestra un mensaje de tráfico suficiente](assets/ap-est-yes.png)

   Si el tráfico es suficiente, el icono [!UICONTROL Tráfico] muestra una marca de verificación verde. Si no hay suficiente, el icono muestra una etiqueta de advertencia en rojo.

## Preguntas más frecuentes sobre el estimador de tráfico

Tenga en cuenta las siguientes preguntas frecuentes mientras trabaja con [!UICONTROL Estimador de tráfico]:

### ¿Por qué los modelos personalizados no se crean aunque mi actividad de AP tenga tráfico suficiente?

En algunas circunstancias, el tráfico es lo suficientemente grande como para generar un modelo personalizado, pero ese tráfico podría informar a [!DNL Target] de que no existe una diferencia significativa entre el modelo personalizado y el aleatorio. Aunque el modelo se ha creado en [!DNL Target] y se ha probado, no se implementa porque no es mejor que aleatorio.

Una posible razón para que el modelo no sea mejor que aleatorio podría ser que las ofertas no son lo suficientemente diferentes entre sí. Si es así, puede intentar hacer que las ofertas sean más visualmente diferentes si la mensajería es similar, o puede intentar cambiar la mensajería en sí.
