---
keywords: a/b;a/a;aa;
description: Descubra qué es una prueba A/A, por qué podría querer realizar una prueba A/A, cuánto tiempo debe ejecutar la prueba y cómo interpretar los resultados.
title: ¿Qué es la prueba A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4e3a94554dd9c1e8cc6e98eda10d454536bc9b1f
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Pruebas A/A

Antes de realizar una prueba A/A en el sitio mediante [!DNL Adobe Target], es importante comprender qué es una prueba A/A, por qué puede querer realizar una prueba A/A, cuánto tiempo debe ejecutar la prueba y cómo interpretar los resultados.

## ¿Qué es la prueba A/A?

Antes de explicar las pruebas A/A, es bueno revisar las pruebas A/B para poder analizar las diferencias.

En una prueba A/B estándar, el tráfico se asigna a dos o más experiencias diferentes. Una experiencia suele ser el &quot;control&quot; y las variaciones de la experiencia se prueban con el control para ver qué experiencia crea el mayor alza en una métrica determinada.

Sin embargo, las pruebas A/A implican la asignación de tráfico a dos experiencias idénticas, normalmente con una división de asignación de tráfico de 50/50. Con una prueba A/B estándar, normalmente desea descubrir un alza en la conversión. Esto difiere de una prueba A/A en la que su objetivo es generalmente determinar que hay *no* diferencia en el alza entre experiencias idénticas.

## ¿Por qué querría probar dos experiencias idénticas y qué se logra con esto?

Algunas organizaciones realizan pruebas A/A al implementar una nueva herramienta de prueba, como [!DNL Target], para determinar si:

* La actividad se configuró correctamente
* El código se implementó correctamente
* El informe es preciso

Aunque pocas organizaciones ejecutan pruebas A/A, en realidad es recomendable ejecutarlas como experimentos de &quot;sanidad&quot; para crear confianza después de implementar la herramienta o antes de realizar pruebas A/B que puedan afectar a la conversión y a los ingresos.

## ¿Por qué podría ver el alza de una experiencia cuando son idénticas?

Existen numerosas razones por las que una experiencia puede aumentar de una experiencia a otra (idéntica):

### La prueba A/A se monitorizó continuamente

Un problema común en la ejecución de cualquier tipo de prueba, incluida una prueba A/A, es observar los resultados de forma continua y detener una prueba antes de tiempo tan pronto como vea la relevancia estadística y declarar una experiencia ganadora. Los analistas suelen hacer lo que se denomina &quot;búsqueda de datos&quot;. La búsqueda de datos implica observar los datos de prueba de forma temprana y frecuente, al mismo tiempo que se intenta determinar qué experiencia tiene un mejor rendimiento. El riesgo es detener la prueba antes de tiempo, lo que podría invalidar los resultados.

En una prueba A/A, la búsqueda de datos puede hacer que los analistas vean el alza en una experiencia, cuando de hecho no debería haber diferencia, ya que las dos experiencias son idénticas. De hecho, con la búsqueda continua, las pruebas A/A son en realidad _garantizado_ para mostrar &quot;relevancia estadística&quot; (es decir, una confianza por encima de un determinado umbral, como 95%) en algún momento durante la prueba.

Para evitarlo, y al igual que con una prueba A/B normal, debe decidir con antelación qué tamaño de muestra utilizar, en función del tamaño mínimo del efecto (el alza mínima por debajo del cual un efecto no es importante para su negocio), los niveles de potencia y de relevancia que considere aceptables.

En una prueba A/A, el objetivo sería: *not* vea un resultado estadísticamente significativo después de que la prueba haya alcanzado el tamaño de muestra deseado.

La variable [!UICONTROL Calculadora de tamaño de muestra de Adobe Target] es una herramienta importante para ayudarle a determinar el tamaño de la muestra que debe especificar y cuánto tiempo debe ejecutar la prueba.

* [Calculadora de tamaño de Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Además, consulte los siguientes artículos para obtener información sobre cuánto tiempo debe ejecutar una actividad, así como otros consejos y trucos útiles:

* [¿Durante cuánto tiempo se debe ejecutar una prueba A/B?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Diez escollos A/B comunes y cómo evitarlos](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La relevancia estadística influye en los resultados de las pruebas

El nivel de relevancia de una prueba determina la probabilidad de que la prueba informe una diferencia significativa en las tasas de conversión entre dos ofertas diferentes cuando, de hecho, no hay ninguna diferencia real. Esto se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y hay un equilibrio entre la tolerancia para falsos positivos y el número de visitantes que deben incluirse en la prueba a la hora de elegir el nivel de relevancia adecuado.

Un nivel de relevancia usado comúnmente en las pruebas A/A y A/B es del 5 %, que corresponde a un nivel de confianza del 95 % (nivel de confianza = 100 % - nivel de relevancia). Un nivel de confianza del 95 % significa que cada vez que realice una prueba, hay un 5 % de probabilidades de detectar un alza estadísticamente relevante aunque no haya diferencia entre las experiencias.

Supongamos que desea alcanzar un nivel de confianza del 95 % con la prueba A/A. Con un nivel de confianza del 95 %, 1 de cada 20 pruebas A/A podría mostrar un aumento estadísticamente significativo en las conversiones. Con un nivel de confianza del 90 %, una de cada diez pruebas podría mostrar un aumento en las conversiones al probar experiencias idénticas.

## Práctica recomendada

Si decide que es necesario realizar una prueba A/A en su organización, tenga en cuenta que las experiencias idénticas podrían mostrar temporalmente una diferencia con respecto al control. Esto puede ser normal, dependiendo del tiempo en que se permita que se ejecute la prueba. La diferencia debe reducirse en función de la cantidad de tiempo y visitantes.

Una práctica recomendada es utilizar una metodología normal de pruebas A/B: decida el tamaño de la muestra con antelación en función de un tamaño de efecto relevante mínimo, la potencia deseada y la relevancia mediante el uso de la variable [Calculadora de tamaño de Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

A continuación, antes de llegar a cualquier conclusión, conceda el tiempo y los visitantes adecuados y recuerde que, en función del nivel de relevancia de la prueba, existe la posibilidad de que una experiencia muestre una diferencia en el alza e incluso se declare la ganadora.
