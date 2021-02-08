---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Obtenga información sobre cómo crear actividades de asignación automática y Destinatario automático en Adobe Target que utilicen Analytics como fuente de sistema de informes (A4T).
title: ¿Admite A4T la asignación automática y las Actividades de Destinatario automático?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 2%

---


# Compatibilidad de A4T con la asignación automática y las actividades de Destinatario automático

La integración [!DNL Adobe Target] a[!DNL Adobe Analytics], conocida como [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) admite actividades [!UICONTROL de asignación automática] y [!UICONTROL Destinatario automático].

La integración de A4T le permite:

* Utilice la capacidad multi-armed bandit de [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para dirigir el tráfico a las experiencias ganadoras.
* Utilice el algoritmo de aprendizaje automático del ensamblado [Destinatario automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para elegir la mejor experiencia para cada visitante en función de su perfil, comportamiento y contexto, todo mientras utiliza una métrica de objetivos [!DNL Adobe Analytics] y [!DNL Adobe Analytics]&#39; sistema de informes y capacidades de análisis enriquecidas.

Asegúrese de que ha [implementado A4T para su uso con actividades de Prueba A/B y de Segmentación de experiencias](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si utiliza `analyticsLogging = client_side`, también debe pasar el valor `sessionId` a [!DNL Analytics]. Para obtener más información, consulte el sistema de informes [Analytics para Destinatario (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) en la guía *SDK para Adobe Target*.

En primer lugar:

1. Al crear una actividad de prueba A/B, en la página **[!UICONTROL Segmentación]**, seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

   * [!UICONTROL Asignar automáticamente a la mejor experiencia]
   * [!UICONTROL Destinatario automático para experiencias personalizadas]

   ![Opciones de métodos de asignación de tráfico: Manual, asignación automática y Destinatario automático](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obtener más información e instrucciones paso a paso, consulte [Creación de una actividad de asignación automática](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Creación de una actividad de Destinatario automático](/help/c-activities/auto-target/create-auto-target.md).

1. Seleccione **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Origen de Sistema de informes]** en la página **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

   ![Sección Origen del sistema de informes en la página Objetivos y configuración](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Elija una métrica de objetivo principal.

   * Elija **[!UICONTROL Conversión]** para utilizar [!DNL Adobe Target] para especificar el objetivo de optimización.
   * Elija **[!UICONTROL Utilice una métrica de Analytics]** y, a continuación, seleccione una métrica de [!DNL Analytics] para utilizarla como objetivo de optimización. Puede utilizar una métrica de conversión [!DNL Analytics] predeterminada o un evento personalizado [!DNL Analytics].

   Consulte [Métricas de objetivo admitidas](#supported) a continuación para obtener más información.

1. Guarde y active la actividad.

   [!UICONTROL La ] asignación automática utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL La segmentación automática ] utilizará la métrica seleccionada para optimizar la actividad, lo que llevará visitantes a una mejor experiencia personalizada.

1. Utilice la ficha **[!UICONTROL Informes]** para vista del sistema de informes de la actividad según su selección de [!DNL Adobe Analytics] métricas. Haga clic en **[!UICONTROL Vista en Analytics]** para profundizar y segmentar los datos de sistema de informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation y  [!UICONTROL Auto-] Targetlet le permiten elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation and  [!UICONTROL Auto-] Targetse requiere que elija una métrica basada en un evento binomio, es decir, un evento que se produce o no, por ejemplo un clic, una conversión, un pedido, etc. Estos tipos de eventos también se conocen a veces como Bernoulli, eventos binarios o discretos.

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation and  [!UICONTROL Auto-] Targetno admite la optimización para métricas continuas como ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. Estos tipos de métricas no admitidos también se conocen a veces como métricas no binomiales o no Bernoulli.

Los siguientes tipos de métricas no son compatibles como métricas de objetivo principales:

* [!DNL Adobe Target] métricas de ingresos y participación
* [!DNL Adobe Analytics] métricas de ingresos y participación

   Puede que sea posible seleccionar una [!DNL Analytics] métrica de ingresos o participación como métrica de objetivo principal porque [!DNL Target] no puede identificar y excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Tenga cuidado de seleccionar sólo métricas de conversión binomiales o eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitaciones y notas

Algunas limitaciones y notas se aplican a actividades [!UICONTROL de asignación automática] y [!UICONTROL de Destinatario automático]. Otras limitaciones y notas se aplican a un tipo de actividad o al otro.

### Asignación automática y Destinatario automático

* La fuente de sistema de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] ni viceversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* [!DNL Target] utiliza el modelo de atribución de &quot;Mismo toque&quot; en la función de  [!UICONTROL asignación ] automática: Analytics para Destinatario (A4T).

### Asignación automática

* [!UICONTROL Los ] emodels de asignación automática siguen entrenándose cada dos horas, como de costumbre.

### Segmentación automática

* [!UICONTROL Los modelos de ] segmentación automática siguen entrenándose cada 24 horas, como de costumbre. Sin embargo, los datos de eventos de conversión provenientes de [!DNL Analytics] se retrasan de seis a 24 horas adicionales. Este retraso significa que la distribución del tráfico por [!DNL Target] rastreará los últimos eventos registrados en [!DNL Analytics]. Esto tiene el mayor efecto en las primeras 48 horas después de activar una actividad. El rendimiento de la actividad reflejará más de cerca el comportamiento de conversión [!DNL Analytics] después de transcurridos cinco días. Debe considerar el uso de [!UICONTROL Asignación automática] en lugar de [!UICONTROL Destinatario automático] para actividades de corta duración en las que la mayor parte del tráfico se produce en los primeros cinco días de la vida de la actividad.
* Cuando se utiliza [!DNL Analytics] como fuente de datos para una actividad [!UICONTROL Destinatario automático], se considera que las sesiones finalizan después de transcurridas seis horas. Las conversiones que se produzcan después de seis horas no se contarán.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en la *Guía de herramientas de Analytics*.
