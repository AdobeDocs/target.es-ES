---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Creación de actividad
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 25%

---


# Creación de actividad{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Seleccione una métrica de éxito final para la actividad. Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## Crear una actividad que utilice Analytics como fuente de sistema de informes

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

## Compatibilidad de Analytics para Destinatario (A4T) con actividades de asignación automática {#a4t-aa}

Hemos actualizado la integración de Adobe Target a Adobe Analytics, conocida como [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md).

[!UICONTROL Las actividades de asignación] automática ahora admiten [!UICONTROL Analytics para Destinatario]. Esta integración le permite utilizar la función de bandido multiarmado de asignación automática para dirigir el tráfico a las experiencias ganadoras, mientras utiliza una métrica de [!DNL Adobe Analytics] objetivo y/o capacidades de sistema de informes y análisis [!DNL Adobe Analytics] . Si ya ha [implementado A4T para su uso con actividades](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)de Prueba A/B y de segmentación de experiencias, ¡ya está listo!

En primer lugar:

1. Cree una actividad de prueba A/B y seleccione Asignar **[!UICONTROL automáticamente a la mejor experiencia]** como método **[!UICONTROL de asignación de]** tráfico en la página [!UICONTROL Segmentación] .
1. Seleccione **[!UICONTROL Adobe Analytics]** para la fuente **[!UICONTROL de]** Sistema de informes en la página **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.
1. Elija una métrica de objetivo principal.

   Elija **[!UICONTROL Conversión]** para [!DNL Adobe Target] especificar el objetivo de optimización.

   O

   Elija **[!UICONTROL Usar una métrica]** de Analytics y, a continuación, seleccione una métrica [!DNL Analytics] para utilizarla como objetivo de optimización. Puede utilizar una métrica de conversión predeterminada [!DNL Analytics] o un evento [!DNL Analytics] personalizado.

1. Guarde y active la actividad.

   [!UICONTROL La asignación] automática utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a la experiencia que maximiza la métrica de objetivos.

1. Utilice la ficha **[!UICONTROL Informes]** para vista del sistema de informes de la actividad según las [!DNL Adobe Analytics] métricas que elija. Haga clic en **[!UICONTROL Vista en Analytics]** para profundizar y segmentar aún más los datos de sistema de informes.

### Métricas de objetivo admitidas

A4T para la asignación  automática le permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

A4T para la asignación  automática requiere que elija una métrica basada en un evento binomio, es decir, un evento que se produce o no, por ejemplo un clic, una conversión, un pedido, etc. (Estos tipos de eventos también se conocen a veces como Bernoulli, eventos binarios o discretos).

A4T para la asignación  automática no admite la optimización para métricas continuas como ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. (Estos tipos de métricas no admitidos también se conocen como métricas no binomiales o no Bernoulli).

Los siguientes tipos de métricas no son compatibles como métricas de objetivo principales:

* [!DNL Adobe Target] métricas de ingresos y participación
* [!DNL Adobe Analytics] métricas de ingresos y participación

   >[!NOTE]
   >
   >Puede que sea posible seleccionar [!DNL Analytics] las métricas de participación e ingresos como métrica objetivo principal porque [!DNL Target] no puede identificar todas las métricas de participación e ingresos de [!DNL Analytics]. Tenga cuidado de seleccionar solo métricas de conversión binomiales o eventos personalizados de [!DNL Analytics].

* Métricas calculadas de Adobe Analytics

### Limitaciones y notas

* El origen del sistema de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] o viceversa una vez activada una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* [!DNL Target] utiliza el modelo de atribución de &quot;mismo toque&quot; en la implementación de asignación automática de A4T.

Para obtener más información, consulte [Atribución general](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) en la Guía *de herramientas* de Analytics.
