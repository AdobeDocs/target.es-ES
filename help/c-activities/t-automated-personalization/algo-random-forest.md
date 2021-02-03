---
keywords: bosque aleatorio;árbol de decisiones;ap;Automated Personalization
description: Algoritmo de personalización principal de Target que se utiliza en la Personalización automatizada y en la Segmentación automática es el de bosque aleatorio. Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un rendimiento más predictivo que el que podría obtenerse de cualquier algoritmo de aprendizaje constituyente. El algoritmo de bosque aleatorio en Personalización automatizada es un método de clasificación o regresión que funciona creando una multitud de árboles de decisión durante el aprendizaje.
title: Algoritmo de bosque aleatorio
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 97%

---


# ![PREMIUM](/help/assets/premium.png) Algoritmo de bosque aleatorio

Algoritmo de personalización principal de Target que se utiliza en la Personalización automatizada y en la Segmentación automática es el de bosque aleatorio. Los métodos de ensamblado, como el bosque aleatorio, utilizan varios algoritmos de aprendizaje para obtener un rendimiento más predictivo que el que podría obtenerse de cualquier algoritmo de aprendizaje constituyente. El algoritmo de bosque aleatorio en Personalización automatizada es un método de clasificación o regresión que funciona creando una multitud de árboles de decisión durante el aprendizaje.

Al considerar las estadísticas, es habitual pensar en un modelo de regresión único para predecir un resultado. Sin embargo, las investigaciones de ciencia de datos más recientes sugieren que los “métodos de ensamblado”, en que se crean varios modelos a partir del mismo conjunto de datos y se combinan de forma inteligente, arrojan mejores resultados que las predicciones basadas en un único modelo.

El algoritmo de bosque aleatorio es la clave que se esconde en el algoritmo de personalización utilizado en actividades de Personalización automatizada y Segmentación automática. Con el bosque aleatorio se combinan cientos de árboles de decisiones para conseguir una mejor predicción que la que se conseguiría con un solo árbol.

## ¿Qué es un árbol de decisiones? {#section_7F5865D8064447F4856FED426243FDAC}

El objetivo de un árbol de decisión es desglosar todos los datos de visitas disponibles de los que un sistema puede aprender y agruparlos de modo que las visitas de cada grupo sean lo más parecidas posibles las unas a las otras con relación a la métrica objetivo. Entre grupos, sin embargo, las visitas son lo más diferentes posibles con relación a la métrica objetivo (por ejemplo, la tasa de conversión). El árbol de decisión tiene en cuenta las diferentes variables existentes en el conjunto de formación para determinar cómo dividir los datos de forma MECE (mutuamente exclusiva, colectivamente exhaustiva) en estos grupos (u “hojas”) para maximizar este objetivo.

Veamos un ejemplo sencillo: imaginemos que solo tenemos dos variables de entrada:

* Sexo (con dos valores potenciales: hombre o mujer)
* Código postal (con cinco valores potenciales en nuestro pequeño conjunto de datos: 11111, 22222, 33333, 44444 o 55555)

Si nuestra métrica objetivo es la conversión, en primer lugar el árbol determinará cuál de nuestras dos variables explica la mayor variación en la tasa de conversión de los datos de visitas.

Pongamos que el código postal es más predictivo. Esta variable formaría la primera “rama” del árbol. A continuación, el árbol de decisión determinaría cómo dividir los datos de visitas, por ejemplo, que la tasa de conversión de los registros de cada división fuera lo más similar posible y la tasa de conversión entre divisiones fuera lo más diferente posible. En nuestro ejemplo, tendremos 11111, 22222 y 33333 en una división y 44444 y 55555 en la otra.

Esta acción se convertirá en la primera capa de nuestro árbol de decisión:

![](assets/decsion_tree_1.png)

El árbol de decisión le preguntará: “¿Cuál es la variable más predictiva?”. En nuestro ejemplo, solo tenemos dos variables, así que la respuesta es claramente el sexo. Ahora el árbol va a realizar un ejercicio similar para dividir los datos *dentro de cada rama*. En primer lugar, consideraremos la rama 11111, 22222 y 33333. En estos códigos postales, si hay alguna diferencia de conversión entre hombres y mujeres, habrá dos hojas (hombres y mujeres) y esta rama estará completa. En la otra rama, 44444 y 55555, asumiremos que no hay ninguna diferencia estadística entre cómo convierten los hombres y las mujeres. En este caso, la primera rama se convierte en la división final.

El árbol de nuestro ejemplo sería el siguiente:

![](assets/decsion_tree_2.png)

## ¿Cómo se utilizan los árboles de decisión por bosque aleatorio? {#section_536C105EF9F540C096D60450CAC6F627}

Los árboles de decisión pueden ser una herramienta estadística muy útil. Sin embargo, presenta algunas desventajas. La más importante es que se puede producir un sobreajuste de datos, con lo que un solo árbol difícilmente predeciría datos futuros que no se hubieran utilizado para crear el árbol inicial. En estadística, este problema se conoce como [compensación sesgo-varianza](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff). Los bosques aleatorios ayudan a superar este problema de sobreajuste. En su máximo nivel, un bosque aleatorio es un conjunto de árboles de decisión que se ha creado de un modo algo distinto a partir del mismo conjunto de datos que “vota” conjuntamente para producir un modelo mejor que un árbol individual. Los árboles se crean seleccionando aleatoriamente un subconjunto de registros de visitas con sustitución (conocidos como empacados) y seleccionando aleatoriamente un subconjunto de los atributos para que el bosque esté formado de árboles de decisión ligeramente distintos. Con este método se introducen pequeñas variaciones en los árboles que se crean en el bosque aleatorio. Al añadir esta cantidad controlada de varianza, la precisión predictiva del algoritmo mejora.

