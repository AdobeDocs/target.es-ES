---
keywords: AB;A/B;AB...n;sample size;sample size calculator;auto-allocate;auto allocate
description: Una prueba A/B exitosa requiere un número adecuado de visitantes (tamaño de muestra) para mejorar su tasa de conversión, pero ¿cómo sabe durante cuánto tiempo se debe ejecutar una prueba A/B? Este artículo contiene información sobre las actividades de Asignación automática y la Calculadora de tamaño de muestra de Target para ayudarle a asegurarse de que su actividad tenga una cantidad suficiente de visitantes para lograr sus objetivos.
title: ¿Durante cuánto tiempo se debe ejecutar una prueba A/B?
feature: ab
uuid: 4f5693c8-5372-425b-8e61-efb595b144cc
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '3108'
ht-degree: 98%

---


# ¿Durante cuánto tiempo se debe ejecutar una prueba A/B?{#how-long-should-you-run-an-a-b-test}

Una prueba A/B exitosa requiere un número adecuado de visitantes (tamaño de muestra) para mejorar su tasa de conversión, pero ¿cómo sabe durante cuánto tiempo se debe ejecutar una prueba A/B? Este artículo contiene información sobre las actividades de Asignación automática y la Calculadora de tamaño de muestra de Target para ayudarle a asegurarse de que su actividad tenga una cantidad suficiente de visitantes para lograr sus objetivos.

Es tentador detener una actividad si una de las ofertas muestra un rendimiento mucho mejor o peor que las otras en los primeros días de la actividad. Sin embargo, cuando el número de observaciones es reducido, existe una alta probabilidad de observar un alza positiva o negativa solo por casualidad, puesto que la tasa de conversión se promedia a partir de un número bajo de visitantes. A medida que la actividad recopila más puntos de datos, las tasas de conversión convergen hacia sus verdaderos valores a largo plazo.

