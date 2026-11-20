---
keywords: prueba multivariable;mvt;factorial completa;mvt o a/b;a/b multivariable;estimador de tráfico;cuándo usar mvt;consideraciones de mvt;multivariable;factorial parcial;factorial parcial;factorial completa
description: Aprenda a usar una [!UICONTROL prueba multivariable] (MVT) en [!DNL Adobe Target] para comparar combinaciones de ofertas en elementos de una página y determinar qué combinación ofrece el mejor rendimiento.
title: ¿Qué es una [!UICONTROL prueba multivariable]?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
TQID: 'https://experienceleague.adobe.com/JKmjIHJuRxAXlhvUOrrmLMVLnJFhA3T4xkahgH-ozHE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 25%
---
# Introducción a [!UICONTROL Prueba multivariable] {#get-started-mvt}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo funciona una prueba multivariada **[!UICONTROL 3&rbrace;, qué términos usa [!DNL Target], cuándo utilizarla en lugar de una prueba A/B y cómo las pruebas factoriales parciales reducen los requisitos de tráfico.]**

>[!ENDSHADEBOX]

Una actividad **[!UICONTROL Prueba multivariada]** (MVT) en [!DNL Adobe Target] compara combinaciones de ofertas en elementos de una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica. También ayuda a identificar qué elemento tiene el mayor impacto en el éxito de la actividad. Las pruebas multivariable le ayudan a descubrir la influencia relativa que tienen determinados elementos en la conversión, en comparación con otros elementos de la página, y pueden ayudarle a refinar una combinación de elementos que han demostrado ser eficaces.

Una **[!UICONTROL prueba multivariable]** proporciona dos ventajas en comparación con una prueba A/B:

* Muestra qué elementos de la página tienen la mayor influencia en la conversión, lo que también se conoce como el &quot;efecto principal&quot;. Esta información resulta útil, por ejemplo, para ayudarle a determinar dónde colocar el contenido que desea que reciba la mayor atención.
* Ayuda a encontrar efectos compuestos entre dos o más elementos de una página, lo que también se conoce como el &quot;efecto interacción&quot;. Por ejemplo, un anuncio concreto podría generar más conversiones si se combinara con un determinado banner o una imagen a pantalla completa (hero).

[!DNL Target] usa pruebas multivariable factoriales completas para ayudarle a optimizar su contenido. Una prueba multivariable factorial completa examina todas las combinaciones posibles de contenido con igual probabilidad. Por ejemplo, si tiene dos elementos de página con tres ofertas cada uno, hay nueve combinaciones posibles (3x3). Cuando hay tres elementos, de los cuales dos contienen tres ofertas posibles y uno tiene dos ofertas, se generan 18 opciones (3x3x2).

En [!DNL Target], cada combinación es una experiencia. La **[!UICONTROL prueba multivariable]** compara cada experiencia para que pueda saber qué combinaciones son las más exitosas. Al mismo tiempo, [!DNL Target] recopila y analiza datos para comprender cómo influyen cada ubicación y las ofertas en la métrica de éxito.

![Combinaciones de pruebas multivariable](assets/multivariate.png)

Una **[!UICONTROL prueba multivariable]** requiere más tiempo y tráfico que una prueba A/B debido al número de combinaciones que se pueden generar. La página debe recibir tráfico suficiente para generar resultados relevantes estadísticamente para cada experiencia. Para obtener resultados útiles, comprenda la cantidad de tráfico que recibe su página y pruebe la cantidad óptima de combinaciones durante el tiempo adecuado.

El [estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator) puede ayudarte a diseñar una prueba que funcione con tu tráfico. Antes de usarlo, debe tener buenas estadísticas que muestren la cantidad de impresiones y conversiones que normalmente recibe su sitio, y considerar sus niveles de tráfico por día. Cuantas más experiencias tenga una actividad, más tráfico deberá incluir la actividad o más tiempo deberá ejecutarse. Si la cantidad de tráfico no es alta, pruebe algunas combinaciones. De lo contrario, la cantidad de tiempo necesaria para producir resultados de prueba significativos podría ser demasiado larga para ser útil.

## Terminología de MVT {#mvt-terminology}

Varios términos se utilizan de diferentes maneras en todo el sector. En la tabla siguiente se definen los términos que [!DNL Target] utiliza al configurar una prueba multivariable.

| Término | Definición |
|--- |--- |
| Combinación | Variaciones de contenido que se crean cuando prueba varias opciones de contenido en varias ubicaciones. Por ejemplo, si está probando tres ubicaciones, cada una con tres opciones de contenido, hay 27 combinaciones posibles (3x3x3). Un visitante del sitio ve una combinación que también se denomina experiencia. |
| Contenido | Texto o imagen que constituye una variación de prueba dentro de una ubicación. En una prueba multivariable, se comparan varias opciones de contenido dentro de varias ubicaciones. En la metodología de las pruebas MVT, el contenido a menudo se denomina *nivel*. |
| Elemento | Elemento DOM que contiene variaciones de contenido que se van a probar en la prueba MVT. Vea también *Ubicación*. |
| Ubicación | Área específica de contenido en una página, a menudo incluida en un solo elemento de DOM. En la metodología de las pruebas MVT, la ubicación a menudo se denomina *factor*. Una prueba multivariable factorial completa compara todas las combinaciones posibles de las ofertas en las ubicaciones. |

