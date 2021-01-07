---
keywords: AB;A/B;AB...n;mistakes;pitfalls;mistake;pitfall;significance;winner;statistically difference;statistical;statistical power;traffic allocation;allocation;
description: Las pruebas A/B en Adobe Target constituyen la columna vertebral de la mayoría de los programas de optimización de marketing digital, lo que ayuda a los especialistas en marketing a ofrecer a sus visitantes y clientes experiencias optimizadas y dirigidas a la oferta. Esta sección describe nueve de los escollos más significativos a los que se enfrentan las compañías al realizar pruebas A/B en Adobe Target. También se explican las formas de evitarlos para que las empresas puedan obtener un ROI más elevado a través de los procesos de prueba y confiar más en los resultados que arrojan las pruebas A/B.
title: Nueve escollos comunes de las pruebas A/B y cómo evitarlos
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '3922'
ht-degree: 87%

---


# Diez escollos comunes de prueba A/B y cómo evitarlos

La prueba A/B en [!DNL Adobe Target] forma la columna vertebral de la mayoría de los programas de optimización de mercadotecnia digital, lo que ayuda a los especialistas en mercadotecnia a optimizar la oferta y dirigir experiencias a sus visitantes y clientes. Esta sección describe diez de los escollos más importantes a los que se enfrentan las compañías al realizar pruebas A/B. También se explican las formas de evitarlos para que las empresas puedan obtener un ROI más elevado a través de los procesos de prueba y confiar más en los resultados que arrojan las pruebas A/B.

## Pitfall 1: Ignorar los efectos del nivel de relevancia {#section_55F5577A13C6470BA1417C2B735C6B1D}

¿Cuánta probabilidad hay de que una prueba arroje una diferencia relevante en la tasa de conversión entre dos ofertas cuando, en realidad, no existe ninguna diferencia? El *nivel de relevancia* de una prueba es lo que ayuda a averiguar esto. A menudo estos resultados erróneos se denominan falsos positivos y, en el mundo de la estadística, se denominan errores de Tipo I (cuando se rechaza incorrectamente la hipótesis null que es verdadera).

Al especificar el nivel de relevancia de una prueba A/B, está buscando un término medio entre su tolerancia para aceptar que esa experiencia es mejor que la otra cuando en realidad no es así (error de Tipo I o “falso positivo”) frente a no ver ninguna diferencia estadística entre las experiencias cuando en realidad sí la hay (error de Tipo II o “falso negativo”). El *nivel de confianza* se determina antes de ejecutar una prueba.

El *intervalo de confianza*, que se determina tras completar una prueba, está influido por tres factores clave: el tamaño de la muestra de la prueba, el nivel de relevancia y la desviación estándar de la población. Como el experto en marketing ha seleccionado el nivel de relevancia antes de que se diseñara la prueba y el estándar de población no puede verse afectado, el único factor “controlable” es el tamaño de la muestra. El tamaño de la muestra requerido para un intervalo de confianza con el que se sienta cómodo y el tiempo resultante que se necesita para conseguir ese tamaño de la muestra son decisiones clave que un experto en marketing debe tomar durante el diseño de la prueba.

Otro término directamente relacionado, *nivel de confianza*, se encarga de ver el vaso medio lleno. En lugar de expresar la probabilidad de obtener un falso positivo, como hace el nivel de relevancia, el nivel de confianza representa la probabilidad de que en la prueba no se produzca este error.

El nivel de confianza y el de relevancia están directamente relacionados porque:

100 % - nivel de confianza = nivel de relevancia

En las pruebas A/B, los especialistas en marketing usan niveles de confianza del 95 %. A partir de la ecuación anterior, esto supone un nivel de relevancia del 5 %. Realizar pruebas con un nivel de confianza del 95 % significa que existe un 5 % de posibilidad de detectar un alza estadísticamente relevante aunque, en realidad, no haya ninguna diferencia entre las ofertas.

