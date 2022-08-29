---
keywords: asignación de tráfico automática;segmentación;ganador;garantía estadística;confianza;determinar ganador;alza;confianza;predeterminada;experiencia predeterminada;asignación automática;asignación automática
description: Obtenga información sobre cómo interpretar los resultados de una actividad A/B de asignación automática en Adobe [!DNL Target] mediante el examen de indicadores importantes, incluidos el alza y la confianza.
title: ¿Cómo interpreto los informes de asignación automática?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 66c662e367b64ca51c5d9246cb097a12755d9aff
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 45%

---

# Interpretación de informes de asignación automática

Interpretación de los resultados de un [!UICONTROL Asignación automática] Actividad A/B en [!UICONTROL Adobe Target] mediante el examen de indicadores importantes, incluidos el alza y la confianza.

Muchos especialistas en marketing cometen el error de declarar una experiencia ganadora precipitadamente antes de que los resultados indiquen el claro ganador. Ahora, le facilitamos la tarea de determinar el ganador.

>[!NOTE]
>
>Para obtener información general sobre cómo declarar un ganador, consulte [Diez escollos comunes de las pruebas A/B y cómo evitarlos](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificar la experiencia ganadora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Al utilizar la función de [!UICONTROL asignación automática], [!DNL Target] muestra un distintivo en la parte superior de la página de la actividad indicando “Ningún ganador aún” hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza.

![Sin distintivo ganador](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Cuando se declara un claro ganador, [!DNL Target] muestra “Ganador: Experiencia X”.

![](assets/winner.png)

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
>Target muestra un ganador después de un número mínimo predefinido de conversiones; sin embargo, la decisión final de elegir al ganador siempre debe estar en los resultados de Adobe Target [calculadora de tamaño de muestra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=es). Target no tiene en cuenta las tasas de conversión base de un sitio y otros aspectos importantes que se incluyen en la calculadora para determinar la duración de la actividad. Como resultado, Target podría mostrar un ganador antes de lo justificado, basándose en un número mínimo de conversiones. Para obtener más información, consulte [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprender los informes de alza y confianza en las actividades de asignación automática {#lift-confidence}

En las actividades de asignación automática, la primera experiencia (de forma predeterminada denominada Experiencia A) siempre se define como una experiencia de &quot;Control&quot; en la pestaña Informes . Esta experiencia no se trata como un verdadero control estadístico en el modelado utilizado para determinar el rendimiento de las experiencias, pero se trata como una referencia o referencia para algunas cifras del informe.

El valor numérico &quot;Alza&quot; y los límites del 95 % para cada experiencia siempre se calculan con referencia a la experiencia definida como &quot;Control&quot;. La experiencia &quot;Control&quot; definida no puede tener un alza en relación a sí misma, por lo que se informa de un valor &quot;—&quot; en blanco para esta experiencia. A diferencia de las pruebas A/B, en las pruebas de asignación automática, si una experiencia tiene un rendimiento peor que el control definido, no se informa de un valor de alza negativo; en su lugar se muestra &quot;—&quot;.

Las barras de intervalo de confianza mostradas representan el intervalo de confianza del 95 % en torno a la estimación media de la tasa de conversión de una experiencia. También están codificados por colores con respecto a la experiencia definida de &quot;Control&quot;. La barra de la experiencia &quot;Control&quot; siempre está coloreada en gris. Las partes de intervalos de confianza por debajo del intervalo de confianza de la experiencia de &quot;Control&quot; están coloreadas en rojo y las partes de intervalos de confianza por encima de la experiencia de &quot;Control&quot; están coloreadas en verde.

Se encuentra un ganador cuando el intervalo de confianza del 95 % de la experiencia principal no se superpone con ninguna otra experiencia. La experiencia ganadora se designa con un distintivo de estrella verde a la izquierda del nombre de la experiencia y en el banner &quot;Ganador&quot;. Cuando no hay ninguna estrella visible, el banner dice &quot;Ningún ganador aún&quot; y aún no se ha encontrado un ganador.

También se comunica un número de &quot;confianza&quot; junto a la experiencia ganadora o líder actual. Esta cifra se registra solamente hasta que la confianza de la experiencia líder alcance al menos el 60%. Si hay exactamente dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la otra experiencia. Si hay más de dos experiencias presentes en el experimento de asignación automática, este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la experiencia definida como &quot;Control&quot;. Si la experiencia &quot;Control&quot; está ganando, no se notifica ninguna cifra de &quot;Confianza&quot;.

## Preguntas frecuentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenga en cuenta las siguientes respuestas a las preguntas más frecuentes:

### Han pasado varios días desde que empezó la actividad. ¿Por qué todos los valores de confianza siguen en el 0 %?

Alguna de las siguientes razones describe la razón por la que se muestra un 0 % en la columna [!UICONTROL Confianza] de todas las actividades en el informe:

* Las pruebas A/B manuales y la asignación automática usan diferentes estadísticas para mostrar valores de confianza.

   Las pruebas A/B manuales utilizan valores p basados en [Prueba T de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Un valor P es la probabilidad de encontrar la diferencia observada (o más extrema) entre una experiencia y el control, dado que en la realidad no existe dicha diferencia. Estos valores P solo pueden utilizarse para determinar si los datos observados son coherentes con una experiencia determinada y si el control es el mismo. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

   La asignación automática muestra la probabilidad de que una experiencia indicada sea la auténtica ganadora de todas las experiencias de la actividad. Esto significa que solo una experiencia ganadora (que tiene más probabilidades de ganar) tendrá un valor de confianza diferente a cero. El resto tienen más probabilidades de perder y mostrarán un 0 %.

* La asignación automática solo empieza a mostrar la confianza después de que la experiencia ganadora reúna un 60 % de confianza. Estos niveles de confianza suelen aparecer en aproximadamente la mitad del tiempo que tardaría una prueba A/B normal en completarse (aunque esto no está garantizado). Para determinar cuánto tiempo tarda en ejecutarse una prueba A/B normal, utilice un [calculadora de tamaño de muestra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html): tasa de conversión de plug-control en &quot;Tasa de conversión de línea de base&quot;, &quot;5 %&quot; para &quot;Alza&quot; y &quot;95 %&quot; para &quot;Confianza&quot;. Normalmente, la confianza empieza a mostrarse después de que cada experiencia haya reunido al menos un 50 % de las muestras por experiencia necesarias. Esto le dará una idea de cuándo empezará a aparecer la confianza.
* Si el informe muestra un 0 % en el panel, es probable que sea pronto para la actividad.

### ¿Están disponibles los distintivos “Sin ganador”, “Ganador” y “estrella” para actividades de [!UICONTROL Asignación automática] que utilizan [!UICONTROL Analytics como fuente de creación de informes] (A4T)?

Los distintivos &quot;Ningún ganador aún&quot; y &quot;Ganador&quot; no están disponibles actualmente en la [!UICONTROL A4T] panel en [!DNL Analysis Workspace]. Estos distintivos tampoco están disponibles si se ve el mismo informe en [!DNL Target]. Un distintivo de &quot;estrella&quot; ganador se muestra en una [!DNL Target] para [!UICONTROL Asignación automática] debe ignorarse la actividad que utiliza A4T.

Para obtener más información sobre esta y otras limitaciones y notas, consulte [Asignación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) en *Compatibilidad con A4T para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades*.


