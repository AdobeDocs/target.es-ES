---
keywords: asignación de tráfico automatizado;segmentación;ganador;garantía estadística;confianza;determinar ganador;alza;confianza;predeterminado;experiencia predeterminada;asignación automática;asignación automática
description: Obtenga información sobre cómo interpretar los resultados de una actividad A/B de asignación automática en Adobe [!DNL Target] mediante el examen de indicadores importantes, incluidos el alza y la confianza.
title: ¿Cómo Interpreto Los Informes De Asignación Automática?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 44%

---

# Interpretación de informes de asignación automática

Interpretación de los resultados de un [!UICONTROL Asignación automática] Actividad A/B en [!UICONTROL Adobe Target] mediante el examen de indicadores importantes, incluidos el alza y la confianza.

Muchos especialistas en marketing cometen el error de declarar una experiencia ganadora precipitadamente antes de que los resultados indiquen el claro ganador. Ahora, le facilitamos la tarea de determinar el ganador.

>[!NOTE]
>
>Para obtener información general sobre cómo declarar un ganador, consulte [Diez dificultades comunes de las pruebas A/B y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificación de la experiencia ganadora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Al utilizar la función de [!UICONTROL asignación automática], [!DNL Target] muestra un distintivo en la parte superior de la página de la actividad indicando “Ningún ganador aún” hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza.

![Sin distintivo ganador](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Cuando se declara un claro ganador, [!DNL Target] muestra “Ganador: Experiencia X”.

![imagen ganadora](assets/winner.png)

>[!NOTE]
>
>Las actividades de asignación automática han sido diseñadas para encontrar la mejor experiencia entre todas las opciones y no solo hacer comparaciones por pares con control.

## Garantías estadísticas de asignación automática {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

Al finalizar una actividad A/B, la asignación automática garantiza que el ganador determinado tiene una tasa efectiva de falsos positivos del 5 %. Esto significa que solo un 5 % de las veces el ganador determinado no es realmente la mejor experiencia de todas las que participan en la actividad. En una prueba A/A (con experiencias idénticas), la prueba se finaliza menos del 5 % de las veces. El comportamiento previsto en una prueba A/A (con experiencias idénticas) es que se ejecute de forma indefinida, de modo que nunca se mostrará el distintivo de ganador.

En la asignación automática no se utiliza la confianza basada en el valor P.

La columna Confianza de una actividad de asignación automática (ilustrada abajo) muestra la probabilidad de que una experiencia sea la ganadora con un 1 % de margen de error (es decir, el algoritmo usa un efecto mínimo detectable del 1 % entre la primera mejor tasa de conversión y la segunda). Observe que el algoritmo usa la [desigualdad de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para calcular esta probabilidad.

Las pruebas A/B normales calculan la confianza según los valores p. La asignación automática no usa valores p. Los valores p calculan de forma “flexible” la probabilidad de que una experiencia indicada sea diferente al control. Estos valores P solo pueden usarse para determinar si una experiencia es diferente al control. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

>[!IMPORTANT]
>
>Target muestra un ganador después de un número mínimo predefinido de conversiones; sin embargo, la decisión final de elegir el ganador siempre debe estar en los resultados de la [!DNL Adobe Target] Calculadora de tamaño de muestra. [!DNL Target] no tiene en cuenta las tasas de conversión base de un sitio ni otros aspectos importantes que se introducen en la calculadora para determinar la duración de la actividad. Como resultado, Target podría mostrar un ganador antes de lo garantizado sobre la base de un número mínimo de conversiones. Para obtener más información, consulte [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprensión de los informes de alza y confianza en las actividades de asignación automática {#lift-confidence}

En las actividades de Asignación automática, la primera experiencia (denominada de forma predeterminada Experiencia A) se define siempre como una experiencia de &quot;Control&quot; en la pestaña Informes. Esta experiencia no se trata como un verdadero control estadístico en el modelado utilizado para determinar el rendimiento de las experiencias, pero se trata como una referencia o línea de base para algunas cifras en el informe.

El valor numérico &quot;Alza&quot; y los límites del 95 % para cada experiencia siempre se calculan con referencia a la experiencia de &quot;Control&quot; definida. La experiencia de &quot;Control&quot; definida no puede tener un alza en relación consigo misma, por lo que se comunica un valor &quot;—&quot; en blanco para esta experiencia. A diferencia de las pruebas A/B, en las pruebas de asignación automática, si una experiencia tiene un rendimiento peor que el control definido, no se comunica un valor de alza negativo; en su lugar, se muestra &quot;—&quot;.

Las barras de intervalo de confianza mostradas representan el intervalo de confianza del 95 % alrededor de la estimación media de la tasa de conversión de una experiencia. También están codificados por colores con respecto a la experiencia de &quot;control&quot; definida. La barra de la experiencia &quot;Control&quot; siempre aparece en color gris. Las partes de los intervalos de confianza situados debajo del intervalo de confianza de la experiencia &quot;Control&quot; se muestran en rojo y las partes de los intervalos de confianza situados encima de la experiencia &quot;Control&quot; en verde.

Se obtiene un ganador cuando el intervalo de confianza del 95 % de la experiencia principal no se superpone con ninguna otra experiencia. La experiencia ganadora se designa con un distintivo de estrella verde a la izquierda del nombre de la experiencia y en el titular &quot;Ganador&quot;. Cuando no se ve ninguna estrella, el cartel dice &quot;Ningún ganador aún&quot; y aún no se ha encontrado un ganador.

También se indica un número de &quot;Confianza&quot; junto a la experiencia principal o ganadora actual. Esta cifra solo se registra hasta que la confianza de la experiencia principal alcanza al menos el 60 %. Si hay exactamente dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia tiene un mejor rendimiento que la otra experiencia. Si hay más de dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia tiene un mejor rendimiento que la experiencia de &quot;control&quot; definida. Si la experiencia &quot;Control&quot; es la ganadora, no se informa de ninguna cifra &quot;Confianza&quot;.

## Preguntas frecuentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenga en cuenta las siguientes respuestas a las preguntas más frecuentes:

### Han pasado varios días desde que empezó la actividad. ¿Por qué todos los valores de confianza siguen en el 0 %?

Alguna de las siguientes razones describe la razón por la que se muestra un 0 % en la columna [!UICONTROL Confianza] de todas las actividades en el informe:

* Las pruebas A/B manuales y la asignación automática usan diferentes estadísticas para mostrar valores de confianza.

   Las pruebas A/B manuales utilizan valores p basados en [Prueba T de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Un valor P es la probabilidad de encontrar la diferencia observada (o más extrema) entre una experiencia y el control, dado que en la realidad no existe dicha diferencia. Estos valores P solo pueden utilizarse para determinar si los datos observados son coherentes con una experiencia determinada y si el control es el mismo. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

   La asignación automática muestra la probabilidad de que una experiencia indicada sea la auténtica ganadora de todas las experiencias de la actividad. Esto significa que solo una experiencia ganadora (que tiene más probabilidades de ganar) tendrá un valor de confianza diferente a cero. El resto tienen más probabilidades de perder y mostrarán un 0 %.

* La asignación automática solo empieza a mostrar la confianza después de que la experiencia ganadora reúna un 60 % de confianza. Estos niveles de confianza suelen aparecer en aproximadamente la mitad del tiempo que tardaría una prueba A/B normal en completarse (aunque esto no está garantizado). Para determinar cuánto tiempo tarda en ejecutarse una prueba A/B normal, utilice el [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): introduzca la tasa de conversión de control en &quot;Tasa de conversión de línea de base&quot;, &quot;5 %&quot; para &quot;Alza&quot; y &quot;95 %&quot; para &quot;Confianza&quot;. Normalmente, la confianza empieza a mostrarse después de que cada experiencia haya reunido al menos un 50 % de las muestras por experiencia necesarias. Esto le dará una idea de cuándo empezará a aparecer la confianza.

* Si el informe muestra un 0 % en el panel, es probable que sea pronto para la actividad.

### ¿Están disponibles los distintivos “Sin ganador”, “Ganador” y “estrella” para actividades de [!UICONTROL Asignación automática] que utilizan [!UICONTROL Analytics como fuente de creación de informes] (A4T)?

Las insignias &quot;Ningún ganador aún&quot; y &quot;Ganador&quot; actualmente no están disponibles en el [!UICONTROL A4T] panel en [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se visualiza el mismo informe en [!DNL Target]. Una insignia de &quot;estrella&quot; ganadora que se muestra en una [!DNL Target] informe para un [!UICONTROL Asignación automática] La actividad de mediante A4T debe ignorarse.

Para obtener más información sobre esta y otras limitaciones y notas, consulte [Asignación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) in *Compatibilidad de A4T con [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades*.


