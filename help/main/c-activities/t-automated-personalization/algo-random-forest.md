---
keywords: bosque aleatorio;árbol de decisión;ap;Automated Personalization
description: Descubra cómo [!DNL Adobe Target] usa el algoritmo de bosque aleatorio en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática].
title: ¿Cómo usa [!DNL Target] el algoritmo de bosque aleatorio?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
TQID: 'https://experienceleague.adobe.com/Ui8E8CkiiJSdqim9fzIgPDdsKG1MMtuu3EUuAqgmm0M'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 7%
---
# Algoritmo de bosque aleatorio {#random-forest-algorithm}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo [!DNL Target] utiliza el algoritmo de bosque aleatorio para crear los modelos de personalización de las actividades **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]**.

>[!ENDSHADEBOX]

El algoritmo de personalización principal usado en las actividades **[!UICONTROL Automated Personalization]** (AP) y **[!UICONTROL Segmentación automática]** es el de bosque aleatorio. Es un método de clasificación o regresión que opera mediante la construcción de una multitud de árboles de decisión cuando se está entrenando.

El bosque aleatorio es un método de ensamblado. Al considerar las estadísticas, es habitual pensar en un modelo de regresión único para predecir un resultado. Las últimas investigaciones de ciencia de datos sugieren que los &quot;métodos de ensamblado&quot;, en los que se crean varios modelos a partir del mismo conjunto de datos y luego se combinan de forma inteligente, producen mejores resultados que las predicciones basadas en un solo modelo o que los que se podrían obtener de cualquiera de los algoritmos de aprendizaje constituyentes.

## ¿Qué es un árbol de decisión? {#section_7F5865D8064447F4856FED426243FDAC}

Un árbol de decisión desglosa en grupos todos los datos de visitas de los que puede aprender un sistema. Las visitas dentro de cada grupo son lo más similares posible entre sí con respecto a la métrica de objetivo (por ejemplo, tasa de conversión) y las visitas entre grupos son lo más diferentes posible. Para ello, el árbol observa las variables del conjunto de formación y divide los datos de forma mutuamente exclusiva y colectivamente exhaustiva (MECE) en grupos (u &quot;hojas&quot;) que maximizan este objetivo.

En el siguiente ejemplo simple, la métrica de objetivo es conversión y hay dos variables de entrada:

* Sexo (con dos valores potenciales: hombre o mujer)
* Código postal (con cinco valores potenciales en el pequeño conjunto de datos: 11111, 22222, 33333, 44444 o 55555)

### Primera división {#first-split}

El árbol determina primero cuál de las dos variables explica la mayor cantidad de variación en la tasa de conversión de los datos de visita. Supongamos que el código postal es más predictivo. Esta variable forma la primera &quot;rama&quot; del árbol. A continuación, el árbol divide los datos de visita en grupos, tal como se ha descrito anteriormente. Supongamos que 11111, 22222 y 33333 son una división, y 44444 y 55555 son una segunda división.

![Primera capa del árbol de decisión](assets/decsion_tree_1.png){width="440" align="center"}

### Dividir dentro de cada rama {#second-split}

El árbol plantea la pregunta: &quot;¿Cuál es la variable más predictiva?&quot; nuevamente, y completa un ejercicio similar para dividir los datos *dentro de cada rama*. Solo queda el género, así que es la respuesta aquí. En las ramas 11111, 22222 y 33333, supongamos que hay una diferencia en la conversión entre hombres y mujeres. Hay entonces dos hojas (hombres y mujeres), y esta rama está completa. En las ramas 44444 y 55555, supongamos que no hay diferencia estadística entre la manera en que mujeres y hombres se convierten. En este caso, la primera división es la división final.

![Completar árbol de decisión](assets/decsion_tree_2.png){width="480" align="center"}

## ¿Cómo utiliza el bosque aleatorio los árboles de decisión? {#section_536C105EF9F540C096D60450CAC6F627}

Los árboles de decisión pueden ser una herramienta estadística muy útil. Sin embargo, presenta algunas desventajas. Lo más importante es que pueden &quot;sobreajustar&quot; los datos, de modo que un árbol individual no prediga bien los datos futuros que no se utilizaron para construir el árbol inicial. En estadística, este problema se conoce como [compensación sesgo-varianza](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff).

Los bosques aleatorios ayudan a superar este desafío. Un bosque aleatorio es una colección de cientos de árboles de decisión que se construyen de manera ligeramente diferente en el mismo conjunto de datos y que &quot;votan&quot; juntos para producir un modelo mejor que un árbol individual. Los árboles se construyen mediante la selección aleatoria de un subconjunto de registros de visita con reemplazo (conocido como ensacado) y la selección aleatoria de un subconjunto de los atributos, de modo que el bosque consta de árboles de decisión ligeramente diferentes. Este método introduce pequeñas variaciones en los árboles. Agregar esta cantidad controlada de varianza ayuda a mejorar la precisión predictiva del algoritmo.

