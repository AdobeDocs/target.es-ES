---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Puede configurar una actividad en Target Standard/Premium para que use Adobe Analytics como fuente de informes (A4T).
title: Crear una actividad que utilice A4T como fuente de sistema de informes
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 20%

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

## Compatibilidad de Analytics para Destinatario (A4T) con actividades de asignación automática y Destinatario automático {#a4t-aa}

Hemos actualizado la integración de Adobe Target a Adobe Analytics, conocida como [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md). Las actividades de asignación automática y Destinatario automático ahora admiten Analytics para Destinatario.

Esta integración le permite:

* Utilice la capacidad multi-armed bandit de [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para dirigir el tráfico a las experiencias ganadoras
* Utilice el algoritmo de aprendizaje automático del ensamblado [Destinatario automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para elegir la mejor experiencia para cada visitante en función de su perfil, comportamiento y contexto, todo mientras utiliza una métrica de objetivos [!DNL Adobe Analytics] y [!DNL Adobe Analytics]&#39; sistema de informes y capacidades de análisis enriquecidas.

Asegúrese de que ha [implementado A4T para su uso con actividades de Prueba A/B y de Segmentación de experiencias](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si utiliza `analyticsLogging = client_side`, también debe pasar el valor `sessionId` a [!DNL Analytics]. Para obtener más información, consulte el sistema de informes [Analytics para Destinatario (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) en la guía *SDK para Adobe Target*.

En primer lugar:

1. Al crear una actividad de prueba A/B, en la página **[!UICONTROL Segmentación]**, seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

   * Asignar automáticamente a la mejor experiencia
   * Destinatario automático para experiencias personalizadas

1. Seleccione **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Origen de Sistema de informes]** en la página **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

1. Elija una métrica de objetivo principal.

   * Elija **[!UICONTROL Conversión]** para utilizar [!DNL Adobe Target] para especificar el objetivo de optimización.
   * Elija **[!UICONTROL Utilice una métrica de Analytics]** y, a continuación, seleccione una métrica de [!DNL Analytics] para utilizarla como objetivo de optimización. Puede utilizar una métrica de conversión [!DNL Analytics] predeterminada o un evento personalizado [!DNL Analytics].

1. Guarde y active la actividad.

   [!UICONTROL La ] asignación automática utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL La segmentación automática ] utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a una mejor experiencia personalizada.

1. Utilice la ficha **[!UICONTROL Informes]** para vista del sistema de informes de la actividad según su selección de [!DNL Adobe Analytics] métricas. Haga clic en **[!UICONTROL Vista en Analytics]** para profundizar y segmentar los datos de sistema de informes.

### Métricas de objetivo admitidas

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation y  [!UICONTROL Auto-] Targetlet le permiten elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation and  [!UICONTROL Auto-] Targetse requiere que elija una métrica basada en un evento binomio, es decir, un evento que se produce o no, por ejemplo un clic, una conversión, un pedido, etc. (Estos tipos de eventos también se conocen a veces como Bernoulli, eventos binarios o discretos).

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation and  [!UICONTROL Auto-] Targetno admite la optimización para métricas continuas como ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. (Estos tipos de métricas no admitidos también se conocen como métricas no binomiales o no Bernoulli).

Los siguientes tipos de métricas no son compatibles como métricas de objetivo principales:

* [!DNL Adobe Target] métricas de ingresos y participación
* [!DNL Adobe Analytics] métricas de ingresos y participación

   Puede que sea posible seleccionar una [!DNL Analytics] métrica de ingresos o participación como métrica de objetivo principal porque [!DNL Target] no puede identificar y excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Tenga cuidado de seleccionar sólo métricas de conversión binomiales o eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

### Limitaciones y notas

Algunas limitaciones y notas se aplican tanto a la asignación automática como al Destinatario automático. Otras limitaciones y notas se aplican a un tipo de actividad o al otro.

#### Asignación automática y Destinatario automático

* La fuente de sistema de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] ni viceversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* [!DNL Target] utiliza el modelo de atribución de &quot;Mismo toque&quot; en la función de  [!UICONTROL asignación ] automática: Analytics para Destinatario (A4T).

#### Asignación automática

* [!UICONTROL Los ] emodels de asignación automática siguen entrenándose cada dos horas, como de costumbre.

#### Segmentación automática

* [!UICONTROL Los modelos de ] segmentación automática siguen entrenándose cada 24 horas, como de costumbre. Sin embargo, los datos de eventos de conversión provenientes de [!DNL Analytics] se retrasan de seis a 24 horas adicionales. Este retraso significa que la distribución del tráfico por [!DNL Target] rastreará los últimos eventos registrados en [!DNL Analytics]. Esto tendrá el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez; el rendimiento de la actividad reflejará más de cerca el comportamiento de conversión [!DNL Analytics] después de transcurridos cinco días. Debe considerar el uso de [!UICONTROL Asignación automática] en lugar de [!UICONTROL Destinatario automático] para actividades de corta duración donde la mayor parte del tráfico se produce dentro de los primeros cinco días de la vida de la actividad.
* Cuando se utiliza [!DNL Analytics] como fuente de datos para una actividad [!UICONTROL Destinatario automático], se considera que las sesiones finalizan después de transcurridas seis horas. Las conversiones que se produzcan después de seis horas no se contarán.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en la *Guía de herramientas de Analytics*.
