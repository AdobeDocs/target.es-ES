---
keywords: AB;A/B;AB...n;comparar experiencias;Segmentación;comparar contenido;segmentación automática;asignación automática
description: 'Obtenga información sobre los distintos tipos de actividades de prueba A/B en Adobe [!DNL Target] : manual, asignación automática y segmentación automática. Elige el que es adecuado para ti.'
title: ¿Qué tipo de actividades A/B están disponibles en Target?
feature: Pruebas A/B
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 38%

---

# Información general sobre la prueba A/B

Una actividad [!UICONTROL Prueba A/B] manual compara dos o más versiones del contenido del sitio web para ver qué versión mejora más las conversiones durante un período de prueba previamente especificado.

>[!NOTE]
>
>Además de la actividad [!UICONTROL Prueba A/B] manual (predeterminada) que se analiza en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades [!UICONTROL Prueba A/B]: [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
>
>Consulte [Tipos de actividades de prueba A/B](#types) a continuación para obtener más información.

Una actividad [!UICONTROL Prueba A/B] manual (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver cuál aumenta más las conversiones, ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

Las pruebas A/B manuales son especialmente útiles cuando se tiene una hipótesis clara de cómo mejorar el rendimiento de la página en función de métricas de éxito o envíos de contenido alternativo.

Las pruebas A/B manuales son ideales para cambios de gran tamaño que puedan implicar nuevos diseños o un tratamiento de los elementos totalmente diferente. Si el diseño de la prueba no se puede desglosar fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes de una [prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Al configurar la prueba A/B, puede determinar el porcentaje de visitantes que ven cada experiencia. Por ejemplo, podría dividir el tráfico uniformemente entre el control y una segunda experiencia; o bien, podría probar una experiencia nueva y más arriesgada al mostrársela a solo el 5 % de su audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Cuando el número de experiencias diferentes es superior a cinco y abarcan dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas son las ubicaciones en las que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Una vez que haya determinado qué ubicaciones y contenido son los más útiles para ayudarle a lograr sus objetivos, puede ejecutar una prueba A/B para restringir aún más los resultados, como probar dos imágenes específicas entre sí o comparar la redacción o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además de la actividad [!UICONTROL Prueba A/B] manual (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

| Tipo de actividad | Descripción |
| --- | --- |
| [!UICONTROL Prueba A/B manual] | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<br>En esta sección se describe cómo configurar una  [!UICONTROL prueba A/B manual, pero los pasos para los demás tipos de actividades de ] prueba   A/B son similares. |
| [!UICONTROL Asignación automática] | Identifica un ganador entre dos o más experiencias y entonces redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<br>Para obtener más información sobre las ventajas de utilizar una actividad de asignación automática, consulte  [Asignación automática ](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en  *Duración de la ejecución de una prueba A/B* y  [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Distintivo Premium ](/help/assets/premium.png) [!UICONTROL Segmentación automática] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más ajustadas a cada visitante en función de su perfil de usuario y el comportamiento pasado de visitantes similares.<br>Para obtener más información, consulte  [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas [!UICONTROL actividades de prueba A/B] es la adecuada para usted, consulte la [Guía interactiva de actividades de Adobe Target en PDF](/help/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de actividades [!UICONTROL Prueba A/B] son similares. Para crear una actividad de [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], comience [creando una actividad de prueba A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), pero cuando llegue a la página [!UICONTROL Segmentación], elija el método de asignación de tráfico deseado, como se muestra a continuación:

* [!UICONTROL Asignar automáticamente a la mejor experiencia]
* [!UICONTROL Segmentación automática para experiencias personalizadas]

![Configuración del método de asignación de tráfico](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de formación: Tipos de actividades (9:03) ![Distintivo Información general](/help/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