## ¿Cómo utilizan los algoritmos de personalización de [!DNL Target] el bosque aleatorio? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Cómo se crean los modelos

[!DNL Target] utiliza datos que recopila automáticamente, así como datos personalizados proporcionados por usted, para generar sus algoritmos de personalización. El diagrama siguiente resume cómo se crean los modelos para las actividades de **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**:

![Flujo que resume cómo se crean los modelos de bosque aleatorio](assets/random_forest_flow.png){width="850" zoomable="yes"}

1. [!DNL Target] recopila datos sobre los visitantes al ofrecer experiencias u ofertas de forma aleatoria.
1. Después de que [!DNL Target] alcance una masa crítica de datos, [!DNL Target] realiza ingeniería de características.
1. [!DNL Target] crea modelos de bosque aleatorio para cada experiencia u oferta.
1. [!DNL Target] valida el modelo comprobando si cumple una puntuación de calidad de umbral.
1. [!DNL Target] inserta el modelo en producción para personalizar el tráfico futuro.

Estos modelos predicen la mejor experiencia u oferta para mostrar a los visitantes. Por lo general, se crea un modelo por experiencia (en una actividad de **[!UICONTROL segmentación automática]**) o por oferta (en una actividad de **[!UICONTROL Automated Personalization]**). [!DNL Target] muestra la experiencia u oferta que produce la métrica de éxito más alta prevista (por ejemplo, tasa de conversión). Los modelos deben recibir formación sobre las visitas servidas aleatoriamente antes de poder utilizarse para la predicción. Como resultado, incluso los visitantes que están en el grupo personalizado ven diferentes experiencias u ofertas aleatoriamente cuando comienza una actividad, hasta que los algoritmos de personalización están listos.

Los modelos se validan en función de su área bajo la curva (AUC) para garantizar que cada modelo sea bueno para predecir el comportamiento de los visitantes antes de que se utilice en su actividad. La hora exacta en la que un modelo empieza a servir experiencias personalizadas depende de los detalles de los datos, ya que el modelo debe validarse primero. En la práctica, y para la planificación del tráfico, normalmente se requiere más de un número mínimo de conversiones para que cada modelo sea válido.

Cuando un modelo se vuelve válido para una experiencia u oferta, el icono de reloj a la izquierda del nombre de la experiencia u oferta cambia a una casilla de verificación verde. Cuando hay modelos válidos para al menos dos experiencias u ofertas, algunas visitas comienzan a personalizarse.

### Transformación de funciones

Antes de que los datos pasen por el algoritmo de personalización, se someten a una transformación de funciones, que puede considerarse como la preparación de los datos recopilados en los registros de formación para su uso en los modelos de personalización. La transformación depende del tipo de atributo (o &quot;función&quot;, como a veces lo describen los científicos de datos):

| Tipo de funcionalidad | Descripción | Transformación |
|---|---|---|
| **Categórico** | No se pueden contar, pero se pueden ordenar en diferentes grupos, como país, sexo o código postal. | Se mantiene un conjunto de todas las funciones posibles y se utiliza la transformación de la probabilidad para reducir el tamaño de los datos. |
| **Numéricos** | Se puede medir o contar, como la edad o los ingresos. | El cambio de escala garantiza que las funciones sean comparables en todos los aspectos. |

### Equilibrio entre aprendizaje y personalización con el método multi-armed bandit

Después de que [!DNL Target] haya creado los modelos de personalización, se enfrenta a un dilema para los visitantes futuros de su actividad. Puede personalizar todo el tráfico en función del modelo actual o puede seguir aprendiendo de los nuevos visitantes ofreciéndoles ofertas aleatorias de forma aleatoria. El algoritmo de personalización siempre debe conocer las nuevas tendencias en sus visitantes, a la vez que personaliza la mayor parte del tráfico. El método multi-armed bandit es cómo [!DNL Target] cumple este objetivo: garantiza que el modelo siempre &quot;gasta&quot; una pequeña fracción de tráfico para seguir aprendiendo a lo largo de la vida de la actividad y evitar la sobreexplotación de las tendencias aprendidas anteriormente.

En el mundo de la ciencia de datos, el problema de los bandidos multiarmados es un ejemplo clásico del dilema de exploración contra explotación, en el que se da una colección de bandidos con un solo brazo, cada uno con una probabilidad de recompensa desconocida. La idea clave es desarrollar una estrategia que resulte en el brazo con la mayor probabilidad de éxito que se juega, de modo que la recompensa total obtenida se maximice. El multi-armed bandit se utiliza en el sistema para la puntuación en línea después de crear los modelos en línea. Este proceso ayuda con el aprendizaje en línea durante la exploración. El algoritmo multiarmado actual es un algoritmo voraz épsilon (). En este algoritmo, con la probabilidad 1 -, se elige el mejor brazo. Con la probabilidad de que se produzca el error, se elige aleatoriamente cualquier otro brazo.
