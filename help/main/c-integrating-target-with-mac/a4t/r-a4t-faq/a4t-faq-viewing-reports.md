---
keywords: preguntas frecuentes;faq;analytics para target;a4T;informe;informes;visualización de informes;creación de informes;metodología de contabilización;impresiones;visitantes;visitas;métrica predeterminada;conversiones de actividad;sin especificar
description: Encuentre respuestas a preguntas que se plantean a menudo sobre la visualización de informes al usar Analytics for [!DNL Target] (A4T). A4T le permite utilizar los informes de Analytics para  [!DNL Target] actividades.
title: ¿Desea encontrar respuestas a preguntas sobre la visualización de informes con A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 25%

---

# Visualización de informes: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la visualización de informes al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Puedo ver mis datos de actividad [!DNL Target] en [!DNL Analysis Workspace]? {#workspace}

+++Respuesta
Puede usar [!DNL Analysis Workspace] para analizar las actividades y experiencias de [!DNL Target]. El [panel de Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=es) le permite ver el alza y la confianza de hasta tres métricas de éxito. También puede profundizar utilizando tablas y visualizaciones.

Para obtener información detallada y ejemplos, abra el [tutorial de Analytics y Target: Prácticas recomendadas de análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por [!UICONTROL Adobe Experience League].

+++

## ¿Dónde se pueden aplicar los segmentos en [!DNL Analysis Workspace]? {#segmentation}

+++Respuesta
Los segmentos se utilizan principalmente en la parte superior de un panel en la zona de colocación de segmentos. El segmento se aplica a todas las tablas y visualizaciones del panel. Esta técnica es más útil para ver cómo afecta la prueba a un subconjunto de personas (por ejemplo, ¿cómo ha funcionado esta prueba para personas en el Reino Unido)?

Un segmento también se puede superponer directamente en la tabla de forma libre, pero tenga en cuenta que debe superponerlo en toda la tabla para conservar los cálculos de alza y confianza dentro del panel A4T. Los segmentos de nivel de columna no son compatibles actualmente con el panel.

+++

## ¿Puedo aplicar el modelo de Attribution IQ &quot;Mismo contacto&quot; en [!DNL Analysis Workspace]?

+++Respuesta
Cuando use [!DNL Target] impresiones y conversiones de actividad en [!DNL Analysis Workspace], aplique el modelo de Attribution IQ &quot;Mismo contacto&quot; a las métricas para garantizar un recuento preciso. Para aplicar un [modelo de atribución no predeterminado](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=es), haga clic con el botón derecho en la métrica para **modificar Configuración de columna > habilitar Utilizar modelo de atribución no predeterminado > seleccione Mismo modelo de contacto**. Si no se aplica este modelo, las métricas se sobrevaloran.

Todos los paquetes actuales de [!DNL Adobe Analytics] pueden agregar este modelo con [!UICONTROL Attribution IQ]. Si no tiene acceso a [!UICONTROL Attribution IQ], confíe en los datos de A4T en [!UICONTROL Reports & Analytics].

+++

## Cuando se aplica un segmento de visita para una actividad [!DNL Target] específica, ¿por qué se devuelven experiencias no relacionadas? {#activity-segmentation}

+++Respuesta
La variable [!DNL Target] enviada a [!DNL Analytics] tiene un período de caducidad predeterminado de 90 días. (Nota: el Servicio de atención al cliente puede ajustar este periodo de caducidad si es necesario). A medida que los visitantes navegan por el sitio durante este período de caducidad, forman parte de muchas actividades [!DNL Target], que se acumulan en la dimensión.

Cuando segmenta para que una actividad esté presente en una visita, obtiene todas las experiencias que forman parte de esa actividad *además* de cualquier otra experiencia que persista en esa visita.

+++

## Al configurar mi [!UICONTROL Goal Metrics], ¿por qué no puedo acceder a [!UICONTROL Advanced Settings]?

+++Respuesta
Para las actividades que usan [!DNL Analytics] como fuente de informes (A4T), la métrica de objetivo usa la configuración &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; y &quot;[!UICONTROL On Every Impression]&quot;. Estas configuraciones *no* se pueden configurar.

Para obtener más información, consulte &quot;Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de configuración avanzada?&quot; en [Definiciones de métricas: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## ¿Debería usar visitantes, visitas o impresiones de actividad como métrica de normalización (es decir, metodología de recuento)? {#metrics}

+++Respuesta
Existen varias opciones para normalizar métricas en la creación de informes de A4T. Esta métrica, también denominada metodología de contabilización, se convierte en el denominador del cálculo del alza. También afecta a la manera en que se agregan los datos antes de que se calcule la confianza.

* ***Los visitantes únicos*** aumentan una vez cuando un usuario cumple los requisitos por primera vez para una actividad.
* ***Las visitas*** aumentan en cada sesión una vez que un usuario (visitante único) entra en una actividad, aunque la actividad no se vea en visitas posteriores.
* ***Impresiones de actividad*** aumenta cada vez que se sirve el contenido de la actividad. (Medido por [!DNL Target]).

Cuando un visitante ve una página que contiene una actividad, se establece una variable para ese visitante que incluye el nombre de esa actividad. Consulte los escenarios detallados que se muestran a continuación para ver cómo se compara cada metodología de recuento.

Tenga en cuenta lo siguiente:

* Las métricas anteriores entran en déclencheur cuando un usuario cumple los requisitos para una actividad y el contenido se devuelve de [!DNL Target]. Esto no significa necesariamente que el usuario haya visto la oferta. Si una experiencia de actividad está por debajo del pliegue y el usuario no se desplaza hacia abajo en la página significa que [!DNL Target] proporcionó la oferta, pero el usuario no la vio.
* [!UICONTROL Activity Impressions] (medido por [!DNL Target]) y [!UICONTROL Instances] (medido por [!DNL Analytics]) son iguales, a menos que haya varias llamadas de mbox en la misma página de la misma actividad. Esto hace que se cuenten varios [!UICONTROL Activity Impressions], pero solo un único [!UICONTROL Instance].

Para obtener más información, consulte [Cómo configurar informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es) en *Tutorials de Adobe Target*.

+++

## ¿Por qué las &quot;impresiones de actividad&quot; y las &quot;conversiones de actividad&quot; son más altas en [!DNL Analysis Workspace] que en [!UICONTROL Reports & Analytics]? {#sametouch}

+++Respuesta
[!DNL Reports & Analytics] aplica un modelo de atribución del mismo contacto a las &quot;impresiones de actividad&quot; y a las &quot;conversiones de actividad&quot;, mientras que [!DNL Analysis Workspace] muestra las métricas sin procesar, que pueden aparecer infladas debido a la persistencia de la dimensión [!DNL Target].

Para evaluar las métricas precisas [!UICONTROL Activity Impressions] y [!UICONTROL Activity Conversions] en [!DNL Analysis Workspace], asegúrese de que ambas métricas tengan [!UICONTROL Same Touch] modelos de atribución aplicados. Los modelos se pueden aplicar haciendo clic en el engranaje de configuración de columna, habilitando [!UICONTROL Non-default attribution models] y seleccionando [!UICONTROL Same Touch]. Obtenga más información acerca de la atribución en [Información general sobre la inteligencia de atributos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) en la *Guía de herramientas de Analytics*.

+++

## ¿Qué significa &quot;conversiones de la actividad&quot; si el especialista en marketing elige una métrica de [!DNL Analytics] durante la configuración de la actividad? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Respuesta
&quot;Conversiones de la actividad&quot; está vacío si se seleccionó una métrica de [!DNL Analytics] como métrica de conversión de la actividad.

+++

## ¿Por qué veo &quot;sin especificar&quot; en los informes de [!DNL Analytics]? ¿Qué quiere decir? {#unspecified}

+++Respuesta
En otros informes, &quot;sin especificar&quot; significa que los datos no cumplían una regla de clasificación, pero esto no debería suceder nunca en A4T. Si ve “sin especificar”, aún no se ha ejecutado el servicio de clasificación. Los datos de la actividad suelen tardar entre 24 y 72 horas en aparecer en los informes. Aunque las actividades no aparecen en este informe hasta llegado ese momento, todos los datos de visitantes asociados a esas actividades se capturan y aparecen cuando se completa la clasificación.

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Si la clasificación se realizó para esa actividad y aún ve una fila &quot;Sin especificar&quot; en el informe, asegúrese de que el informe no esté usando una métrica que no sea [!DNL Target] para mostrar los datos. A menos que el informe esté usando una métrica específica de [!DNL Target], esa fila &quot;Sin especificar&quot; contiene eventos para llamadas que no están asociadas con [!DNL Target]. Esa fila no contendrá información asociada con [!DNL Target] (por ejemplo, visitantes/visitas/impresiones).

+++

## ¿Por qué se envían [!DNL Target] métricas a [!DNL Analytics] incluso después de desactivar la actividad? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Respuesta
La variable [!DNL Target] enviada a [!DNL Analytics] tiene un período de caducidad predeterminado de 90 días. El Servicio de atención al cliente puede ajustar este periodo de caducidad si es necesario. Esta configuración es global para todas las actividades; sin embargo, no debe ajustarse para un caso.

Puede ver [!DNL Target] variables enviadas a [!DNL Analytics] después del período de caducidad porque esta caduca a los 90 días, pero solo si ese usuario nunca ve otra actividad [!DNL Target] habilitada para A4T. Si un usuario regresa al sitio el día 45 y ve otra actividad, el contador del valor de la eVar de A4T se restablece a 90 días. Esto significa que la primera campaña del día 1 podría perdurar durante un total de 45 + 90 = 135 días. Si el usuario sigue regresando, es posible que llegue al punto en el que ve las métricas enviadas a [!DNL Analytics] en sus informes desde actividades mucho más antiguas. A medida que los usuarios eliminan las cookies y no regresan al sitio, los números de esa actividad disminuyen, pero aún puede verlos.

Esto significa que las actividades siguen teniendo vistas de página, visitas, etc., durante un máximo de 90 días después de que finalice la actividad para los visitantes que formaron parte de la actividad mientras estaba activa. Sin embargo, si observa la métrica [!UICONTROL Activity Impressions], no debería ver ninguna impresión una vez finalizada la actividad.

Este comportamiento es normal. La variable de A4T funciona como cualquier otra eVar: el valor está asociado al usuario hasta que se alcanza la fecha de caducidad (90 días). Como resultado, si una actividad está activa solo durante dos semanas, el valor sigue asociado con el usuario durante al menos los próximos 90 días.

La práctica recomendada consiste en ver solamente los informes de la actividad que correspondan al periodo de tiempo en el cual dicha actividad estaba activa. Las fechas deben configurarse correctamente de forma predeterminada al ver la actividad en [!DNL Analytics], por lo que, a menos que haya ampliado manualmente la fecha, no debería suponer un problema desde el punto de vista de la creación de informes.

Por ejemplo, supongamos que la variable A4T caduca pasados 90 días y que la prueba está activa del 1 al 15 de enero.

El 1 de enero, el usuario llega al sitio, ve la actividad XYZ una vez y, después, efectúa cinco vistas de página. En las dos semanas siguientes, el usuario no regresa al sitio. Los datos referentes a ese usuario serían los siguientes:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

El usuario regresa el 1 de febrero, ve cinco páginas más y no encuentra más actividades de Target y la actividad original ya no está activa. Aunque ya no está activa, la actividad todavía sigue al usuario mediante la persistencia de eVar. Los datos de este momento son estos:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

El usuario vuelve el 1 de marzo y ve una actividad nueva: ABC. Esta vez también ve cinco páginas. Como la actividad XYZ sigue al usuario a través de la persistencia y este usuario tiene ABC establecido, verá dos elementos de línea en los informes:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

El usuario regresa el 1 de abril, ve otras cinco páginas y realiza una compra. La caducidad de 90 días de ese primer valor de eVar se restablece el 1 de abril, por lo que verá eso en los informes. Se atribuye el origen de la conversión a todas las actividades de Target que el usuario ve, pero el número total de conversiones se desduplica:

| Nombre de la actividad | Instancias (impresiones) | Vistas de páginas | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Dado que ambas experiencias se vieron antes de la conversión, ambas reciben &quot;crédito&quot; por el pedido. Sin embargo, en el sistema solo se ha efectuado un pedido y esto se refleja en el total. Para la creación de informes de [!DNL Target], ya que no va a colocar una actividad de [!DNL Target] en otra actividad para ver cuál tiene más éxito, no importa que todas las actividades que vio el usuario obtengan crédito. Está comparando los resultados de dos elementos dentro de la misma actividad. Un usuario no puede ver diferentes experiencias en la misma actividad para que no tenga que preocuparse por la contaminación cruzada del crédito de pedidos.

Para obtener más información, consulte [Variables de conversión (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) en la *Guía de administración de Analytics*.

+++

## ¿Por qué sigo viendo más impresiones después de desactivar mi actividad? {#deactivated}

+++Respuesta
Una fuente de impresiones en el informe de una actividad de A4T después de la desactivación puede ser el tráfico en modo de control de calidad. Target normalmente no registra eventos para una actividad desactivada, pero Analytics no tiene forma de saber que las impresiones provienen del modo de control de calidad. Cuando se recupera el informe de actividad de Target de Analytics, muestra estas impresiones. Esto funciona según lo diseñado porque los clientes necesitan una forma de comprobar los informes de A4T aunque la actividad no esté activa mediante el modo de control de calidad.

+++

## ¿Por qué [!DNL Analytics] y [!UICONTROL Analytics for Adobe Target] (A4T) calculan los números de la métrica [!UICONTROL Unique Visitors] de forma diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Respuesta
Cuando ejecuta una prueba A/B, que usa la prueba T de [Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (la métrica de confianza) para elegir al ganador de una prueba, una de las suposiciones es que hay un horizonte de tiempo fijo. La prueba no es estadísticamente válida a menos que observe ese tamaño de muestra fijo.

La métrica [!UICONTROL Unique Visitors] es diferente en [!DNL Analytics] y [!DNL Target] solo cuando se está observando un período más corto que la prueba real. Si no ha alcanzado el tamaño de la muestra, la prueba no es tan fiable. Consulte [Cómo no ejecutar una prueba A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) en [el sitio web de Evan Miller](https://www.evanmiller.org/index.html) para obtener más información.

La métrica [!UICONTROL Unique Visitors] muestra el número de personas que han estado expuestas a la prueba y que han visitado el sitio durante el período de tiempo especificado. Esas personas son parte de la prueba y deben ser contadas. Si desea ver solo el número de personas que han estado expuestas durante una semana, puede crear un segmento de visitantes que efectuaron una impresión de actividad y aplicarlo al informe.

Puede acortar el tiempo que la variable [!DNL Target] persiste hasta una sesión; sin embargo, esto resulta problemático en las pruebas en las que el evento de conversión no es tan probable que ocurra dentro de la misma sesión.

+++

## ¿Por qué a veces se cuenta el mismo visitante en varias experiencias en [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Respuesta
En la siguiente lista se explican los motivos por los cuales se pudo contar el mismo visitante en varias experiencias en [!DNL Analytics]:

* El perfil [!DNL Target] expiró pero la cookie [!DNL Analytics] sigue ahí. En este caso, [!DNL Target] vuelve a evaluar al usuario, pero [!DNL Analytics] considera que el visitante es la misma persona.
* Si el visitante usa `mbox3rdPartyId`, cuando el visitante anónimo se combina con el perfil de ID de terceros, [!DNL Target] podría poner al visitante en una experiencia diferente para emparejarlo con el ID de terceros. Para obtener más información, consulte [Sincronización de perfiles en tiempo real para mbox con ID de terceros](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] podría estar realizando un seguimiento de diferentes dispositivos como si fuera el mismo visitante de forma distinta al seguimiento que hace [!DNL Target] de dichos dispositivos: la configuración del ID de terceros en [!DNL Target] es diferente que en Analytics.

+++

## ¿Admite A4T grupos de informes virtuales? {#virtual}

+++Respuesta
Aunque los grupos de informes virtuales no se incluyen en la lista [!UICONTROL Report Suite], cualquier dato de A4T compartido con un grupo de informes vinculado a un grupo de informes virtuales en [!DNL Analytics] tiene acceso a esos datos. Tenga en cuenta que cualquier audiencia creada a partir de un grupo de informes virtuales no se puede compartir de nuevo con [!DNL Target].

+++

## ¿Puedo cambiar el porcentaje de asignación de tráfico en una actividad que utiliza A4T después de activar la actividad?

+++Respuesta
Cambiar el porcentaje de asignación de tráfico en una actividad después de la activación puede generar informes incoherentes en [!DNL Analytics] porque el cambio solo afecta a los nuevos visitantes. Los visitantes que regresan no se ven afectados.

Se recomienda detener la actividad existente y luego crear una nueva, en lugar de cambiar el porcentaje después de la activación. Los informes de la nueva actividad comienzan con los nuevos visitantes y los datos de los visitantes que regresan no provocan informes incoherentes.

+++

## ¿Cómo se cuentan las visitas en [!DNL Analytics] y cómo se asigna el crédito de conversión en una actividad de [!UICONTROL Auto-Target] que usa A4T?

+++Respuesta
Cuando un visitante cumple los requisitos, ve contenido o convierte en una actividad de A4T, [!DNL Target] envía datos de evento a [!DNL Analytics]. Estos datos de evento permiten que [!DNL Analytics] atribuya eventos de conversión y otros eventos de flujo de navegación que se producen en la página a las actividades y experiencias de [!DNL Target] relevantes.

Tenga en cuenta lo siguiente al ver los informes de [!DNL Analytics]:

* En general, como práctica recomendada, la ventana de creación de informes debe comenzar desde la fecha de inicio de la actividad.
* Si se produce una conversión fuera de la ventana del informe, la conversión no será visible en [!DNL Analytics].
* En la porción &quot;segmentada&quot; del tráfico de [!UICONTROL Auto-Target] actividades, los visitantes pueden ver diferentes experiencias de una sesión a la siguiente. Por ejemplo, si su perfil o contexto ha cambiado y los algoritmos de aprendizaje automático de [!DNL Target] deciden que es más probable que se conviertan en una nueva experiencia. A medida que los visitantes pasan de una experiencia a otra, el recuento de visitas aumenta con cada experiencia vista. Esto es distinto de las actividades normales de las pruebas A/B, donde las experiencias se pegan a un visitante en todas las visitas.
* Si un visitante ve varias experiencias en todas las visitas, cualquier conversión siempre se atribuye a la última experiencia que vio el visitante. Como se ha mencionado, el recuento de visitas aumenta para cada experiencia que vio el visitante. Esto puede reducir artificialmente las tasas de conversión por experiencia al ver experiencias bajo la dimensión &quot;[!UICONTROL Targeted]&quot; en [!DNL Adobe Analytics] informes.

+++

## ¿Cómo realizo un seguimiento de las impresiones de actividad en [!DNL Analysis Workspace] al usar [!UICONTROL Analytics for Target] (A4T)? {#activity-impressions}

+++Respuesta

Para ver impresiones de actividad en [!DNL Analysis Workspace]:

1. En la interfaz de usuario de [!DNL Target], haga clic en **[!UICONTROL View in Analytics]**.
1. Agregar la columna **[!UICONTROL Activity Impressions]** al informe [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank}.
1. En la columna **[!UICONTROL Activity Impressions]**, haga clic en el icono [!UICONTROL Gear].
1. Haga clic en **[!UICONTROL Use non-default attribution model]**.
1. Seleccione **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++