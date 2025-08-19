---
keywords: asignación de tráfico automatizado;segmentación;ganador;garantía estadística;confianza;determinar ganador;alza;confianza;predeterminado;experiencia predeterminada;asignación automática;asignación automática
description: Aprenda a interpretar los resultados de una actividad A/B de [!UICONTROL Auto-Allocate] en Adobe [!DNL Target] examinando los indicadores importantes, incluidos el alza y la confianza.
title: ¿Cómo Interpreto Los Informes De [!UICONTROL Auto-Allocate]?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 21%

---

# Interpretación de informes de asignación automática

Interprete los resultados de una actividad A/B de [!UICONTROL Auto-Allocate] en [!UICONTROL Adobe Target] mediante el examen de indicadores importantes, incluidos el alza y la confianza.

Muchos especialistas en marketing cometen el error de declarar una experiencia ganadora precipitadamente antes de que los resultados indiquen el claro ganador. [!DNL Target] facilita la determinación del ganador.

Para obtener información general sobre cómo declarar un ganador, consulte [Diez dificultades comunes de las pruebas A/B y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificación de la experiencia ganadora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Al usar la característica [!UICONTROL Auto-Allocate], [!DNL Target] muestra un distintivo en la parte superior de la página de la actividad indicando &quot;Ningún ganador aún&quot; hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza.

![Sin distintivo ganador](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Cuando se declara un claro ganador, [!DNL Target] muestra &quot;Ganador: Experiencia *X*&quot;.

![imagen ganadora](assets/winner.png)

>[!NOTE]
>
>Las actividades de asignación automática han sido diseñadas para encontrar la mejor experiencia entre todas las opciones y no solo hacer comparaciones por pares con control.

## Garantías estadísticas de asignación automática {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

Al final de una actividad A/B, [!UICONTROL Auto-Allocate] garantiza que el ganador determinado tenga una tasa de falsos positivos efectiva del 5%. Esto significa que solo un 5 % de las veces el ganador determinado no es realmente la mejor experiencia de todas las que participan en la actividad. Para una prueba [A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (con experiencias idénticas), [!DNL Target] concluye una prueba menos del 5% de las veces. El comportamiento previsto en una prueba A/A (con experiencias idénticas) es que se ejecute de forma indefinida, de modo que nunca se mostrará el distintivo de ganador.

[!DNL Target] no utiliza confianza basada en valor p para [!UICONTROL Auto-Allocate].

La columna [!UICONTROL Confidence] de una actividad [!UICONTROL Auto-Allocate] (ilustrada a continuación) muestra la probabilidad de que una experiencia sea la ganadora dentro del margen de error del 1 %. El algoritmo utiliza un efecto detectable mínimo del 1 % entre las mejores y las segundas mejores tasas de conversión. El algoritmo usa [la desigualdad de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para calcular esta probabilidad.

Las pruebas A/B normales calculan la confianza según los valores p. [!UICONTROL Auto-Allocate] no utiliza valores P. Los valores p calculan de forma “flexible” la probabilidad de que una experiencia indicada sea diferente al control. Estos valores P solo pueden usarse para determinar si una experiencia es diferente al control. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

>[!IMPORTANT]
>
>[!DNL Target] muestra un ganador después de un número mínimo predefinido de conversiones; sin embargo, la decisión final de elegir el ganador siempre debe estar en los resultados de la calculadora de tamaño de muestra [!DNL Adobe Target]. [!DNL Target] no tiene en cuenta las tasas de conversión base de un sitio ni otros aspectos importantes que se incluyen en la calculadora para determinar la duración de la actividad. Como resultado, [!DNL Target] podría mostrar un ganador antes de lo garantizado en función de un número mínimo de conversiones. Para obtener más información, vea [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprender los informes de alza y confianza en [!UICONTROL Auto-Allocate] actividades {#lift-confidence}

En las actividades [!UICONTROL Auto-Allocate], la primera experiencia (con el nombre predeterminado Experiencia A) siempre se define como una experiencia de &quot;Control&quot; en la ficha [!UICONTROL Reports]. Esta experiencia no se trata como un verdadero control estadístico en el modelado utilizado para determinar el rendimiento de las experiencias, pero se trata como una referencia o línea de base para algunas cifras en el informe.

El valor numérico &quot;Alza&quot; y los límites del 95 % para cada experiencia siempre se calculan con referencia a la experiencia de &quot;Control&quot; definida. La experiencia de &quot;Control&quot; definida no puede tener un alza en relación consigo misma, por lo que se comunica un valor &quot;—&quot; en blanco para esta experiencia. A diferencia de las pruebas A/B, en [!UICONTROL Auto-Allocate] pruebas, si una experiencia tiene un rendimiento peor que el del control definido, no se comunica un valor de alza negativo; en su lugar, se muestra &quot;—&quot;.

Las [!UICONTROL Confidence Interval] barras mostradas representan el intervalo de confianza del 95 % en torno a la estimación media de la tasa de conversión de una experiencia. Estas barras también están codificadas por colores con respecto a la experiencia de &quot;control&quot; definida. La barra de la experiencia &quot;Control&quot; siempre aparece en color gris. Las partes de los intervalos de confianza situados debajo del intervalo de confianza de la experiencia &quot;Control&quot; se muestran en rojo y las partes de los intervalos de confianza situados encima de la experiencia &quot;Control&quot; en verde.

Se encuentra un ganador cuando el 95 % [!UICONTROL Confidence Interval] de la experiencia principal no se superpone con ninguna otra experiencia. La experiencia ganadora se designa con un distintivo de estrella verde a la izquierda del nombre de la experiencia y en el titular &quot;Ganador&quot;. Cuando no se ve ninguna estrella, el cartel dice &quot;Ningún ganador aún&quot; y aún no se ha encontrado un ganador.

También se indica un número de &quot;Confianza&quot; junto a la experiencia principal o ganadora actual. Esta cifra solo se registra hasta que [!UICONTROL Confidence] de la experiencia principal alcance al menos el 60 %. Si hay dos experiencias presentes en la actividad [!UICONTROL Auto-Allocate], este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la otra experiencia. Si hay más de dos experiencias presentes en la actividad [!UICONTROL Auto-Allocate], este número representa el nivel de confianza de que la experiencia está teniendo un mejor rendimiento que la experiencia de &quot;control&quot; definida. Si la experiencia &quot;Control&quot; es la ganadora, no se informa de ninguna cifra &quot;Confianza&quot;.

## Preguntas frecuentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Tenga en cuenta las siguientes respuestas a las preguntas más frecuentes:

### Han pasado unos días desde que comenzó la actividad. ¿Por qué todos los valores de confianza siguen mostrando un 0 %?

Cualquiera de los siguientes motivos describe por qué el 0% se muestra en la columna [!UICONTROL Confidence] del informe para todas las actividades:

* Las pruebas A/B manuales y [!UICONTROL Auto-Allocate] utilizan estadísticas diferentes para mostrar los valores de [!UICONTROL Confidence].

  Las pruebas A/B manuales usan valores p basados en [prueba t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Un valor P es la probabilidad de encontrar la diferencia observada (o más extrema) entre una experiencia y el control, dado que en la realidad no existe dicha diferencia. Estos valores P solo pueden utilizarse para determinar si los datos observados son coherentes con una experiencia determinada y si el control es el mismo. Estos valores no pueden usarse para determinar si una experiencia es diferente a otra experiencia (no control).

  [!UICONTROL Auto-Allocate] muestra la probabilidad de que una experiencia determinada sea una verdadera ganadora en todas las experiencias de la actividad. Solo una experiencia ganadora (que es la que tiene más probabilidades de ser la ganadora) tiene un valor de confianza distinto de cero. Todos los demás tienen más probabilidades de ser perdedores y mostrar 0%.

* [!UICONTROL Auto-Allocate] comienza a mostrar confianza solo después de que la experiencia ganadora recopila un 60 % de confianza. Estos niveles de confianza suelen aparecer en aproximadamente la mitad del tiempo que tardaría una prueba A/B normal en completarse (aunque este lapso de tiempo no está garantizado). Para determinar cuánto tiempo tarda en ejecutarse una prueba A/B normal, use la [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): introduzca la tasa de conversión de control en &quot;Tasa de conversión de línea de base&quot;, &quot;5%&quot; para &quot;Alza&quot; y &quot;95%&quot; para &quot;Confianza&quot;. Normalmente, la confianza empieza a mostrarse después de que cada experiencia haya reunido al menos un 50 % de las muestras por experiencia necesarias. Esto le da una idea de cuándo empieza a aparecer la confianza.

* Si el informe muestra un 0 % en el panel, es probable que sea pronto para la actividad.

### ¿Están disponibles los distintivos &quot;Sin ganador&quot;, &quot;Ganador&quot; y &quot;estrella&quot; para [!UICONTROL Auto-Allocate] actividades que utilizan [!UICONTROL Analytics as the reporting source] (A4T)?

Los distintivos &quot;Ningún ganador aún&quot; y &quot;Ganador&quot; no están disponibles actualmente en el panel [!UICONTROL A4T] de [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se ve el mismo informe en [!DNL Target]. Se debe ignorar un distintivo de &quot;estrella&quot; ganador que se muestra en un informe [!DNL Target] para una actividad [!UICONTROL Auto-Allocate] que usa A4T.

Para obtener más información sobre esta y otras limitaciones y notas, consulte [Asignación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) en *Compatibilidad con A4T para [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] actividades*.