Como se ve en el gráfico siguiente, cuantas más pruebas se efectúen, más probabilidades existen de que al menos una de ellas arroje un falso positivo. Por ejemplo, si ejecuta 10 pruebas usando un nivel de confianza del 95 %, habrá aproximadamente un 40 % de probabilidad de que se detecten uno o varios falsos positivos [siempre que no haya un alza real: Pr(al menos un falso positivo) = 1 - Pr(ningún falso positivo) = 1 - 0,95^10 = 40 %].

![](assets/pitfalls1.png)

Normalmente, el 95 % de una organización de marketing constituye un término medio razonable entre el riesgo de un falso positivo y los falsos negativos.

Sin embargo, existen dos situaciones en las que hay que prestar especial atención al nivel de relevancia y sus implicaciones en los resultados de las pruebas: la segmentación posterior a las pruebas y la realización de pruebas con varias ofertas.

* **Segmentación posterior a las pruebas:** normalmente, los especialistas en marketing diseccionan los resultados de una prueba a partir de los segmentos del visitante al finalizar una prueba A/B. Entre los segmentos más comunes encontramos los de tipo de navegador, tipo de dispositivo, zona geográfica, hora del día y visitantes nuevos frente a visitantes que regresan. Esta práctica, conocida como “segmentación posterior a las pruebas”, ofrece información muy valiosa sobre los segmentos del visitantes. A su vez, los especialistas en marketing pueden usar esta información para crear contenido diferenciado, más relevante y mejor segmentado.

   Si no hay una diferencia real en la tasa de conversión, cada vez que se pruebe un segmento, la probabilidad de un falso positivo es igual al nivel de relevancia. Y, como ya hemos señalado, cuantas más pruebas se ejecuten, más probabilidad habrá de obtener, al menos, un falso positivo en alguna de ellas. En definitiva, cada segmento posterior a una prueba representa una prueba independiente. Con un nivel de relevancia del 5 %, en 20 segmentos posteriores a una prueba existe, de media, un falso positivo. El gráfico anterior muestra cómo aumenta esa probabilidad.

   Y, como ya hemos señalado, cuantas más pruebas se ejecuten, más probabilidad habrá de obtener, al menos, un falso positivo en alguna de ellas. En esencia, cada segmento posterior a la prueba representa una prueba separada, que aumenta la probabilidad de un falso positivo. Este aumento puede ser incluso más significativo si los segmentos están correlacionados.

   ¿Entonces hay que prescindir de la segmentación posterior a las pruebas? No, los segmentos posteriores a las pruebas son útiles. Para evitar el problema de acumulación de falsos positivos en la segmentación posterior a las pruebas, después de identificar un segmento de este tipo se puede probar en una prueba nueva. Otra opción es aplicar la corrección de Bonferroni, que explicamos más adelante.

* **Realización de pruebas con varias ofertas:** a menudo, los especialistas en marketing prueban más de dos ofertas (o experiencias) para compararlas. Por este motivo, a veces las soluciones de pruebas A/B se llaman pruebas “A/B/n”, donde “n” es el número de ofertas que se prueban simultáneamente.

   Cabe destacar que *cada una* de las ofertas sometidas a prueba tiene una tasa de falsos positivos equivalente al nivel de relevancia, como hemos explicado arriba. Al cotejar varias ofertas en un mismo entorno de pruebas, estará ejecutando varias pruebas de una forma eficaz. Por ejemplo, si compara cinco ofertas en una prueba A/B/C/D/E, se establecen cuatro comparaciones: control con B, control con C, control con D y control con E. Con un nivel de confianza del 95 %, la probabilidad de un falso positivo es del 18,5 % en lugar del 5 %. 2

   Para mantener el nivel de confianza general en el 95 % y evitar este problema, se debe aplicar lo que se conoce como “corrección de Bonferroni”. Por medio de esta corrección, el nivel de relevancia se divide entre el número de comparaciones para obtener el nivel de relevancia necesario para lograr un nivel de confianza del 95 %.

   Aplicando la corrección de Bonferroni en el ejemplo anterior, se usaría un nivel de relevancia de 5 %/4 = 1,25 %, que es lo mismo que un nivel de confianza del 98,75 % en una prueba individual (100 % - 1,25 % = 98,75 %). Este ajuste mantiene el nivel de confianza real en el 95 % cuando se realizan cuatro pruebas, como en el ejemplo descrito.