## ¿Cómo utilizan los algoritmos de personalización de Destinatario el bosque aleatorio? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

**¿Cómo se crean los modelos?**

El diagrama siguiente resume cómo se crean los modelos para las actividades de Segmentación automática o de Personalización automatizada:

![](assets/random_forest_flow.png)

1. Target recopila datos sobre visitantes, mientras sirve aleatoriamente experiencias y ofertas.
1. Cuando Target consigue una cantidad de datos importante, realiza ingeniería de características.
1. Target crea modelos de bosque aleatorio para cada experiencia/oferta.
1. Target comprueba si el modelo llega al umbral de la puntuación de calidad.
1. Target lleva el modelo a producción para personalizar el tráfico futuro.

Target utiliza los datos que recopila automáticamente, así como los datos personalizados proporcionados por el usuario, para crear sus algoritmos personalizados. Estos modelos predicen la mejor experiencia u oferta para mostrar a los visitantes. Normalmente, un modelo se crea por experiencia (en el caso de una actividad de Segmentación automática) o por oferta (en el caso de una actividad de Personalización automatizada). A continuación, Target opta por mostrar la experiencia u oferta que proporcione la métrica con mayor predicción de éxito (por ejemplo, la tasa de conversión). Estos modelos deben prepararse a partir de visitas ofrecidas aleatoriamente para que se puedan utilizar para la predicción. Como consecuencia, al iniciar una actividad, se muestran aleatoriamente experiencias u ofertas diferentes incluso a los visitantes que se encuentran en el grupo personalizado mientras los algoritmos de personalización no están listos.

Todos los modelos se deben validar para garantizar que son aptos para predecir el comportamiento de visitantes antes de utilizarse en la actividad. Los modelos se validan a partir de su ABC (área bajo la curva). Como se requiere una validación, el momento exacto en que un modelo empieza a ofrecer experiencias personalizadas depende de los detalles de los datos. En la práctica, y para la planificación del tráfico, normalmente se requiere más de un número mínimo de conversiones para que cada modelo sea válido.

Cuando un modelo es válido para una experiencia u oferta, el icono de reloj situado a la izquierda del nombre de la experiencia/oferta se convierte en una casilla de verificación verde. Si hay modelos válidos para un mínimo de dos experiencias/ofertas, algunas visitas empiezan a personalizarse.

**Transformación de la característica **

Antes de que los datos pasen por el algoritmo de personalización, se someten a una transformación de la característica, que se puede considerar como una preparación de los datos recopilados en registros de formación para que los modelos de personalización los puedan utilizar.

Las transformaciones de la característica dependen del tipo de atributo. Principalmente, hay dos tipos de atributos (o “características”, tal como a veces los describen los analistas de datos):

* **Características categóricas:** no se pueden contar, pero se pueden ordenar en distintos grupos. Pueden ser características como país, sexo o código postal.
* **Características numéricas:** se pueden medir o contar, como la edad, los ingresos, etc.

Para las características categóricas, se mantiene un conjunto de todas las características posibles y la posibilidad de que se use la transformación para reducir el tamaño de los datos. Para las características numéricas, el reajuste de escala garantiza que las características se puedan comparar en el panel.

**Equilibrio entre aprendizaje y personalización con el Multi-Armed Bandit**

Cuando Target haya creado modelos de personalización para personalizar su tráfico, deberá afrontar una clara compensación en el caso de los futuros visitantes de su actividad: ¿debe personalizar todo el tráfico a partir del modelo actual o debe seguir aprendiendo de los nuevos visitantes haciéndoles ofertas aleatorias? Le interesa asegurarse de que el algoritmo de personalización siempre aprenda de las tendencias nuevas de sus visitantes, al mismo tiempo que personaliza la mayor parte del tráfico.

El método multi-armed bandit es la forma en que Target le ayuda a cumplir este objetivo. El método multi-armed bandit garantiza que el modelo siempre destine una pequeña fracción de tráfico a seguir con el aprendizaje mientras dure el aprendizaje de la actividad y a evitar la sobreexplotación de las tendencias aprendidas anteriormente.

En el mundo del análisis de datos, el problema multi-armed bandit (MAB) es un ejemplo clásico del dilema de exploración frente a explotación que se da ante una colección de máquinas tragaperras de una palanca, cada una de ellas con una probabilidad de premio desconocida. La idea principal consiste en desarrollar una estrategia que conozca cuál es la palanca con la mayor probabilidad de éxito que debe accionarse, para maximizar el premio total obtenido. El problema MAB se usa en el sistema para la puntuación en línea después de crear los modelos en línea. Esto ayuda en el aprendizaje en línea durante la exploración. El algoritmo MAB actual es el algoritmo voraz con epsilon (ε). En este algoritmo, con probabilidad 1- ε, se elige la mejor palanca. Y, con probabilidad ε, se elige cualquier otra palanca aleatoriamente.
