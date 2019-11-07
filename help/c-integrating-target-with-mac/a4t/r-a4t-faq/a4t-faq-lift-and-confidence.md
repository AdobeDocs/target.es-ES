---
keywords: faq;preguntas frecuentes;analytics para target;a4T;alza;específicos;creador de informes;confianza
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al usar Analytics como fuente de informes para Target (A4T).
title: 'Alza y confianza: preguntas más frecuentes sobre A4T'
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Alza y confianza: preguntas más frecuentes sobre A4T{#lift-and-confidence-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al usar Analytics como fuente de informes para Target (A4T).

## ¿Puedo realizar cálculos sin conexión para A4T?{#section_55B5B750E17D414CAECBEECE27B15D81}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics]. Para obtener más información, consulte “Realización de cálculos sin conexión para Analytics para Target (A4T)” en [Nivel de confianza e Intervalo de confianza](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## ¿Cómo se calcula el alza?{#section_8CAE788EED5646C4B1D64A0D22070734}

El alza es la diferencia porcentual entre los resultados de la página de control y la variante de una prueba con éxito.

## ¿Cómo se calcula la confianza?   {#section_97DB24D833E742988318CA65DA65DAD9}

El nivel de confianza es la probabilidad de que la tasa de conversión medida sea diferente a la tasa de conversión de la página ganadora por motivos que no sean simple casualidad.

## ¿Por qué no veo el alza y la confianza en las métricas calculadas?   {#section_D3E44E24782A409DBD88AE4D1595CB58}

Actualmente, el alza y la confianza no se pueden generar en las métricas calculadas. Sin embargo, en la mayoría de los casos, no debería ser un problema porque la métrica de normalización se encarga de normalizar el alza. Por ejemplo, si selecciona el alza para los pedidos y la métrica de normalización es las visitas, el alza se calcula según la relación entre estos dos, que es la tasa de conversión.

## ¿Cómo gestiona A4T los cálculos de confianza?   {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T usa los cálculos de métricas no binarios con la suma de los datos al cuadrado. La varianza se calcula con la suma de los datos al cuadrado. Los pedidos extremos no se tienen en cuenta.

Se puede aplicar cualquier segmento de Analytics al informe. Así puede obtener la cantidad de “pedidos extremos”, entre otras opciones de segmentación. También se podría crear una métrica para limitar aspectos como el número de conversiones que puede generar un visitante.

## ¿El alza y la confianza funcionan en las soluciones Ad Hoc y Report Builder? Si no es una opción ya integrada, ¿puedo usar esas soluciones para hacerlo yo? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

El alza y la confianza no funcionan en Ad Hoc ni en Report Builder, y no las puedes calcular para las variables continuas. Es posible calcularlas manualmente en el caso de las métricas binarias.