## Pitfall 2: Declarar ganadores de varias pruebas de oferta sin diferencia estadísticamente significativa {#section_FA83977C71DB4F69B3D438AF850EF3B6}

Al realizar pruebas con varias ofertas, los especialistas en marketing suelen declarar como ganadora de la prueba la oferta con la mayor alza aunque no exista una diferencia estadísticamente relevante entre el ganador y el segundo finalista. Esta situación se da cuando la diferencia entre las alternativas es inferior a la diferencia entre las alternativas y el control. La imagen siguiente ilustra este concepto. Las barras negras de error representan los intervalos de confianza del alza del 95 %. El alza verdadera de cada oferta en relación con la oferta de control tiene un 95 % de probabilidad de incluirse en el intervalo de confianza (el rango señalado por las barras de error).

![](assets/pitfalls2.png)

Las ofertas A y B tienen la mayor alza observada durante la prueba y es poco probable que la oferta C supere en rendimiento a estas ofertas en una próxima prueba, ya que el intervalo de confianza de C ni siquiera se superpone con los intervalos de confianza de A y B. Sin embargo, aunque la oferta A tiene la mayor alza observada durante la prueba, hay muchas posibilidades de que la oferta B ofrezca un mejor rendimiento en una próxima prueba debido a la superposición de los intervalos de confianza.

La conclusión es que ambas ofertas, la A y la B, se deben considerar ganadoras de la prueba.

Por lo general, no es viable ejecutar la prueba durante el tiempo suficiente para identificar el rendimiento relativo verdadero de las alternativas y, con frecuencia, sucede que la diferencia en rendimiento de las alternativas es demasiado pequeña para tener una repercusión sustancial en la tasa de conversión. En estos casos, el resultado se puede interpretar como una asociación y se pueden considerar otros factores, como la estrategia o la alineación con otros elementos de la página, para determinar qué oferta debemos implementar. Al realizar varias pruebas, hay que estar abierto a la posibilidad de que haya más de un ganador, lo cual, en algunos casos, amplía las posibilidades de desarrollo en el sitio web.

Recuerde que, si lo que desea es identificar la oferta con la mayor tasa de conversión, debe comparar todas las ofertas entre sí. En el ejemplo anterior, hay n = 5 ofertas, por lo que hay que realizar n(n-1)/2 o 5*(5-1)/2 = 10 comparaciones. En este caso, la corrección de Bonferroni exige que el nivel de relevancia de la prueba sea de 5 %/10 = 0,5 %, lo que corresponde a un nivel de confianza del 99,5 %. No obstante, este nivel de confianza puede requerir que la prueba se ejecute durante un periodo de tiempo demasiado prolongado.

## Pitfall 3: Ignorar los efectos de la potencia estadística {#section_0D517079B7D547CCAA75F80981CBE12A}

La potencia estadística es la probabilidad de que una prueba detecte una diferencia real en la tasa de conversión de distintas ofertas. Debido a la naturaleza aleatoria o, como la denominan los estadistas, estocástica de los eventos de conversión, es posible que una prueba no muestre una diferencia con relevancia estadística aunque haya una diferencia real entre las tasas de conversión de dos ofertas a largo plazo. Podemos considerarlo mala suerte o casualidad. La imposibilidad de detectar una diferencia verdadera en la tasa de conversión se llama “falso negativo” o “error de tipo II”.

Hay dos factores clave que determinan la efectividad de una prueba. En primer lugar, el tamaño de la muestra, es decir, el número de visitantes incluidos en la prueba. Y, en segundo lugar, la magnitud de la diferencia en la tasa de conversión que quiere que detecte la prueba. Esto es bastante intuitivo, pero si lo que le interesa es detectar solo diferencias grandes en la tasa de conversión, hay mucha más probabilidad de que la prueba las detecte. Sería como descubrir que hay un elefante en nuestro salón: es mucho más fácil que ver una mosca a través del tubo de cartón del papel de cocina. De forma similar, cuanto menor sea la diferencia que quiera detectar, mayor deberá ser el tamaño de la muestra y, por lo tanto, el tiempo para obtener ese tamaño de la muestra requerido.

