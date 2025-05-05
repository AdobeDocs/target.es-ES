---
keywords: asignación de tráfico automatizada;segmentación;aumentar recuento y mantener al usuario en la actividad;asignación de tráfico;asignación automática;asignación automática
description: Aprenda a utilizar una actividad [!UICONTROL Auto-Allocate] en  [!DNL Adobe Target] que identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico.
title: ¿Qué es una actividad de [!UICONTROL Auto-Allocate]?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3502'
ht-degree: 35%

---

# Resumen de [!UICONTROL Auto-Allocate]

Una actividad [!UICONTROL Auto-Allocate] en [!DNL Adobe Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.

Mientras [crea una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) mediante el flujo de trabajo guiado de tres pasos, elija la opción **[!UICONTROL Auto-Allocate to best experience]** en la página **[!UICONTROL Targeting]** (paso 2).

## El reto {#section_85D5A03637204BACA75E19646162ACFF}

Las pruebas A/B estándar tienen un coste inherente. Debe invertir tráfico para medir el rendimiento de cada experiencia y utilizar el análisis para determinar la experiencia ganadora. La distribución del tráfico sigue siendo fija incluso después de reconocer que el rendimiento de algunas experiencias supera al de otras. Además, es complicado determinar el tamaño de la muestra, y la actividad debe haber finalizado para poder tomar medidas con la mejor experiencia. Y, todavía hay una posibilidad de que el ganador identificado no sea un verdadero ganador.

## La solución: [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

Una actividad de [!UICONTROL Auto-Allocate] reduce el costo y los gastos generales de determinar una experiencia ganadora. [!UICONTROL Auto-Allocate] supervisa el rendimiento de la métrica de objetivos de todas las experiencias y envía proporcionalmente a más visitantes nuevos a las experiencias de alto rendimiento. Se reserva bastante tráfico para explorar el resto de las experiencias. Las ventajas de la prueba se pueden observar en los resultados, incluso con la actividad aún en curso: la optimización se produce en paralelo al aprendizaje.

[!UICONTROL Auto-Allocate] mueve a los visitantes hacia experiencias ganadoras de forma gradual, en lugar de requerir que espere hasta que termine una actividad para determinar un ganador. Saca provecho del alza más rápidamente porque a los visitantes de la actividad a los que se ha enviado a experiencias con peor rendimiento se les muestran experiencias que potencialmente son las ganadoras.

Una prueba A/B normal en [!DNL Target] muestra solamente comparaciones por pares de aspirantes con el control. Por ejemplo, si una actividad tiene experiencias A, B, C y D, donde A es el control, una prueba A/B [!DNL Target] normal compararía A contra B, A contra C y A contra D.

En estas pruebas, la mayoría de los productos, incluido [!DNL Target], usan una prueba T de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para generar confianza basada en el valor p. Este valor de confianza se utiliza para determinar si el aspirante es lo suficientemente distinto del elemento de control. Sin embargo, [!DNL Target] no realiza automáticamente las comparaciones implícitas (B con C, B con D y C con D) necesarias para encontrar la &quot;mejor&quot; experiencia. Por tanto, el experto en marketing debe analizar manualmente los resultados para determinar cuál es esta “mejor” experiencia.

[!UICONTROL Auto-Allocate] realiza todas las comparaciones implícitas entre experiencias y produce un ganador &quot;verdadero&quot;. No existe ninguna experiencia de “control” en la prueba.

[!UICONTROL Auto-Allocate] asigna de forma inteligente nuevos visitantes a las experiencias hasta que el intervalo de confianza de la mejor experiencia no se superponga con el intervalo de confianza de ninguna otra experiencia. Normalmente, este proceso podría producir falsos positivos, pero [!UICONTROL Auto-Allocate] usa intervalos de confianza basados en la desigualdad de [Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank} que compensa las evaluaciones repetidas. En este punto, hay un verdadero ganador. Cuando [!UICONTROL Auto-Allocate] se detiene, siempre que no exista una dependencia del tiempo sustancial para los visitantes que llegan a la página, hay al menos un 95 % de probabilidades de que [!UICONTROL Auto-Allocate] devuelva una experiencia cuya respuesta verdadera no sea peor que un 1 % (relativo) menor que la respuesta verdadera de la experiencia ganadora.

## Cuándo usar [!UICONTROL Auto-Allocate] frente a [!UICONTROL A/B Test] o [!UICONTROL Automated Personalization] actividades {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Use **[!UICONTROL Auto-Allocate]** cuando quiera optimizar su actividad desde el principio e identificar las experiencias ganadoras lo más rápido posible. Al ofrecer experiencias de alto rendimiento con mayor frecuencia, se aumenta el rendimiento general de la actividad.
* Use una **[Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** estándar cuando quiera caracterizar el rendimiento de todas las experiencias antes de optimizar el sitio. Una prueba A/B le ayuda a clasificar todas sus experiencias, mientras que [!UICONTROL Auto-Allocate] encuentra los mejores ejecutantes, pero no garantiza la diferenciación entre los de menor rendimiento.
* Use [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) cuando quiera algoritmos de optimización de la mayor complejidad, como modelos de aprendizaje automático que generen predicciones basadas en atributos de perfil individuales. [!UICONTROL Auto-Allocate] observa el comportamiento agregado de las experiencias (como las pruebas A/B estándar) y no diferencia entre visitantes.

## Ventajas principales de [!UICONTROL Auto-Allocate] {#section_0913BF06F73C4794862561388BBDDFF0}

* Tiene el mismo rigor que una prueba A/B
* Encuentra una experiencia ganadora con relevancia estadística más rápido que una prueba A/B manual
* Proporciona un alza de la campaña de media superior a la de una prueba A/B manual

## Terminología   {#section_670F8785BA894745B43B6D4BFF953188}

Los siguientes términos pueden resultar útiles al tratar el tema de [!UICONTROL Auto-Allocate]:

**Bandido multibrazo:** Un método de [bandido multibrazo](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} para la optimización equilibra el aprendizaje exploratorio con la explotación de ese aprendizaje.

## Funcionamiento del algoritmo {#section_ADB69A1C7352462D98849F2918D4FF7B}

La lógica general detrás de [!UICONTROL Auto-Allocate] incorpora tanto el rendimiento medido (como la tasa de conversión) como los intervalos de confianza de los datos acumulados. A diferencia de una prueba A/B estándar en la que el tráfico se divide a partes iguales entre experiencias, [!UICONTROL Auto-Allocate] cambia la asignación del tráfico entre experiencias.

* El 80 % de los visitantes se asignan mediante la lógica inteligente que se describe a continuación.
* El 20 % de los visitantes se asigna de forma aleatoria entre todas las experiencias para adaptarse a los cambios en el comportamiento de los visitantes.

El método multi-armed bandit mantiene libres algunas experiencias para la exploración a la vez que explota las experiencias con buen rendimiento. Se colocan más visitantes nuevos en experiencias con buen rendimiento, mientras que se reserva la capacidad de reaccionar a condiciones cambiantes. Estos modelos se actualizan por lo menos una vez cada hora para garantizar que el modelo reaccione a los datos más recientes.

A medida que entran más visitantes a la actividad, algunas experiencias empiezan a mejorar el rendimiento y se envía más tráfico hacia esas experiencias con buenos resultados. El 20 % del tráfico se sigue ofreciendo de forma aleatoria para explorar todas las experiencias. Si una de las experiencias de bajo rendimiento empieza a mejorar su rendimiento, se le asignará más tráfico. Del mismo modo, si disminuye el éxito de una actividad de alto rendimiento, se le asignará menos tráfico a dicha experiencia. Por ejemplo, si un evento provoca que los visitantes busquen información diferente en su sitio web multimedia o si las ventas del fin de semana de su sitio de comercio minorista proporcionan diferentes resultados.

La siguiente ilustración representa el rendimiento que podría tener el algoritmo durante una prueba con cuatro experiencias (haga clic para expandir la ilustración):

![asignar automáticamente la imagen](assets/auto-allocate.png){width="600" zoomable="yes"}

La ilustración muestra cómo progresa el tráfico asignado a cada experiencia durante varias rondas de la duración de una actividad hasta que se determina un claro ganador.

| Ronda | Descripción |
|--- |--- |
| ![Ronda de calentamiento](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Ronda de calentamiento (0):** durante la ronda de calentamiento, cada experiencia obtiene la misma asignación de tráfico hasta que cada experiencia de la actividad tenga un mínimo de 1000 visitantes y 50 conversiones.<ul><li>Experiencia A = 25 %</li><li>Experiencia B = 25 %</li><li>Experiencia C = 25 %</li><li>Experiencia D = 25 %</li></ul>Una vez que cada experiencia logra 1000 visitantes y 50 conversiones, [!DNL Target] inicia la asignación automática del tráfico. Todas las asignaciones tienen lugar por rondas y se eligen dos experiencias para cada ronda.<br>Solo dos experiencias pasan a la siguiente ronda: D y C.<br>Al pasar a la siguiente ronda, se asignará a ambas experiencias un 80% del tráfico de forma equitativa. Las otras dos experiencias siguen participando, pero solo forman parte de la asignación aleatoria del tráfico del 20 % a medida que los nuevos visitantes entran en la actividad.<br>Todas las asignaciones se actualizan cada hora (tal y como se muestra por rondas en el eje X anterior). Después de cada ronda, se comparan los datos acumulados. |
| ![Ronda 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **Ronda 1**: durante esta ronda, el 80 % del tráfico se asigna a las experiencias C y D (un 40 % a cada una). El 20 % del tráfico se asigna aleatoriamente a las experiencias A, B, C y D (un 5 % a cada una). Durante esta ronda, la experiencia A presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia A también supera esta primera prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias D y A pasan a la siguiente ronda. |
| ![Ronda 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **Ronda 2**: durante esta ronda, el 80 % del tráfico se asigna a las experiencias A y D (un 40 % a cada una). El 20 % del tráfico se asigna aleatoriamente, de modo que A, B, C y D reciben, respectivamente, un 5 % del tráfico. Durante esta ronda, la experiencia B presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia B también supera esta segunda prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias D y B pasan a la siguiente ronda. |
| ![Ronda 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **Ronda 3**: durante esta ronda, el 80 % del tráfico se asigna a las experiencias B y D (un 40 % a cada una). El 20 % del tráfico se asigna aleatoriamente, de modo que A, B, C y D reciben, respectivamente, un 5 % del tráfico. Durante esta ronda, la experiencia D sigue teniendo un buen rendimiento y la experiencia C también logra buenos resultados.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia C también pasa a la siguiente ronda porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein de las experiencias restantes.</li></ul>Las experiencias D y C pasan a la siguiente ronda. |
| ![Ronda 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **Ronda 4**: durante esta ronda, el 80 % del tráfico se asigna a las experiencias C y D (un 40 % a cada una). El 20 % del tráfico se asigna aleatoriamente, de modo que A, B, C y D reciben, respectivamente, un 5 % del tráfico. Durante esta ronda, la experiencia C presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia C pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia D también supera esta cuarta prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias C y D pasan a la siguiente ronda. |
| ![Ronda n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **Ronda *n***: a medida que progresa la actividad, una experiencia de alto rendimiento comienza a emerger y el proceso continúa hasta que haya una experiencia ganadora. Cuando el intervalo de confianza de la experiencia con la tasa de conversión más alta no se superpone con el intervalo de confianza de ninguna otra experiencia, se etiqueta como ganador. Aparece un distintivo [en la página de la actividad ganadora](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) y en la lista [!UICONTROL Activity].<ul><li>El algoritmo decide que la experiencia C es la clara ganadora.</li></ul>En este punto, el algoritmo otorga el 80 % del tráfico a la experiencia C, mientras que el 20 % del tráfico se sigue ofreciendo aleatoriamente a todas las experiencias (A, B, C y D). En total, C recibe el 85 % del tráfico. En el improbable caso de que el intervalo de confianza del ganador empiece a superponerse de nuevo, el algoritmo restablece el comportamiento de la ronda 4.<P>**Importante**: Si elige un ganador de forma manual antes de que finalice el proceso, habría sido fácil elegir la experiencia incorrecta. Por ese motivo, lo más recomendable es esperar a que el algoritmo determine cuál es la experiencia ganadora. |

>[!NOTE]
>
>Si una actividad solo tiene dos experiencias, ambas recibirán el mismo tráfico hasta que [!DNL Target] encuentre una experiencia ganadora con un 75 % de confianza. En ese momento, dos tercios del tráfico se asignan al ganador y un tercio al perdedor. Después, cuando una experiencia alcanza el 95 % de confianza, el 90 % del tráfico se asigna al ganador y el 10 % al perdedor. [!DNL Target] siempre envía tráfico a la experiencia de &quot;pérdida&quot; para evitar falsos positivos al final (es decir, mantener cierta exploración).

Después de activar una actividad [!UICONTROL Auto-Allocate], no se permiten las siguientes operaciones desde la interfaz de usuario de Target:

* Cambiar el modo “Asignación del tráfico” a “Manual”
* Cambiar el tipo de la métrica de objetivo
* Cambiando opciones en el panel &quot;[!UICONTROL Advanced Settings]&quot;

## Ver cómo funciona la asignación automática

Para obtener más información, vea [La asignación automática puede proporcionar resultados de prueba con mayor rapidez, así como mayores ingresos que una prueba manual](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Advertencias  {#section_5C83F89F85C14FD181930AA420435E1D}

Tenga en cuenta la siguiente información cuando trabaje con [!UICONTROL Auto-Allocate]:

### La característica [!UICONTROL Auto-Allocate] solo funciona con una configuración de métrica avanzada: [!UICONTROL Increment Count and Keep User in Activity]

No se admiten las siguientes configuraciones de métricas avanzadas: [!UICONTROL Increment Count], [!UICONTROL Release User], [!UICONTROL Allow Reentry and Increment Count] y [!UICONTROL Release User and Bar from Reentry].

### Los visitantes asiduos pueden inflar las tasas de conversión de la experiencia.

Si un visitante que ve la experiencia A vuelve a menudo y genera varias conversiones, la tasa de conversión de la experiencia A se incrementa de forma artificial. Compare este resultado con la experiencia B, en la que los visitantes realizan conversiones, pero no regresan con frecuencia. Como resultado, la RC de la experiencia A se ve mejor que la RC de la experiencia B, por lo que es más probable que los nuevos visitantes se asignen a A que a B. Si elige contar una vez por participante, el CR de A y el CR de B podrían ser idénticos.

Si los visitantes que vuelven se distribuyen de forma aleatoria, es más probable que se equilibre su impacto en las tasas de conversión. Para mitigar este impacto, plantéese la opción de cambiar el método de recuento de la métrica de objetivos para que solo contabilice una vez por cada visitante.

### Diferencia entre los de alto rendimiento, no entre los de bajo rendimiento.

[!UICONTROL Auto-Allocate] es buena para diferenciar entre experiencias de alto rendimiento (y encontrar un ganador). Puede que en ocasiones no haya suficiente diferencia entre las experiencias con rendimiento bajo.

Si desea producir una diferenciación estadísticamente significativa entre todas las experiencias, le recomendamos considerar el uso del modo de asignación de tráfico manual.

### Las tasas de conversión correlacionadas con el tiempo (o que varían según el contexto) pueden inclinar las cantidades de asignación.

Algunos factores que se pueden ignorar durante una prueba A/B estándar porque afectan a todas las experiencias por igual no se pueden ignorar en una actividad [!UICONTROL Auto-Allocate]. El algoritmo es sensible a las tasas de conversión observadas.

A continuación tiene algunos ejemplos de factores que pueden afectar al rendimiento de la experiencia de forma desigual:

* Experiencias con relevancia contextual variable (tiempo, ubicación, sexo, etc.).

  Por ejemplo:

   * &quot;Menos mal que es viernes&quot; genera más conversiones los viernes.
   * &quot;Empieza el lunes con energía&quot; obtiene más conversiones los lunes.
   * &quot;Prepárese para un invierno en la costa este&quot; proporciona una mayor conversión en ubicaciones de la costa este o afectadas por el invierno.

  El uso de experiencias con relevancia contextual variable puede distorsionar más los resultados de una prueba [!UICONTROL Auto-Allocate] que de una prueba A/B, ya que esta analiza los resultados a lo largo de un período más largo.

* Experiencias con diferentes retrasos en la conversión, posiblemente debidos a la urgencia del mensaje.

  Por ejemplo, el mensaje “El descuento del 30% acaba hoy” señala al visitante que debe generar hoy la conversión, mientras que “Descuento del 50% en la primera compra” no crea la misma sensación de urgencia.

## Preguntas frecuentes {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Consulte las siguientes preguntas frecuentes y respuestas mientras trabaja con [!UICONTROL Auto-Allocate] actividades:

### ¿Admite [!UICONTROL Analytics for Target] (A4T) actividades [!UICONTROL Auto-Allocate]?

Sí. Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### ¿Los visitantes de retorno se asignan automáticamente a experiencias de alto rendimiento?

No. Solo se asigna automáticamente a los visitantes nuevos. Los visitantes que regresan siguen viendo su experiencia original para proteger la validez de la prueba A/B.

### ¿Cómo trata el algoritmo los falsos positivos?

El algoritmo garantiza una tasa de confianza del 95 % o una tasa de falso positivo del 5 % si espera hasta que aparezca el distintivo de ganador.

### ¿Cuándo empieza a asignar tráfico [!UICONTROL Auto-Allocate]?

El algoritmo empieza a funcionar cuando todas las experiencias de la actividad tienen un mínimo de 1000 visitantes y 50 conversiones.

### ¿Con qué agresividad explota el algoritmo?

El 80% del tráfico se sirve usando [!UICONTROL Auto-Allocate] y el 20% del tráfico se sirve aleatoriamente. Cuando se identifica un ganador, se le destina el 80 % del tráfico, mientras que todas las experiencias siguen recibiendo tráfico como parte del 20 %, incluida la experiencia ganadora.

### ¿Se muestran las experiencias perdedoras?

Sí. El método multi-armed bandit garantiza que al menos el 20 % del tráfico se reserva para explorar las tasas de conversión o los patrones cambiantes en todas las experiencias.

### ¿Qué sucede con las actividades con retrasos de conversión largos?

Siempre que todas las experiencias que se vayan a optimizar sufran los mismos retrasos, el comportamiento será igual al de una actividad con un ciclo de conversión más rápido. Sin embargo, se tarda más en alcanzar el umbral de conversión 50 antes de que comience el proceso de asignación de tráfico.

### ¿En qué se diferencia [!UICONTROL Auto-Allocate] de [!UICONTROL Automated Personalization]?

[!UICONTROL Automated Personalization] utiliza los atributos de perfil de cada visitante para determinar la mejor experiencia. Con esto, no solo se optimiza la actividad del usuario, sino que se personaliza.

[!UICONTROL Auto-Allocate], por otro lado, es una prueba A/B que produce un ganador agregado (la experiencia más popular, pero no necesariamente la experiencia más efectiva para cada visitante).

### ¿Los visitantes de retorno inflan la tasa de conversión en mi métrica de éxito?

Actualmente, la lógica favorece a los visitantes que realizan la conversión rápidamente o visitan con más frecuencia porque inflan temporalmente la tasa de conversión general de la experiencia a la que pertenecen. El algoritmo se ajusta a menudo, de modo que el aumento en la tasa de conversión se amplifica en cada instantánea. Si el sitio recibe numerosos visitantes de retorno, sus conversiones pueden aumentar potencialmente la tasa de conversión general de la experiencia a la que pertenecen. Hay probabilidades de que los visitantes que vuelven se distribuyan de forma aleatoria. En ese caso, el efecto agregado (alza incrementada) se equilibra. Para mitigar este impacto, plantéese la opción de cambiar el método de recuento de la métrica de éxito para que solo contabilice una vez por cada visitante.

### ¿Puedo usar la calculadora de tamaño de la muestra al usar [!UICONTROL Auto-Allocate] para estimar el tiempo que tarda la actividad en identificar al ganador?

Puede usar la [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) existente para obtener una estimación de cuánto tiempo se ejecuta la prueba. (Al igual que con las pruebas A/B tradicionales, aplique la corrección de Bonferroni si está probando más de dos ofertas o más de una métrica/hipótesis de conversión). Esta calculadora está diseñada para pruebas A/B tradicionales de horizonte fijo y proporciona solo una estimación. El uso de la calculadora para una actividad [!UICONTROL Auto-Allocate] es opcional porque [!UICONTROL Auto-Allocate] declara un ganador en su lugar. No es necesario que elija un punto fijo en el tiempo para ver los resultados de la prueba. Los valores proporcionados siempre son estadísticamente válidos.

Los experimentos internos [!DNL Adobe] han encontrado lo siguiente:

* Al probar exactamente dos experiencias, [!UICONTROL Auto-Allocate] encuentra un ganador con mayor rapidez que las pruebas de horizonte fijo (es decir, el lapso de tiempo sugerido por la calculadora de tamaño de muestra) cuando la diferencia de rendimiento entre experiencias es grande. Sin embargo, [!UICONTROL Auto-Allocate] podría requerir tiempo adicional para identificar a un ganador cuando la diferencia de rendimiento entre experiencias sea pequeña. En estos casos, las pruebas de horizonte fijo normalmente habrían finalizado sin un resultado estadísticamente significativo.
* Al probar más de dos experiencias, [!UICONTROL Auto-Allocate] encuentra un ganador con mayor rapidez que las pruebas de horizonte fijo (es decir, el lapso de tiempo sugerido por la calculadora de tamaño de muestra) cuando una sola experiencia supera con creces al resto de las experiencias. Cuando dos o más experiencias están &quot;ganando&quot; en comparación con otras experiencias pero están estrechamente relacionadas entre sí, [!UICONTROL Auto-Allocate] podría requerir tiempo adicional para determinar cuál es superior. En estos casos, las pruebas de horizonte fijo normalmente habrían finalizado concluyendo que las experiencias &quot;ganadoras&quot; eran mejores que las de menor rendimiento, pero no habían identificado cuál era mejor.

### ¿Debo eliminar una experiencia con bajo rendimiento de una actividad [!UICONTROL Auto-Allocate] para acelerar el proceso de determinar un ganador?

En realidad, no hay razón para eliminar una experiencia de bajo rendimiento. [!UICONTROL Auto-Allocate] proporciona automáticamente experiencias de alto rendimiento con mayor frecuencia y de bajo rendimiento con menor frecuencia. Dejar una experiencia con bajo rendimiento en la actividad no afecta de manera significativa a la velocidad para determinar un ganador.

El 20 % de los visitantes se asigna de forma aleatoria entre todas las experiencias. La cantidad de tráfico proporcionado en una experiencia de bajo rendimiento es mínima (20 % dividido entre el número de experiencias).

### ¿Puedo cambiar la métrica de objetivo a mitad de camino a través de una actividad [!UICONTROL Auto-Allocate]? {#change-metric}

[!DNL Adobe] no recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad mediante la IU de [!DNL Target], siempre debe iniciar una nueva actividad. [!DNL Adobe] no garantiza lo que sucederá si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] que usan [!DNL Target] o [!DNL Analytics] (A4T) como origen de informes.

### ¿Puedo cambiar la fuente de informes a mitad de camino a través de una actividad [!UICONTROL Auto-Allocate]? {#change-reporting}

[!DNL Adobe] no recomienda cambiar el origen de los informes a mitad de una actividad. Aunque es posible cambiar la fuente de informes (de [!DNL Target] a A4T o viceversa) durante una actividad mediante la interfaz de usuario de [!DNL Target], siempre debe iniciar una nueva actividad. [!DNL Adobe] no garantiza lo que suceda si cambia el origen de los informes en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] que usan [!DNL Target] o [!DNL Analytics] (A4T) como origen de informes.

### ¿Puedo usar la opción [!UICONTROL Reset Report Data] mientras ejecuto una actividad [!UICONTROL Auto-Allocate]?

No se recomienda usar la opción [!UICONTROL Reset Report Data] para las actividades [!UICONTROL Auto-Allocate]. Aunque quita los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo [!UICONTROL Auto-Allocate]. En lugar de usar la opción [!UICONTROL Reset Report Data] para [!UICONTROL Auto-Allocate] actividades, cree una nueva actividad y desactive la actividad original. (Esta guía también se aplica a las actividades [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization].)

### ¿Cómo genera modelos [!UICONTROL Auto-Allocate] con respecto a los entornos?

[!UICONTROL Auto-Allocate] crea modelos basados en el comportamiento de tráfico y conversión registrado solamente en el entorno predeterminado. De manera predeterminada, [!UICONTROL Production] es el entorno predeterminado, pero el entorno predeterminado se puede cambiar en [!DNL Target] ([Administración > Entornos](/help/main/administrating-target/environments.md)).

Si se produce una visita en otro entorno (no predeterminado), el tráfico se distribuye según el comportamiento de conversión observado en el entorno predeterminado. El resultado de esa visita (conversión o no conversión) se registra con fines de generación de informes, pero no se tiene en cuenta en el modelo [!UICONTROL Auto-Allocate].

Al seleccionar otro entorno, el informe muestra el tráfico y las conversiones de ese entorno. El entorno seleccionado de forma predeterminada para un informe es el predeterminado de toda la cuenta que está seleccionado. El entorno predeterminado no se puede establecer por actividad.

### ¿Puede una actividad de [!UICONTROL Auto-Allocate] ajustar la ventana retrospectiva a lo largo de una prueba para tener en cuenta los cambios en las tendencias a lo largo del tiempo?

Por ejemplo, ¿puede la actividad considerar el mes de diciembre para decidir cómo asignar el tráfico en lugar de consultar los datos de visitantes de septiembre (cuando comenzó la prueba)?

No, [!UICONTROL Auto-Allocate] considera el rendimiento de toda la actividad.

### ¿Muestra [!UICONTROL Auto-Allocate] una experiencia ganadora a un visitante que regresa si la experiencia ganadora es diferente de lo que vio el visitante al calificar para la actividad?

[!UICONTROL Auto-Allocate] utiliza la toma de decisiones fija por las mismas razones por las que las actividades de [!UICONTROL A/B Test] son fijas. La asignación de tráfico solo funciona para visitantes nuevos.

## Vídeos de formación {#section_893E5B36DC4A415C9B1D287F51FCCB83}

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Flujo de trabajo de actividad - Segmentación (2:14) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre cómo configurar la asignación de tráfico.

* Asignar una audiencia a la actividad
* Acelerar o desacelerar el tráfico
* Seleccionar el método de asignación de tráfico
* Asignar tráfico entre distintas experiencias

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Creación de pruebas A/B (8:36) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de Target. Se habla sobre [!UICONTROL Auto-Allocate] a partir del minuto 4:45.

* Crear una actividad A/B en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/30133?captions=spa)
