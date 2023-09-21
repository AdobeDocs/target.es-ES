---
keywords: a/b;a/a;aa;
description: Descubra qué es una prueba A/A, por qué podría querer realizarla, durante cuánto tiempo debe ejecutarla y cómo interpretar los resultados.
title: ¿Qué es la prueba A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4f0ebdd06287a438e519d9bccb677ab1a9093396
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 1%

---

# Pruebas A/A

Antes de realizar una prueba A/A en el sitio mediante [!DNL Adobe Target]Sin embargo, es importante comprender qué es una prueba A/A, por qué podría desear realizarla, durante cuánto tiempo debe ejecutarla y cómo interpretar los resultados.

## ¿Qué es la prueba A/A?

Antes de explicar las pruebas A/A, es bueno revisar las pruebas A/B para poder discutir las diferencias.

En una prueba A/B estándar, el tráfico se asigna a dos o más experiencias diferentes. Una experiencia suele ser el &quot;control&quot;, y las variaciones de la experiencia se prueban con el control para ver qué experiencia genera el mayor alza en una métrica determinada.

Sin embargo, las pruebas A/A implican la asignación de tráfico a dos experiencias idénticas, normalmente con una división de asignación de tráfico del 50/50. Con una prueba A/B estándar, normalmente desea descubrir un alza en la conversión. Esto difiere de una prueba A/A en la que el objetivo suele ser determinar que hay *no* diferencia de alza entre las experiencias idénticas.

## ¿Por qué querría probar dos experiencias idénticas y qué logra esto?

Algunas organizaciones realizan pruebas A/A al implementar una nueva herramienta de pruebas, como [!DNL Target], para determinar si:

* La actividad se ha configurado correctamente
* El código se implementó correctamente
* La información es precisa

Aunque pocas organizaciones ejecutan pruebas A/A, es recomendable ejecutarlas como experimentos de &quot;cordura&quot; para generar confianza después de implementar la herramienta o antes de realizar pruebas A/B que puedan afectar a la conversión y a los ingresos.

## ¿Por qué podría ver el alza de una experiencia cuando las experiencias son idénticas?

Existen numerosas razones por las que podría ver el alza de una experiencia sobre otra experiencia (idéntica):

### La prueba A/A se monitorizó continuamente

Un problema común al ejecutar cualquier tipo de prueba, incluida una prueba A/A, es observar los resultados continuamente y detener prematuramente una prueba cuando vea significación estadística y declarar una experiencia ganadora. Los analistas suelen hacer lo que se denomina &quot;búsqueda de datos&quot;. La observación de datos implica ver los datos de prueba de forma temprana y frecuente, a la vez que se intenta determinar qué experiencia está teniendo un mejor rendimiento. El riesgo es detener la prueba prematuramente, lo que podría invalidar los resultados.

En una prueba A/A, la observación de datos a menudo puede hacer que los analistas vean el alza en una experiencia, cuando en realidad no debería haber ninguna diferencia, ya que las dos experiencias son idénticas. De hecho, con el peeking continuo, las pruebas A/A son *garantizado* para mostrar &quot;relevancia estadística&quot; (es decir, una confianza por encima de un determinado umbral, como el 95 %) en algún momento durante la prueba.

Para evitarlo, y al igual que con una prueba A/B normal, debe decidir con antelación qué tamaño de muestra utilizar, en función del tamaño mínimo del efecto (el alza mínima por debajo de la cual un efecto no es importante para su negocio), la potencia y los niveles de relevancia que considere aceptables.

En una prueba A/A, el objetivo sería *no* ver un resultado estadísticamente significativo después de que la prueba haya alcanzado el tamaño de muestra deseado.

El [!UICONTROL Calculadora de tamaño de muestra para Adobe Target] es una herramienta importante para determinar el tamaño de muestra que debe tener como objetivo y durante cuánto tiempo debe ejecutar la prueba.

* [Calculadora de tamaño de Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Además, consulte los siguientes artículos para obtener información sobre cuánto tiempo debe durar una actividad y otros consejos y trucos útiles:

* [¿Durante cuánto tiempo se debe ejecutar una prueba A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Diez dificultades A/B comunes y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La relevancia estadística afecta a los resultados de las pruebas

El nivel de relevancia de una prueba determina la probabilidad de que la prueba notifique una diferencia significativa en las tasas de conversión entre dos ofertas diferentes cuando, de hecho, no hay ninguna diferencia real. Esto se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y existe un equilibrio entre la tolerancia de los falsos positivos y el número de visitantes que deben incluirse en la prueba a la hora de elegir el nivel de relevancia adecuado.

Un nivel de relevancia comúnmente utilizado en las pruebas A/A y A/B es del 5 %, que corresponde a un nivel de confianza del 95 % (nivel de confianza = 100 % - nivel de relevancia). Un nivel de confianza del 95 % significa que, cada vez que realice una prueba, existe una probabilidad del 5 % de detectar un alza estadísticamente significativa, aunque no haya diferencia entre las experiencias.

Supongamos que desea alcanzar un nivel de confianza del 95 % con la prueba A/A. Con un nivel de confianza del 95 %, 1 de cada 20 pruebas A/A podría mostrar un alza estadísticamente significativa en las conversiones. Con un nivel de confianza del 90 %, 1 de cada 10 pruebas podría mostrar un aumento en las conversiones al probar experiencias idénticas.

## Práctica recomendada

Si decide que es necesaria una prueba A/A en su organización, tenga en cuenta que las experiencias idénticas podrían mostrar temporalmente una diferencia con respecto al control. Esto puede ser normal, dependiendo del tiempo que la prueba pueda ejecutarse. La diferencia debería reducirse con más tiempo y visitantes.

La práctica recomendada es utilizar una metodología de prueba A/B normal: decidir el tamaño de la muestra con antelación en función de un tamaño de efecto relevante mínimo, la potencia deseada y la relevancia utilizando [Calculadora de tamaño de Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Deje tiempo y visitantes adecuados antes de sacar conclusiones, y recuerde que, según el nivel de relevancia de la prueba, existe la posibilidad de que una experiencia muestre una diferencia de alza e incluso de que se la declare ganadora.