Hoy en día, los especialistas en marketing emplean una potencia estadística insuficiente en gran cantidad de pruebas. En otras palabras, el tamaño de muestra que utilizan es demasiado pequeño. Esto quiere decir que tienen escasas posibilidades de detectar verdaderos positivos aunque exista una diferencia notable en la tasa de conversión. Es más: si se ejecutan continuamente pruebas con una potencia estadística insuficiente, el número de falsos positivos puede ser equiparable al de verdaderos positivos e, incluso, lo puede sobrepasar. A menudo, esto desemboca en la implementación de cambios neutros en un sitio (una pérdida de tiempo) o cambios que, paradójicamente, reducen las tasas de conversión.

![](assets/pitfalls3.png)

Para evitar que esto ocurra, hay que tener en cuenta que el estándar típico para que una prueba arroje resultados fiables es un nivel de confianza del 95 % y una potencia estadística del 80 %. Estos porcentajes indican que la prueba ofrece un 95 % de probabilidad de evitar un falso positivo y un 80 % de evitar un falso negativo.

## Paso 4: Uso de pruebas unidireccionales {#section_8BB136D1DD6341FA9772F4C31E9AA37C}

Las pruebas unilaterales requieren una diferencia observada más reducida en las tasas de conversión entre las ofertas para declarar un ganador con un cierto nivel de relevancia. Esto parece interesante porque los ganadores se pueden declarar antes y con más frecuencia que cuando se usan pruebas bidireccionales. Sin embargo, sabemos que todo tiene su precio y las pruebas unidireccionales no podían ser menos.

En una prueba unidireccional, probamos si la oferta B es mejor que la oferta A. El sentido de la prueba se debe establecer antes de que esta comience o, en términos estadísticos, “a priori”. Es decir, hay que decidir si lo que queremos probar es si la prueba B es mejor que la A o si la A es mejor que la B, y esto se debe hacer *antes* de iniciar la prueba. No obstante, si miramos los resultados de la prueba A/B, observamos que la B tiene mejor rendimiento que la A y *luego* decidimos llevar a cabo una prueba unidireccional para ver si la diferencia es estadísticamente relevante, estaríamos infringiendo las presuposiciones de la prueba estadística. Infringir las presuposiciones de la prueba significa que los intervalos de confianza no son fiables y que la prueba tiene una tasa de falsos positivos superior a la esperada.

Las pruebas unidireccionales se pueden ver cómo llevar a juicio una oferta con un juez que ya tiene el veredicto. En una prueba unidireccional, decidimos de antemano la oferta ganadora y lo que queremos es demostrarlo. Las ofertas no tienen igualdad de oportunidades para erigirse en ganadoras. Este tipo de prueba solo debería usarse en las infrecuentes situaciones en que queramos saber si una oferta es mejor que la otra y no al revés. Para evitar el inconveniente de las pruebas unidireccionales, debemos recurrir a una solución de pruebas A/B que siempre utilice pruebas bidireccionales, como [!DNL Adobe Target].

## Pitfall 5: Pruebas de monitoreo {#section_EA42F8D5967B439284D863C46706A1BA}

Habitualmente, los especialistas en marketing supervisan las pruebas A/B hasta que se obtiene un resultado relevante. Al fin y al cabo, ¿para qué hacer pruebas cuando se ha alcanzado una relevancia estadística?

Lamentablemente, no es tan sencillo. No queremos complicar las cosas, pero lo cierto es que supervisar los resultados influye negativamente en la relevancia estadística real de la prueba. De hecho, aumenta en gran medida la probabilidad de falsos positivos y disminuye la fiabilidad de los intervalos de confianza.

