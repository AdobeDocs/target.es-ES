---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Crear una actividad que utilice A4T como fuente de sistema de informes
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 20%

---


# Crear una actividad que utilice Analytics como fuente de sistema de informes

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Seleccione una métrica de éxito final para la actividad. Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## Cree la actividad

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. Haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. Seleccione el tipo de actividad y comience a configurarla.
1. Cuando llegue a la fase de **[!UICONTROL configuración]** en el flujo de trabajo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y escriba el nombre de su empresa.
1. Seleccione un grupo de informes.

   Puede seleccionar cualquier grupo de informes que haya disponible en [!DNL Analytics]. El grupo de informes define dónde estarán disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * No ve el grupo de informes que esperaba.

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   Si aún no aparece el grupo de informes en la lista, póngase en contacto con el [Servicio de atención al cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia.
1. Especifique el objetivo de la actividad.

   Debe seleccionar una métrica de éxito para utilizarla como objetivo en cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. Por ejemplo, puede controlar los clics en una página, algo que no se suele rastrear en [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] los segmentos están disponibles en el informe [!DNL Target] Actividades.

1. Haga clic en **[!UICONTROL Guardar]**.

## Compatibilidad de Analytics para Destinatario (A4T) con la asignación automática y las actividades de Destinatario automático {#a4t-aa}

Hemos actualizado la integración de Adobe Target a Adobe Analytics, conocida como [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md). Las actividades de asignación automática y Destinatario automático ahora admiten Analytics para Destinatario.

Esta integración le permite:

* Utilice la capacidad multi-armed bandit de asignación [automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)para dirigir el tráfico a las experiencias ganadoras
* Utilice el algoritmo de aprendizaje automático del conjunto de Destinatario [](/help/c-activities/auto-target/auto-target-to-optimize.md)automático para elegir la mejor experiencia para cada visitante en función de su perfil, comportamiento y contexto, todo mientras utiliza una métrica de [!DNL Adobe Analytics] objetivos y las capacidades de sistema de informes y análisis enriquecidas [!DNL Adobe Analytics]de los mismos.

Asegúrese de que ha [implementado A4T para utilizarlo con actividades](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)de Prueba A/B y de segmentación de experiencias. Si utiliza `analyticsLogging = client_side`, también debe pasar el `sessionId` valor a [!DNL Analytics]. Para obtener más información, consulte el sistema de informes [](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) Analytics para Destinatario (A4T) en la guía SDK *de* Adobe Target.

En primer lugar:

1. Al crear una actividad de prueba A/B, en la página **[!UICONTROL Segmentación]** , seleccione una de las siguientes opciones como método **[!UICONTROL de asignación]** de tráfico:

   * Asignar automáticamente a la mejor experiencia
   * Destinatario automático para experiencias personalizadas

1. Seleccione **[!UICONTROL Adobe Analytics]** para la fuente **[!UICONTROL de]** Sistema de informes en la página **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

1. Elija una métrica de objetivo principal.

   * Elija **[!UICONTROL Conversión]** para [!DNL Adobe Target] especificar el objetivo de optimización.
   * Elija **[!UICONTROL Usar una métrica]** de Analytics y, a continuación, seleccione una métrica [!DNL Analytics] para utilizarla como objetivo de optimización. Puede utilizar una métrica de conversión predeterminada [!DNL Analytics] o un evento [!DNL Analytics] personalizado.

1. Guarde y active la actividad.

   [!UICONTROL La asignación] automática utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL El Destinatario] automático utilizará la métrica seleccionada para optimizar la actividad, lo que llevará a visitantes a una mejor experiencia personalizada.

1. Utilice la ficha **[!UICONTROL Informes]** para vista del sistema de informes de la actividad según las [!DNL Adobe Analytics] métricas que elija. Haga clic en **[!UICONTROL Vista en Analytics]** para profundizar y segmentar aún más los datos de sistema de informes.

### Métricas de objetivo admitidas

[!UICONTROL A4T] para asignación  automática y Destinatario  automático le permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4T] para la asignación  automática y el Destinatario  automático requiere que elija una métrica basada en un evento binomial, es decir, un evento que se produce o no, por ejemplo un clic, una conversión, un pedido, etc. (Estos tipos de eventos también se conocen a veces como Bernoulli, eventos binarios o discretos).

[!UICONTROL A4T] para la asignación  automática y el Destinatario  automático no admite la optimización para métricas continuas como ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. (Estos tipos de métricas no admitidos también se conocen como métricas no binomiales o no Bernoulli).

Los siguientes tipos de métricas no son compatibles como métricas de objetivo principales:

* [!DNL Adobe Target] métricas de ingresos y participación
* [!DNL Adobe Analytics] métricas de ingresos y participación

   Puede que sea posible seleccionar una métrica de participación [!DNL Analytics] o ingresos como métrica de objetivo principal porque [!DNL Target] no puede identificar y excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Tenga cuidado de seleccionar solo métricas de conversión binomiales o eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

### Limitaciones y notas

Algunas limitaciones y notas se aplican tanto a la asignación automática como al Destinatario automático. Otras limitaciones y notas se aplican a un tipo de actividad o al otro.

#### Asignación automática y Destinatario automático

* La fuente de sistema de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* [!DNL Target] utiliza el modelo de atribución de &quot;mismo toque&quot; en la implementación de A4T de asignación [!UICONTROL automática] .

#### Asignación automática

* [!UICONTROL Los modelos de asignación] automática siguen entrenándose cada dos horas, como de costumbre.

#### Segmentación automática

* [!UICONTROL Los modelos de Destinatario] automático siguen entrenándose cada 24 horas, como de costumbre. Sin embargo, los datos de eventos de conversión procedentes de [!DNL Analytics] se retrasan de seis a 24 horas adicionales. Este retraso significa que la distribución del tráfico por [!DNL Target] rastreará los últimos eventos registrados en [!DNL Analytics]. Esto tendrá el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez; el rendimiento de la actividad reflejará más de cerca el comportamiento [!DNL Analytics] de conversión después de transcurridos cinco días. Debe considerar el uso de la asignación  automática en lugar del Destinatario  automático para actividades de corta duración, donde la mayoría del tráfico se produce en los primeros cinco días de vida de la actividad.
* Cuando se utilizan [!DNL Analytics] como fuente de datos para una actividad de Destinatario  automático, las sesiones se consideran finalizadas después de transcurridas seis horas. Las conversiones que se produzcan después de seis horas no se contarán.

Para obtener más información, consulte Modelos [de atribución y ventanas](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/models.html) retroactivas en la Guía *de herramientas de* Analytics.
