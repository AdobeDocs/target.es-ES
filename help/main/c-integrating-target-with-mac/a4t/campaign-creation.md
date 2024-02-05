---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Obtenga información sobre cómo configurar una actividad en Adobe [!DNL Target] que utiliza Adobe Analytics como fuente de informes (A4T).
title: ¿Cómo creo una actividad que utiliza A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 28%

---

# Creación de una actividad que use Analytics como fuente de informes

Puede configurar una actividad en [!DNL Adobe Target] para utilizar [!DNL Adobe Analytics] como fuente de informes (A4T).

Antes de configurar una actividad que utiliza [!DNL Analytics] como fuente de informes, establezca el objetivo de la actividad (por ejemplo, mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras). Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar más métricas en cualquier momento en [!DNL Analytics]No obstante, debe especificar una métrica concreta a la que espere que afecte esta prueba.

## Creación de la actividad

Creación de un [!DNL Target] actividad que utiliza [!DNL Analytics] como la fuente de informes es similar a la configuración de una [!DNL Target] actividad, con algunas diferencias importantes. Por ejemplo, no puede seleccionar un segmento para los informes mientras crea la actividad porque todos los segmentos están disponibles en [!DNL Analytics] se puede aplicar al ver un informe.

1. Haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >Un nombre de actividad no puede incluir el carácter &quot;%&quot; si [!DNL Analytics] se utiliza como fuente de informes.
   >
   >No utilice el mismo nombre de actividad para dos actividades independientes [workspaces](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) que utilizan informes de A4T.

1. Seleccione el tipo de actividad y comience a configurarla.

   Si desea crear un [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática] actividad, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obtener más información.

1. Cuando llegue a la **[!UICONTROL Configuración]** En la parte del flujo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y especifique su empresa.
1. Seleccione un grupo de informes.

   Puede elegir cualquier grupo de informes disponible en [!DNL Analytics]. El grupo de informes define dónde están disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.

     Compruebe su [!DNL Analytics] empresa. Si su [!DNL Adobe Experience Cloud] la cuenta está vinculada a más de una [!DNL Analytics] empresa, cerrar sesión [!DNL Target]e inicie sesión en [!DNL Analytics] bajo la compañía correcta. A continuación, vuelva a [!DNL Target]y se cargan los grupos de informes.

   * No ve el grupo de informes que esperaba.

     Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo.

   Si todavía faltan uno o más grupos de informes en la lista, [Contactar con Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia.
1. Especifique la meta de la actividad.

   Debe seleccionar una métrica de éxito para utilizarla como objetivo para cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier [!DNL Analytics] métrica disponible en el [!DNL Analytics] selector de métricas.

   >[!NOTE]
   >
   >Puede enviar una métrica personalizada basada en Target a [!DNL Analytics] en lugar de depender solo de [!DNL Analytics] datos. Por ejemplo, puede controlar los clics en una página, algo que no se suele rastrear mediante [!DNL Analytics]. Esta métrica personalizada se envía a [!DNL Analytics] automáticamente desde el [!DNL Target] y aparece como &quot;&quot;.[!DNL Target] Métrica &quot;Conversión&quot; en el selector de métricas de [!DNL Analytics]. El [!DNL Target] La métrica de conversión está vacía si elige usar [!DNL Analytics] métricas.

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >Al configurar una actividad después de configurar [!DNL Analytics] como fuente de informes, no hay opción de configurar audiencias para los informes. [!DNL Analytics] Los segmentos de están disponibles en [!DNL Target] Informe Actividades.

1. Haga clic en **[!UICONTROL Guardar]**.

## Actividades de A4T y asignación automática y segmentación automática

Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