Esto puede resultar confuso. Parece que decimos que solo por mirar los resultados a mitad de la prueba, estos pierden su relevancia estadística, pero no es exactamente así. En el ejemplo siguiente vemos por qué.

Imagine que simulamos 10 000 eventos de conversión de dos ofertas y que las dos tienen una tasa de conversión del 10 %. Como las tasas de conversión son iguales, no se debería detectar ninguna diferencia en el alza de conversión al comparar las dos pruebas. Con un intervalo de confianza del 95 %, la prueba genera la tasa de falsos positivos esperada del 5 % cuando se evalúa después de recopilar las 10 000 observaciones. De modo que, si ejecutamos 100 de estas pruebas, obtendremos de media cinco falsos positivos (en realidad, todos los positivos son falsos en este ejemplo, ya que no hay diferencia en la tasa de conversión de ambas ofertas). Sin embargo, si evaluamos la prueba 10 veces durante el proceso (cada 1000 observaciones), resulta que la tasa de falsos positivos sube al 16 %. Al supervisar la prueba, el riesgo de falsos positivos es más del triple. ¿Cómo puede ser?

Para entender por qué sucede esto, hay que tener en cuenta las distintas acciones adoptadas cuando se detecta una resultado relevante y cuando no se detecta. Cuando se detecta un resultado estadísticamente relevante, la prueba se detiene y se declara un ganador. No obstante, si el resultado no tiene relevancia estadística, permitiremos que la prueba continúe. Esta situación favorece enormemente un resultado positivo y, por tanto, distorsiona el nivel de relevancia estadística de la prueba.

Para evitar este problema, debe determinar el tiempo que durará la ejecución de la prueba antes de iniciarla. Está bien consultar los resultados de la prueba durante su desarrollo para asegurarse de que la hemos implementado correctamente, pero no hay que sacar conclusiones ni detenerla antes de alcanzar el número requerido de visitantes. En otras palabras, ¡nada de echar un vistazo!

## Pitfall 6: Deteniendo pruebas de forma prematura {#section_DF01A97275E44CA5859D825E0DE2F49F}

Es tentador detener una prueba si una de las ofertas muestra un rendimiento mucho mejor o peor que las otras en los primeros días de la prueba. Sin embargo, cuando el número de observaciones es reducido, existe una alta probabilidad de observar un alza positiva o negativa solo por casualidad, puesto que la tasa de conversión se promedia a partir de un número bajo de visitantes. A medida que la prueba recopila más puntos de datos, las tasas de conversión convergen hacia sus verdaderos valores a largo plazo.

En la ilustración siguiente vemos cinco ofertas que tienen la misma tasa de conversión a largo plazo. La oferta B tuvo una tasa de conversión deficiente durante los primeros 2000 visitantes y la tasa de conversión estimada tarda mucho en volver a la tasa verdadera a largo plazo.

![](assets/pitfalls4.png)

Este fenómeno se conoce como “regresión a la media” y puede llevar a decepciones cuando una oferta que mostró un buen rendimiento durante los días iniciales de una prueba no es capaz de mantener el mismo rendimiento a largo plazo. También puede suponer la pérdida de ingresos cuando una buena oferta no se implementa debido a un mal rendimiento en los primeros días de una prueba solo por casualidad.

Al igual que sucede con la supervisión de la prueba, la mejor forma de evitar estos problemas consiste en determinar un número adecuado de visitantes antes de ejecutar la prueba y, una vez iniciada, dejar que siga su curso hasta que este número de visitantes se haya expuesto a las ofertas.

## Pitfall 7: Cambio de la asignación de tráfico durante el período de prueba {#allocation}

Se recomienda no cambiar los porcentajes de asignación de tráfico durante el período de prueba, ya que esto puede distorsionar los resultados de la prueba hasta que los datos se normalicen.
Por ejemplo, supongamos que tiene una actividad de prueba A/B en la que el 80 % del tráfico se asigna a la Experiencia A (el control) y el 20 % del tráfico se asigna a la Experiencia B. Durante el período de prueba, la asignación se cambia al 50 % para cada experiencia. Unos días después, puede cambiar la asignación de tráfico a 100 % en la Experiencia B.

