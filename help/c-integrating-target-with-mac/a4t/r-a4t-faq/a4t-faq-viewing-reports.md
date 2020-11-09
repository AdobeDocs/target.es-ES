---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la visualización de informes al usar Analytics como fuente de informes para Target (A4T).
title: 'Visualización de informes: preguntas más frecuentes sobre A4T'
feature: a4t troubleshooting
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1986'
ht-degree: 65%

---


# Visualización de informes: preguntas más frecuentes sobre A4T{#view-reports-a-t-faq}

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Can I view my Target activity data in Analysis Workspace? {#workspace}

Puede usar [!DNL Analysis Workspace] para analizar sus [!DNL Target] actividades y experiencias. El panel [](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Análisis para Destinatario le permite ver el alza y la confianza de hasta tres métricas de éxito. También puede profundizar con tablas y visualizaciones.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## ¿Dónde se pueden aplicar segmentos en Analysis Workspace? {#segmentation}

Los segmentos se suelen aplicar a la parte superior de un panel en la zona de colocación del segmento. El segmento se aplica a todas las tablas y visualizaciones del panel. La mayor utilidad de esta técnica es que permite ver cómo afecta una prueba un subconjunto de personas (por ejemplo, qué resultado ha tenido esta prueba entre la gente de España)?

## Cuando se aplica un segmento de visita para una actividad de Destinatario específica, ¿por qué se devuelven experiencias no relacionadas? {#activity-segmentation}

La variable de [!DNL Target] enviada a [!DNL Analytics] caduca, de forma predeterminada, en un plazo de 90 días. (Nota: el Servicio de atención al cliente puede ajustar este período de caducidad si es necesario). A medida que los visitantes navegan por el sitio a través de esta ventana de caducidad, forman parte de muchas [!DNL Target] actividades, todas las cuales se recopilan en la dimensión.

Como resultado, cuando segmente para que una actividad esté presente en una visita, obtendrá todas las experiencias que forman parte de esa actividad *además* de cualquier otra experiencia que persista en esa visita.

## ¿Debería usar visitantes, visitas o impresiones de actividad como métrica de normalización (es decir, metodología de recuento)? {#metrics}

Existen varias opciones para normalizar métricas en A4T sistema de informes. Esta métrica, también denominada metodología de contabilización, se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza.

* ***Visitantes únicos*** aumenta cuando un usuario reúne por primera vez los requisitos para una actividad.
* ***Visitas*** aumenta para cada sesión cuando un usuario (visitante único) accede a una actividad, incluso si la actividad no se visualiza en visitas posteriores.
* ***Impresiones de actividad*** aumenta cada vez que se sirve el contenido de la actividad. (Medido por [!DNL Target]).

Cuando un visitante ve una página que contiene una actividad, se establece una variable para ese visitante que incluye el nombre de esa actividad. Consulte los escenarios detallados que se muestran a continuación para ver cómo se compara cada metodología de recuento.

Tenga en cuenta lo siguiente:

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. Esto no significa necesariamente que el usuario haya visto la oferta. Si una experiencia de actividad está por debajo del pliegue y el usuario no se desplaza hacia abajo en la página significa que [!DNL Target] proporcionó la oferta, pero el usuario no la vio.
* [!UICONTROL Impresiones de actividad] (medida mediante [!DNL Target]) e [!UICONTROL Instancias] (medida mediante [!DNL Analytics]) son iguales, a menos que haya varias llamadas de mbox en la misma página de la misma actividad. De esta forma se contabilizan varias [!UICONTROL Impresiones de actividad], pero una sola [!UICONTROL Instancia].

## ¿Por qué las &quot;impresiones de actividad&quot; y las &quot;conversiones de actividad&quot; son más altas en Analysis Workspace que en Informes y análisis? {#sametouch}

[!DNL Reports & Analytics] aplica un modelo de atribución de mismo toque a &quot;impresiones de actividad&quot; y &quot;conversiones de actividad&quot;, mientras que [!DNL Analysis Workspace] muestra las métricas sin procesar, que pueden aparecer infladas debido a la persistencia de la [!DNL Target] dimensión.

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. Los modelos se pueden aplicar si hace clic en el engranaje de configuración de columna y habilita [!UICONTROL Modelos de atribución no predeterminados] y, a continuación, selecciona [!UICONTROL Mismo contacto]. Obtenga más información sobre la atribución en Información general [de IQ de](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) atributos en la Guía *de herramientas de* Analytics.

## ¿Qué significa “conversiones de la actividad” si el especialista en marketing elige una métrica de Analytics durante la configuración de la actividad?{#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## ¿Por qué pone “sin especificar” en los informes de Analytics? ¿Qué quiere decir? {#unspecified}

En otros informes, “sin especificar” significa que los datos no cumplían una regla de clasificación, pero esto no debería suceder nunca en A4T. Si ve “sin especificar”, aún no se ha ejecutado el servicio de clasificación. Los datos de la actividad suelen tardar entre 24 y 72 horas en aparecer en los informes. Aunque las actividades no aparecen en este informe hasta llegado ese momento, todos los datos de visitantes asociados a esas actividades se recopilan y aparecerán cuando se complete la clasificación.

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

## ¿Por qué se envían métricas de Target a Analytics aunque la actividad se haya desactivado?{#section_38AA8380A4D54A18972F1EF3E73E22EF}

La variable de [!DNL Target] enviada a [!DNL Analytics] caduca, de forma predeterminada, en un plazo de 90 días. El Servicio de atención al cliente puede ajustar este período de caducidad si es necesario. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. Si un usuario regresa al sitio el día 45 y ve otra actividad, el contador del valor de la eVar de A4T se restablece a 90 días. Esto significa que la primera campaña del día 1 podría perdurar durante un total de 45 + 90 = 135 días. If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. Cuando los usuarios eliminan las cookies y dejan de volver al sitio, las cifras de esa actividad caen, pero se siguen viendo.

Esto significa que la actividad sigue recibiendo visualizaciones de página, visitas, etc., 90 días después del momento en que finaliza la actividad para los visitantes que participaron en ella mientras estaba activa. Sin embargo, si consulta la métrica [!UICONTROL Impresiones de actividad], no debería ver ninguna impresión una vez finalizada la actividad.

Este comportamiento es normal. La variable de A4T funciona como cualquier otra eVar: el valor está asociado al usuario hasta que se alcanza la fecha de caducidad (90 días). En consecuencia, si una actividad solo está activa durante dos semanas, el valor seguirá estando asociado al usuario durante al menos los siguientes 90 días.

La práctica recomendada consiste en ver solamente los informes de la actividad que correspondan al periodo de tiempo en el cual dicha actividad estaba activa. The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

Vamos a suponer, por ejemplo, que la variable de A4T caduca pasados 90 días y que nuestra prueba está activa del 1 al 15 de enero.

El 1 de enero, el usuario llega al sitio, ve la actividad XYZ una vez y, después, efectúa cinco vistas de página. En las dos semanas siguientes, el usuario no regresa al sitio. Los datos referentes a ese usuario serían los siguientes:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

El usuario vuelve el 1 de febrero y ve otras cinco páginas. No encuentra más actividades de Target y la actividad original ya no está activa. Aunque ya no está activa, la actividad todavía sigue al usuario mediante la persistencia de eVar. Los datos de este momento son estos:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

El usuario vuelve el 1 de marzo y ve una actividad nueva: ABC. Esta vez también ve cinco páginas. Como la actividad XYZ todavía sigue al usuario mediante la persistencia y este ve después la actividad ABC, observaremos dos líneas en el informe:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

El usuario regresa el 1 de abril, ve otras cinco páginas y realiza una compra. El periodo de caducidad de 90 días del primer valor de eVar se restableció el 1 de abril y esto se refleja en el informe. Se atribuye el origen de la conversión a todas las actividades de Target que el usuario ve, pero el número total de conversiones se desduplica:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Puesto que las dos experiencias se vieron antes de la conversión, ambas son las “responsables” del pedido. Sin embargo, en el sistema solo se ha efectuado un pedido y esto se refleja en el total. For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. Lo que se compara son los resultados de dos elementos de una misma actividad y, como un usuario no puede ver distintas experiencias en la misma actividad, no hay que preocuparse por la contaminación de los orígenes de los pedidos.

For more information, see [Conversion Variables (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## ¿Por qué Analytics y Analytics for Target (A4T) calculan las cifras de la métrica Visitantes únicos de distinta forma?{#section_0C3B648AB54041F9A2AA839D51791883}

Una de las presuposiciones que se dan al ejecutar una prueba A/B, que emplea la prueba T de estudiante (la métrica de confianza) para elegir al ganador de una prueba, es que hay un plazo de tiempo fijo. La prueba solo es válida estadísticamente si se mira este tamaño de muestra fijo.

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. Si no se ha alcanzado el tamaño de la muestra, la prueba no es tan fiable. Consulte [Cómo no ejecutar una prueba A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) en [el sitio web de Evan Miller](https://www.evanmiller.org/index.html) para obtener más información.

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. Esas personas siguen formando parte de la prueba y se deben contabilizar. Si desea ver solo el número de personas que han estado expuestas durante una semana, puede crear un segmento de visitantes que efectuaron una impresión de actividad y aplicarlo al informe.

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## ¿Por qué en Analytics a veces se cuenta el mismo visitante en diferentes experiencias?   {#section_1397E972D31C4207A142E4D2D6D794A2}

A continuación se explican los motivos por los que puede ser que el mismo visitante se cuente en varias experiencias en [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* Si el visitante utiliza `mbox3rdPartyId`, cuando el visitante anónimo se fusiona con su perfil de ID de terceros,  podría poner al visitante en una experiencia distinta para emparejarlo con el ID de terceros. [!DNL Target] Para obtener más información, consulte [Sincronización de perfiles en tiempo real para mbox con ID de terceros](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] puede estar rastreando diferentes dispositivos como el mismo visitante de una manera diferente que [!DNL Target] rastrea dichos dispositivos: la configuración del ID de terceros en [!DNL Target] es diferente a la de Analytics.

## ¿Admite A4T grupos de informes virtuales?

Los grupos de informes virtuales *no* se incluyen en la lista de grupos de informes y las audiencias de los grupos de informes virtuales no se admiten en los informes de A4T.

## ¿Puedo cambiar el porcentaje de asignación de tráfico en una actividad que utiliza A4T después de activar la actividad?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. Los visitantes que regresan no se ven afectados.

Se recomienda detener la actividad existente y luego crear una nueva, en lugar de cambiar el porcentaje después de la activación. Los informes de la nueva actividad comienzan con los nuevos visitantes y los datos de los visitantes que regresan no provocarán informes incoherentes.