## Cuándo usar [!UICONTROL Prueba multivariable] frente a A/B {#when-to-use-mvt}

La tabla siguiente muestra cuándo usar una **[!UICONTROL prueba multivariable]**, una prueba A/B o ambas para optimizar la página.

| Situación | Qué hacer | Detalles |
|--- |--- |--- |
| Hay menos de tres elementos que probar. | Ejecute una serie de pruebas A/B. | Utilice una prueba MVT cuando tenga al menos tres elementos que probar. |
| Desea optimizar tanto el diseño como el contenido de la página. | Utilice una prueba A/B para optimizar el diseño de la página, seguida de una prueba MVT para determinar el mejor contenido en cada elemento de la página. | Las pruebas A/B pueden proporcionar información importante sobre el diseño, mientras que las pruebas MVT son excelentes para probar contenido dentro de los elementos del diseño de la página. La ejecución de una prueba A/B en el diseño antes de probar varias opciones de contenido le ayuda a determinar el mejor diseño y el contenido más impactante. |
| El número de experiencias diferentes es superior a cinco y abarca dos o más elementos. | Utilice una prueba MVT para determinar qué elemento es el más importante y, después, realice una prueba A/B que se centre en ese elemento. | La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estos son los elementos en los que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es el elemento más importante para lograr sus objetivos. A continuación, puede ejecutar una prueba A/B para restringir aún más los resultados, por ejemplo, probando dos imágenes específicas una contra la otra o comparando las palabras o los colores de una call to action. Si sigue una prueba MVT con una o más pruebas A/B, podrá determinar el contenido más adecuado para los resultados que desee. |

Para obtener más información, como cuántos elementos incluir y cómo planificar la prueba, consulte [Prácticas recomendadas de pruebas multivariable](/help/main/c-activities/c-multivariate-testing/best-practices.md).

## Pruebas factoriales parciales {#partial-factorial}

[!DNL Target] ofrece pruebas multivariable totalmente factoriales como opción de actividad integrada. En estadística, &quot;Diseño de experimentos&quot; ofrece muchos enfoques, o diseños, para determinar qué factores influyen en los resultados. Uno de estos enfoques es el [Método Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) para pruebas factoriales parciales. El método Taguchi permite a los especialistas en marketing realizar una serie de suposiciones que reducen el número de permutaciones de experiencias que se deben probar, lo que a su vez reduce los requisitos de tráfico para una prueba multivariable. Puede aplicar este enfoque en [!DNL Target] mediante esta [hoja de cálculo sin conexión](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Si su equipo utiliza otros enfoques de Diseño de experimentos, puede utilizar la hoja de cálculo como implementación de referencia para diseños de experimentos personalizados.

Al utilizar la hoja de cálculo sin conexión, tenga en cuenta las siguientes sugerencias:

* Elija los elementos que desea cambiar y el número de versiones de cada elemento (3x2, 4x3, etc.).
* Sea coherente en la numeración. Por ejemplo, si el botón es el Elemento 1 y las opciones son Azul, Verde y Amarillo, el botón azul es 1-1, el verde es 1-2 y el amarillo es 1-3.
* La hoja de cálculo sin conexión ofrece el número apropiado de experiencias (cuatro para 3x2, nueve para 4x3, etcétera).
* Cree las experiencias en el flujo de trabajo A/B con el [Compositor de experiencias visuales (VEC)](/help/main/c-experiences/experiences.md). Puede utilizar código personalizado, editar HTML, WYSIWYG o cualquier combinación.
* Una vez terminada la actividad (en función del calculador de tamaño de muestra), ejecute los resultados en la hoja de cálculo para obtener los demás detalles.

## Vídeos de formación {#training-videos}

Los siguientes vídeos contienen más información sobre los conceptos mencionados en esta página.

### Tipos de actividades (9:03) ![Distintivo de información general](/help/main/assets/overview.png)

En este vídeo de información general se explican los tipos de actividades disponibles en [!DNL Target]. Las pruebas multivariable se describen a partir del minuto 4:20. En este vídeo, aprenderá a hacer lo siguiente:

* Describir los tipos de actividades incluidas en [!DNL Adobe Target].
* Seleccione el tipo de actividad adecuado para lograr sus objetivos.
* Describa el flujo de trabajo guiado de tres pasos que se aplica a todos los tipos de actividades.

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo comprender, planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target]. En este vídeo, aprenderá a hacer lo siguiente:

* Defina y diseñe una prueba multivariable.
* Cree una prueba multivariable.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
