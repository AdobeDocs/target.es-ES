---
keywords: AB;A/B;AB...n;comparar experiencias;Segmentación;comparar contenido;Segmentación automática;Asignación automática
description: 'Obtenga información acerca de los distintos tipos de actividades de prueba A/B en Adobe [!DNL Target] : manual, asignación automática y segmentación automática. Elija el que sea adecuado para usted.'
title: ¿Qué tipo de actividades A/B hay disponibles en Target?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: b5da2f5d41739af39d97e0ce9761006794c04d2b
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 25%

---

# Información general sobre las pruebas A/B

Una actividad manual [!UICONTROL A/B Test] compara dos o más versiones del contenido de su sitio web para ver cuál mejora más las conversiones durante un período de prueba previamente establecido.

>[!NOTE]
>
>Además de la actividad manual (predeterminada) [!UICONTROL A/B Test] (que se describe en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades [!UICONTROL A/B Test]: [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]. Consulte [Tipos de actividades de pruebas A/B](#types) más abajo para obtener más información.

Una actividad manual [!UICONTROL A/B Test] (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver qué versión mejora las conversiones, las ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

Las pruebas A/B manuales son útiles cuando tiene una hipótesis clara de formas de mejorar el rendimiento de la página en función de métricas de éxito o de una entrega de contenido alternativo.

Las pruebas A/B manuales son adecuadas para cambios grandes que pueden implicar nuevos diseños o tratamientos drásticamente diferentes de los elementos. Si el diseño de la prueba no se desglosa fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes que una [prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Al configurar la prueba A/B, puede determinar el porcentaje de visitantes que ven cada experiencia. Por ejemplo, podría dividir el tráfico uniformemente entre el control y una segunda experiencia; o bien, podría probar una experiencia nueva y más arriesgada al mostrársela a solo el 5 % de su audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Cuando el número de experiencias diferentes es superior a cinco y abarca dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas áreas son las ubicaciones en las que el experto en marketing debe centrarse. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Después de determinar qué ubicaciones y contenido son más útiles para alcanzar sus objetivos, puede ejecutar una prueba A/B para refinar aún más los resultados. Por ejemplo, para probar dos imágenes específicas una contra la otra o para comparar las palabras o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad [!UICONTROL A/B Test] manual (que se describe en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].

| Tipo de actividad | Descripción |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<P>En esta sección se describe cómo configurar una actividad [!UICONTROL A/B Test] manual, pero los pasos para los otros tipos de actividades [!UICONTROL A/B Test] son similares. |
| [!UICONTROL Auto-Allocate] | Identifica un ganador entre dos o más experiencias y luego redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<P>Para obtener más información sobre las ventajas de usar una actividad [!UICONTROL Auto-Allocate], consulte [Asignación automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en *Cuánto tiempo se debe ejecutar una prueba A/B* y [Información general sobre la asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Insignia premium](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing. A continuación, se ofrece a los visitantes la experiencia más adaptada en función de sus perfiles de cliente individuales y de los comportamientos anteriores de visitantes similares.<P>Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas [!UICONTROL A/B Test] actividades es la adecuada para usted, consulte el [PDF interactivo de la Guía de actividades de Adobe Target](/help/main/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de actividades [!UICONTROL A/B Test] son similares. Para crear una actividad [!UICONTROL Auto-Allocate] o [!UICONTROL Auto-Target], comience por [crear una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), pero cuando llegue a la página [!UICONTROL Targeting], elija el método de asignación de tráfico que desee, como se muestra a continuación:

* [!UICONTROL Auto-allocate to best experience]
* [!UICONTROL Auto-target for personalized experience]

![Configuración del método de asignación de tráfico](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Incluir recomendaciones dentro de actividades A/B

Puede incluir recomendaciones dentro de las actividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] (y las actividades [!UICONTROL Experience Targeting] (XT)). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

Esta funcionalidad requiere que tenga una [licencia de Target Premium](/help/main/c-intro/intro.md#premium)

## Vídeo de aprendizaje: Tipos de actividades (9:03) ![Distintivo de información general](/help/main/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