Detener una actividad de forma prematura es uno de los nueve escollos importantes con los que se puede encontrar al realizar una prueba A/B. Para obtener más información, consulte  [Nueve escollos comunes de las pruebas A/B y cómo evitarlos](../../c-activities/t-test-ab/common-ab-testing-pitfalls.md#concept_578A7947C9554868B30F12DFF9E3F8E3).

Target proporciona herramientas para ayudar a garantizar que su actividad tenga un tamaño de muestra lo suficientemente grande como para lograr sus objetivos de conversión:

* **Asignación automática:** una actividad de asignación automática es un tipo de prueba A/B que identifica a un ganador entre dos o más experiencias y reasigna automáticamente más tráfico al ganador para aumentar las conversiones mientras la prueba continúa ejecutándose y aprendiendo.

   Las pruebas A/B estándar tienen un coste inherente. Debe invertir tráfico para medir el rendimiento de cada experiencia y utilizar el análisis para determinar la experiencia ganadora. La distribución del tráfico sigue siendo fija incluso después de reconocer que el rendimiento de algunas experiencias supera al de otras. Además, es complicado determinar el tamaño de la muestra, y la actividad debe haber finalizado para poder tomar medidas con la mejor experiencia. Después de todo esto, existe la posibilidad de que la mejor experiencia identificada en realidad no sea la mejor.

   La solución es la asignación automática. La asignación automática reduce este coste y gastos derivados de determinar una experiencia ganadora. La asignación automática supervisa el rendimiento de la métrica de objetivos de todas las experiencias y envía a más participantes de manera proporcional a las experiencias de mayor rendimiento. Se reserva bastante tráfico para explorar el resto de las experiencias. Las ventajas de la prueba se pueden observar en los resultados, incluso con la actividad aún en curso: la optimización se produce en paralelo al aprendizaje.

   La asignación automática envía a los visitantes de forma gradual hacia las experiencias ganadoras, en vez de hacerles esperar hasta que la actividad acabe para determinar un ganador. Saca provecho del alza más rápidamente porque a los visitantes de la actividad a los que se ha enviado a experiencias con peor rendimiento se les muestran experiencias que potencialmente son las ganadoras.

   Al utilizar la función de asignación automática, Target muestra un distintivo en la parte superior de la página de la actividad indicando “Ningún ganador aún” hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza. Target luego declara la experiencia ganadora al mostrar un distintivo en la parte superior de la página de la actividad.

   Para obtener más información, consulte [Asignación automática](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

* **Calculadora de tamaño de muestra:** si elige usar una prueba A/B manual en lugar de Asignación automática, la Calculadora de tamaño de muestra de Target le ayuda a determinar el tamaño de muestra necesario para una prueba exitosa. Una prueba A/B manual es una prueba de horizonte fijo, por lo que la calculadora resulta extremadamente útil. El uso de la calculadora para una actividad de asignación automática es opcional porque la asignación automática le declarará ganador. La calculadora proporciona una estimación aproximada del tamaño de la muestra necesario. Siga leyendo para obtener más información sobre cómo usar la calculadora.

## Calculadora de tamaño de muestra de Adobe Target.  {#section_6B8725BD704C4AFE939EF2A6B6E834E6}

Before setting up your A/B test, access the Adobe Target [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html).

![Calculadora de tamaño de muestra de Adobe Target.](/help/c-activities/t-test-ab/assets/sample_size_calculator-new.png)

Es importante determinar un tamaño de la muestra (número de visitantes) que sea adecuado antes de realizar una prueba A/B, a fin de establecer el tiempo con el que deberá contar para realizar la prueba antes de evaluar los resultados. Si solo se supervisa la prueba hasta que se consigue una relevancia estadística, el intervalo de confianza quedará ampliamente subestimado y la prueba no será fiable. La intuición que hay tras el resultado es que, en el caso de que se detecte un resultado estadísticamente relevante, se detendrá la prueba y se declarará un ganador. Sin embargo, si el resultado no es estadísticamente relevante, se permite que la prueba siga realizándose. Este procedimiento favorece enormemente un resultado positivo, que aumenta la tasa de falsos positivos y, por tanto, distorsiona el nivel de relevancia estadística de la prueba.

Esto puede generar un gran número de falsos positivos, que puede ocasionar que se implementen ofertas que no ofrecen el alza predicha a largo plazo. Un alza pobre se considera un resultado no satisfactorio, pero una consecuencia aún más grave es que con el paso del tiempo, el hecho de no poder predecir el alza con exactitud puede mermar la confianza que la organización tenga la práctica de pruebas.

En este artículo se comentan los factores que deben equilibrarse cuando se determina un tamaño de muestra y se presenta una herramienta en hoja de cálculo que permite calcular un tamaño adecuado de la muestra. Si calcula el tamaño de la muestra con la calculadora de tamaño de la muestra (encontrará el vínculo más arriba) antes de iniciar cualquier prueba A/B, tendrá la garantía de que siempre se ejecuten pruebas A/B de nivel superior que cumplan los estándares estadísticos.

Hay cinco parámetros definidos por el usuario que definen una prueba A/B. Estos parámetros están interconectados, así que cuatro de ellos están establecidos y el quinto se puede calcular:

* Relevancia estadística
* Potencia estadística
* Alza mínima fiable detectable
* Tasa de conversión de línea de base
* Número de visitantes

Para una prueba A/B, el analista fija la relevancia estadística, la eficacia estadística, el alza mínima fiable detectable y la tasa de conversión de línea de base, y el número de visitantes se calcula a partir de estos valores. En este artículo se comentan estos elementos y se ofrecen directrices para ajustarlos para una determinada prueba.

![](assets/samplesize.png)

En la siguiente imagen se muestran los cuatro resultados posibles de una prueba A/B:

![](assets/outcomes.png)

Es deseable no obtener falsos positivos ni falsos negativos. Sin embargo, esto nunca se puede garantizar mediante una prueba estadística. Siempre es posible que las tendencias observadas no sean representativas de las tasas de conversión subyacentes. Por ejemplo, en una prueba para ver si era más probable obtener la cara o la cruz de una moneda al lanzarla, incluso con una moneda equilibrada, se obtendrían 10 caras en los 10 lanzamientos solo por casualidad. La relevancia y la potencia estadísticas nos permiten cuantificar las tasas de falsos positivos y falsos negativos, y mantenerlos en niveles razonables para una determinada prueba.

## Relevancia estadística {#section_8230FB9C6D1241D8B1786B72B379C3CD}

El nivel de relevancia de una prueba determina con qué probabilidad la prueba notificará una diferencia relevante en las tasas de conversión de dos ofertas distintas, cuando en realidad no hay ninguna diferencia. Esto se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y es un equilibrio entre la tolerancia para falsos positivos y el número de visitantes que se tienen que incluir en la prueba.

En una prueba A/B, inicialmente se presupone que las dos ofertas tienen la misma tasa de conversión. Después, la probabilidad del resultado observado se calcula en función de esta presuposición. Si esta probabilidad (el valor p) es menor que algunos de los umbrales predefinidos (nivel de relevancia), Target concluye que la presuposición inicial (que ambas ofertas tienen la misma tasa de conversión) es incorrecta y, por tanto, las tasas de conversión de A y B son estadísticamente diferentes en el nivel de relevancia dado.

Un nivel de relevancia usado comúnmente en las pruebas A/B es el 5 %, que corresponde a un nivel de confianza del 95 % (nivel de confianza = 100 % - nivel de relevancia). Un nivel de confianza del 95 % significa que cada vez que realice una prueba, hay un 5 % de probabilidades de detectar un alza estadísticamente relevante, aunque no haya ninguna diferencia entre las ofertas.

Las interpretaciones típicas del nivel de confianza se resumen en la siguiente tabla:

| Nivel de confianza | Interpretación |
|--- |--- |
| &lt; 90 % | No hay ninguna evidencia de que haya diferencia entre las tasas de conversión. |
| 90-95 % | Hay una evidencia débil de que haya diferencia entre las tasas de conversión. |
| 95-99 % | Hay una evidencia moderada de que haya diferencia entre las tasas de conversión. |
| 99-99,9 % | Hay una fuerte evidencia de que haya diferencia entre las tasas de conversión. |
| +99,9 % | Hay una evidencia muy fuerte de que haya una diferencia entre las tasas de conversión. |

Se recomienda usar siempre un nivel de confianza del 95 % o superior.

Es preferible usar el mayor nivel de confianza posible, para que la prueba arroje pocos falsos positivos. Sin embargo, un nivel de confianza mayor requiere un gran número de visitantes, lo que aumenta el tiempo necesario para realizar la prueba. Además, un aumento en el nivel de confianza ocasiona una reducción en la potencia estadística.

## Potencia estadística {#section_1169C27F8E4643719D38FB9D6EBEB535}

La potencia estadística de una prueba A/B es la probabilidad de detectar una diferencia real en la tasa de conversión de una determinada magnitud. Debido a la naturaleza aleatoria (estocástica) de los eventos de conversión, es posible que no se observe una diferencia con relevancia estadística (solo por casualidad) aunque haya una diferencia real en la tasa de conversión entre las dos ofertas. Esto se conoce como falso negativo o error de tipo II.

La potencia estadística a menudo se ignora porque en una prueba A/B no es necesario determinarla, al contrario de lo que ocurre con la relevancia estadística. Sin embargo, si se ignora la potencia estadística, hay una posibilidad considerable de que las diferencias reales entre las tasas de conversión de diferentes ofertas no se detecten en la prueba porque el tamaño de la prueba es demasiado pequeño. La consecuencia es que las pruebas estarán repletas de falsos positivos.

Es preferible tener una potencia estadística elevada para que la prueba tenga muchas probabilidades de identificar una diferencia real en las tasas de conversión y genere menos falsos positivos. Sin embargo, se necesita un elevado número de visitantes para aumentar la potencia estadística de detectar cualquier alza dada, lo que aumenta el tiempo necesario para realizar la prueba.

Un valor usado comúnmente para la potencia estadística es el 80 %, lo que supone que la prueba tiene una probabilidad del 80 % de detectar una diferencia igual al alza mínima fiable detectable. La prueba tiene una probabilidad menor de detectar altas menores y una probabilidad mayor de detectar alzas mayores.

## Alza mínima fiable detectable {#section_6101367EE9634C298410BBC2148E33A9}

La mayoría de las organizaciones desean medir la menor diferencia posible en la tasa de conversión, porque merece la pena implementar incluso un alza pequeña. Sin embargo, si quiere que la prueba A/B tenga una alta probabilidad de detectar un alza muy pequeña, el número de visitantes que debe incluirse en la prueba sería altísimo. El motivo de esto es que, si la diferencia en la tasa de conversión es pequeña, las dos tasas de conversión deberán calcularse con alta precisión para identificar la diferencia, lo que requiere un gran número de visitantes. Por tanto, el alza mínima fiable detectable deberá determinarse según los requisitos de la empresa, teniendo en cuenta el equilibrio que hay que mantener entre detectar las alzas pequeñas y ejecutar la prueba durante largos períodos de tiempo.

Por ejemplo, supongamos que dos ofertas (A y B) tienen tasas de conversión verdaderas del 10 y el 15 % respectivamente. Si estas ofertas se muestran a 100 visitantes cada una, hay un 95 % de probabilidades de observar tasas de conversión de entre 4 y 16 % para la oferta A, y de entre 8 y 22 % para la oferta B, debido a la naturaleza estocástica de las conversiones. En estadística, estos rangos se conocen como intervalos de confianza. Representan la confianza en la precisión de las tasas de conversión estimadas. Cuando mayor sea el tamaño de la muestra (más visitantes), tendrá mayor certeza de que las estimaciones de las tasas de conversión serán precisas.

En la siguiente imagen se muestran estas distribuciones de probabilidad.

![](assets/probability_distributions.png)

Debido al gran solapamiento entre los dos rangos, la prueba no puede determinar si las tasas de conversión son diferentes. Por tanto, esta prueba con 100 visitantes no puede distinguir entre las dos ofertas. Sin embargo, si exponemos las ofertas a 5000 visitantes cada una, hay un 95 % de posibilidades de que las tasas de conversión observadas entren dentro de los rangos de 9-11 % y 14-16 % respectivamente.

![](assets/probability_distributions2.png)

En este caso, es muy poco probable que la prueba llegue a una conclusión equivocada, por lo que la prueba con 5000 visitantes puede distinguir entre las dos ofertas. La prueba con 5000 visitantes tiene un intervalo de confianza de +/-1 % aproximadamente. Esto significa que la prueba puede detectar diferencias de alrededor del 1 %. Por tanto, se necesitarían incluso más visitantes si las tasas de conversión reales de las ofertas fueran, por ejemplo, del 10 % y el 10,5 %, en lugar del 10 % y el 15 %.

## Tasa de conversión de línea de base {#section_39380C9CA3C649B6BE6E1F8A06178B05}

La tasa de conversión de línea de base es la tasa de conversión de la oferta de control (oferta A). A menudo, puede disponer de un buen sentido del nivel de conversión para la oferta, basado en su experiencia anterior. Si este no es el caso, por ejemplo porque es un nuevo tipo de oferta o es creativa, se puede realizar la prueba durante un día aproximadamente, para obtener una estimación aproximada de la tasa de conversión de línea de base que se puede usar en el cálculo del tamaño de la muestra.

## Calcular el tamaño de la muestra {#section_19009F165505429E95291E6976E498DD}

Puede resultar difícil equilibrar los costes de oportunidad que conlleva ejecutar una prueba durante mucho tiempo, con el riesgo de falsos positivos y falsos negativos. Obviamente, no deseará tomar decisiones equivocadas, pero tampoco resulta deseable quedar paralizado por estándares de pruebas demasiado estrictos o demasiado rígidos. Como guía general, se recomienda un nivel de confianza del 95 % y una potencia estadística del 80 %.

En la calculadora de tamaño de la muestra (encontrará el vínculo más arriba), se le pedirá que tome una decisión sobre la relevancia estadística (se recomienda el 95 %) y la potencia estadística (se recomienda el 80 %). Tras indicar la tasa de conversión de línea de base y el tráfico diario en todas las ofertas, la hoja de cálculo muestra el número de visitantes necesarios para detectar un alza de 1 %, 2 %, 5 %, 10 %, 15 % y 20 % con una probabilidad igual a la potencia especificada en la prueba. La hoja de cálculo también permite al usuario indicar un valor personalizado para el alza mínima fiable detectable. Además, la hoja de cálculo muestra el número de semanas necesarias para realizar la prueba, en función del nivel de tráfico indicado por el usuario. Este número de semanas se redondea hasta la semana completa más próxima, para evitar cualquier efecto de día de la semana que pueda influir en los resultados.

Existe un equilibrio entre el alza mínima que la prueba puede detectar de manera fiable y el número de visitantes necesario. En la imagen de abajo, que es válida para una tasa de conversión de línea de base (control) del 5 %, se muestra una fuerte reducción de los valores devueltos conforme aumenta el número de visitantes. El alza mínima que se puede detectar de manera fiable mejora considerablemente cuando se agregan algunos de los primeros visitantes a la prueba, pero toma un número de visitantes cada vez mayor para mejorar la prueba. La imagen ayuda a encontrar un equilibrio adecuado entre el tiempo necesario para realizar la prueba (según viene determinado por el número de visitantes necesario y el tráfico del sitio) y el alza mínima que la prueba puede detectar de manera fiable.

![](assets/samplesizecontrol.png)

En este ejemplo, es posible que considere adecuado poder detectar un alza del 5 % (correspondiente a una tasa de conversión de la oferta alternativa (100 % + 5 %)*5 % = 5,25 %) en 80 de 100 pruebas, por lo que necesitará un tamaño de muestra de 100 000 visitantes para cada oferta. Si el sitio tiene 20 000 visitantes al día y realiza la prueba de dos ofertas, la prueba debería permitir ejecutar 2*100 000/20 000 = 10 días, antes de poder determinar si la oferta alternativa tiene una relevancia estadística superior a la de la oferta de control. Una vez más, se recomienda que el tiempo necesario se redondee siempre a la semana completa más próxima, para evitar cualquier efecto de día de la semana. Por tanto, en este ejemplo, la prueba se realizaría durante dos semanas antes de evaluar los resultados.

## Métrica de ingresos por visita.  {#section_C704C0861C9B4641AB02E911648D2DC2}

Cuando se usan los ingresos por visita (RPV) como métrica, se añade una fuente de varianza adicional, ya que RPV es el producto de los ingresos por pedido y la tasa de conversión (RPV = ingresos/nº visitantes = (ingresos por pedido * nº de pedidos)/nº de visitantes = ingresos por pedido * (nº de visitantes * CTR)/nº de visitantes = ingresos por pedido * CTR), cada uno con su propia varianza. La varianza de la tasa de conversión se puede calcular directamente mediante un modelo matemático pero la varianza de los ingresos por pedido es específica de la campaña. Por tanto, aproveche los datos de esta varianza que tenga de campañas anteriores o realice la prueba A/B durante unos pocos días para calcular la varianza en los ingresos. La varianza se calcula a partir de los valores de Suma de ventas, Suma de ventas al cuadrado y Número de visitantes que se encuentran en el archivo CSV descargable. Después de establecerla, utilice la hoja de cálculo para calcular el tiempo necesario para completar la prueba.

La calculadora de tamaño de la muestra (vínculo proporcionado arriba) puede ayudarle a configurar la métrica de RPV. Cuando abra la calculadora, verá una pestaña con la etiqueta Métrica de RPV. Necesitará la siguiente información al usar la versión de RPV de la calculadora:

* Número de visitantes a la oferta de control
* Ingresos totales para la oferta de control

   Asegúrese de que el filtro de pedidos extremos esté seleccionado.
* La suma de ingresos al cuadrado para la oferta de control

   Asegúrese de que el filtro de pedidos extremos esté seleccionado.

En general, el uso de RPV como métrica exige entre un 20 y un 30 % más de tiempo para obtener el mismo nivel de confianza estadística para el mismo nivel de alza medida, porque RPV tiene la varianza agregada de diferentes tipos de pedidos por conversión. Eso debería ser un punto para tener en cuenta a la hora de elegir entre una tasa de conversión uniforme y RPV como métrica en la cual basar la decisión final comercial.

## Corrección para comparar varias ofertas {#section_1474113764224D0B85472D8B023CCA15}

Cada vez que compara dos ofertas, las posibilidades de obtener un falso positivo (es decir, observar una diferencia con relevancia estadística aunque no haya diferencia en la tasa de conversión) son iguales al nivel de relevancia. Por ejemplo, si hay cinco ofertas, A/B/C/D/E, y A es la oferta control, se realizan las cuatro comparaciones (control frente a B, control frente a C, control frente a D y control frente a E), y la probabilidad de obtener un falso positivo es del 18,5 % aunque el nivel de confianza sea del 95 % porque Pr (al menos un falso positivo) = 1 - Pr (sin falsos positivos) = 1 - 0,95 = 18,5 %. En este contexto, un falso positivo se define como la notificación de que el control es mejor que la alternativa, o que la alternativa es mejor que el control cuando, de hecho, no hay ninguna diferencia entre ellos.

## Conclusión.  {#section_AEA2427B90AE4E9395C7FF4F9C5CA066}

Al utilizar una actividad de Asignación automática, Target identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. La asignación automática facilita el logro de sus objetivos de conversión y elimina las suposiciones.

Al usar la calculadora de tamaño de la muestra (encontrará el vínculo más arriba) que se detalla en este artículo y permitir que la prueba se realice durante la cantidad de tiempo sugerida por esta herramienta, tendrá la seguridad de que siempre realizará pruebas A/B de calidad que se ajusten a las tasas de falsos positivos y falsos negativos que considera que son adecuadas para la prueba específica. Esto garantiza que sus pruebas sean coherentes y capaces de detectar el alza que está buscando.
