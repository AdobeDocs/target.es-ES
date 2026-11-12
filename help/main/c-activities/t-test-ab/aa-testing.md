---
keywords: a/b;a/a;aa;
description: Descubra qué es una prueba A/A, por qué podría querer realizarla, durante cuánto tiempo debe ejecutarla y cómo interpretar los resultados.
title: ¿Qué es la prueba A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
TQID: 'https://experienceleague.adobe.com/-kLz0mG8LaFqEbB-9M89vJWTFjfypupbcOQ3MjQz-jQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 322dbbd67ea981ad05ed8a1fdc1137ec50effd12
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 1%
---
# Pruebas A/A {#aa-testing}

>[!BEGINSHADEBOX]

**En esta página:** Descubra qué es una prueba A/A, por qué podría ejecutar una, por qué podría ver un alza entre experiencias idénticas y la práctica recomendada para ejecutar una prueba A/A en [!DNL Target].

>[!ENDSHADEBOX]

Antes de realizar una prueba A/A en el sitio con [!DNL Adobe Target], es importante comprender qué es una prueba A/A, por qué podría querer realizarla, durante cuánto tiempo debería ejecutarla y cómo interpretar los resultados.

## ¿Qué es la prueba A/A? {#what-is-aa}

Una prueba A/A difiere de una prueba A/B estándar en la forma en que se asigna el tráfico y en lo que desea aprender:

* **Prueba A/B:** El tráfico se asigna a dos o más experiencias diferentes. Una experiencia suele ser el &quot;control&quot;, y las variaciones de la experiencia se prueban con el control para ver qué experiencia genera el mayor alza en una métrica determinada. Normalmente, desea descubrir un alza en la conversión.
* Prueba **A/A:** El tráfico se asigna a dos experiencias idénticas, normalmente con una división de asignación de tráfico 50/50. Su objetivo suele ser determinar que no hay *ninguna* diferencia en el alza entre las experiencias idénticas.

## ¿Por qué ejecutar una prueba A/A? {#why-aa}

Algunas organizaciones realizan pruebas A/A al implementar una nueva herramienta de pruebas, como [!DNL Target], para determinar si:

* La actividad se ha configurado correctamente
* El código se implementó correctamente
* La información es precisa

Aunque pocas organizaciones ejecutan pruebas A/A, es recomendable ejecutarlas como experimentos de &quot;cordura&quot; para generar confianza después de implementar la herramienta o antes de realizar pruebas A/B que puedan afectar a la conversión y a los ingresos.

## Por qué experiencias idénticas pueden mostrar un alza {#why-lift}

Existen numerosas razones por las que podría ver el alza de una experiencia sobre otra experiencia (idéntica):

### La prueba A/A se monitorizó continuamente

Un problema común al ejecutar cualquier tipo de prueba, incluida una prueba A/A, es observar los resultados continuamente y detener prematuramente una prueba cuando vea significación estadística y declarar una experiencia ganadora. Los analistas suelen hacer lo que se denomina &quot;búsqueda de datos&quot;. La observación de datos implica ver los datos de prueba de forma temprana y frecuente, a la vez que se intenta determinar qué experiencia está teniendo un mejor rendimiento. El riesgo es detener la prueba prematuramente, lo que podría invalidar los resultados.

En una prueba A/A, la observación de datos a menudo puede hacer que los analistas vean el alza en una experiencia, cuando en realidad no debería haber ninguna diferencia, ya que las dos experiencias son idénticas. De hecho, con el peeking continuo, las pruebas A/A están *garantizadas* para mostrar &quot;relevancia estadística&quot; (es decir, una confianza por encima de un determinado umbral, como el 95 %) en algún momento durante la prueba.

### La relevancia estadística afecta a los resultados de las pruebas

El nivel de relevancia de una prueba determina la probabilidad de que la prueba notifique una diferencia significativa en las tasas de conversión entre dos ofertas diferentes cuando, de hecho, no hay ninguna diferencia real. Esto se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y existe un equilibrio entre la tolerancia de los falsos positivos y el número de visitantes que deben incluirse en la prueba a la hora de elegir el nivel de relevancia adecuado.

Un nivel de relevancia comúnmente utilizado en las pruebas A/A y A/B es del 5 %, que corresponde a un nivel de confianza del 95 % (nivel de confianza = 100 % - nivel de relevancia). Un nivel de confianza del 95 % significa que, cada vez que realice una prueba, existe una probabilidad del 5 % de detectar un alza estadísticamente significativa, aunque no haya diferencia entre las experiencias.

Supongamos que desea alcanzar un nivel de confianza del 95 % con la prueba A/A. Con un nivel de confianza del 95 %, 1 de cada 20 pruebas A/A podría mostrar un alza estadísticamente significativa en las conversiones. Con un nivel de confianza del 90 %, 1 de cada 10 pruebas podría mostrar un aumento en las conversiones al probar experiencias idénticas.

## Práctica recomendada {#best-practice}

Si decide que es necesaria una prueba A/A en su organización, tenga en cuenta que las experiencias idénticas podrían mostrar temporalmente una diferencia con respecto al control. Esto puede ser normal, dependiendo del tiempo que la prueba pueda ejecutarse. La diferencia debería reducirse con más tiempo y visitantes.

Utilice una metodología de prueba A/B normal:

1. Decida con antelación qué tamaño de muestra utilizar, en función del tamaño mínimo del efecto (el alza mínima por debajo de la cual un efecto no es importante para su negocio), la potencia y los niveles de relevancia que considere aceptables. La calculadora de tamaño de muestra **[!UICONTROL Adobe Target]** es una herramienta importante que le ayudará a determinar el tamaño de muestra que debe obtener y el tiempo que debe durar la ejecución de la prueba. Consulte la [Calculadora de tamaño de muestra de Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

1. Deje que transcurra el tiempo y los visitantes adecuados antes de sacar conclusiones. En una prueba A/A, el objetivo es *no* ver un resultado estadísticamente significativo después de que la prueba haya alcanzado el tamaño de muestra deseado.

1. Recuerde que, según el nivel de relevancia de la prueba, existe la posibilidad de que una experiencia muestre una diferencia en el alza e incluso se declare ganadora.

Para obtener información sobre cuánto tiempo debe durar una actividad y otros consejos y trucos útiles, consulte los siguientes artículos:

* [¿Durante cuánto tiempo se debe ejecutar una prueba A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Diez dificultades A/B comunes y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)
