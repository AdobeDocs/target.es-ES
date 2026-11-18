---
keywords: asignación de tráfico automatizado;segmentación;ganador;garantía estadística;confianza;determinar ganador;alza;confianza;predeterminado;experiencia predeterminada;asignación automática;asignación automática
description: Descubra cómo interpretar los resultados de la actividad A/B [!UICONTROL Asignación automática], centrándose en indicadores clave como el alza y la confianza.
title: ¿Cómo Interpreto Los Informes [!UICONTROL Asignación Automática]?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
TQID: 'https://experienceleague.adobe.com/o4mFGMk-M5QUvJ57kYnfjMPvVZL8l6YegJQSJyHjAxc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 174d4631b6f4a481c039bd7fff52a8e70161e19e
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 3%
---
# Interpretar [!UICONTROL informes de asignación automática] {#interpret-auto-allocate-reports}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a identificar la experiencia ganadora de una actividad de **[!UICONTROL Asignación automática]**, que proporciona garantías estadísticas **[!UICONTROL Asignación automática]**, y a leer las cifras de alza y confianza del informe.

>[!ENDSHADEBOX]

El informe de una actividad A/B de **[!UICONTROL Asignación automática]** en [!DNL Adobe Target] muestra si la actividad ha encontrado un ganador y cuán seguro está [!DNL Target] de ese resultado. Los indicadores como el distintivo de ganador, el alza y la confianza le ayudan a interpretar los resultados.