En este escenario, ¿cómo se asignan los usuarios a las experiencias?

Si cambia manualmente la división de asignación al 100 % para la experiencia B, los visitantes que se asignaron originalmente a la experiencia A (el control) permanecerán en su experiencia asignada inicialmente (Experiencia A). El cambio en la asignación del tráfico afecta únicamente a los nuevos participantes.

Si desea cambiar los porcentajes o afectar en gran medida el flujo de visitantes en cada experiencia, le recomendamos que cree una nueva actividad o copie la actividad y luego edite los porcentajes de asignación de tráfico.

Si cambia los porcentajes de distintas experiencias durante el período de prueba, los datos tardan unos días en normalizarse, especialmente si muchos compradores devuelven visitantes.
Otro ejemplo es que, si la asignación de tráfico de la prueba A/B se divide 50/50 y, a continuación, se cambia la división a 80/20, durante los primeros días posteriores a ese cambio los resultados podrían verse distorsionados. Si el tiempo promedio de conversión es alto, lo que significa que alguien tarda varias horas o incluso días en realizar una compra, estas conversiones demoradas pueden afectar a los informes. Así que, en esa primera experiencia donde el número pasó del 50% al 80%, y el tiempo promedio para la conversión es de dos días, sólo visitantes del 50% de la población se están convirtiendo el primer día de la prueba, aunque hoy el 80% de la población está entrando en la experiencia. Esto hace que parezca que la tasa de conversión se desplomó, pero se normalizará nuevamente después de que el 80% de los visitantes hayan tardado dos días en convertirse.

## Pitfall 8: No considerar los efectos de la novedad {#section_90F0D24C40294A8F801B1A6D6DEF9003}

Si no dejamos que una prueba se ejecute durante el tiempo suficiente, pueden suceder otras cosas inesperadas. En este caso, no se trata de un problema estadístico, sino de la reacción de los visitantes al cambio. Si cambia una parte consolidada de su sitio web, es posible que los visitantes que regresan interactúen menos con la oferta nueva al principio por los cambios efectuados en el flujo de trabajo habitual. Esto puede hacer que, temporalmente, una nueva oferta superior tenga un rendimiento inferior hasta que los visitantes que regresan se acostumbren a ella: un pequeño precio que hay que pagar teniendo en cuenta las ganancias a largo plazo que reportará la oferta superior.

Para averiguar si el rendimiento de la oferta nueva es inferior por el efecto de la novedad o porque en realidad es peor, puede segmentar a los visitantes en visitantes nuevos y visitantes que regresan para después comparar las tasas de conversión. Si solo es el efecto de la novedad, la oferta nueva ganará entre los visitantes nuevos. A la larga, cuando los visitantes que regresan se vayan acostumbrando a los nuevos cambios, la oferta también ganará entre estos.

El efecto de la novedad también puede funcionar a la inversa. Los visitantes suelen reaccionar de forma positiva a un cambio solo porque introduce algo nuevo. Pasado un tiempo, cuando el contenido se queda anticuado o ya no le resulta tan interesante al visitante, la tasa de conversión cae. Este efecto es más difícil de identificar, pero supervisar minuciosamente los cambios en la tasa de conversión es fundamental para detectarlo.

## Pitfall 9: No considerar las diferencias en el período de consideración {#section_B166731B5BEE4E578816E351ECDEA992}

El periodo de consideración es el tiempo que transcurre desde que la solución de pruebas A/B presenta una oferta a un visitante hasta que este efectúa la conversión. Esto puede ser importante en el caso de las ofertas que afectan al periodo de consideración de forma significativa, como una oferta que establezca un plazo, por ejemplo, “Oferta de tiempo limitado: Haga su pedido antes del domingo”.

