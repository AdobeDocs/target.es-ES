---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Obtenga información sobre cómo configurar una actividad en Adobe [!DNL Target] que utiliza Adobe Analytics como fuente de informes (A4T).
title: ¿Cómo creo una actividad que utilice A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 38%

---

# Creación de una actividad que use Analytics como fuente de informes

Puede configurar una actividad en [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fuente de informes (A4T).

Antes de configurar una actividad que utilice [!DNL Analytics] como fuente de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar más métricas en cualquier momento en [!DNL Analytics], aún debe especificar una métrica en particular a la que espera que afecte esta prueba.

## Cree la actividad

Creación de [!DNL Target] actividad que utiliza [!DNL Analytics] ya que la fuente de informes es similar a la configuración de un [!DNL Target] actividad, con algunas diferencias importantes. Por ejemplo, no puede seleccionar un segmento para crear informes mientras crea la actividad, ya que todos los segmentos están disponibles en [!DNL Analytics] se puede aplicar al ver un informe.

1. Haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >Un nombre de actividad no puede incluir el carácter &quot;%&quot; si [!DNL Analytics] se usa como fuente de informes.

1. Seleccione el tipo de actividad y comience a configurarla.

   Si desea crear un [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática] actividad, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obtener más información.

1. Cuando llegue a la fase de **[!UICONTROL configuración]** en el flujo de trabajo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y escriba el nombre de su empresa.
1. Seleccione un grupo de informes.

   Puede seleccionar cualquier grupo de informes que haya disponible en [!DNL Analytics]. El grupo de informes define dónde están disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.

      Compruebe su [!DNL Analytics] empresa. Si su [!DNL Adobe Experience Cloud] la cuenta está vinculada a más de una [!DNL Analytics] empresa, cierre la sesión [!DNL Target]e inicie sesión en [!DNL Analytics] en la compañía correcta. A continuación, vuelva a [!DNL Target]y se cargan los grupos de informes.

   * No ve el grupo de informes que esperaba.

      Solo los grupos de informes aprovisionados para conectarse a [!DNL Target] están disponibles para su selección. Si no ve los grupos de informes esperados, intente cerrar la sesión y volver a iniciarla en el [!DNL Adobe Experience Cloud] para intentarlo de nuevo.
   Si todavía faltan uno o más grupos de informes en la lista, [póngase en contacto con el servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia.
1. Especifique el objetivo de la actividad.

   Debe seleccionar una métrica de éxito para utilizarla como objetivo en cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. La práctica recomendada es no ejecutar nunca una prueba sin tener como objetivo mejorar de una manera específica. Puede elegir cualquier [!DNL Analytics] métrica disponible en la variable [!DNL Analytics] selector de métricas.

   >[!NOTE]
   >
   >Puede enviar una métrica personalizada basada en Target a [!DNL Analytics] en lugar de confiar únicamente en [!DNL Analytics] datos. Por ejemplo, se puede controlar si se hace clic en una página, algo que no se suele rastrear con [!DNL Analytics]. Esta métrica personalizada se envía a [!DNL Analytics] automáticamente desde el [!DNL Target] y aparece como el[!DNL Target] Métrica &quot;Conversión&quot; en el selector de métricas de [!DNL Analytics]. La variable [!DNL Target] La métrica de conversión está vacía si elige usar [!DNL Analytics] métricas.

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >Al configurar una actividad después de configurarla [!DNL Analytics] como fuente de informes, no hay opción de configurar audiencias para los informes. [!DNL Analytics] los segmentos están disponibles en la [!DNL Target] Informe de actividades.

1. Haga clic en **[!UICONTROL Guardar]**.

## A4T y actividades de asignación automática y segmentación automática

Para obtener más información, consulte [Compatibilidad con A4T para actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
