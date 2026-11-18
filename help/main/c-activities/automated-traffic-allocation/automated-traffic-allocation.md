---
keywords: asignación de tráfico automatizada;segmentación;aumentar recuento y mantener al usuario en la actividad;asignación de tráfico;asignación automática;asignación automática
description: Aprenda a usar una actividad [!UICONTROL Asignación automática] en [!DNL Adobe Target] que identifique un ganador entre dos o más experiencias y le reasigne automáticamente más tráfico.
title: ¿Qué es una actividad de [!UICONTROL asignación automática]?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
TQID: 'https://experienceleague.adobe.com/V5ZS2vBGVilH0-4bacB4x7iQi8M6qroLe3R9LNMoVEc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
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
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '3662'
ht-degree: 16%
---
# Introducción a [!UICONTROL Asignación automática] {#auto-allocate-overview}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo una actividad de **[!UICONTROL Asignación automática]** identifica una experiencia ganadora y le reasigna tráfico, cuándo utilizarla, cómo funciona el algoritmo y qué considerar antes de utilizarla.

>[!ENDSHADEBOX]

Una actividad **[!UICONTROL Asignación automática]** en [!DNL Adobe Target] identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.

Crea una actividad **[!UICONTROL Asignación automática]** con el flujo de trabajo guiado de tres pasos de una actividad A/B: elija la opción **[!UICONTROL Asignación automática a la mejor experiencia]** en la página **[!UICONTROL Segmentación]** (paso 2). Para ver los pasos, consulte [Crear una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md).

## Por qué usar [!UICONTROL Asignación automática] {#why-auto-allocate}

Las pruebas A/B estándar tienen un coste inherente. Debe gastar tráfico para medir el rendimiento de cada experiencia, y la distribución del tráfico permanece fija incluso después de que algunas experiencias superen a otras. El tamaño de la muestra es complicado de determinar, la actividad debe ejecutar todo su curso antes de poder actuar sobre un ganador y aún existe la posibilidad de que el ganador identificado no sea un verdadero ganador.

Una actividad **[!UICONTROL de asignación automática]** reduce este costo y estos gastos generales:

* Monitoriza el rendimiento de la métrica de objetivos de todas las experiencias y envía proporcionalmente a más participantes nuevos a las experiencias de alto rendimiento. Se reserva bastante tráfico para explorar el resto de las experiencias.
* La optimización se produce en paralelo con el aprendizaje, por lo que puede ver las ventajas en los resultados mientras la actividad sigue ejecutándose.
* Los visitantes avanzan gradualmente hacia las experiencias ganadoras, por lo que no es necesario esperar hasta que finalice la actividad. Saca provecho del alza más rápidamente porque a los visitantes de la actividad a los que se ha enviado a experiencias con peor rendimiento se les muestran experiencias que potencialmente son las mejores.

Ventajas principales:

* Conserva el rigor de una prueba A/B.
* Encuentra un ganador estadísticamente significativo más rápido que una prueba A/B manual.
* Proporciona un alza de campaña promedio mayor que una prueba A/B manual.

### Cómo [!UICONTROL Asignación automática] identifica a un ganador {#true-winner}

Una prueba A/B normal de [!DNL Target] compara cada aspirante únicamente con el control. Por ejemplo, si una actividad tiene experiencias A, B, C y D, donde A es el control, la prueba compara A con B, A con C y A con D. La mayoría de los productos, entre ellos [!DNL Target], usan una prueba T de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para estas comparaciones a fin de generar confianza basada en el valor p. Sin embargo, [!DNL Target] no realiza automáticamente las comparaciones implícitas (B con C, B con D y C con D) necesarias para encontrar la &quot;mejor&quot; experiencia, por lo que debe analizar los resultados manualmente.

**[!UICONTROL Asignación automática]** elimina este paso manual:

