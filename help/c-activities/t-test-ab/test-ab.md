---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: Una actividad de prueba A/B manual compara dos o más versiones del contenido del sitio web para ver qué versiones mejoran mejor las conversiones durante un período de prueba previo especificado.
title: Descripción general de la prueba A/B
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# Descripción general de la prueba A/B

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>Además de la actividad de prueba [!UICONTROL A/B manual (predeterminada) (analizada en esta sección),] proporciona dos tipos adicionales de actividades de prueba [!DNL Target]  A/B: [!UICONTROL Asignación] automática y Destinatario automático.
>
>Consulte [Tipos de actividades](#types) de prueba A/B a continuación para obtener más información.

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

Las pruebas A/B manuales son especialmente útiles cuando se dispone de una hipótesis clara de formas de mejorar el rendimiento de la página en función de las métricas de éxito o del envío de contenido alternativo.

Las pruebas A/B manuales son adecuadas para cambios de gran tamaño que pueden implicar nuevos diseños o un tratamiento de los elementos totalmente diferente. If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Al configurar la prueba A/B, puede determinar el porcentaje de visitantes que ven cada experiencia. Por ejemplo, podría dividir el tráfico uniformemente entre el control y una segunda experiencia; o bien, podría probar una experiencia nueva y más arriesgada al mostrársela a solo el 5 % de su audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Cuando el número de experiencias diferentes es superior a cinco y abarcan dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas son las ubicaciones en las que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Una vez que haya determinado qué ubicaciones y contenido son más útiles para ayudarle a alcanzar sus objetivos, puede ejecutar una prueba A/B para restringir aún más los resultados, como probar dos imágenes específicas entre sí o comparar la redacción o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad de prueba  A/B manual (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Asignación] automática y Destinatario automático.

| Tipo de actividad | Descripción |
| --- | --- |
| [!UICONTROL Prueba A/B manual] | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<br>En esta sección se describe cómo configurar una actividad de prueba [!UICONTROL A/] B manual, pero los pasos para los otros tipos de actividades de prueba  A/B son similares. |
| [!UICONTROL Asignación automática] | Identifica un ganador entre dos o más experiencias y entonces redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<br>Para obtener información sobre las ventajas de utilizar una actividad de asignación automática, consulte Asignación [automática](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en *Cuánto tiempo debe ejecutar una prueba* A/B y una descripción general [de asignación](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)automática. |
| ![Distintivo](/help/assets/premium.png) Premium de Destinatario [!UICONTROL automático] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más ajustadas a cada visitante en función de su perfil de usuario y el comportamiento pasado de visitantes similares.<br>Para obtener más información, consulte Destinatario [automático](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas actividades de prueba [!UICONTROL A/] B es la más adecuada para usted, consulte la guía interactiva de Actividades de [Adobe Target en PDF](/help/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de actividades de prueba [!UICONTROL A/] B son similares. Para crear una actividad de asignación  automática o de Destinatario  automático, haga un inicio [creando una actividad](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)de prueba A/B, pero cuando llegue a la página [!UICONTROL Segmentación] , elija el método de asignación de tráfico deseado, como se muestra a continuación:

* [!UICONTROL Asignar automáticamente a la mejor experiencia]
* [!UICONTROL Destinatario automático para una experiencia personalizada]

![Configuración del método de asignación de tráfico](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de capacitación: Distintivo ![Información general de tipos de actividades (9:03)](/help/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
