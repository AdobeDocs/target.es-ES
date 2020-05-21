---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Creación de actividad
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 47%

---


# Creación de actividad{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Seleccione una métrica de éxito final para la actividad. Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

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
