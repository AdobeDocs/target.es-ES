---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Obtenga información sobre cómo configurar una actividad en el Adobe  [!DNL Target]  que usa Adobe Analytics como fuente de informes (A4T).
title: ¿Cómo creo una actividad que utiliza A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 28%

---

# Creación de una actividad que use Analytics como fuente de informes

Puede configurar una actividad en [!DNL Adobe Target] para que use [!DNL Adobe Analytics] como fuente de informes (A4T).

Antes de configurar una actividad que usa [!DNL Analytics] como fuente de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar más métricas en cualquier momento en [!DNL Analytics], debe especificar una métrica concreta a la que espera que afecte esta prueba.

## Creación de la actividad

Crear una actividad [!DNL Target] que use [!DNL Analytics] como origen de informes es similar a configurar una actividad [!DNL Target] normal, con algunas diferencias importantes. Por ejemplo, no puede seleccionar un segmento para la creación de informes mientras crea la actividad, ya que todos los segmentos disponibles en [!DNL Analytics] se pueden aplicar cuando se visualiza un informe.

1. Haga clic en **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Un nombre de actividad no puede incluir el carácter &quot;%&quot; si se usa [!DNL Analytics] como fuente de informes.
   >
   >No use el mismo nombre de actividad para dos actividades de [espacios de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) separados que usen informes de A4T.

1. Seleccione el tipo de actividad y comience a configurarla.

   Si desea crear una actividad [!UICONTROL Auto-Allocate] o [!UICONTROL Auto-Target], consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obtener más información.

1. Cuando llegue a la parte **[!UICONTROL Settings]** del flujo de trabajo de creación de la actividad, elija **[!UICONTROL Adobe Analytics]** y especifique su empresa.
1. Seleccione un grupo de informes.

   Puede elegir cualquier grupo de informes disponible en [!DNL Analytics]. El grupo de informes define dónde están disponibles los datos recopilados. Los grupos de informes virtuales no se incluyen en la lista de grupos de informes.

   Pueden surgir dos errores al seleccionar el grupo de informes:

   * Recibe un error que indica que no hay grupos de informes disponibles, pero su cuenta está configurada correctamente.

     Compruebe su compañía de [!DNL Analytics]. Si su cuenta de [!DNL Adobe Experience Cloud] está vinculada a más de una compañía de [!DNL Analytics], cierre la sesión de [!DNL Target] e inicie sesión en [!DNL Analytics] en la compañía correcta. Luego vuelva a [!DNL Target] y se cargarán los grupos de informes.

   * No ve el grupo de informes que esperaba.

     Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo.

   Si faltan uno o más grupos de informes en la lista, [comuníquese con el Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Indique el servidor de seguimiento.

   Consulte [Usar un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina la experiencia.
1. Especifique la meta de la actividad.

   Debe seleccionar una métrica de éxito para utilizarla como objetivo para cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier métrica [!DNL Analytics] disponible en el selector de métricas [!DNL Analytics].

   >[!NOTE]
   >
   >Puede enviar una métrica personalizada basada en Target a [!DNL Analytics], en lugar de depender solamente de los datos de [!DNL Analytics]. Por ejemplo, puede supervisar que se haga clic en una página, algo que [!DNL Analytics] no suele rastrear. Esta métrica personalizada se envía a [!DNL Analytics] automáticamente desde el servidor [!DNL Target] y aparece como la métrica &quot;[!DNL Target] Conversión&quot; en el selector de métricas de [!DNL Analytics]. La métrica de conversión [!DNL Target] está vacía si elige usar las métricas [!DNL Analytics].

   El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Sin embargo, el objetivo es establecer un recordatorio de lo que se quiere mejorar con la actividad.

   El visitante permanece en la actividad después de alcanzar el objetivo. El visitante sigue viendo contenido de la actividad pero no se cuenta como una nueva participación en la actividad.

   >[!NOTE]
   >
   >Al configurar una actividad después de configurar [!DNL Analytics] como fuente de informes, no hay ninguna opción para configurar audiencias para los informes. [!DNL Analytics] segmentos están disponibles en el informe [!DNL Target] actividades.

1. Haga clic en **[!UICONTROL Save]**.

## Actividades de A4T y asignación automática y segmentación automática

Para obtener más información, consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
