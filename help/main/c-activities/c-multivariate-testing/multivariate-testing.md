---
keywords: prueba multivariable;mvt;factorial completa;mvt o a/b;a/b multivariable;estimador de tráfico;cuándo usar mvt;consideraciones de mvt;multivariable;factorial parcial;factorial parcial;factorial completa
description: Aprenda a usar un [!UICONTROL Multivariate Test] (MVT) en  [!DNL Adobe Target] para comparar combinaciones de ofertas en elementos de una página y determinar qué combinación ofrece el mejor rendimiento.
title: ¿Qué es un [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 48%

---

# Resumen de [!UICONTROL Multivariate Test]

Una actividad [!UICONTROL Multivariate Test] (MVT) en [!DNL Adobe Target] compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica. Una actividad [!UICONTROL Multivariate Test] también ayuda a identificar qué elemento tiene el mayor impacto en el éxito de la actividad.

Las pruebas multivariable ayudan a descubrir la influencia relativa que tienen determinados elementos en la conversión, en comparación con otros elementos de la página. Las pruebas multivariable también pueden ayudarle a refinar una combinación de elementos que han demostrado ser eficaces.

Una ventaja que proporciona [!UICONTROL Multivariate Test] en comparación con una prueba A/B es la capacidad de mostrar qué elementos de la página tienen la mayor influencia en la conversión. Esta ventaja también se conoce como el &quot;efecto principal&quot;. Esta información es útil, por ejemplo, para ayudarle a determinar dónde colocar el contenido que desea que reciba la mayor atención.

Las actividades [!UICONTROL Multivariate Test] también le ayudan a encontrar efectos compuestos entre dos o más elementos de una página. Por ejemplo, un anuncio concreto podría generar más conversiones si se combinara con un determinado banner o una imagen a pantalla completa (hero). Esto también se conoce como el “efecto interacción”.

[!DNL Target] usa pruebas multivariable factoriales completas para ayudarle a optimizar su contenido. Una prueba multivariable factorial completa examina todas las combinaciones posibles de contenido con igual probabilidad. Por ejemplo, si tiene dos elementos de página con tres ofertas cada uno, hay nueve combinaciones posibles (3x3). Cuando hay tres elementos, de los cuales dos contienen tres ofertas posibles y uno tiene dos ofertas, se generan 18 opciones (3x3x2).

En [!DNL Target], cada combinación es una experiencia. El [!UICONTROL Multivariate Test] compara cada experiencia para que pueda saber qué combinaciones son las más exitosas. Al mismo tiempo, se recopilan y analizan datos para comprender en qué medida influyen las ubicaciones y las ofertas en la métrica de éxito.

![imagen multivariable](assets/multivariate.png)

Dado el número de combinaciones que se pueden generar, un [!UICONTROL Multivariate Test] requiere más tiempo y tráfico que una prueba A/B. La página debe recibir tráfico suficiente para generar resultados relevantes estadísticamente para cada experiencia. Para obtener resultados útiles, debe comprender la cantidad de tráfico que recibe su página y probar la cantidad óptima de combinaciones durante el tiempo adecuado para obtener los resultados requeridos.

El [estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) de Target puede ayudarle a diseñar una prueba que funcione con su tráfico. Antes de usar el estimador de tráfico, debe disponer de estadísticas fiables que muestren el número de impresiones y conversiones que normalmente recibe su sitio. Considere los niveles de tráfico por día. Cuantas más experiencias haya en una actividad, más tráfico deberá incluir la actividad o más tiempo deberá ejecutarse. Si la cantidad de tráfico no es alta, debe probar algunas combinaciones; de lo contrario, la cantidad de tiempo necesaria para generar resultados de prueba significativos podría ser demasiado larga para ser útil.

## Terminología de MVT {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

Cuando configure una prueba multivariable, le resultará útil conocer alguna terminología básica.

Hay varios términos que se utilizan de manera distinta en el sector. En esta sección explicamos los términos que se utilizan en [!DNL Target].

**Combinación:** las variaciones de contenido que se crean al probar varias opciones de contenido en varias ubicaciones. Por ejemplo, si va a probar tres ubicaciones, cada una de ellas con tres opciones de contenido, entonces hay 27 combinaciones posibles (3x3x3). Un visitante del sitio ve una combinación que también se denomina experiencia.

**Contenido:** el texto o la imagen que contiene una variación de prueba dentro de una ubicación. En una prueba multivariable, se comparan varias opciones de contenido dentro de varias ubicaciones. En la metodología de las pruebas MVT, el contenido a menudo se denomina *nivel*.

**Elemento:** elemento DOM que tiene las variaciones de contenido que se van a probar en la prueba MVT. Vea también *Ubicación*.

**Ubicación:** área específica de contenido en una página, a menudo incluida en un solo elemento de DOM. En la metodología de las pruebas MVT, la ubicación a menudo se denomina *factor*. Una prueba multivariable factorial completa compara todas las combinaciones posibles de las ofertas en las ubicaciones.

## Cuándo usar [!UICONTROL Multivariate Test] frente a A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Las pruebas multivariable (MVT) se pueden utilizar junto con las pruebas A/B para optimizar la página. Estos son algunos ejemplos de cuándo puede interesarle usar las dos pruebas:

* Utilice una prueba A/B para optimizar el diseño de la página, seguida de una prueba MVT para determinar el mejor contenido en cada elemento de la página.

  Una prueba A/B puede proporcionar información importante sobre el diseño, mientras que una prueba MVT es excelente para probar contenido dentro de los elementos del diseño de la página. Si ejecuta una prueba A/B sobre el diseño antes de probar varias opciones de contenido, podrá determinar cuál es el mejor diseño y qué contenido logra un mayor impacto.

* Utilice una prueba MVT para determinar qué elemento es el más importante y, después, realice una prueba A/B que se centre en ese elemento.

  Cuando el número de experiencias diferentes es superior a cinco y abarca dos o más elementos, es aconsejable realizar una prueba MVT antes de ejecutar las pruebas A/B. La prueba multivariable muestra qué áreas de la página tienen más posibilidad de mejorar la conversión. Estos son los elementos en los que debería centrarse un especialista en marketing. Por ejemplo, la prueba MVT podría mostrar que la llamada a la acción es el elemento más importante para lograr sus objetivos. Una vez que haya determinado qué elementos y contenido son más útiles para ayudarle a alcanzar sus objetivos, puede ejecutar una prueba A/B para refinar aún más los resultados. Por ejemplo, puede probar dos imágenes específicas una contra la otra o comparar las palabras o los colores de una llamada a la acción. Si después de una prueba MVT se realizan una o varias pruebas A/B, puede determinar el mejor contenido posible para los resultados que desea obtener.

## Consideraciones   {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Utilice una prueba MVT cuando tenga al menos tres elementos que probar. Si tiene menos, ejecute una serie de pruebas A/B.
* Seleccione los elementos de página que crea que tienen un impacto más significativo en los resultados.
* No incluya demasiados elementos o ubicaciones en una prueba. Cuanto mayor sea el número, mayor será la duración de la prueba.
* Planifique el diseño de la prueba con antelación. No edite una prueba después de que se active y de que los datos comiencen a recopilarse y analizarse.
* Los elementos deben ser independientes entre sí.

  Por ejemplo, no realice una prueba del diseño y del contenido a la vez.

* Planifique un tiempo adicional de control de calidad debido al aumento en el número de experiencias. También puede utilizar pruebas factoriales parciales para reducir la cantidad de tráfico necesario para una prueba multivariable. Para obtener más información, consulte Pruebas factoriales parciales a continuación:

## Pruebas factoriales parciales

[!DNL Target] ofrece pruebas multivariable totalmente factoriales como opción de actividad integrada. En las estadísticas,
&quot;Diseño de experimentos&quot; ofrece muchos enfoques, o diseños, para determinar qué factores influyen en los resultados. Uno de estos enfoques es el [Método Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) para pruebas factoriales parciales. Taguchi permite a los especialistas en marketing realizar una serie de suposiciones que reducen el número de permutaciones de experiencias que se deben probar, lo que a su vez reduce los requisitos de tráfico para una prueba multivariable. Esta funcionalidad y enfoque de prueba se pueden aplicar en [!DNL Target] con esta [hoja de cálculo sin conexión](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Si su equipo utiliza otros enfoques de Diseño de experimentos, puede utilizar esta hoja de cálculo como implementación de referencia para diseños de experimentos personalizados.

Al utilizar la hoja de cálculo sin conexión, tenga en cuenta las siguientes sugerencias:

* Elija los elementos que desea cambiar y el número de versiones de cada elemento (3x2, 4x3, etc.).
* Sea coherente en la numeración. Por ejemplo, si el botón es el Elemento 1 y las opciones son Azul, Verde y Amarillo, el botón azul es 1-1, el verde es 1-2 y el amarillo es 1-3.
* La hoja de cálculo sin conexión ofrece el número apropiado de experiencias (cuatro para 3x2, nueve para 4x3, etcétera).
* Cree las experiencias en el flujo de trabajo A/B con el [Compositor de experiencias visuales (VEC)](/help/main/c-experiences/experiences.md). Puede utilizar código personalizado, editar HTML, WYSIWYG o cualquier combinación.
* Una vez terminada la actividad (en función del calculador de tamaño de muestra), ejecute los resultados en la hoja de cálculo para obtener los demás detalles.

Para obtener más consideraciones y prácticas recomendadas, consulte [Prácticas recomendadas de pruebas multivariable](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Tipos de actividades (9:03) ![Distintivo de información general](/help/main/assets/overview.png)

En este vídeo de información general se explican los tipos de actividades disponibles en [!DNL Target]. Las pruebas multivariable se describen a partir del minuto 4:20.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo comprender, planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de Target.

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)
