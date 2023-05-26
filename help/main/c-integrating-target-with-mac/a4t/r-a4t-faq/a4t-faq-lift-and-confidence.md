---
keywords: faq;preguntas frecuentes;analytics para target;a4T;alza;específicos;creador de informes;confianza
description: Encuentre respuestas a preguntas acerca del alza y la confianza al usar Analytics para [!DNL Target] (A4T). A4T le permite utilizar los informes de Analytics para [!DNL Target] actividades.
title: ¿Dónde puedo encontrar información sobre el alza y la confianza con A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 15%

---

# Alza y confianza: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al utilizar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Puedo realizar cálculos sin conexión para A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++Respuesta Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics]. Para obtener más información, consulte [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## ¿Cómo se calcula el alza? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++El alza de respuestas es la diferencia porcentual entre los resultados de la página de control y una variante de prueba con éxito.

+++

## ¿Cómo se calcula la confianza?   {#section_97DB24D833E742988318CA65DA65DAD9}

+++Respuesta El nivel de confianza es una probabilidad, expresada como porcentaje, igual a `1 - p-value`, donde la variable `p-value` se calcula a partir de una prueba t. Consulte [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## ¿Por qué no veo el alza y la confianza en las métricas calculadas?   {#lift-confidence}

+++Respuesta Actualmente, las métricas calculadas no son compatibles con las funciones de alza y confianza. Analytics calcula las métricas a nivel agregado, en lugar de a nivel de visitante. La confianza, en particular, es un cálculo a nivel de visitante.

Los eventos no calculados (estándar) son compatibles con el alza y la confianza. Se convierten en el numerador en la función de elevación; el numerador no puede ser un cálculo en sí mismo. El denominador son las métricas de normalización (impresiones, visitas o visitantes). Algunos ejemplos de eventos estándar son pedidos, ingresos, conversiones de actividad, eventos personalizados 1-1000, etc. Las métricas de optimización comunes, como tasa de conversación (pedidos/visitante) y RPV (ingresos/visitante), son compatibles con el alza y la confianza.

Algunos ejemplos de métricas o casos de uso no admitidos son:

* Valor de pedido promedio (ingresos/pedido, por visitante). AOV no es compatible porque el numerador es una métrica calculada. En su lugar, la recomendación es tener en cuenta las dos métricas que influyen en AOV: los ingresos por visitante y la tasa de conversión.
* Métricas calculadas que son la suma de eventos estándar. Por ejemplo, puede rastrear diez formularios de posibles clientes diferentes en diez eventos independientes y luego agregarlos para obtener envíos totales de posibles clientes. Un método recomendado para rastrear estos eventos es implementar un solo evento de envío de posibles clientes en Analytics y, a continuación, utilizar un eVar para recopilar el tipo de formulario de posibles clientes. El uso de este método requiere menos variables y garantiza que pueda utilizar la métrica de envío de un solo posible cliente en las funciones de alza y confianza.

+++

## ¿Cómo gestiona A4T los cálculos de confianza?   {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++Respuesta
[!DNL Adobe Analytics] trata todas las métricas como no binarias y, por lo tanto, calcula los valores de confianza/p de una manera diferente al uso de las métricas binarias en una prueba t normal. En concreto, los cálculos utilizados por A4T permiten que cada usuario tenga un resultado de métrica continuo (no solo 1 o 0 para cada usuario), de modo que la varianza (o, relacionada, la desviación estándar) para cada experiencia debe calcularse correctamente. No se tienen en cuenta los pedidos extremos. Además, el cálculo de confianza no aplica una corrección de Bonferroni para varias ofertas.

+++

## ¿El alza y la confianza funcionan en las soluciones Ad Hoc y Report Builder? Si no es una opción ya integrada, ¿puedo usar esas soluciones para hacerlo yo? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++El alza y la confianza de respuestas no funcionan en Ad Hoc ni en Report Builder, y no las puedes calcular para las variables continuas. Es posible calcularlas manualmente en el caso de las métricas binarias.
+++
