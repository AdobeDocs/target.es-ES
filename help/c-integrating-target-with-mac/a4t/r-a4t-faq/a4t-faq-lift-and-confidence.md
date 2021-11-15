---
keywords: faq;preguntas frecuentes;analytics para target;a4T;alza;específicos;creador de informes;confianza
description: Encuentre respuestas a preguntas sobre el alza y la confianza al usar Analytics para [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] actividades.
title: ¿Dónde puedo encontrar información sobre el alza y la confianza con A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: 36c1a897c159b5662a4a2a6127f8bcabbd7101b8
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 29%

---

# Alza y confianza: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Puedo realizar cálculos sin conexión para A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics]. Para obtener más información, consulte “Realización de cálculos sin conexión para Analytics para Target (A4T)” en [Nivel de confianza e Intervalo de confianza](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## ¿Cómo se calcula el alza? {#section_8CAE788EED5646C4B1D64A0D22070734}

El alza es la diferencia porcentual entre los resultados de la página de control y la variante de una prueba con éxito.

## ¿Cómo se calcula la confianza?   {#section_97DB24D833E742988318CA65DA65DAD9}

El nivel de confianza es una probabilidad, expresada como porcentaje, igual a `1 - p-value`, donde la variable `p-value` se calcula a partir de una prueba t. Consulte [Tasa de conversión](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## ¿Por qué no veo el alza y la confianza en las métricas calculadas?   {#lift-confidence}

Actualmente, las métricas calculadas no son compatibles con las funciones de alza y confianza. Analytics calcula las métricas en un nivel agregado, no en un nivel de visitante. La confianza, en particular, es un cálculo a nivel de visitante.

Los eventos no calculados (estándar) se admiten en alza y confianza. Se convierten en el numerador de la función de alza; el numerador no puede ser un cálculo en sí. El denominador son las métricas de normalización (impresiones, visitas o visitantes). Algunos ejemplos de eventos estándar incluyen pedidos, ingresos, conversiones de actividad, eventos personalizados 1-1000, etc. Las métricas de optimización comunes, como la tasa de conversión (Pedidos/Visitante) y RPV (Ingresos/Visitante) son compatibles con el alza y la confianza.

Algunos ejemplos de métricas o casos de uso no compatibles son:

* Valor de pedido promedio (ingresos/pedido, por visitante). No se admite AOV porque el numerador es una métrica calculada. En su lugar, la recomendación es considerar las dos métricas influyentes de AOV - Ingresos por visitantes y Tasa de conversión.
* Métricas calculadas que son la suma de eventos estándar. Por ejemplo, puede rastrear diez formularios de posibles clientes diferentes en diez eventos independientes y luego agregarlos para obtener el total de envíos de posibles clientes. Un método recomendado para rastrear estos eventos es implementar un solo evento de envío de posibles clientes en Analytics y, a continuación, utilizar un eVar para recopilar el tipo de formulario de posibles clientes. El uso de este método requiere menos variables y garantiza que puede utilizar la métrica de envío de posible cliente único en las funciones de alza y confianza.

## ¿Cómo gestiona A4T los cálculos de confianza?   {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

[!DNL Adobe Analytics] trata todas las métricas como no binarias y, por lo tanto, calcula los valores de confianza/p de una manera diferente al uso de métricas binarias en una prueba t normal. En concreto, los cálculos utilizados por A4T permiten que cada usuario tenga un resultado de métrica continuo (no solo 1 o 0 por cada usuario), de modo que la varianza (o, en relación, la desviación estándar) de cada experiencia se debe calcular adecuadamente. No se tienen en cuenta los pedidos extremos. Además, el cálculo de confianza no aplica una corrección de Bonferroni para varias ofertas.

## ¿El alza y la confianza funcionan en las soluciones Ad Hoc y Report Builder? Si no es una opción ya integrada, ¿puedo usar esas soluciones para hacerlo yo? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

El alza y la confianza no funcionan en Ad Hoc ni en Report Builder, y no las puedes calcular para las variables continuas. Es posible calcularlas manualmente en el caso de las métricas binarias.
