---
keywords: AB;A/B;AB...n;comparar experiencias;Segmentación;comparar contenido;Segmentación automática;Asignación automática
description: Explore las actividades de prueba A/B en [!DNL Target] - [!UICONTROL Manual], [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
title: Descubra las actividades de prueba A/B disponibles en [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: 'https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: d887712962ad4e3cecd6b3b86ee33a4bcb99f2a8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 19%
---
# Información general sobre las pruebas A/B {#test-ab}

>[!BEGINSHADEBOX]

**En esta página:** Descubra qué es una prueba A/B manual, cuándo utilizarla en lugar de una prueba multivariable y cómo se relaciona con los tipos de actividad de asignación automática y segmentación automática.

>[!ENDSHADEBOX]

Una actividad manual de **[!UICONTROL Prueba A/B]** (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver qué versión mejora las conversiones, las ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

## Cuándo se debe utilizar una prueba A/B manual {#when-to-use}

Utilice una prueba A/B manual cuando:

* Tiene una hipótesis clara de las formas de mejorar el rendimiento de su página, en función de las métricas de éxito o de la entrega de contenido alternativo.
* Desea probar cambios grandes, como nuevos diseños o tratamientos drásticamente diferentes de los elementos. Si el diseño de la prueba no se desglosa fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes de ejecutar una [prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).
* Desea decidir el porcentaje de visitantes que ven cada experiencia. Por ejemplo, puede dividir el tráfico de forma uniforme entre el control y una segunda experiencia, o puede probar una experiencia nueva y más arriesgada mostrándola solo al 5 % de la audiencia.

Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

### Combinar una prueba multivariable y pruebas A/B

Cuando el número de experiencias diferentes es superior a cinco y abarca dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B:

1. **Ejecute una prueba multivariable** para ver qué áreas de la página tienen más probabilidades de mejorar la conversión. Estas áreas son las ubicaciones en las que el experto en marketing debe centrarse. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos.

1. **Ejecute una o más pruebas A/B** en esas ubicaciones para restringir aún más los resultados. Por ejemplo, para probar dos imágenes específicas entre sí o para comparar las palabras o los colores de un call to action.

Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad manual **[!UICONTROL Prueba A/B]**, [!DNL Target] proporciona dos tipos adicionales de actividades de **[!UICONTROL Prueba A/B]**: **[!UICONTROL Asignación automática]** y **[!UICONTROL Segmentación automática]**.

| Tipo de actividad | Descripción |
| --- | --- |
| **[!UICONTROL Prueba A/B manual]** | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<P>En esta sección se describe cómo configurar una actividad **[!UICONTROL Prueba A/B]** manual, pero los pasos para los demás tipos de actividades **[!UICONTROL Prueba A/B]** son similares. |
| **[!UICONTROL Asignación automática]** | Identifica un ganador entre dos o más experiencias y luego redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<P>Para obtener más información sobre las ventajas de usar una actividad **[!UICONTROL Asignación automática]**, consulta [Asignación automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en *Cuánto tiempo debes ejecutar una prueba A/B* y [Información general sobre la asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Distintivo Premium](/help/main/assets/premium.png) **[!UICONTROL Segmentación automática]** | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing. A continuación, se ofrece a los visitantes la experiencia más adaptada en función de sus perfiles de cliente individuales y de los comportamientos anteriores de visitantes similares.<P>Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas **[!UICONTROL pruebas A/B]** es la adecuada para usted, consulte la [Guía de actividades de Adobe Target interactiva en PDF](/help/main/c-activities/target-activities-guide.md).

>[!NOTE]
>
>Puede incluir recomendaciones dentro de las actividades **[!UICONTROL Prueba A/B]**, **[!UICONTROL Asignación automática]** y **[!UICONTROL Segmentación automática]** (así como las actividades **[!UICONTROL Segmentación de experiencias]** (XT) ). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).
