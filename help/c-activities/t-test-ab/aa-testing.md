---
keywords: a/b;a/a;aa;
description: Descubra qué es una prueba A/A, por qué podría desear realizar una prueba A/A, cuánto tiempo debe ejecutar la prueba y cómo interpretar los resultados.
title: ¿Qué es la prueba A/A?
feature: A/B Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 1%

---


# Pruebas A/A

Antes de realizar una prueba A/A en el sitio mediante [!DNL Adobe Target], es importante comprender qué es una prueba A/A, por qué puede desear realizar una prueba A/A, cuánto tiempo debe ejecutar la prueba y cómo interpretar los resultados.

## ¿Qué es la prueba A/A?

Antes de explicar las pruebas A/A, es bueno revisar las pruebas A/B para poder analizar las diferencias.

En una prueba A/B estándar, el tráfico se asigna a dos o más experiencias diferentes. Una experiencia es generalmente el &quot;control&quot; y las variaciones de la experiencia se prueban con el control para ver qué experiencia crea el mayor alza en una métrica determinada.

Sin embargo, la prueba A/A implica asignar tráfico a dos experiencias idénticas, normalmente con una división de asignación de tráfico de 50/50. Con una prueba A/B estándar, normalmente desea descubrir un alza en la conversión. Esto difiere de una prueba A/A en la que su objetivo es generalmente determinar que existe *ninguna* diferencia en alza entre las experiencias idénticas.

## ¿Por qué desea probar dos experiencias idénticas y qué se logra con esto?

Algunas organizaciones realizan pruebas A/A al implementar una nueva herramienta de prueba, como [!DNL Target], para determinar si:

* La actividad se configuró correctamente
* El código se implementó correctamente
* El sistema de informes es preciso

Aunque pocas organizaciones ejecutan pruebas A/A, en realidad es recomendable ejecutarlas como experimentos de &quot;sanidad&quot; para generar confianza después de implementar la herramienta o antes de realizar pruebas A/B que puedan afectar a la conversión y a los ingresos.

## ¿Por qué podría ver el alza de una experiencia cuando las experiencias son idénticas?

Existen numerosas razones por las que una experiencia puede mostrar un alza con respecto a otra (idéntica) experiencia:

### La prueba A/A no se pudo ejecutar durante el tiempo suficiente

Un problema común al ejecutar cualquier tipo de prueba, incluida una prueba A/A, es detener una prueba prematuramente y declarar una experiencia ganadora. Los analistas suelen hacer lo que se denomina &quot;búsqueda de datos&quot;. La búsqueda de datos implica mirar los datos de la prueba de forma temprana y frecuente mientras se intenta determinar qué experiencia tiene un mejor rendimiento. El riesgo es detener la prueba prematuramente, lo que podría invalidar los resultados.

En una prueba A/A, la búsqueda de datos puede hacer que los analistas vean el alza en una experiencia, cuando asumen que no debería haber diferencia, porque las dos experiencias son idénticas. Dado el tiempo y las visitas suficientes, la diferencia en el alza debería reducirse.

Al igual que con una prueba A/B normal, debe decidir con antelación el tamaño de la muestra que debe utilizarse, en función del tamaño mínimo del efecto, la potencia y los niveles de relevancia que considere aceptables. En una prueba A/A, el objetivo sería *no* ver un resultado estadísticamente significativo después de que la prueba haya alcanzado el tamaño de muestra deseado.

La [!UICONTROL Calculadora de tamaño de la muestra de Adobe Target] es una herramienta importante para ayudarle a determinar el tamaño de la muestra que debe tener y durante cuánto tiempo debe ejecutar la prueba.

* [Calculadora de tamaño de Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Además, consulte los siguientes artículos para obtener información sobre cuánto tiempo debe ejecutar una actividad, así como otros consejos y trucos útiles:

* [¿Durante cuánto tiempo se debe ejecutar una prueba A/B?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Diez escollos A/B comunes y cómo evitarlos](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### La relevancia estadística afecta a los resultados de la prueba

El nivel de relevancia de una prueba determina la probabilidad de que la prueba arroje una diferencia significativa en las tasas de conversión entre dos ofertas diferentes cuando, de hecho, no hay ninguna diferencia real. Esto se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y existe una compensación entre la tolerancia de falsos positivos y el número de visitantes que deben incluirse en la prueba al elegir el nivel de relevancia adecuado.

Un nivel de relevancia usado comúnmente en las pruebas A/A y A/B es del 5 %, que corresponde a un nivel de confianza del 95 % (nivel de confianza = 100 % - nivel de relevancia). Un nivel de confianza del 95 % significa que cada vez que realice una prueba, hay un 5 % de probabilidades de detectar un alza estadísticamente significativa, incluso si no hay ninguna diferencia entre las experiencias.

Supongamos que desea alcanzar un nivel de confianza del 95 % con la prueba A/A. Con un nivel de confianza del 95 %, 1 de cada 20 pruebas A/A podría mostrar un alza estadísticamente significativa en las conversiones. Con un nivel de confianza del 90 %, 1 de cada 10 pruebas podría mostrar un alza en las conversiones al probar experiencias idénticas.

## Práctica recomendada

Si decide que una prueba A/A es necesaria en su organización, tenga en cuenta que las experiencias idénticas pueden mostrar temporalmente una diferencia con respecto al control. Esto puede ser normal, dependiendo del tiempo en que se permita la ejecución de la prueba. La diferencia debería reducirse en función del tiempo y los visitantes.

Lo mejor es utilizar una metodología de prueba A/B normal: decida el tamaño de la muestra con antelación en función del tamaño mínimo del efecto, la potencia deseada y la relevancia mediante la [calculadora de tamaño de Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

A continuación, permita tiempo y visitantes adecuados antes de llegar a cualquier conclusión, y recuerde que, dependiendo del nivel de relevancia de la prueba, existe la posibilidad de que una experiencia muestre una diferencia en alza e incluso sea declarada ganadora.
