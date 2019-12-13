---
keywords: automated traffic allocation;targeting;winner;statistical guarantee;confidence;determine winner;lift;confidence;default;default experience
description: Determine el ganador de una actividad A/B de asignación automática consultando los indicadores en la interfaz de usuario de Target.
title: Determinar un ganador
topic: Standard
uuid: 0bcc11b2-44bd-450c-a504-a8ff7a4d72e6
translation-type: tm+mt
source-git-commit: 9937bf3f9f2675f43de535d8a09c493769b060be

---


# Interpretar informes de asignación automática {#determine-a-winner}

Interprete los resultados de una actividad A/B de asignación automática examinando indicadores importantes, incluidos el alza y la confianza, en la interfaz de usuario de Target.

Muchos especialistas en marketing cometen el error de declarar una experiencia ganadora precipitadamente antes de que los resultados indiquen el claro ganador. Ahora, le facilitamos la tarea de determinar el ganador.

## Identifique la experiencia ganadora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Al utilizar la función de [!UICONTROL asignación automática], [!DNL Target] muestra un distintivo en la parte superior de la página de la actividad indicando “Ningún ganador aún” hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza.

![Sin distintivo ganador](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

Cuando se declara un claro ganador, [!DNL Target] muestra “Ganador: Experiencia X”.

![](assets/auto_traffic_winner.png)

>[!NOTE]
>
>Las actividades de asignación automática han sido diseñadas para encontrar la mejor experiencia entre todas las opciones y no solo hacer comparaciones por pares con control.

## Statistical guarantees of Auto-Allocate {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

Al finalizar una actividad A/B, la asignación automática garantiza que el ganador determinado tiene una tasa efectiva de falsos positivos del 5 %. Esto significa que solo un 5 % de las veces el ganador determinado no es realmente la mejor experiencia de todas las que participan en la actividad. En una prueba A/A (con experiencias idénticas), la prueba se finaliza menos del 5 % de las veces. El comportamiento previsto en una prueba A/A (con experiencias idénticas) es que se ejecute de forma indefinida, de modo que nunca se mostrará el distintivo de ganador.

En la asignación automática no se utiliza la confianza basada en el valor P.

La columna Confianza de una actividad de asignación automática (ilustrada abajo) muestra la probabilidad de que una experiencia sea la ganadora con un 1 % de margen de error (es decir, el algoritmo usa un efecto mínimo detectable del 1 % entre la primera mejor tasa de conversión y la segunda). Observe que el algoritmo usa la [desigualdad de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) para calcular esta probabilidad.

Las pruebas A/B normales calculan la confianza según los valores p. La asignación automática no usa valores p. Los valores p calculan de forma “flexible” la probabilidad de que una experiencia indicada sea diferente al control. Estos valores P solo pueden usarse para determinar si una experiencia es diferente al control. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

La siguiente ilustración muestra una actividad en la que aún no hay ganador:

![](assets/no_winner.png)

La siguiente ilustración muestra una actividad en la que ya hay un ganador:

![](assets/winner_found.png)

## Comprender los informes de alza y confianza en las actividades de asignación automática {#lift-confidence}

En las actividades de asignación automática, la primera experiencia (de forma predeterminada denominada Experiencia A) siempre se define como una experiencia de "control" en la ficha Informes. Esta experiencia no se trata como un verdadero control estadístico en el modelado utilizado para determinar el rendimiento de las experiencias, pero se trata como una referencia o una referencia para algunas cifras del informe.

El valor numérico "Alza" y los límites del 95 % para cada experiencia siempre se calculan con referencia a la experiencia definida como "Control". La experiencia "Control" definida no puede tener un alza en relación a sí misma, por lo que se informa de un valor "—" en blanco para esta experiencia. A diferencia de las pruebas A/B, en las pruebas de asignación automática, si una experiencia tiene un peor rendimiento que el control definido, no se notifica un valor de alza negativo; en su lugar se muestra "—".

Las barras Intervalo de confianza que se muestran representan el intervalo de confianza del 95 % en torno a la estimación media de la tasa de conversión de una experiencia. También están codificados por colores con respecto a la experiencia definida de "control". La barra de la experiencia "Control" siempre está coloreada en gris. Las partes de los intervalos de confianza por debajo del intervalo de confianza de la experiencia "Control" están coloreadas en rojo y las partes de los intervalos de confianza por encima de la experiencia "Control" están coloreadas en verde.

Se encuentra un ganador cuando el intervalo de confianza del 95 % de la experiencia líder no se superpone con ninguna otra experiencia. La experiencia ganadora se designa con una marca de estrella verde a la izquierda del nombre de la experiencia y en la pancarta "Ganador". Cuando no hay ninguna estrella visible, la pancarta dice "Ningún ganador aún" y todavía no se ha encontrado un ganador.

También se indica un número de "confianza" junto a la experiencia ganadora o líder en ese momento. Esta cifra se registra solamente hasta que la confianza de la experiencia líder alcance al menos el 60 %. Si hay exactamente dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la otra experiencia. Si hay más de dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la experiencia definida como "Control". Si la experiencia "Control" está ganando, no se notifica ninguna cifra de "Confianza".

## Preguntas frecuentes {#section_C8E068512A93458D8C006760B1C0B6A2}

**Han pasado varios días desde que empezó la actividad. ¿Por qué todos los valores de confianza siguen en el 0 %?**

Alguna de las siguientes razones describe la razón por la que se muestra un 0 % en la columna [!UICONTROL Confianza] de todas las actividades en el informe:

* Las pruebas A/B manuales y la asignación automática usan diferentes estadísticas para mostrar valores de confianza.

   Las pruebas A/B manuales usan valores p según una [prueba T de estudiante](https://en.wikipedia.org/wiki/Student%27s_t-test). Un valor P es la probabilidad de encontrar la diferencia observada (o más extrema) entre una experiencia y el control, dado que en la realidad no existe dicha diferencia. Estos valores P solo pueden utilizarse para determinar si los datos observados son coherentes con una experiencia determinada y si el control es el mismo. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

   La asignación automática muestra la probabilidad de que una experiencia indicada sea la auténtica ganadora de todas las experiencias de la actividad. Esto significa que solo una experiencia ganadora (que tiene más probabilidades de ganar) tendrá un valor de confianza diferente a cero. El resto tienen más probabilidades de perder y mostrarán un 0 %.

* La asignación automática solo empieza a mostrar la confianza después de que la experiencia ganadora reúna un 60 % de confianza. Estos niveles de confianza suelen aparecer en aproximadamente la mitad del tiempo que tardaría una prueba A/B normal en completarse (aunque esto no está garantizado). To determine how long a normal A/B test would run, please use a [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug control's conversion-rate in "Baseline conversion rate," "5%" for "Lift," and 95% for "Confidence." Normalmente, la confianza empieza a mostrarse después de que cada experiencia haya reunido al menos un 50 % de las muestras por experiencia necesarias. Esto le dará una idea de cuándo empezará a aparecer la confianza.
* Si el informe muestra un 0 % en el panel, es probable que sea pronto para la actividad.

