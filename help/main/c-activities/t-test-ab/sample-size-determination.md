---
keywords: AB;A/B;AB...n;tamaño de muestra;calculadora de tamaño de muestra;asignación automática;asignación automática;calculadora
description: Obtenga información sobre cuánto tiempo se debe ejecutar una prueba A/B. Una prueba A/B correcta en [!DNL Adobe Target] requiere suficientes visitantes (tamaño de muestra) para mejorar la tasa de conversión.
title: ¿Durante cuánto tiempo se debe ejecutar una prueba A/B?
feature: A/B Tests
exl-id: 4f4ce387-bbbe-44af-965b-affc3ee09d74
source-git-commit: 216134ba7d0ce7ebdad2ba477b9ad1e9fab1dff2
workflow-type: tm+mt
source-wordcount: '3092'
ht-degree: 57%

---

# ¿Durante cuánto tiempo se debe ejecutar una prueba A/B?

Un exitoso [!UICONTROL Prueba A/B] actividad en [!DNL Adobe Target] requiere suficientes visitantes (tamaño de muestra) para mejorar la tasa de conversión. ¿Cómo sabe durante cuánto tiempo se debe ejecutar una prueba A/B? Este artículo contiene información sobre [!UICONTROL Asignación automática] actividades y la [!UICONTROL Adobe Target] Calculadora de tamaño de muestra para ayudarle a asegurarse de que su actividad tenga suficientes visitantes para lograr sus objetivos.

Es tentador detener una actividad si una de las ofertas muestra un rendimiento mucho mejor o peor que las otras en los primeros días de la actividad. Sin embargo, cuando el número de observaciones es reducido, existe una alta probabilidad de observar un alza positiva o negativa solo por casualidad, puesto que la tasa de conversión se promedia a partir de un número bajo de visitantes. A medida que la actividad recopila más puntos de datos, las tasas de conversión convergen hacia sus verdaderos valores a largo plazo.