Las ofertas de este tipo animan a los visitantes a realizar la conversión antes y se ven favorecidas si la prueba se detiene justo después de que caduque la oferta, ya que es posible que la oferta alternativa tenga un plazo más extenso o que no tenga plazo, lo que significa que tiene un periodo de consideración mayor. La alternativa conseguiría conversiones una vez terminada la prueba, pero si la detiene al final del plazo, las siguientes conversiones no se tendrían en cuenta en la tasa de conversión de la prueba.

En la ilustración siguiente observamos dos ofertas que dos visitantes distintos ven a la vez un domingo por la tarde. El periodo de consideración de la oferta A es breve y el visitante realiza la conversión más tarde ese mismo día. Sin embargo, el periodo de consideración de la oferta B es más extenso y el visitante que la vio piensa en ella un tiempo y acaba efectuando la conversión el lunes por la mañana. Si detiene la prueba el domingo por la noche, la conversión asociada a la oferta A se cuenta en la métrica de conversión de dicha oferta, mientras que la conversión asociada a la oferta B no se contabilizará en la métrica correspondiente de esta oferta. Esto pone en una situación de gran desventaja a la oferta B.

![](assets/pitfalls5.png)

Si quiere evitar este escollo, debe dejar un tiempo para que los visitantes que estuvieron expuestos a las ofertas de la prueba generen la conversión después de haberse detenido una nueva entrada de la prueba. Con esto, podría ver una comparación justa de las ofertas.

## Pitfall 10: Uso de métricas que no reflejan los objetivos del negocio {#section_F0CD6DC7993B4A6F9BEEBB31CD1D9BEE}

Los especialistas en marketing pueden sentir la tentación de usar métricas de conversión de tráfico elevado y varianza baja en el canal superior, como la tasa de pulsaciones (CTR), para alcanzar con mayor rapidez un número adecuado de conversiones de prueba. No obstante, debemos pensar muy bien si la CTR es un medio apropiado para el objetivo comercial que deseamos conseguir. Las ofertas con mayores cifras de CTR pueden conducir fácilmente a una caída de los ingresos. Esto puede ocurrir cuando las ofertas atraen a visitantes con menor propensión a comprar o cuando la propia oferta (un descuento, por ejemplo) supone, de por sí, unos ingresos menores.

![](assets/pitfalls6.png)

Vamos a fijarnos en la oferta para esquiar que hay abajo. Genera una CTR mucho mayor que la oferta de ciclismo, pero, como los visitantes gastan mucho más dinero de media cuando eligen la oferta de ciclismo, los ingresos esperados de exponer dicha oferta a un visitante determinado son más elevados. Por lo tanto, una prueba A/B cuya métrica fuera la CTR elegiría una oferta que no maximizara los ingresos: el objetivo esencial del negocio.

![](assets/pitfalls7.png)

Para evitar este problema, supervise atentamente las métricas del negocio a fin de identificar el impacto comercial de las ofertas o, mejor aún, use una métrica que se aproxime más al objetivo comercial (si es posible).

## Conclusión: Éxito con las pruebas A/B reconociendo y superando los escollos {#section_54D33248163A481EBD4421A786FE2B15}

Ahora que ya conoce los escollos más habituales de las pruebas A/B, esperamos que sea capaz de identificar cuándo y dónde podría haber incurrido en uno de estos errores. También esperamos que ahora comprenda mejor algunos de los conceptos de estadística y probabilidad que se usan en las pruebas A/B y que, a veces, parece que solo los matemáticos pueden entender.

Los pasos siguientes sirven para evitar estos escollos y lograr mejores resultados en las pruebas A/B:

* Examine detenidamente cuál es la métrica apropiada para la prueba en función de los objetivos relevantes del negocio.
* Decida un nivel de confianza antes de iniciar la prueba y aténgase a este umbral al evaluar los resultados cuando esta finalice.
* Calcule el tamaño de la muestra (número de visitantes) antes de que iniciar la prueba.
* Antes de detener la prueba, espere a que se llegue al tamaño de la muestra calculado.
* Ajuste el nivel de confianza al realizar la segmentación posterior a la prueba o al evaluar más de una alternativa, por ejemplo, mediante la corrección de Bonferroni.

