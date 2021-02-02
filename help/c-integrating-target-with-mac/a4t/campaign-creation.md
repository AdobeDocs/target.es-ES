---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Crear una actividad que utilice A4T como fuente de sistema de informes
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 43%

---


# Crear una actividad que utilice Analytics como fuente de sistema de informes

Puede configurar una actividad en [!DNL Target] para que utilice [!DNL Adobe Analytics] como fuente de sistema de informes (A4T).

Antes de configurar una actividad que utilice [!DNL Analytics] como fuente de sistemas de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar métricas adicionales en cualquier momento en [!DNL Analytics], debe especificar una métrica en particular a la que espera que esta prueba afecte.

## Cree la actividad

La creación de una actividad [!DNL Target] que utilice [!DNL Analytics] como fuente de sistema de informes es similar a la configuración de una actividad [!DNL Target] regular, con algunas diferencias importantes. Por ejemplo: no puede seleccionar un segmento para el sistema de informes al crear la actividad porque todos los segmentos disponibles en [!DNL Analytics] se pueden aplicar al ver un informe.

1. Haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >Un nombre de actividad no puede incluir el carácter &quot;%&quot; si se utiliza [!DNL Analytics] como origen de sistema de informes.

1. Seleccione el tipo de actividad y comience a configurarla.

   Si desea crear una actividad [!UICONTROL de asignación automática] o [!UICONTROL de Destinatario automático], consulte [Compatibilidad de A4T con la asignación automática y las actividades de Destinatario automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obtener más información.

1. Cuando llegue a la fase de **[!UICONTROL configuración]** en el flujo de trabajo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y escriba el nombre de su empresa.
1. Seleccione un grupo de informes.

   Puede seleccionar cualquier grupo de informes que haya disponible en [!DNL Analytics]. El grupo de informes define dónde estarán disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.

      Es posible que deba comprobar su compañía [!DNL Analytics]. Si su cuenta [!DNL Adobe Experience Cloud] está vinculada a más de una compañía [!DNL Analytics], cierre la sesión de [!DNL Target] e inicie sesión en [!DNL Analytics] en la compañía correcta. A continuación, vuelva a [!DNL Target] y se cargarán los grupos de informes.

   * No ve el grupo de informes que esperaba.

      Sólo estarán disponibles para selección los grupos de informes que estén aprovisionados para conectarse a [!DNL Target]. Si no ve los grupos de informes que espera, intente cerrar la sesión y volver a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo.
   Si aún no aparece el grupo de informes en la lista, póngase en contacto con el [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia.
1. Especifique el objetivo de la actividad.

   Debe seleccionar una métrica de éxito para utilizarla como objetivo en cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier métrica [!DNL Analytics] disponible en el selector de métricas [!DNL Analytics].

   >[!NOTE]
   >
   >Puede enviar una métrica personalizada basada en Destinatarios a [!DNL Analytics] en lugar de depender solamente de datos [!DNL Analytics]. Por ejemplo, puede controlar los clics en una página, algo que no se suele rastrear en [!DNL Analytics]. Esta métrica personalizada se envía automáticamente a [!DNL Analytics] desde el servidor [!DNL Target] y aparece como la métrica &quot;[!DNL Target] Conversión&quot; en el selector de métricas en [!DNL Analytics]. La métrica de conversión [!DNL Target] está vacía si elige utilizar métricas [!DNL Analytics].

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >Al configurar una actividad después de configurar [!DNL Analytics] como fuente de sistema de informes, no hay opción de configurar audiencias para sistema de informes. [!DNL Analytics] los segmentos están disponibles en el informe  [!DNL Target] Actividades.

1. Haga clic en **[!UICONTROL Guardar]**.

## A4T y actividades de asignación automática y Destinatario automático

Para obtener más información, consulte [Compatibilidad de A4T con la asignación automática y actividades de Destinatario automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).