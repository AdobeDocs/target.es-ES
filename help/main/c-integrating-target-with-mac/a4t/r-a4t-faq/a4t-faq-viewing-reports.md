---
keywords: preguntas frecuentes;faq;analytics para target;a4T;informe;informes;visualización de informes;creación de informes;metodología de contabilización;impresiones;visitantes;visitas;métrica predeterminada;conversiones de actividad;sin especificar
description: Encuentre respuestas a preguntas que se plantean a menudo sobre la visualización de informes al usar Analytics para [!DNL Target] (A4T). A4T le permite usar los informes de Analytics para [!DNL Target] actividades.
title: ¿Encuentra respuestas a preguntas sobre la visualización de informes con A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 66c662e367b64ca51c5d9246cb097a12755d9aff
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 34%

---

# Visualización de informes: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la visualización de informes al utilizar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Puedo ver mi [!DNL Target] datos de actividad en Analysis Workspace? {#workspace}

Puede usar [!DNL Analysis Workspace] para analizar su [!DNL Target] actividades y experiencias. La variable [Panel de Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es) permite ver el alza y la confianza hasta en tres métricas de éxito. También puede profundizar con tablas y visualizaciones.

Para obtener información detallada y ejemplos, abra el [Analytics y Target: Tutorial Prácticas recomendadas de análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por Adobe Experience League.

## ¿Dónde se pueden aplicar los segmentos en Analysis Workspace? {#segmentation}

Los segmentos se utilizan generalmente en la parte superior de un panel en la zona de colocación de segmentos. El segmento se aplica a todas las tablas y visualizaciones del panel. La mayor utilidad de esta técnica es que permite ver cómo afecta una prueba un subconjunto de personas (por ejemplo, qué resultado ha tenido esta prueba entre la gente de España)?

Un segmento también puede colocarse directamente en la tabla de forma libre, pero tenga en cuenta que debe superponerse en toda la tabla para conservar los cálculos de alza y confianza dentro del panel de A4T. Actualmente, los segmentos de nivel de columna no son compatibles con el panel.

## Cuando se aplica un segmento de visita para un [!DNL Target] actividad, ¿por qué se devuelven experiencias no relacionadas? {#activity-segmentation}

La variable de [!DNL Target] enviada a [!DNL Analytics] caduca, de forma predeterminada, en un plazo de 90 días. (Nota: el Servicio de atención al cliente puede ajustar este periodo de caducidad si es necesario). A medida que los visitantes navegan por el sitio a lo largo de esta ventana de caducidad, forman parte de muchos [!DNL Target] actividades, todas las cuales se recopilan en la dimensión .

Cuando segmenta para que una actividad esté presente en una visita, obtiene todas las experiencias que forman parte de esa actividad *plus* cualquier otra experiencia que persista en esa visita.

## Al configurar las métricas de objetivo, ¿por qué no puedo acceder a la Configuración avanzada?

Para actividades que utilizan [!DNL Analytics] como fuente de informes (A4T), la métrica de objetivos usa la variable[!UICONTROL Aumentar recuento y mantener al usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Esta configuración es *not* configurable.

Para obtener más información, consulte &quot;Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada?&quot; en [Definiciones de métricas: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## ¿Debería usar visitantes, visitas o impresiones de actividad como métrica de normalización (es decir, metodología de recuento)? {#metrics}

Existen varias opciones para normalizar métricas en los informes de A4T. Esta métrica, también denominada metodología de contabilización, se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza.

* ***Visitantes únicos*** aumenta cuando un usuario reúne por primera vez los requisitos para una actividad.
* ***Visitas*** aumenta para cada sesión cuando un usuario (visitante único) accede a una actividad, incluso si la actividad no se visualiza en visitas posteriores.
* ***Impresiones de actividad*** aumenta cada vez que se sirve el contenido de la actividad. (Medido por [!DNL Target]).

Cuando un visitante ve una página que contiene una actividad, se establece una variable para ese visitante que incluye el nombre de esa actividad. Consulte los escenarios detallados que se muestran a continuación para ver cómo se compara cada metodología de recuento.

Tenga en cuenta lo siguiente:

* Las métricas anteriores déclencheur cuando un usuario reúne los requisitos para una actividad y el contenido se devuelve de [!DNL Target]. Esto no significa necesariamente que el usuario haya visto la oferta. Si una experiencia de actividad está por debajo del pliegue y el usuario no se desplaza hacia abajo en la página significa que [!DNL Target] proporcionó la oferta, pero el usuario no la vio.
* [!UICONTROL Impresiones de actividad] (medida mediante [!DNL Target]) e [!UICONTROL Instancias] (medida mediante [!DNL Analytics]) son iguales, a menos que haya varias llamadas de mbox en la misma página de la misma actividad. De esta forma se contabilizan varias [!UICONTROL Impresiones de actividad], pero una sola [!UICONTROL Instancia].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) en *Tutorials de Adobe Target*.

## ¿Por qué las &quot;impresiones de la actividad&quot; y las &quot;conversiones de la actividad&quot; son más altas en Analysis Workspace que en Reports &amp; Analytics? {#sametouch}

[!DNL Reports & Analytics] aplica un modelo de atribución de mismo contacto a &quot;impresiones de actividad&quot; y &quot;conversiones de actividad&quot;, mientras que [!DNL Analysis Workspace] muestra las métricas sin procesar, que pueden aparecer infladas debido a la persistencia de la variable [!DNL Target] dimensión.

Para evaluar con precisión [!UICONTROL Impresiones de actividad] y [!UICONTROL Conversiones de actividades] métricas en [!DNL Analysis Workspace], asegúrese de que ambas métricas tengan [!UICONTROL Mismo contacto] modelos de atribución aplicados. Los modelos se pueden aplicar si hace clic en el engranaje de configuración de columna y habilita [!UICONTROL Modelos de atribución no predeterminados] y, a continuación, selecciona [!UICONTROL Mismo contacto]. Obtenga más información sobre la atribución en [Información general sobre Atributos IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) en el *Guía de herramientas de Analytics*.

## ¿Qué significa “conversiones de la actividad” si el especialista en marketing elige una métrica de Analytics durante la configuración de la actividad? {#section_F3EBACF85AF846E9B366A549AAB64356}

Las &quot;conversiones de actividad&quot; están vacías si [!DNL Analytics] se seleccionó como métrica de conversión para la actividad.

## ¿Por qué pone “sin especificar” en los informes de Analytics? ¿Qué quiere decir? {#unspecified}

En otros informes, “sin especificar” significa que los datos no cumplían una regla de clasificación, pero esto no debería suceder nunca en A4T. Si ve “sin especificar”, aún no se ha ejecutado el servicio de clasificación. Los datos de la actividad suelen tardar entre 24 y 72 horas en aparecer en los informes. Aunque las actividades no aparecen en este informe hasta ese momento, todos los datos de visitantes asociados a esas actividades se capturan y aparecen cuando se completa la clasificación.

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

En caso de que la clasificación se haya realizado para esa actividad y siga viendo una fila &quot;No especificado&quot; en el informe, asegúrese de que el informe no esté usando una[!DNL Target] para mostrar los datos. A menos que el informe utilice un [!DNL Target]-métrica específica, que la fila &quot;No especificado&quot; contiene eventos para llamadas que no están asociadas a [!DNL Target]. Esa fila no contendrá ninguna [!DNL Target]- información asociada (por ejemplo, visitantes/visitas/impresiones).

## ¿Por qué [!DNL Target] métricas enviadas a Analytics incluso después de desactivar la actividad. {#section_38AA8380A4D54A18972F1EF3E73E22EF}

La variable de [!DNL Target] enviada a [!DNL Analytics] caduca, de forma predeterminada, en un plazo de 90 días. El Servicio de atención al cliente puede ajustar este periodo de caducidad si es necesario. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

Es posible que vea [!DNL Target] variables enviadas a [!DNL Analytics] después del periodo de caducidad porque la caducidad es de 90 días, pero solo si ese usuario nunca ve otro activado para A4T [!DNL Target] actividad. Si un usuario regresa al sitio el día 45 y ve otra actividad, el contador del valor de la eVar de A4T se restablece a 90 días. Esto significa que la primera campaña del día 1 podría perdurar durante un total de 45 + 90 = 135 días. Si el usuario sigue regresando, es posible que llegue al punto en el que vea las métricas enviadas a [!DNL Analytics] en los informes de actividades mucho más antiguas. A medida que los usuarios eliminan cookies y no regresan al sitio, los números de esa actividad caen, pero aún puede verlos.

Esto significa que las actividades siguen recibiendo vistas de página, visitas, etc., hasta 90 días después de que finalice la actividad para los visitantes que participaron en ella mientras estaba activa. Sin embargo, si consulta la métrica [!UICONTROL Impresiones de actividad], no debería ver ninguna impresión una vez finalizada la actividad.

Este comportamiento es normal. La variable de A4T funciona como cualquier otra eVar: el valor está asociado al usuario hasta que se alcanza la fecha de caducidad (90 días). Como resultado, si una actividad solo está activa durante dos semanas, el valor seguirá estando asociado al usuario durante al menos los siguientes 90 días.

La práctica recomendada consiste en ver solamente los informes de la actividad que correspondan al periodo de tiempo en el cual dicha actividad estaba activa. Las fechas deben configurarse correctamente de forma predeterminada cuando se ve la actividad en [!DNL Analytics], por lo que, a menos que haya ampliado la fecha manualmente, no debería suponer un problema desde el punto de vista de los informes.

Por ejemplo, supongamos que la variable de A4T caduca pasados 90 días y que la prueba está activa del 1 al 15 de enero.

El 1 de enero, el usuario llega al sitio, ve la actividad XYZ una vez y, después, efectúa cinco vistas de página. En las dos semanas siguientes, el usuario no regresa al sitio. Los datos referentes a ese usuario serían los siguientes:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

El usuario vuelve el 1 de febrero y ve otras cinco páginas. No encuentra más actividades de Target y la actividad original ya no está activa. Aunque ya no está activa, la actividad todavía sigue al usuario mediante la persistencia de eVar. Los datos de este momento son estos:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

El usuario vuelve el 1 de marzo y ve una actividad nueva: ABC. Esta vez también ve cinco páginas. Debido a que la actividad XYZ sigue al usuario a través de la persistencia y este usuario luego tiene ABC configurado, verá dos artículos de línea en los informes:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

El usuario regresa el 1 de abril, ve otras cinco páginas y realiza una compra. El vencimiento de 90 días de ese primer valor de eVar se restablece el 1 de abril, por lo que lo ve en el informe. Se atribuye el origen de la conversión a todas las actividades de Target que el usuario ve, pero el número total de conversiones se desduplica:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Puesto que ambas experiencias se vieron antes de la conversión, ambas son las &quot;responsables&quot; del pedido. Sin embargo, en el sistema solo se ha efectuado un pedido y esto se refleja en el total. Para [!DNL Target] informe, porque no está poniendo un [!DNL Target] actividad contra otra actividad para ver cuál es más exitosa, no importa que todas las actividades que vio el usuario obtuvieran crédito. Está comparando los resultados de dos elementos dentro de la actividad única. No es posible que un usuario vea experiencias diferentes en la misma actividad, por lo que no tiene que preocuparse por la contaminación cruzada del crédito de pedido.

Para obtener más información, consulte [Variables de conversión (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) en el *Guía de administración de Analytics*.

## ¿Por qué sigo viendo más impresiones después de desactivar mi actividad? {#deactivated}

Una fuente de impresiones sobre el informe de una actividad de A4T después de la desactivación puede ser el tráfico en modo de control de calidad. Normalmente, Target no registra eventos para una actividad desactivada, pero Analytics no tiene forma de saber que las impresiones provienen del modo de control de calidad. Cuando el informe de actividad de Target se recupera de Analytics, muestra estas impresiones. Esto funciona como está diseñado, ya que los clientes necesitan una forma de comprobar los informes de A4T aunque la actividad no esté activa mediante el modo de control de calidad.

## ¿Por qué Analytics y Analytics for Adobe Target (A4T) calculan las cifras de la métrica Visitantes únicos de distinta forma? {#section_0C3B648AB54041F9A2AA839D51791883}

Al ejecutar una prueba A/B, que usa la variable [Prueba T de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (la métrica de confianza) para elegir el ganador de una prueba; uno de los supuestos es que hay un horizonte temporal fijo. La prueba no es válida estadísticamente a menos que esté mirando ese tamaño de muestra fijo.

La variable [!UICONTROL Visitantes únicos] es diferente en [!DNL Analytics] y [!DNL Target] solo cuando observa un periodo más corto que la prueba real. Si no ha alcanzado el tamaño de la muestra, la prueba no es tan fiable. Consulte [Cómo no ejecutar una prueba A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) en [el sitio web de Evan Miller](https://www.evanmiller.org/index.html) para obtener más información.

La variable [!UICONTROL Visitantes únicos] muestra el número de personas que han estado expuestas a la prueba y que han visitado el sitio durante el período de tiempo especificado. Estas personas forman parte de la prueba y deben incluirse en el recuento. Si desea ver solo el número de personas que han estado expuestas durante una semana, puede crear un segmento de visitantes que efectuaron una impresión de actividad y aplicarlo al informe.

Puede acortar la cantidad de tiempo que se tarda en [!DNL Target] persiste hasta una sesión; sin embargo, esto es problemático en las pruebas en las que el evento de conversión no es tan probable que ocurra dentro de la misma sesión.

## ¿Por qué en Analytics a veces se cuenta el mismo visitante en diferentes experiencias?   {#section_1397E972D31C4207A142E4D2D6D794A2}

A continuación se explican los motivos por los que puede ser que el mismo visitante se cuente en varias experiencias en [!DNL Analytics]:

* La variable [!DNL Target] El perfil de caducó, pero el [!DNL Analytics] la cookie sigue ahí. En esta situación, [!DNL Target] vuelve a evaluar al usuario, pero [!DNL Analytics] considera que el visitante es la misma persona.
* Si el visitante está utilizando la variable `mbox3rdPartyId`, cuando el visitante anónimo se fusiona con el perfil de ID de terceros, [!DNL Target] podría poner al visitante en una experiencia diferente para que coincida con el ID de terceros. Para obtener más información, consulte [Sincronización de perfiles en tiempo real para mbox con ID de terceros](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] puede estar rastreando diferentes dispositivos como el mismo visitante de una manera diferente a [!DNL Target] rastrea esos dispositivos: la configuración del ID de terceros en [!DNL Target] es diferente a en Analytics.

## ¿Admite A4T grupos de informes virtuales? {#virtual}

Aunque los grupos de informes virtuales no están incluidos en la variable [!UICONTROL Grupo de informes] cualquier dato de A4T compartido con un grupo de informes vinculado a un grupo de informes virtuales en [!DNL Analytics] tiene acceso a esos datos. Tenga en cuenta que cualquier audiencia creada a partir de grupos de informes virtuales no se puede volver a compartir en [!DNL Target].

## ¿Puedo cambiar el porcentaje de asignación de tráfico en una actividad que utiliza A4T después de activar la actividad?

Cambiar el porcentaje de asignación de tráfico en una actividad después de la activación puede provocar informes incoherentes en [!DNL Analytics] porque el cambio solo afecta a los visitantes nuevos. Los visitantes que regresan no se ven afectados.

Se recomienda detener la actividad existente y luego crear una nueva, en lugar de cambiar el porcentaje después de la activación. Los informes de la nueva actividad comienzan con nuevos visitantes y los datos de los visitantes que regresan no generan informes incoherentes.

## ¿Cómo se cuentan las visitas en Analytics y el crédito de conversión asignados en una actividad de segmentación automática que utiliza A4T?

Cuando un visitante cumple los requisitos, visualiza contenido o convierte en una actividad de A4T, [!DNL Target] envía datos de evento a [!DNL Analytics]. Estos datos de evento permiten [!DNL Analytics] para atribuir eventos de conversión y otros eventos de flujo de navegación que se produzcan en la página al valor [!DNL Target] actividades y experiencias.

A continuación se indican algunos puntos que hay que tener en cuenta al ver [!DNL Analytics] informes:

* En general, como práctica recomendada, la ventana de informes debe comenzar desde la fecha de inicio de la actividad.
* Si se produce una conversión fuera de la ventana del informe, la conversión no es visible en [!DNL Analytics].
* Cuando se encuentra en la parte &quot;segmentada&quot; del tráfico para [!UICONTROL Segmentación automática] , es posible que los visitantes vean experiencias diferentes de una sesión a otra. Por ejemplo, si su perfil o contexto ha cambiado y [!DNL Target]Los algoritmos de aprendizaje automático de deciden que es más probable que se conviertan en una nueva experiencia. A medida que los visitantes pasan de una experiencia a otra, el recuento de visitas aumenta con cada experiencia vista. A diferencia de las actividades normales de prueba A/B, las experiencias se mantienen fieles a los visitantes en todas las visitas.
* Si un visitante ve varias experiencias en todas las visitas, cualquier conversión siempre se atribuye a la última experiencia que vio el visitante. Como se ha mencionado, el recuento de visitas aumenta con cada experiencia que vio el visitante. Esto puede reducir artificialmente las tasas de conversión por experiencia al ver las experiencias en el[!UICONTROL Segmentado]&quot; en [!DNL Adobe Analytics] informes.