>[!IMPORTANT]
>
>Detener una actividad de forma prematura es uno de los diez escollos importantes a los que podría verse expuesto al realizar pruebas A/B. Para obtener más información, consulte [Diez dificultades comunes de las pruebas A/B y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md#concept_578A7947C9554868B30F12DFF9E3F8E3).

[!DNL Adobe Target] proporciona herramientas para garantizar que su actividad tenga un tamaño de muestra lo suficientemente grande como para lograr sus objetivos de conversión: Asignación automática.

## Asignación automática {#auto-allocate}

Un [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) actividad es un tipo de prueba A/B que identifica un ganador entre dos o más experiencias. Una prueba de asignación automática reasigna automáticamente más tráfico al ganador para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.

Las pruebas A/B estándar tienen un coste inherente. Debe invertir tráfico para medir el rendimiento de cada experiencia y utilizar el análisis para determinar la experiencia ganadora. La distribución del tráfico sigue siendo fija incluso después de reconocer que el rendimiento de algunas experiencias supera al de otras. Además, es complicado determinar el tamaño de la muestra, y la actividad debe haber finalizado para poder tomar medidas con la mejor experiencia. Y todavía hay una posibilidad de que el ganador identificado no sea un verdadero ganador.

La solución es [!UICONTROL Asignación automática]. [!UICONTROL La asignación automática reduce este coste y gastos derivados de determinar una experiencia ganadora. ] [!UICONTROL La asignación automática supervisa el rendimiento de la métrica de objetivos de todas las experiencias y envía a más participantes de manera proporcional a las experiencias de mayor rendimiento. ] Se reserva bastante tráfico para explorar el resto de las experiencias. Puede ver los beneficios de la actividad en los resultados, incluso mientras la actividad sigue ejecutándose: la optimización se produce en paralelo con el aprendizaje.

[!UICONTROL La asignación automática envía a los visitantes de forma gradual hacia las experiencias ganadoras, en vez de hacerles esperar hasta que la actividad acabe para determinar un ganador. ] Saca provecho del alza más rápidamente porque a los visitantes de la actividad a los que se ha enviado a experiencias con peor rendimiento se les muestran experiencias que potencialmente son las ganadoras.

Al utilizar la función de [!UICONTROL asignación automática], [!DNL Adobe Target] muestra un distintivo en la parte superior de la página de la actividad indicando “Ningún ganador aún” hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza. [!DNL Target] luego declara la experiencia ganadora al mostrar un distintivo en la parte superior de la página de la actividad.

Para obtener más información, consulte [Información general sobre la asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

## Adobe [!DNL Target] Calculadora de tamaño de muestra {#section_6B8725BD704C4AFE939EF2A6B6E834E6}

Si decide utilizar un manual [!UICONTROL Prueba A/B] actividad en lugar de [!UICONTROL Asignación automática], el [!DNL Target] La calculadora de tamaño de muestra le ayuda a determinar el tamaño de muestra necesario para que la prueba se realice correctamente. Una prueba A/B manual es una prueba de horizonte fijo, por lo que la calculadora resulta útil. Uso de la calculadora para un [!UICONTROL Asignación automática] la actividad es opcional porque [!UICONTROL Asignación automática] declara un ganador para usted. La calculadora le da una estimación aproximada del tamaño de la muestra necesaria. Siga leyendo para obtener más información sobre cómo usar la calculadora.

Antes de configurar la prueba A/B, acceda al [!DNL Adobe Target] [Calculadora de tamaño de muestra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=es).

![Calculadora de tamaño de muestra de Adobe Target.](/help/main/c-activities/t-test-ab/assets/sample_size_calculator-new.png)

Es importante determinar un tamaño de muestra adecuado (número de visitantes) antes de realizar cualquier prueba A/B para establecer el tiempo que la actividad debe ejecutarse antes de evaluar los resultados. El simple seguimiento de la actividad hasta que se alcance la relevancia estadística provoca que el intervalo de confianza se subestime enormemente, lo que hace que la prueba no sea fiable. La intuición que hay tras el resultado es que, en el caso de que se detecte un resultado estadísticamente relevante, se detendrá la prueba y se declarará un ganador. Sin embargo, si el resultado no es estadísticamente relevante, se permite que la prueba siga realizándose. Este procedimiento favorece enormemente un resultado positivo, que aumenta la tasa de falsos positivos y, por tanto, distorsiona el nivel de relevancia estadística de la prueba.

Esto puede dar como resultado muchos falsos positivos, lo que conduce a la implementación de ofertas que no ofrecen el alza prevista al final. El alza deficiente en sí es un resultado insatisfactorio, pero una consecuencia aún más grave es que, con el tiempo, la incapacidad para predecir con precisión el alza erosiona la confianza de la organización en las pruebas como práctica.

Este artículo analiza los factores que deben equilibrarse cuando se determina un tamaño de muestra e introduce una calculadora para estimar un tamaño de muestra adecuado. El cálculo del tamaño de la muestra mediante la calculadora de tamaño de muestra (vínculo proporcionado anteriormente) antes de que comience cualquier prueba A/B garantiza que siempre se ejecuten pruebas A/B de alta calidad que cumplan con los estándares estadísticos.

Hay cinco parámetros definidos por el usuario que definen una prueba A/B. Estos parámetros están interconectados, así que cuatro de ellos están establecidos y el quinto se puede calcular:

* Relevancia estadística
* Potencia estadística
* Alza mínima fiable detectable
* Tasa de conversión de línea de base
* Número de visitantes

>[!IMPORTANT]
>
>Para obtener resultados precisos, debe volver a cargar la página antes de cambiar los números de parámetro. Repita este proceso cada vez que cambie los números de parámetros.

Para una prueba A/B, el analista fija la relevancia estadística, la eficacia estadística, el alza mínima fiable detectable y la tasa de conversión de línea de base, y el número de visitantes se calcula a partir de estos valores. Este artículo analiza estos elementos y proporciona directrices para determinar estas métricas para una prueba específica.

![imagen de tamaño de muestra](assets/samplesize.png)

En la siguiente imagen se muestran los cuatro resultados posibles de una prueba A/B:

![imagen de resultados](assets/outcomes.png)

Es deseable no obtener falsos positivos ni falsos negativos. Sin embargo, la obtención de cero falsos positivos nunca puede garantizarse mediante una prueba estadística. Siempre es posible que las tendencias observadas no sean representativas de las tasas de conversión subyacentes. Por ejemplo, en una prueba para ver si las cabezas o colas en un giro de moneda era más probable, incluso con una moneda justa, se podían obtener diez cabezas en diez lanzamientos por casualidad. La relevancia y la potencia estadísticas nos permiten cuantificar las tasas de falsos positivos y falsos negativos, y mantenerlos en niveles razonables para una determinada prueba.

### Relevancia estadística {#section_8230FB9C6D1241D8B1786B72B379C3CD}

El nivel de relevancia de una prueba determina la probabilidad de que la prueba notifique una diferencia significativa en las tasas de conversión entre dos ofertas diferentes cuando, de hecho, no hay ninguna diferencia real. Esta situación se conoce como falso positivo o error de tipo I. El nivel de relevancia es un umbral especificado por el usuario y es un equilibrio entre la tolerancia de los falsos positivos y el número de visitantes que deben incluirse en la prueba.

En una prueba A/B, inicialmente se presupone que las dos ofertas tienen la misma tasa de conversión. Después, la probabilidad del resultado observado se calcula en función de esta presuposición. Si esta probabilidad (el valor p) es menor que algún umbral predefinido (el nivel de relevancia), [!DNL Target] concluye que la suposición inicial (que ambas ofertas tienen la misma tasa de conversión) es incorrecta. Y, por lo tanto, las tasas de conversión de A y B son estadísticamente diferentes en el nivel de significancia dado.

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

Es deseable utilizar el nivel de confianza más alto posible, de modo que la prueba arroje pocos falsos positivos. Sin embargo, un nivel de confianza mayor requiere un gran número de visitantes, lo que aumenta el tiempo necesario para realizar la prueba. Además, un aumento en el nivel de confianza ocasiona una reducción en la potencia estadística.

### Potencia estadística {#section_1169C27F8E4643719D38FB9D6EBEB535}

La potencia estadística de una prueba A/B es la probabilidad de detectar una diferencia real en la tasa de conversión de una determinada magnitud. Debido a la naturaleza aleatoria (estocástica) de los eventos de conversión, es posible que no se observe una diferencia con relevancia estadística (solo por casualidad) aunque haya una diferencia real en la tasa de conversión entre las dos ofertas. Este escenario se denomina &quot;falso negativo&quot; o &quot;error de tipo II&quot;.

La potencia estadística a menudo se ignora porque en una prueba A/B no es necesario determinarla, al contrario de lo que ocurre con la relevancia estadística. Sin embargo, si se ignora la potencia estadística, hay una posibilidad considerable de que las diferencias reales entre las tasas de conversión de diferentes ofertas no se detecten en la prueba porque el tamaño de la prueba es demasiado pequeño. La consecuencia es que las pruebas estarán repletas de falsos positivos.

Es preferible tener una potencia estadística elevada para que la prueba tenga muchas probabilidades de identificar una diferencia real en las tasas de conversión y genere menos falsos positivos. Sin embargo, se necesita un mayor número de visitantes para aumentar la potencia estadística de detección de cualquier alza determinada, lo que aumenta el tiempo necesario para realizar la prueba.

Un valor usado comúnmente para la potencia estadística es el 80 %, lo que supone que la prueba tiene una probabilidad del 80 % de detectar una diferencia igual al alza mínima fiable detectable. La prueba tiene una probabilidad menor de detectar altas menores y una probabilidad mayor de detectar alzas mayores.

### Alza mínima fiable detectable {#section_6101367EE9634C298410BBC2148E33A9}

La mayoría de las organizaciones desean medir la menor diferencia posible en la tasa de conversión, porque merece la pena implementar incluso un alza pequeña. Sin embargo, si desea que la prueba A/B tenga una alta probabilidad de detectar un pequeño alza, el número de visitantes que debe incluirse en la prueba sería prohibitivamente grande. El motivo es que, si la diferencia en la tasa de conversión es pequeña, ambas tasas de conversión deben estimarse con alta precisión para identificar la diferencia, lo que requiere muchos visitantes. Por tanto, el alza mínima fiable detectable deberá determinarse según los requisitos de la empresa, teniendo en cuenta el equilibrio que hay que mantener entre detectar las alzas pequeñas y ejecutar la prueba durante largos períodos de tiempo.

Por ejemplo, supongamos que dos ofertas (A y B) tienen tasas de conversión verdaderas del 10 y el 15 % respectivamente. Si estas ofertas se muestran a 100 visitantes cada una, hay un 95 % de probabilidades de observar tasas de conversión de entre 4 y 16 % para la oferta A, y de entre 8 y 22 % para la oferta B, debido a la naturaleza estocástica de las conversiones. En estadística, estos rangos se conocen como intervalos de confianza. Representan la confianza en la precisión de las tasas de conversión estimadas. Cuando mayor sea el tamaño de la muestra (más visitantes), tendrá mayor certeza de que las estimaciones de las tasas de conversión serán precisas.

En la siguiente imagen se muestran estas distribuciones de probabilidad.

![imagen probability_distributions](assets/probability_distributions.png)

Debido al gran solapamiento entre los dos rangos, la prueba no puede determinar si las tasas de conversión son diferentes. Por tanto, esta prueba con 100 visitantes no puede distinguir entre las dos ofertas. Sin embargo, si Target expone las ofertas a 5000 visitantes cada una, existe una probabilidad del 95 % de que las tasas de conversión observadas caigan en los intervalos del 9 % al 11 % y del 14 % al 16 %, respectivamente.

![imagen probability_distributions2](assets/probability_distributions2.png)

En este caso, es poco probable que la prueba llegue a una conclusión incorrecta, por lo que la prueba con 5000 visitantes puede distinguir entre las dos ofertas. La prueba con 5000 visitantes tiene un intervalo de confianza de +/-1 % aproximadamente. Esto significa que la prueba puede detectar diferencias de alrededor del 1 %. Por tanto, se necesitarían incluso más visitantes si las tasas de conversión reales de las ofertas fueran, por ejemplo, del 10 % y el 10,5 %, en lugar del 10 % y el 15 %.

### Tasa de conversión de línea de base {#section_39380C9CA3C649B6BE6E1F8A06178B05}

La tasa de conversión de línea de base es la tasa de conversión de la oferta de control (oferta A). A menudo, puede disponer de un buen sentido del nivel de conversión para la oferta, basado en su experiencia anterior. Si este no es el caso, por ejemplo porque es un nuevo tipo de oferta o es creativa, se puede realizar la prueba durante un día aproximadamente, para obtener una estimación aproximada de la tasa de conversión de línea de base que se puede usar en el cálculo del tamaño de la muestra.

### Número de visitantes {#section_19009F165505429E95291E6976E498DD}

Puede resultar difícil equilibrar los costes de oportunidad que conlleva ejecutar una prueba durante mucho tiempo, con el riesgo de falsos positivos y falsos negativos. Obviamente, no deseará tomar decisiones equivocadas, pero tampoco resulta deseable quedar paralizado por estándares de pruebas demasiado estrictos o demasiado rígidos.

Como guía general, se recomienda un nivel de confianza del 95 % y una potencia estadística del 80 %.

En la calculadora de tamaño de la muestra (encontrará el vínculo más arriba), se le pedirá que tome una decisión sobre la relevancia estadística (se recomienda el 95 %) y la potencia estadística (se recomienda el 80 %). Tras indicar la tasa de conversión de línea de base y el tráfico diario en todas las ofertas, la hoja de cálculo muestra el número de visitantes necesarios para detectar un alza de 1 %, 2 %, 5 %, 10 %, 15 % y 20 % con una probabilidad igual a la potencia especificada en la prueba. La hoja de cálculo también permite al usuario indicar un valor personalizado para el alza mínima fiable detectable. Además, la hoja de cálculo muestra el número de semanas necesarias para realizar la prueba, en función del nivel de tráfico indicado por el usuario. Este número de semanas se redondea hasta la semana completa más próxima, para evitar cualquier efecto de día de la semana que pueda influir en los resultados.

Existe un equilibrio entre el alza mínima que la prueba puede detectar de manera fiable y el número de visitantes necesario. En la imagen de abajo, que es válida para una tasa de conversión de línea de base (control) del 5 %, se muestra una fuerte reducción de los valores devueltos conforme aumenta el número de visitantes. El alza mínima que se puede detectar de manera fiable mejora considerablemente cuando se agregan algunos de los primeros visitantes a la prueba, pero toma un número de visitantes cada vez mayor para mejorar la prueba. La imagen ayuda a encontrar un equilibrio adecuado entre el tiempo necesario para realizar la prueba (según viene determinado por el número de visitantes necesario y el tráfico del sitio) y el alza mínima que la prueba puede detectar de manera fiable.

![imagen samplesizecontrol](assets/samplesizecontrol.png)

En este ejemplo, es posible que decida que se puede detectar un alza del 5 % (correspondiente a una tasa de conversión de la oferta alternativa (100 % + 5 %)&#42;5 % = 5,25 %) en 80 de 100 pruebas es adecuado, por lo que necesita un tamaño de muestra de 100 000 visitantes para cada oferta. Si el sitio tiene 20 000 visitantes al día y está probando dos ofertas, la prueba debería poder ejecutarse durante 2&#42;100 000/20 000 = 10 días antes de que se pueda determinar si la oferta alternativa tiene una relevancia estadística superior a la de la oferta de control.

Una vez más, se recomienda que el tiempo necesario se redondee siempre a la semana completa más próxima, para evitar cualquier efecto de día de la semana. Por tanto, en este ejemplo, la prueba se realizaría durante dos semanas antes de evaluar los resultados.

### Métrica de ingresos por visita.  {#section_C704C0861C9B4641AB02E911648D2DC2}

Al utilizar Ingresos por visita (RPV) como métrica, se agrega una fuente de variación adicional porque RPV es el producto de ingresos por pedido y tasa de conversión (RPV = Ingresos / #visitors = (Ingresos por pedido) &#42; #orders) / # visitantes = Ingresos por pedido &#42; (#visitors &#42; CTR) / #visitors = Ingresos por pedido &#42; CTR), cada una con su propia variación. La varianza de la tasa de conversión puede estimarse directamente utilizando un modelo matemático, pero la varianza de los ingresos por pedido es específica de la actividad. Por lo tanto, utilice el conocimiento de esta variación de actividades anteriores o ejecute la prueba A/B durante unos días para estimar la variación en los ingresos. La variación se calcula a partir de los valores de Suma de ventas, Suma de ventas al cuadrado y Número de visitantes que se encuentran en el archivo de descarga CSV. Una vez establecido, utilice la hoja de cálculo para calcular el tiempo necesario para completar la prueba.

La calculadora de tamaño de la muestra (vínculo proporcionado arriba) puede ayudarle a configurar la métrica de RPV. Cuando abra la calculadora, verá una pestaña denominada [!UICONTROL Métrica de RPV]. Necesitará la siguiente información al usar la versión de RPV de la calculadora:

* Número de visitantes a la oferta de control
* Ingresos totales para la oferta de control

   Asegúrese de que está seleccionado el filtro de pedidos extremos.

* La suma de ingresos al cuadrado para la oferta de control

   Asegúrese de que el filtro de pedidos extremos esté seleccionado.

En general, el uso de RPV como métrica requiere entre un 20 y un 30 % más de tiempo para lograr el mismo nivel de confianza estadística para el mismo nivel de alza medida. Esto se debe a que RPV tiene la variación añadida de diferentes tamaños de pedidos por conversión. Esto debería tenerse en cuenta a la hora de elegir entre la tasa de conversión directa y RPV como métrica en la que basar la decisión comercial final.

## Corrección para comparar varias ofertas {#section_1474113764224D0B85472D8B023CCA15}

Cada vez que compara dos ofertas, las posibilidades de obtener un falso positivo (es decir, observar una diferencia con relevancia estadística aunque no haya diferencia en la tasa de conversión) son iguales al nivel de relevancia. Por ejemplo, si hay cinco ofertas, A/B/C/D/E, y A es la oferta control, se realizan las cuatro comparaciones (control frente a B, control frente a C, control frente a D y control frente a E), y la probabilidad de obtener un falso positivo es del 18,5 % aunque el nivel de confianza sea del 95 % porque Pr (al menos un falso positivo) = 1 - Pr (sin falsos positivos) = 1 - 0,95 = 18,5 %. En este contexto, un falso positivo se define como la notificación de que el control es mejor que la alternativa, o que la alternativa es mejor que el control cuando, de hecho, no hay ninguna diferencia entre ellos.

## Conclusión.  {#section_AEA2427B90AE4E9395C7FF4F9C5CA066}

Mediante un [!UICONTROL Asignación automática] actividad, [!DNL Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. [!UICONTROL La asignación automática facilita el logro de sus objetivos de conversión y elimina las suposiciones.]

Al utilizar la calculadora de tamaño de la muestra (vínculo proporcionado arriba) presentada en este artículo y permitir que la prueba se ejecute durante el tiempo sugerido por ella, puede asegurarse de que siempre está haciendo pruebas A/B de alta calidad que se adhieren a las tasas de falsos positivos y falsos negativos que ha decidido que son adecuados para la prueba específica. Esto garantiza que sus pruebas sean coherentes y capaces de detectar el alza que está buscando.
