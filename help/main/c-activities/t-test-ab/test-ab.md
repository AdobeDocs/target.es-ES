---
keywords: AB;A/B;AB...n;comparar experiencias;Segmentación;comparar contenido;Segmentación automática;Asignación automática
description: Explore las actividades de prueba A/B en  [!DNL Target] - [!UICONTROL Manual], [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].
title: Descubra las actividades de prueba A/B disponibles en  [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 21%

---

# Información general sobre las pruebas A/B

Una actividad manual [!UICONTROL A/B Test] (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver qué versión mejora las conversiones, las ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

>[!TIP]
>
>Además de la actividad [!UICONTROL Manual] (predeterminada) [!UICONTROL A/B Test] (que se describe en este artículo), [!DNL Target] proporciona dos tipos adicionales de actividades [!UICONTROL A/B Test]: [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]. Consulte [Tipos de actividades de pruebas A/B](#types) más abajo para obtener más información.

Las pruebas A/B manuales son útiles cuando tiene una hipótesis clara de formas de mejorar el rendimiento de la página en función de métricas de éxito o de una entrega de contenido alternativo.

Las pruebas A/B manuales son adecuadas para cambios grandes que pueden implicar nuevos diseños o tratamientos drásticamente diferentes de los elementos. Si el diseño de la prueba no se desglosa fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes de ejecutar una [prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Al configurar la prueba A/B, puede determinar el porcentaje de visitantes que ven cada experiencia. Por ejemplo, puede dividir el tráfico de forma uniforme entre el control y una segunda experiencia, o puede probar una experiencia nueva y más arriesgada mostrándola solo al 5 % de la audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Cuando el número de experiencias diferentes es superior a cinco y abarca dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas áreas son las ubicaciones en las que el experto en marketing debe centrarse. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Después de determinar qué ubicaciones y contenido son más útiles para alcanzar sus objetivos, puede ejecutar una prueba A/B para refinar aún más los resultados. Por ejemplo, para probar dos imágenes específicas entre sí o para comparar las palabras o los colores de un call to action. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad manual [!UICONTROL A/B Test], [!DNL Target] proporciona dos tipos adicionales de actividades [!UICONTROL A/B Testing]: [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].

| Tipo de actividad | Descripción |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<P>En esta sección se describe cómo configurar una actividad [!UICONTROL A/B Test] manual, pero los pasos para los otros tipos de actividades [!UICONTROL A/B Test] son similares. |
| [!UICONTROL Auto-Allocate] | Identifica un ganador entre dos o más experiencias y luego redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<P>Para obtener más información sobre las ventajas de usar una actividad [!UICONTROL Auto-Allocate], consulte [Asignación automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en *Cuánto tiempo se debe ejecutar una prueba A/B* y [Información general sobre la asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Insignia premium](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing. A continuación, se ofrece a los visitantes la experiencia más adaptada en función de sus perfiles de cliente individuales y de los comportamientos anteriores de visitantes similares.<P>Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas [!UICONTROL A/B Test] actividades es la adecuada para usted, consulte la [Guía de actividades de Adobe Target PDF](/help/main/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de actividades [!UICONTROL A/B Test] son similares. Para crear una actividad [!UICONTROL Auto-Allocate] o [!UICONTROL Auto-Target]:

1. Comience por [crear una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).
1. Cuando llegue a la página [!UICONTROL Targeting], haga clic en el control [!UICONTROL Traffic Allocation] y, a continuación, elija el método de asignación de tráfico que desee en el panel derecho, como se muestra a continuación:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experience]

   ![Configuración del método de asignación de tráfico](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## Incluir recomendaciones dentro de actividades A/B

Puede incluir recomendaciones dentro de las actividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] (y las actividades [!UICONTROL Experience Targeting] (XT)). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).
