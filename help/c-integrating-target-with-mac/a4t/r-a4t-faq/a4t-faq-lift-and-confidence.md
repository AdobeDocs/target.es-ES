---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al usar Analytics como fuente de informes para Target (A4T).
title: 'Alza y confianza: preguntas más frecuentes sobre A4T'
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: a06747412ba93cacb012e0d68334590fc3d52ab7

---


# Alza y confianza: preguntas más frecuentes sobre A4T{#lift-and-confidence-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el alza y la confianza al usar Analytics como fuente de informes para Target (A4T).

## ¿Puedo realizar cálculos sin conexión para A4T?{#section_55B5B750E17D414CAECBEECE27B15D81}

Puede realizar cálculos sin conexión para A4T, pero es necesario realizar un paso de exportaciones de datos en [!DNL Analytics]. Para obtener más información, consulte “Realización de cálculos sin conexión para Analytics para Target (A4T)” en [Nivel de confianza e Intervalo de confianza](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## ¿Cómo se calcula el alza?{#section_8CAE788EED5646C4B1D64A0D22070734}

El alza es la diferencia porcentual entre los resultados de la página de control y la variante de una prueba con éxito.

## ¿Cómo se calcula la confianza?   {#section_97DB24D833E742988318CA65DA65DAD9}

El nivel de confianza es la probabilidad de que la tasa de conversión medida sea diferente a la tasa de conversión de la página ganadora por motivos que no sean simple casualidad.

## ¿Por qué no veo el alza y la confianza en las métricas calculadas?   {#lift-confidence}

El alza y la confianza no son compatibles actualmente con las métricas calculadas. Sin embargo, en la mayoría de los casos esto no debería ser un problema porque la tasa de conversión calculada en el informe de A4T ya es una métrica calculada en la que el denominador es la métrica de normalización (instancias, visitas o visitantes). Por ejemplo, si selecciona la métrica de pedidos y la métrica de normalización es visitantes, la tasa de conversión (pedidos/visitantes) se calcula automáticamente a través del sistema de informes de A4T. La métrica de alza resultante refleja la diferencia en esa tasa de conversión entre las experiencias de texto cuando se compara con la predeterminada.

La mayoría de las métricas calculadas para la optimización se dividen en una de las dos categorías: Métricas acumuladas u otros cálculos de conversión, como Valor de pedido promedio (AOV).

Las métricas Acumuladas se utilizan cuando una organización emplea eventos únicos para capturar diferentes &quot;sabores&quot; de la conversión de almacenamiento. Por ejemplo: si su objetivo es promocionar los envíos de formularios de posibles clientes y tiene diez formularios de posibles clientes diferentes, puede crear eventos únicos para contar cada tipo de conversión de formularios. Para ver la cantidad total de todos los formularios de posibles clientes enviados, debe crear una métrica calculada simple para agregarlos juntos. Una forma mejor y más moderna de rastrear esto es implementar un solo evento de envío de posibles clientes en Analytics y, a continuación, usar una eVar para recopilar el tipo de formulario de posibles clientes. El uso de este método requiere menos variables y elimina la necesidad de acumuladas métricas individuales, y aún así puede ver la conversión holística del formulario de posibles clientes y desglosarla por tipo de formulario de posibles clientes mediante la eVar. Esto también elimina la necesidad de métricas acumuladas al evaluar el rendimiento de una actividad de Destinatario.

Otra métrica calculada común, Valor de pedido promedio, no se admite actualmente con alza y confianza porque la métrica de normalización no es una métrica estándar (instancias, visitas o visitantes). En su lugar, se recomienda vigilar las dos métricas que influyen en AOV, Ingresos por Visitantes y Tasa de conversión.

## ¿Cómo gestiona A4T los cálculos de confianza?   {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T usa los cálculos de métricas no binarios con la suma de los datos al cuadrado. La varianza se calcula con la suma de los datos al cuadrado. Los pedidos extremos no se tienen en cuenta.

Se puede aplicar cualquier segmento de Analytics al informe. Así puede obtener la cantidad de “pedidos extremos”, entre otras opciones de segmentación. También se podría crear una métrica para limitar aspectos como el número de conversiones que puede generar un visitante.

## ¿El alza y la confianza funcionan en las soluciones Ad Hoc y Report Builder? Si no es una opción ya integrada, ¿puedo usar esas soluciones para hacerlo yo? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

El alza y la confianza no funcionan en Ad Hoc ni en Report Builder, y no las puedes calcular para las variables continuas. Es posible calcularlas manualmente en el caso de las métricas binarias.
