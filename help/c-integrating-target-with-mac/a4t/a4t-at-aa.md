---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Aprenda a crear actividades de asignación automática y segmentación automática en Adobe Target que empleen Analytics como fuente de informes (A4T).
title: ¿Admite A4T las actividades de asignación automática y segmentación automática?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 3%

---


# Compatibilidad de A4T con actividades de asignación automática y segmentación automática

La integración [!DNL Adobe Target]-to-[!DNL Adobe Analytics], conocida como [Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) admite actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

La integración de A4T le permite:

* Utilice la capacidad multi-armed bandit de [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para dirigir el tráfico a las experiencias ganadoras.
* Utilice el algoritmo de aprendizaje automático del ensamblado de [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) para elegir la mejor experiencia para cada visitante. La segmentación automática elige la mejor experiencia en función de los perfiles, los comportamientos y el contexto de los usuarios, al mismo tiempo que utiliza una métrica de objetivo [!DNL Adobe Analytics] y capacidades de análisis e informes enriquecidos de [!DNL Adobe Analytics].

Asegúrese de que ha [implementado A4T para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Si utiliza `analyticsLogging = client_side`, también debe pasar el valor `sessionId` a [!DNL Analytics]. Para obtener más información, consulte [Informes de Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) en la guía *SDK de Adobe Target*.

En primer lugar:

1. Al crear una actividad de prueba A/B, en la página **[!UICONTROL Segmentación]**, seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

   * [!UICONTROL Asignar automáticamente a la mejor experiencia]
   * [!UICONTROL Segmentación automática para experiencias personalizadas]

   ![Opciones de Métodos de asignación de tráfico: Manual, asignación automática y segmentación automática](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obtener más información e instrucciones paso a paso, consulte [Crear una actividad de asignación automática](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Crear una actividad de segmentación automática](/help/c-activities/auto-target/create-auto-target.md).

1. Seleccione **[!UICONTROL Adobe Analytics]** para la **[!UICONTROL Fuente de informes]** en la página **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

   ![Sección Fuente de informes en la página Objetivos y configuración](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Elija una métrica de objetivo principal.

   * Para utilizar [!DNL Adobe Target] para especificar el objetivo de optimización, elija **[!UICONTROL Conversión]** .
   * Elija **[!UICONTROL Usar una métrica de Analytics]** y luego seleccione una métrica de [!DNL Analytics] para usarla como objetivo de optimización. Puede utilizar una métrica de conversión [!DNL Analytics] predeterminada o un evento personalizado [!DNL Analytics].

   Consulte [Métricas de objetivo compatibles](#supported) a continuación para obtener más información.

1. Guarde y active su actividad.

   [!UICONTROL Asignación automática ] utiliza la métrica seleccionada para optimizar la actividad, lo que lleva a los visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL La segmentación automática ] utiliza la métrica seleccionada para optimizar la actividad, lo que lleva a los visitantes a una mejor experiencia personalizada.

1. Utilice la pestaña **[!UICONTROL Reports]** para ver los informes de su actividad según su selección de métricas [!DNL Adobe Analytics]. Haga clic en **[!UICONTROL Ver en Analytics]** para profundizar y segmentar los datos de los informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation y  [!UICONTROL Auto-] Targetlet le permiten elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation y  [!UICONTROL Auto-] Target requieren que elija una métrica basada en un evento binomial. Un evento binomial ocurre o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. Estos tipos de eventos también se denominan a veces eventos Bernoulli, binarios o discretos.

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocation y  [!UICONTROL Auto-] Target no son compatibles con la optimización para métricas continuas. Las métricas continuas incluyen ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. A veces, estos tipos de métricas no compatibles también se denominan métricas no binomiales o no Bernoulli.

Los siguientes tipos de métricas no son compatibles con las métricas de objetivo principales:

* [!DNL Adobe Target] métricas de participación e ingresos
* [!DNL Adobe Analytics] métricas de participación e ingresos

   Es posible seleccionar una métrica de ingresos o participación [!DNL Analytics] como métrica de objetivo principal porque [!DNL Target] no puede identificar ni excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Seleccione solo las métricas de conversión binomiales o los eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitaciones y notas

Algunas limitaciones y notas se aplican tanto a las actividades de [!UICONTROL Asignación automática] como a2/>Segmentación automática]. [!UICONTROL  Otras limitaciones y notas se aplican a un tipo de actividad o al otro.

### Asignación automática y segmentación automática

* La fuente de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] ni a la inversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado correspondiente a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución de tráfico desigual, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* [!DNL Target] utiliza el modelo de atribución &quot;Mismo contacto&quot; en la función de  [!UICONTROL asignación ] automática: Analytics for Target (A4T).

### Asignación automática

* [!UICONTROL Los ] modelos de asignación automática siguen formándose cada dos horas, como de costumbre.

### Segmentación automática

* [!UICONTROL Los modelos de ] segmentación automática siguen formándose cada 24 horas, como de costumbre. Sin embargo, los datos de eventos de conversión procedentes de [!DNL Analytics] se retrasan de seis a 24 horas más. Este retraso significa que la distribución del tráfico por [!DNL Target] sigue los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad inicialmente. El rendimiento de la actividad reflejará más estrechamente el comportamiento de conversión [!DNL Analytics] después de cinco días. Considere la posibilidad de utilizar [!UICONTROL Asignación automática] en lugar de [!UICONTROL Segmentación automática] para actividades de corta duración en las que la mayoría del tráfico se produce dentro de los cinco primeros días de la vida de la actividad.
* Cuando se utiliza [!DNL Analytics] como fuente de datos para una actividad de [!UICONTROL Segmentación automática], las sesiones finalizan después de que hayan transcurrido seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en la *Guía de herramientas de Analytics*.
