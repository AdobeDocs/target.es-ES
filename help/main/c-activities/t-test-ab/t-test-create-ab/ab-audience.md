---
keywords: audiencia;seleccionar audiencia;elegir audiencia;selectores
description: La audiencia determina qué visitantes del sitio entran en el Adobe [!DNL Target] actividad.
title: ¿Cómo selecciono una audiencia en una? [!DNL Target] ¿Actividad A/B?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 70%

---

# Seleccionar la audiencia

La audiencia determina qué visitantes del sitio entran en su [!DNL Adobe Target] actividad.

>[!NOTE]
>
>Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. En el [!UICONTROL Audiencia] , haga clic en **[!UICONTROL Editar]** (los puntos suspensivos verticales) y haga clic en **[!UICONTROL Reemplazar audiencia]**.

   ![Opción Reemplazar audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   De forma predeterminada, su audiencia son todos los visitantes. No obstante, puede modificar la audiencia. Las audiencias se seleccionan en la biblioteca de audiencias, o bien puede crear una audiencia solo de actividad. La biblioteca de audiencias contiene las audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de [!DNL Target].

1. Seleccione o cree la audiencia que desee:

   * Seleccione una audiencia de la biblioteca
   * [Combinación de varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [Creación de una nueva audiencia](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [Creación de una audiencia solo de actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   Para una prueba A/B sin segmentación de audiencia específica, elija el valor predeterminado, [!UICONTROL Todos los visitantes].

   También puede editar o copiar una audiencia pasando el puntero sobre ella en el [!UICONTROL Añadir audiencia] , como se muestra a continuación.

   Copiar una audiencia es útil si quiere crear una audiencia similar a otra ya existente. Puede crear una copia de la audiencia, realizar sus modificaciones y después guardarla como una audiencia nueva. Esta funcionalidad (pasar el cursor sobre un elemento) está disponible para otros tipos de actividad.

   ![Pase de audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   Al crear una audiencia puede seleccionar una ubicación (mbox) y especificar parámetros para dicha ubicación. En [!UICONTROL Parámetros personalizados], seleccione el mbox y, a continuación, especifique los parámetros que desee.

   >[!NOTE]
   >
   >Las audiencias se importan automáticamente en segundo plano cuando abre la lista de audiencias y las audiencias importadas tienen más de diez minutos de antigüedad.

1. (Condicional) Especifique el porcentaje de visitantes correspondiente que desea incluir en la actividad.

   Por ejemplo, podría optar por incluir el 50 % de todos los visitantes.

   ![Porcentaje de audiencia](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   También puede elegir que Target  [asigne el tráfico automáticamente](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Uso de audiencias en Adobe Target (6:21) ![Distintivo de información general](/help/main/assets/overview.png)

En este vídeo se describe cómo usar las audiencias en [!DNL Target Standard/Premium].

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### Flujo de trabajo de actividad - Segmentación (2:14) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre cómo configurar las audiencias.

* Asignar una audiencia a la actividad
* Acelerar o desacelerar el tráfico
* Seleccionar el método de asignación de tráfico
* Asignar tráfico entre distintas experiencias

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Para obtener información detallada, consulte [Audiencias](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).