* Realiza comparaciones implícitas entre todas las experiencias y produce una ganadora “real”. No existe ninguna experiencia de “control” en la prueba.
* Asigna nuevos visitantes a las experiencias hasta que el intervalo de confianza de la mejor experiencia no se superponga con el intervalo de confianza de ninguna otra experiencia.
* Utiliza intervalos de confianza basados en la desigualdad de [Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank}, que compensa las evaluaciones repetidas que normalmente producirían falsos positivos.
* Cuando se detiene, siempre que no exista una dependencia del tiempo sustancial para los visitantes que llegan a la página, hay al menos un 95 % de probabilidades de que devuelva una experiencia cuya respuesta verdadera no sea peor que un 1 % (relativo) menos que la respuesta verdadera de la experiencia ganadora.

## Cuándo usar [!UICONTROL Asignación automática] {#when-to-use}

Elija entre las actividades **[!UICONTROL Asignación automática]**, **[!UICONTROL Prueba A/B]** y **[!UICONTROL Automated Personalization]** según su objetivo:

| Actividad | Úselo cuando | En qué se diferencia |
|---|---|---|
| **[!UICONTROL Asignación automática]** | Desea optimizar su actividad desde el principio e identificar las experiencias ganadoras lo antes posible. | Al ofrecer experiencias de alto rendimiento con mayor frecuencia, se aumenta el rendimiento general de la actividad. |
| [**[!UICONTROL Prueba A/B]**](/help/main/c-activities/t-test-ab/test-ab.md#test-ab) | Desea caracterizar el rendimiento de todas las experiencias antes de optimizar el sitio. | Una prueba A/B le ayuda a clasificar todas sus experiencias, mientras que **[!UICONTROL Asignación automática]** encuentra los mejores ejecutantes, pero no garantiza la diferenciación entre los de menor rendimiento. |
| [**[!UICONTROL Personalización automatizada]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) | Desea algoritmos de optimización de la mayor complejidad, como modelos de aprendizaje automático que creen predicciones basadas en atributos de perfil individuales. | **[!UICONTROL Asignación automática]** observa el comportamiento agregado de las experiencias (como las pruebas A/B estándar) y no diferencia entre visitantes. |

## Funcionamiento del algoritmo {#how-it-works}

El algoritmo de **[!UICONTROL Asignación automática]** es un método de optimización [multi-armed bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank}, que equilibra el aprendizaje exploratorio y la explotación de ese aprendizaje. Incorpora tanto el rendimiento medido (como la tasa de conversión) como los intervalos de confianza de los datos acumulados. A diferencia de una prueba A/B estándar, en la que el tráfico se divide a partes iguales entre experiencias, **[!UICONTROL Asignación automática]** cambia la asignación del tráfico entre experiencias:

* El 80 % de los visitantes se asignan según la lógica descrita en esta sección.
* El 20 % de los visitantes se asigna de forma aleatoria entre todas las experiencias para adaptarse a los cambios en el comportamiento de los visitantes.

El método multi-armed bandit mantiene un poco de tráfico libre para la exploración, mientras que explota las experiencias que tienen un buen rendimiento. Cada vez más visitantes nuevos obtienen mejores resultados, al tiempo que se preserva la capacidad de reacción ante condiciones cambiantes. Los modelos se actualizan al menos una vez cada hora para garantizar que reaccionan a los datos más recientes.

A medida que ingresan más visitantes a la actividad, algunas experiencias se vuelven más exitosas y reciben más tráfico. El 20 % del tráfico se sigue ofreciendo de forma aleatoria para explorar todas las experiencias. Si una de las experiencias de bajo rendimiento empieza a mejorar su rendimiento, se le asignará más tráfico. Si se reduce el éxito de una experiencia de mayor rendimiento, se le asigna menos tráfico. Esto puede ocurrir, por ejemplo, cuando un evento hace que los visitantes busquen información diferente en el sitio multimedia o cuando las ventas de fin de semana en el sitio minorista ofrecen resultados diferentes.

La siguiente ilustración representa el rendimiento que podría tener el algoritmo durante una prueba con cuatro experiencias (haga clic para expandir la ilustración):

![asignar automáticamente la imagen](assets/auto-allocate.png){width="600" zoomable="yes"}

La ilustración muestra cómo progresa el tráfico asignado a cada experiencia durante varias rondas de la duración de una actividad hasta que se determina un claro ganador.

| Ronda | Descripción |
|--- |--- |
| ![Ronda de calentamiento](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Ronda de calentamiento (0)**: Cada experiencia obtiene el mismo tráfico hasta que cada experiencia de la actividad tenga un mínimo de 1000 visitantes y 50 conversiones.<ul><li>Experiencia A = 25 %</li><li>Experiencia B = 25 %</li><li>Experiencia C = 25 %</li><li>Experiencia D = 25 %</li></ul>Una vez que cada experiencia alcanza los 1000 visitantes y las 50 conversiones, [!DNL Target] inicia la asignación de tráfico automatizada. Todas las asignaciones se realizan en rondas y se seleccionan dos experiencias para cada ronda. Solo dos experiencias pasan a la siguiente ronda: D y C.<ul><li>Avanzar significa que a las dos experiencias se les asigna el 80 % del tráfico de forma equitativa.</li><li>Las otras dos experiencias siguen participando, pero se sirven solo como parte de la asignación aleatoria del 20 % del tráfico cuando entran nuevos visitantes en la actividad.</li><li>Todas las asignaciones se actualizan cada hora (tal y como muestran los redondeos del eje x anterior). Después de cada ronda, se comparan los datos acumulados.</li></ul> |
| ![Ronda 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **Ronda 1**: el 80% del tráfico se asigna a las experiencias C y D (un 40% a cada una). El 20 % del tráfico se asigna aleatoriamente a las experiencias A, B, C y D (un 5 % a cada una). Durante esta ronda, la experiencia A presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia A también supera esta primera prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias D y A pasan a la siguiente ronda. |
| ![Ronda 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **Ronda 2**: el 80% del tráfico se asigna a las experiencias A y D (un 40% a cada una). El 20 % del tráfico se asigna de forma aleatoria, por lo que las experiencias A, B, C y D obtienen cada una el 5 % del tráfico. Durante esta ronda, la experiencia B presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia B también supera esta segunda prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias D y B pasan a la siguiente ronda. |
| ![Ronda 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **Ronda 3**: el 80% del tráfico se asigna a las experiencias B y D (un 40% a cada una). El 20 % del tráfico se asigna de forma aleatoria, por lo que las experiencias A, B, C y D obtienen cada una el 5 % del tráfico. Durante esta ronda, la experiencia D sigue teniendo un buen rendimiento y la experiencia C también logra buenos resultados.<ul><li>El algoritmo decide que la experiencia D pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia C también pasa a la siguiente ronda porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein de las experiencias restantes.</li></ul>Las experiencias D y C pasan a la siguiente ronda. |
| ![Ronda 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **Ronda 4**: el 80% del tráfico se asigna a las experiencias C y D (un 40% a cada una). El 20 % del tráfico se asigna de forma aleatoria, por lo que las experiencias A, B, C y D obtienen cada una el 5 % del tráfico. Durante esta ronda, la experiencia C presenta un buen rendimiento.<ul><li>El algoritmo decide que la experiencia C pasa a la siguiente ronda porque tiene la tasa de conversión más alta (tal y como indica la escala vertical de cada actividad).</li><li>El algoritmo decide que la experiencia D también supera esta cuarta prueba porque tiene la cota superior más alta del intervalo de confianza del 95 % de Bernstein en comparación con las demás experiencias.</li></ul>Las experiencias C y D pasan a la siguiente ronda. |
| ![Ronda n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **Ronda *n***: a medida que progresa la actividad, una experiencia de alto rendimiento comienza a emerger y el proceso continúa hasta que haya una experiencia ganadora. Cuando el intervalo de confianza de la experiencia con la tasa de conversión más alta no se superponga con el intervalo de confianza de ninguna otra experiencia, se etiqueta el ganador. Se muestra un distintivo [en la página de la actividad ganadora](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) y en la lista**[!UICONTROL  Actividad ]**.<ul><li>El algoritmo decide que la experiencia C es la clara ganadora.</li></ul>En este punto, el algoritmo proporciona el 80 % del tráfico a la experiencia C, mientras que el 20 % del tráfico sigue proporcionándose aleatoriamente a todas las experiencias (A, B, C y D). En total, C recibe el 85 % del tráfico. En el improbable caso de que el intervalo de confianza del ganador comience a superponerse de nuevo, el algoritmo vuelve al comportamiento de la ronda 4.<br>**Importante**: Si elige un ganador de forma manual antes de que finalice el proceso, sería fácil elegir la experiencia incorrecta. Por ese motivo, lo más recomendable es esperar a que el algoritmo determine cuál es la experiencia ganadora. |

>[!NOTE]
>
>Si una actividad solo tiene dos experiencias, ambas recibirán el mismo tráfico hasta que [!DNL Target] encuentre una experiencia ganadora con un 75 % de confianza. En ese momento, dos tercios del tráfico se asignan al ganador y un tercio al perdedor. Después, cuando una experiencia alcanza el 95 % de confianza, el 90 % del tráfico se asigna al ganador y el 10 % al perdedor. [!DNL Target] siempre envía tráfico a la experiencia de &quot;pérdida&quot; para evitar falsos positivos al final (es decir, para mantener cierta exploración).

Después de activar una actividad **[!UICONTROL Asignación automática]**, no se permiten las siguientes operaciones en la interfaz de usuario de [!DNL Target]:

* Cambiando el modo **[!UICONTROL Asignación del tráfico]** a **[!UICONTROL Manual]**.
* Cambiar el tipo de métrica de objetivo.
* Cambiando opciones en el panel **[!UICONTROL Configuración avanzada]**.

Para obtener más información, vea [Cómo la asignación automática supera una prueba manual](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Advertencias {#caveats}

Tenga en cuenta la siguiente información cuando trabaje con **[!UICONTROL Asignación automática]**.

### Solo se admite una configuración de métrica avanzada

La característica **[!UICONTROL Asignación automática]** funciona con una sola configuración de métrica avanzada: **[!UICONTROL Aumentar recuento y mantener al usuario en la actividad]**. No se admiten las siguientes configuraciones de métricas avanzadas: **[!UICONTROL Recuento de incrementos]**, **[!UICONTROL Liberar usuario]**, **[!UICONTROL Permitir la reentrada y el recuento de incrementos]** y **[!UICONTROL Liberar usuario y barra de la reentrada]**.

### Los visitantes asiduos pueden inflar las tasas de conversión {#return-visitors}

Si un visitante que ve la experiencia A regresa con frecuencia y se convierte varias veces, la tasa de conversión (CR) de la experiencia A se incrementa artificialmente. Compare este resultado con la experiencia B, en la que los visitantes realizan la conversión pero no regresan con frecuencia. Como resultado, la RC de la experiencia A se ve mejor que la RC de la experiencia B, por lo que es más probable que los nuevos visitantes se asignen a A que a B. Si elige contar una vez por participante, el CR de A y el CR de B podrían ser idénticos.

La lógica favorece a los visitantes que realizan la conversión rápidamente o visitan con más frecuencia, ya que inflan temporalmente la tasa de conversión general de la experiencia a la que pertenecen. El algoritmo se ajusta a menudo, de modo que el aumento en la tasa de conversión se amplifica en cada instantánea.

Si los visitantes que vuelven se distribuyen de forma aleatoria, es más probable que se equilibre su impacto en las tasas de conversión. Para mitigar este impacto, plantéese la opción de cambiar el método de recuento de la métrica de objetivos para que solo contabilice una vez por cada visitante.

### La diferenciación es entre los de alto rendimiento, no entre los de bajo rendimiento

**[!UICONTROL Asignación automática]** es buena para diferenciar entre experiencias de alto rendimiento (y encontrar un ganador). Podría haber momentos en que no se tenga la suficiente diferenciación entre las experiencias de bajo rendimiento.

Si desea producir una diferenciación estadísticamente significativa entre todas las experiencias, considere la posibilidad de utilizar el modo de asignación de tráfico manual.

### Las tasas de conversión correlacionadas con el tiempo pueden distorsionar la asignación

Algunos factores que se pueden ignorar durante una prueba A/B estándar, ya que afectan a todas las experiencias por igual, no se pueden ignorar en una actividad **[!UICONTROL Asignación automática]**. El algoritmo es sensible a las tasas de conversión observadas. Los siguientes factores pueden afectar el rendimiento de la experiencia de forma desigual:

* Experiencias con relevancia contextual variable (tiempo, ubicación, sexo, etc.).

  Por ejemplo:

  * &quot;Menos mal que es viernes&quot; genera más conversiones los viernes.
  * &quot;Empieza el lunes con energía&quot; obtiene más conversiones los lunes.
  * &quot;Prepárese para un invierno en la costa este&quot; proporciona una mayor conversión en ubicaciones de la costa este o afectadas por el invierno.

  El uso de experiencias con relevancia contextual variable puede distorsionar los resultados de una prueba **[!UICONTROL Asignación automática]** más que los de una prueba A/B, ya que esta analiza los resultados a lo largo de un período más largo.

* Experiencias con diferentes retrasos en la conversión, posiblemente debidos a la urgencia del mensaje.

  Por ejemplo, el mensaje &quot;El descuento del 30% acaba hoy&quot; señala al visitante que debe generar hoy la conversión, mientras que &quot;Descuento del 50% en la primera compra&quot; no crea la misma sensación de urgencia.

## Preguntas más frecuentes {#faq}

Consulte las siguientes preguntas y respuestas cuando trabaje con actividades de **[!UICONTROL asignación automática]**.

+++ ¿Admite [!UICONTROL Analytics for Target] (A4T) actividades [!UICONTROL Asignación automática]?

Sí. Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

+++

+++ ¿Los visitantes de retorno se asignan automáticamente a experiencias de alto rendimiento?

No. Solo se asigna automáticamente a los visitantes nuevos. Los visitantes que regresan siguen viendo su experiencia original para proteger la validez de la prueba A/B.

+++

+++ ¿Cómo trata el algoritmo los falsos positivos?

El algoritmo garantiza una tasa de confianza del 95 % o una tasa de falso positivo del 5 % si espera hasta que aparezca el distintivo de ganador.

+++

+++ ¿Cuándo empieza a asignar tráfico [!UICONTROL Asignación automática]?

El algoritmo empieza a funcionar cuando todas las experiencias de la actividad tienen un mínimo de 1000 visitantes y 50 conversiones.

+++

+++ ¿Con qué agresividad explota el algoritmo?

El 80% del tráfico se sirve usando **[!UICONTROL Asignación automática]** y el 20% del tráfico se sirve aleatoriamente. Cuando se identifica un ganador, se le destina el 80 % del tráfico, mientras que todas las experiencias siguen recibiendo tráfico como parte del 20 %, incluida la experiencia ganadora.

+++

+++ ¿Se muestran las experiencias perdedoras?

Sí. El método multi-armed bandit garantiza que al menos el 20 % del tráfico se reserva para explorar las tasas de conversión o los patrones cambiantes en todas las experiencias.

+++

+++ ¿Qué sucede con las actividades con retrasos de conversión largos?

Siempre que todas las experiencias que se vayan a optimizar sufran los mismos retrasos, el comportamiento será el mismo que para una actividad con un ciclo de conversión más rápido. Sin embargo, se tarda más en alcanzar el umbral de 50 conversiones antes de que comience el proceso de asignación de tráfico.

+++

+++ ¿En qué se diferencia [!UICONTROL Asignación automática] de [!UICONTROL Automated Personalization]?

**[!UICONTROL Automated Personalization]** usa los atributos de perfil de cada visitante para determinar la mejor experiencia. Al hacerlo, no solo optimiza, sino que también personaliza la actividad de para ese visitante.

**[!UICONTROL Asignación automática]**, por otro lado, es una prueba A/B que produce un ganador agregado (la experiencia más popular, pero no necesariamente la experiencia más efectiva para cada visitante).

+++

+++ ¿Los visitantes de retorno inflan la tasa de conversión de mi métrica de éxito?

Sí, pueden. Consulte [Los visitantes de retorno frecuentes pueden inflar las tasas de conversión](#return-visitors) para ver la explicación y la forma de mitigar este efecto.

+++

+++ ¿Puedo usar la calculadora de tamaño de la muestra con [!UICONTROL Asignación automática] para estimar el tiempo que tarda la actividad en identificar al ganador?

Puede usar la [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) existente para obtener una estimación de cuánto tiempo se ejecuta la prueba. Al igual que con las pruebas A/B tradicionales, aplique la corrección de Bonferroni si va a probar más de dos ofertas o más de una métrica de conversión o hipótesis. Esta calculadora está diseñada para pruebas A/B tradicionales de horizonte fijo y proporciona solo una estimación. El uso de la calculadora para una actividad de **[!UICONTROL asignación automática]** es opcional, ya que **[!UICONTROL asignación automática]** declara un ganador por usted. No es necesario que elija un punto fijo en el tiempo para ver los resultados de la prueba. Los valores proporcionados siempre son estadísticamente válidos.

Los experimentos internos [!DNL Adobe] han encontrado lo siguiente:

* Al probar exactamente dos experiencias, **[!UICONTROL Asignación automática]** encuentra un ganador más rápidamente que las pruebas de horizonte fijo (es decir, el lapso de tiempo sugerido por la calculadora de tamaño de muestra) cuando la diferencia de rendimiento entre experiencias es grande. Sin embargo, **[!UICONTROL Asignación automática]** podría requerir tiempo adicional para identificar a un ganador cuando la diferencia de rendimiento entre experiencias sea pequeña. En estos casos, las pruebas de horizonte fijo normalmente habrían finalizado sin un resultado estadísticamente significativo.
* Al probar más de dos experiencias, **[!UICONTROL Asignación automática]** encuentra un ganador más rápidamente que las pruebas de horizonte fijo (es decir, el lapso de tiempo sugerido por la calculadora de tamaño de muestra) cuando una sola experiencia supera con creces a todas las demás experiencias. Cuando dos o más experiencias están &quot;ganando&quot; en comparación con otras, pero están estrechamente emparejadas entre sí, **[!UICONTROL Asignación automática]** podría requerir tiempo adicional para determinar cuál es superior. En estos casos, las pruebas de horizonte fijo normalmente habrían finalizado concluyendo que las experiencias &quot;ganadoras&quot; eran mejores que las de menor rendimiento, pero no habrían identificado cuál era mejor.

+++

+++ ¿Debo eliminar una experiencia de bajo rendimiento de una actividad de [!UICONTROL asignación automática] para acelerar el proceso de determinar un ganador?

No hay ninguna razón real para eliminar una experiencia de bajo rendimiento. **[!UICONTROL Asignación automática]** proporciona automáticamente experiencias de alto rendimiento con mayor frecuencia y de bajo rendimiento con menor frecuencia. Dejar una experiencia con bajo rendimiento en la actividad no afecta de manera significativa a la velocidad de determinar un ganador.

El 20 % de los visitantes se asigna de forma aleatoria entre todas las experiencias. La cantidad de tráfico proporcionado en una experiencia de bajo rendimiento es mínima (20 % dividido entre el número de experiencias).

+++

+++ ¿Puedo cambiar la métrica de objetivos a mitad de camino a través de una actividad [!UICONTROL Asignación automática]?

[!DNL Adobe] no recomienda cambiar la métrica de objetivo a mitad de una actividad. Aunque es posible cambiar la métrica de objetivo durante una actividad en la interfaz de usuario de [!DNL Target], siempre debe iniciar una nueva actividad. [!DNL Adobe] no garantiza lo que sucederá si cambia la métrica de objetivo en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de **[!UICONTROL Asignación automática]**, **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]** que usan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

+++

+++ ¿Puedo cambiar la fuente de informes a mitad de camino a través de una actividad [!UICONTROL Asignación automática]?

[!DNL Adobe] no recomienda cambiar el origen de los informes a mitad de una actividad. Aunque es posible cambiar la fuente de informes (de [!DNL Target] a A4T o viceversa) durante una actividad en la interfaz de usuario de [!DNL Target], siempre debe iniciar una nueva actividad. [!DNL Adobe] no garantiza lo que suceda si cambia el origen de los informes en una actividad después de que se esté ejecutando.

Esta recomendación se aplica a las actividades de **[!UICONTROL Asignación automática]**, **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]** que usan [!DNL Target] o [!DNL Analytics] (A4T) como fuente de informes.

+++

+++ ¿Puedo usar la opción [!UICONTROL Restablecer los datos del informe] al ejecutar una actividad de [!UICONTROL Asignación automática]?

No se recomienda usar la opción **[!UICONTROL Restablecer los datos del informe]** para las actividades **[!UICONTROL Asignación automática]**. Aunque quita los datos de informes visibles, esta opción no quita todos los registros de aprendizaje del modelo **[!UICONTROL Asignación automática]**. En lugar de usar la opción **[!UICONTROL Restablecer los datos del informe]**, cree una nueva actividad y desactive la actividad original. Esta guía también se aplica a las actividades de **[!UICONTROL Segmentación automática]** y **[!UICONTROL Automated Personalization]**.

+++

+++ ¿Cómo crea [!UICONTROL Asignación automática] modelos con respecto a los entornos?

**[!UICONTROL Asignación automática]** crea modelos basados en el comportamiento de tráfico y conversión registrado solamente en el entorno predeterminado. De manera predeterminada, **[!UICONTROL Production]** es el entorno predeterminado, pero el entorno predeterminado se puede cambiar en [!DNL Target] ([Administration > Environments](/help/main/administrating-target/environments.md)).

Si se produce una visita en otro entorno (no predeterminado), el tráfico se distribuye según el comportamiento de conversión observado en el entorno predeterminado. El resultado de esa visita (conversión o no conversión) se registra con fines de creación de informes, pero no se tiene en cuenta en el modelo **[!UICONTROL Asignación automática]**.

Al seleccionar otro entorno, el informe muestra el tráfico y las conversiones de ese entorno. El entorno seleccionado de forma predeterminada para un informe es el predeterminado de toda la cuenta. El entorno predeterminado no se puede establecer por actividad.

+++

+++ ¿Puede una actividad de [!UICONTROL Asignación automática] ajustar la ventana retrospectiva a lo largo de una prueba para tener en cuenta los cambios en las tendencias a lo largo del tiempo?

Por ejemplo, ¿puede la actividad considerar el mes de diciembre para decidir cómo asignar el tráfico en lugar de consultar los datos de visitantes de septiembre (cuando comenzó la prueba)?

No. **[!UICONTROL Asignación automática]** considera el rendimiento de toda la actividad.

+++

+++ ¿[!UICONTROL Asignación automática] muestra una experiencia ganadora a un visitante que regresa si la experiencia ganadora es diferente de lo que vio el visitante al calificar para la actividad?

**[!UICONTROL Asignación automática]** usa la toma de decisiones fija por las mismas razones por las que las actividades de **[!UICONTROL Prueba A/B]** son fijas. La asignación de tráfico solo funciona para visitantes nuevos.

+++

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

En este vídeo se explica cómo crear una prueba A/B siguiendo el flujo de trabajo guiado de tres pasos de Target. **[!UICONTROL Asignación automática]** se discute a partir del minuto 4:45.

* Crear una actividad A/B en [!DNL Adobe Target]
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
