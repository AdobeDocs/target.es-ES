---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content
description: Una prueba A/B compara dos o más versiones del contenido de su sitio web para comprobar cuál mejora más las conversiones durante un periodo previamente establecido.
title: Prueba A/B
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 130edc89b2c324a0d892a4221f644248e23357a4
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 58%

---


# Prueba A/B

Una prueba A/B manual compara dos o más versiones del contenido del sitio Web para ver qué versión mejora mejor las conversiones durante un período de prueba previo especificado.

>[!NOTE]
>
>Además de la actividad de prueba A/B manual (predeterminada) (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Asignación] automática y Destinatario automático.
>
>Consulte [Tipos de actividades](#types) de prueba A/B a continuación para obtener más información.

Una prueba A/B manual (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver cuál aumenta mejor las conversiones, las ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

Las pruebas A/B manuales son especialmente útiles cuando se dispone de una hipótesis clara de formas de mejorar el rendimiento de la página en función de las métricas de éxito o del envío de contenido alternativo.

Las pruebas A/B manuales son adecuadas para cambios de gran tamaño que pueden implicar nuevos diseños o un tratamiento de los elementos totalmente diferente. Si el diseño de la prueba no se puede dividir fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes que una prueba multivariable.

Al configurar la prueba, se puede determinar el porcentaje de visitantes que verán cada experiencia. Por ejemplo, podría dividir el tráfico uniformemente entre el control y una segunda experiencia; o bien, podría probar una experiencia nueva y más arriesgada al mostrársela a solo el 5 % de su audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](../../c-activities/t-test-ab/sample-size-determination.md#concept_2801F552DB874C20B8A17C1B774C0383).

Cuando el número de experiencias diferentes es superior a cinco y abarcan dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas son las ubicaciones en las que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Una vez que haya determinado qué ubicaciones y contenido son los más útiles para ayudarle a lograr sus objetivos, puede ejecutar una prueba A/B para restringir aún más los resultados, como probar dos imágenes específicas entre sí, o comparar las palabras o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad de prueba A/B manual (predeterminada) (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Asignación] automática y Destinatario automático.

| Tipo de actividad | Descripción |
| --- | --- |
| Prueba A/B manual | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<br>Esta sección describe cómo configurar una actividad de prueba A/B manual, pero los pasos para los otros tipos de actividades de prueba A/B son similares. |
| [!UICONTROL Asignación automática] | Identifica un ganador entre dos o más experiencias y entonces redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<br>Para obtener más información, consulte [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Distintivo](/help/assets/premium.png) Premium de Destinatario [!UICONTROL automático] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más ajustadas a cada visitante en función de su perfil de usuario y el comportamiento pasado de visitantes similares.<br>Para obtener más información, consulte Destinatario [automático](/help/c-activities/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas actividades de prueba A/B es la más adecuada para usted, consulte la guía interactiva de Actividades de [Adobe Target en PDF](/help/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de actividades de prueba A/B son similares. Para crear una actividad de asignación  automática o de Destinatario  automático, haga un inicio [creando una actividad](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)de prueba A/B, pero cuando llegue a la página [!UICONTROL Segmentación] , elija el método de asignación de tráfico que desee:

* [!UICONTROL Asignar automáticamente a la mejor experiencia]
* [!UICONTROL Destinatario automático para una experiencia personalizada]

![Configuración del método de asignación de tráfico](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de capacitación: Distintivo ![Información general de tipos de actividades (9:03)](/help/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