Muchos especialistas en marketing cometen el error de declarar una experiencia ganadora prematuramente antes de que los resultados indiquen un claro ganador. [!DNL Target] facilita la determinación del ganador. Para obtener información general sobre cómo declarar un ganador, consulte [Diez dificultades comunes de las pruebas A/B y cómo evitarlas](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificación de la experiencia ganadora {#identify-winner}

Al usar la característica **[!UICONTROL Asignación automática]**, [!DNL Target] muestra un distintivo en la parte superior de la página de actividad. La insignia indica &quot;Ningún ganador aún&quot; hasta que la actividad alcance el número mínimo de conversiones con suficiente confianza.

![Sin distintivo ganador](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

Cuando se declara un claro ganador, [!DNL Target] muestra el distintivo &quot;Ganador: Experiencia *X*&quot;.

![Insignia del ganador](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

El distintivo de ganador también aparece en la ventana emergente de información de una actividad de la lista **[!UICONTROL Actividades]**, para que pueda ver el estado de una actividad de **[!UICONTROL Asignación automática]** sin necesidad de abrirla.

>[!NOTE]
>
>Las actividades de **[!UICONTROL Asignación automática]** se han diseñado para encontrar la mejor experiencia entre todas las opciones, no solo para hacer comparaciones por pares con el control.

## Garantías estadísticas de [!UICONTROL asignación automática] {#statistical-guarantees}

Al final de una actividad A/B, **[!UICONTROL Asignación automática]** garantiza que el ganador determinado tenga una tasa efectiva de falsos positivos del 5%. Esto significa que solo un 5 % de las veces el ganador determinado no es realmente la mejor experiencia de todas las que participan en la actividad.

Para una prueba [A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (con experiencias idénticas), [!DNL Target] concluye una prueba menos del 5% de las veces. El comportamiento esperado para una prueba A/A es ejecutarse indefinidamente, por lo que el distintivo de ganador nunca debe aparecer.

### Confianza y valores p {#confidence-p-values}

[!DNL Target] no usa confianza basada en valor p para **[!UICONTROL Asignación automática]**. La columna **[!UICONTROL Confianza]** en una actividad de **[!UICONTROL Asignación automática]** muestra la probabilidad de que una experiencia sea la ganadora con un margen de error del 1%. El algoritmo usa un efecto detectable mínimo del 1% entre las mejores y las segundas mejores tasas de conversión, y usa la desigualdad de [Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para calcular esta probabilidad.

Las pruebas A/B normales calculan la confianza en función de los valores p, que calculan de forma &quot;flexible&quot; la probabilidad de que una experiencia determinada sea diferente al control. Estos valores P solo pueden usarse para determinar si una experiencia es diferente al control. No se pueden usar para determinar si una experiencia es diferente de otra experiencia (no el control).

>[!IMPORTANT]
>
>[!DNL Target] muestra un ganador después de un número mínimo predefinido de conversiones. Sin embargo, la decisión final de elegir al ganador siempre debe basarse en los resultados de la calculadora de tamaño de muestra [!DNL Adobe Target]. [!DNL Target] no tiene en cuenta las tasas de conversión base de un sitio ni otros aspectos importantes que se incluyen en la calculadora para determinar la duración de la actividad. Como resultado, [!DNL Target] podría mostrar un ganador antes de lo garantizado en función de un número mínimo de conversiones. Para obtener más información, vea [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Comprender los informes de alza y confianza {#lift-confidence}

La ficha **[!UICONTROL Informes]** de una actividad **[!UICONTROL Asignación automática]** muestra las siguientes cifras:

| Figura | Descripción |
|---|---|
| **Experiencia de control** | La primera experiencia (denominada Experiencia A de forma predeterminada) siempre se define como la experiencia &quot;Control&quot; en la ficha **[!UICONTROL Informes]**. Esta experiencia no se trata como un verdadero control estadístico en el modelado utilizado para determinar el rendimiento de las experiencias, pero se trata como una referencia o línea de base para algunas cifras en el informe. |
| **Alza** | El valor &quot;Alza&quot; y los límites del 95 % de cada experiencia se calculan siempre con referencia a la experiencia de &quot;Control&quot; definida. La experiencia de &quot;Control&quot; no puede tener un alza en relación consigo misma, por lo que el informe muestra un valor &quot;—&quot; en blanco para esta experiencia.<br>A diferencia de las pruebas A/B, en las pruebas de **[!UICONTROL Asignación automática]**, si una experiencia tiene un rendimiento peor que el del control definido, no se informa de un valor de alza negativo. En su lugar, se muestra &quot;—&quot;. |
| **Intervalos de confianza** | Las barras **[!UICONTROL Intervalo de confianza]** mostradas representan el intervalo de confianza del 95 % alrededor de la estimación media de la tasa de conversión de una experiencia. Las barras están codificadas por colores con respecto a la experiencia de &quot;control&quot; definida:<ul><li>La barra de la experiencia &quot;Control&quot; siempre es gris.</li><li>Las partes de los intervalos de confianza debajo del intervalo de confianza de la experiencia &quot;Control&quot; están en rojo.</li><li>Las partes de los intervalos de confianza que se encuentran por encima del intervalo de confianza de la experiencia &quot;Control&quot; son verdes.</li></ul> |
| **Ganador** | Se encuentra un ganador cuando el 95 % **[!UICONTROL Intervalo de confianza]** de la experiencia principal no se superpone con ninguna otra experiencia. La experiencia ganadora se designa con un distintivo de estrella verde a la izquierda del nombre de la experiencia y en el titular &quot;Ganador&quot;. Cuando no se ve ninguna estrella, el cartel dice &quot;Ningún ganador aún&quot; y aún no se ha encontrado un ganador. |
| **Número de confianza** | También se indica un número de &quot;Confianza&quot; junto a la experiencia principal o ganadora actual. Se informa de esta cifra solamente hasta que la **[!UICONTROL confianza]** de la experiencia líder alcance al menos el 60%.<ul><li>Si hay dos experiencias presentes en la actividad **[!UICONTROL Asignación automática]**, el número representa el nivel de confianza de que la experiencia está funcionando mejor que la otra experiencia.</li><li>Si hay más de dos experiencias, el número representa el nivel de confianza de que la experiencia tiene un mejor rendimiento que la experiencia de &quot;control&quot; definida.</li><li>Si la experiencia &quot;Control&quot; es la ganadora, no se informa de ninguna cifra &quot;Confianza&quot;.</li></ul> |

## Preguntas más frecuentes {#faq}

Tenga en cuenta las siguientes respuestas a las preguntas más frecuentes.

+++ Han pasado unos días desde que comenzó la actividad. ¿Por qué todos los valores de confianza siguen mostrando un 0 %?

Cualquiera de las siguientes razones describe por qué el 0% se muestra en la columna **[!UICONTROL Confianza]** del informe para todas las experiencias:

* Las pruebas A/B manuales y **[!UICONTROL Asignación automática]** usan estadísticas diferentes para mostrar los valores de **[!UICONTROL Confianza]**.

  Las pruebas A/B manuales usan valores p basados en [prueba t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Un valor p es la probabilidad de encontrar la diferencia observada (o más extrema) entre una experiencia y el control, dado que en realidad no existe dicha diferencia. Estos valores p solo pueden utilizarse para determinar si los datos observados son coherentes con una experiencia determinada y si el control es el mismo. No se pueden usar para determinar si una experiencia es diferente de otra experiencia (no el control).

  **[!UICONTROL Asignación automática]** muestra la probabilidad de que una experiencia determinada sea una verdadera ganadora en todas las experiencias de la actividad. Solo una experiencia ganadora (que es la que tiene más probabilidades de ser la ganadora) tiene un valor de confianza distinto de cero. Todos los demás tienen más probabilidades de ser perdedores y mostrar 0%.

* **[!UICONTROL Asignación automática]** empieza a mostrar confianza solo después de que la experiencia ganadora recopile un 60% de confianza. Estos niveles de confianza suelen aparecer en aproximadamente la mitad del tiempo que tardaría una prueba A/B normal en completarse (aunque este lapso de tiempo no está garantizado). Para determinar cuánto tiempo tarda en ejecutarse una prueba A/B normal, use la [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): escriba la tasa de conversión del control en &quot;Tasa de conversión de línea de base&quot;, &quot;5%&quot; para &quot;Alza&quot; y &quot;95%&quot; para &quot;Confianza&quot;. Normalmente, la confianza comienza a mostrarse después de que cada experiencia haya acumulado al menos el 50 % de las muestras requeridas por experiencia. Esto le da una idea de cuándo empieza a aparecer la confianza.

* Si el informe muestra el 0 % en todos los casos, es probable que sea demasiado pronto en la actividad.

+++

+++ ¿Están disponibles los distintivos &quot;Sin ganador&quot;, &quot;Ganador&quot; y &quot;estrella&quot; para las actividades [!UICONTROL Asignación automática] que usan [!UICONTROL Analytics] como fuente de informes (A4T)?

Los distintivos &quot;Ningún ganador aún&quot; y &quot;Ganador&quot; aparecen en la ventana emergente de información de la actividad en la lista **[!UICONTROL Actividades]**. No aparecen en el panel **[!UICONTROL A4T]** de [!DNL Analysis Workspace] ni cuando ve el mismo informe en [!DNL Target]. Si un informe de [!DNL Target] de una actividad de A4T **[!UICONTROL Asignación automática]** muestra un distintivo de &quot;estrella&quot; ganadora, ignórelo.

Para obtener más información sobre esta y otras limitaciones y notas, consulte [Asignación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) en *Compatibilidad de A4T con [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades*.

+++
