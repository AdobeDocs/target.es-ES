---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Creación de actividad
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Creación de actividad{#activity-creation}

Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).

Antes de configurar una actividad que use Analytics como fuente de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar métricas adicionales en cualquier momento en Analytics, es necesario que especifique una métrica en particular en torno a la cual desea que gire la prueba.

Crear una actividad de Target Standard que use Analytics como origen para la creación de informes es como configurar una actividad normal de Target Standard con algunas diferencias importantes. Por ejemplo, no se puede seleccionar un segmento para la creación de informes mientras se crea la actividad, ya que se pueden aplicar todos los segmentos disponibles en Analytics cuando se está viendo un informe.

1. Haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >Un nombre de actividad no puede incluir el carácter “%” si se usa Analytics como fuente de informes.

1. Seleccione el tipo de actividad y comience a configurarla.
1. Cuando llegue a la fase de **[!UICONTROL configuración]** en el flujo de trabajo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y escriba el nombre de su empresa.
1. Seleccione un grupo de informes.

   Puede seleccionar cualquier grupo de informes que haya disponible en Adobe Analytics. El grupo de informes define dónde estarán disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.
   Es posible que deba comprobar su empresa de Analytics. Si la cuenta de Experience Cloud está ligada a más de una compañía de Analytics, cierre la sesión de Target e inicie sesión en Analytics con la compañía correcta. A continuación, regrese a Target, y se cargarán los grupos de informes.

   * No ve el grupo de informes que esperaba.
   Solo se podrán seleccionar los grupos de informes que estén aprovisionados para conectarse a Adobe Target. Si no ve los grupos de informes previstos, cierre la sesión y vuelva a iniciarla en Adobe Experience Cloud para probar de nuevo.

   Si aún no aparece el grupo de informes en la lista, póngase en contacto con el [Servicio de atención al cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia..
1. Especifique el objetivo de la actividad.

   Debe seleccionar una métrica de éxito que se utilizará como objetivo en cada prueba. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier métrica de Analytics disponible en el selector de métricas de Analytics.

   >[!NOTE]
   >
   >Puede enviar una métrica personalizada basada en Target a Analytics, en lugar de emplear únicamente los datos de Analytics. Por ejemplo, puede controlar los clics en una página, algo que no se suele rastrear en Analytics. Esta métrica personalizada se envía a Analytics automáticamente desde el servidor de Target y aparece como la métrica “Conversión de Target” en el selector de métricas de Analytics. La métrica Conversión de Target está vacía si elige utilizar las métricas de Analytics.

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >Cuando se configura una actividad después de establecer Analytics como fuente de informes, ya no se pueden configurar audiencias para los informes. Los segmentos de Analytics se encuentran disponibles en el informe Actividades de Target.

1. Haga clic en **[!UICONTROL Guardar]**.

