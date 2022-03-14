---
keywords: AB;A/B;AB...n;comparar experiencias;Segmentación;comparar contenido;segmentación automática;asignación automática
description: 'Obtenga información sobre los distintos tipos de actividades de prueba A/B en Adobe [!DNL Target] : manual, asignación automática y segmentación automática. Elige el que es adecuado para ti.'
title: ¿Qué tipo de actividades A/B están disponibles en Target?
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 39%

---

# Información general sobre la prueba A/B

Un manual [!UICONTROL Prueba A/B] actividad compara dos o más versiones del contenido del sitio web para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.

>[!NOTE]
>
>Además del Manual (predeterminado) [!UICONTROL Prueba A/B] actividad (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de [!UICONTROL Prueba A/B] actividades: [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].
>
>Consulte [Tipos de actividades de prueba A/B](#types) más abajo para obtener más información.

Un manual [!UICONTROL Prueba A/B] actividad (a veces denominada prueba A/B...N) compara dos o más versiones del contenido del sitio web para ver cuál aumenta más las conversiones, las ventas u otras métricas que identifique. Utilice una prueba A/B para comparar los cambios en las páginas con respecto al diseño de página predeterminado, para determinar qué experiencias generan los mejores resultados.

Las pruebas A/B manuales son especialmente útiles cuando se tiene una hipótesis clara de cómo mejorar el rendimiento de la página en función de métricas de éxito o envíos de contenido alternativo.

Las pruebas A/B manuales son ideales para cambios de gran tamaño que puedan implicar nuevos diseños o un tratamiento de los elementos totalmente diferente. Si el diseño de la prueba no se puede dividir fácilmente en elementos de página individuales, debe ejecutar una prueba A/B antes de una [prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Al configurar la prueba A/B, puede determinar el porcentaje de visitantes que ven cada experiencia. Por ejemplo, podría dividir el tráfico uniformemente entre el control y una segunda experiencia; o bien, podría probar una experiencia nueva y más arriesgada al mostrársela a solo el 5 % de su audiencia.

>[!NOTE]
>
>Para obtener información detallada sobre cómo determinar el tamaño de muestra óptimo para una prueba A/B, consulte [Planificación de la prueba A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Cuando el número de experiencias diferentes es superior a cinco y abarcan dos o más ubicaciones, es aconsejable realizar una [prueba MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estas son las ubicaciones en las que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es la ubicación más importante para lograr sus objetivos. Una vez que haya determinado qué ubicaciones y contenido son los más útiles para ayudarle a lograr sus objetivos, puede ejecutar una prueba A/B para restringir aún más los resultados, como probar dos imágenes específicas entre sí o comparar la redacción o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Tipos de actividades de prueba A/B {#types}

Además del manual [!UICONTROL Prueba A/B] actividad (analizada en esta sección), [!DNL Target] proporciona dos tipos adicionales de actividades de prueba A/B: [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

| Tipo de actividad | Descripción |
| --- | --- |
| [!UICONTROL Prueba A/B manual] | Compara dos o más experiencias para ver cuál mejora más las conversiones durante un periodo de prueba previamente establecido.<br>En esta sección se describe cómo configurar un manual [!UICONTROL Prueba A/B] actividad, pero los pasos para los demás tipos de [!UICONTROL Prueba A/B] las actividades son similares. |
| [!UICONTROL Asignación automática] | Identifica un ganador entre dos o más experiencias y entonces redirige el tráfico hacia el ganador para aumentar las conversiones mientras la prueba se ejecuta y aprende.<br>Para obtener más información sobre las ventajas de utilizar una actividad de asignación automática, consulte [Asignación automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) en *Durante cuánto tiempo se debe ejecutar una prueba A/B* y [Información general de asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Distintivo Premium](/help/main/assets/premium.png) [!UICONTROL Segmentación automática] | Utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones identificando múltiples experiencias de alto rendimiento definidas por expertos en marketing; y sirve las experiencias más ajustadas a cada visitante en función de su perfil de usuario y el comportamiento pasado de visitantes similares.<br>Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obtener más información sobre cuál de estas [!UICONTROL Prueba A/B] actividades es adecuado para usted, consulte la [PDF de la guía de actividades de Adobe Target](/help/main/c-activities/target-activities-guide.md).

Los pasos para crear los tres tipos de [!UICONTROL Prueba A/B] las actividades son similares. Para crear un [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática] actividad, comenzar por [creación de una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), pero cuando llega al [!UICONTROL Segmentación] , elija el método de asignación de tráfico que desee, como se muestra a continuación:

* [!UICONTROL Asignar automáticamente a la mejor experiencia]
* [!UICONTROL Segmentación automática para experiencias personalizadas]

![Configuración del método de asignación de tráfico](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de aprendizaje: Tipos de actividades (9:03) ![Distintivo de información general](/help/main/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)
