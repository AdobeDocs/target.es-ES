---
keywords: a4t;A4T;Analytics como fuente de informes para Target;analytics para Target
description: Aprenda a crear actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] en  [!DNL Target] que usen [!DNL Analytics] como fuente de informes (A4T).
title: ¿Admite A4T actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 80e4741f5f501a48b15b718c6c0bf55a86c4d676
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 1%

---

# Compatibilidad con A4T para actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]

La integración de [!DNL Adobe Target] a [!DNL Adobe Analytics], conocida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), admite actividades de [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target].

La integración con A4T le permite:

* Usa la capacidad de bandido multibrazo de [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para dirigir el tráfico a las experiencias ganadoras.
* Use el algoritmo de aprendizaje automático de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para elegir la mejor experiencia para cada visitante. [!UICONTROL Auto-Target] elige la mejor experiencia en función del perfil, el comportamiento y el contexto de cada usuario, todo mientras usa una métrica de objetivos de [!DNL Adobe Analytics] y las abundantes capacidades de análisis e informes de [!DNL Adobe Analytics].

Asegúrese de que ha [implementado A4T para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si usa `analyticsLogging = client_side`, también debe pasar el valor `sessionId` a [!DNL Analytics]. Para obtener más información, consulte [Informes de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} en la *Guía para desarrolladores de Adobe Target*.

En primer lugar:

1. Mientras [crea una actividad [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), en la página **[!UICONTROL Targeting]**, seleccione una de las siguientes opciones como **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Opciones de métodos de asignación de tráfico: manual, asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obtener más información e instrucciones paso a paso, consulte [Crear una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Crear una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md).

1. Seleccione **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Reporting Source]** en la página **[!UICONTROL Goals & Settings]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

   ![Sección Reporting Source en la página Objetivos y configuración](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Elija una métrica [!UICONTROL Primary Goal].

   * Para usar [!DNL Adobe Target] para especificar el objetivo de optimización, elija **[!UICONTROL Conversion]**
   * Elija **[!UICONTROL Use an Analytics metric]** y luego seleccione una métrica de [!DNL Analytics] para usarla como objetivo de optimización. Puede usar una métrica de conversión [!DNL Analytics] lista para usar o un evento personalizado [!DNL Analytics].

   Consulte [Métricas de objetivo admitidas](#supported) a continuación para obtener más información.

1. Guarde y active la actividad.

   [!UICONTROL Auto-Allocate] utiliza la métrica que seleccionó para optimizar la actividad, lo que lleva a los visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL Auto-Target] usa la métrica que seleccionó para optimizar la actividad y así los visitantes obtienen una mejor experiencia personalizada.

1. Use la ficha **[!UICONTROL Reports]** para ver los informes de su actividad según su elección de [!DNL Adobe Analytics] métricas. Haga clic **[!UICONTROL View in Analytics]** para profundizar y segmentar aún más los datos de informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4T] para [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] le permite elegir cualquiera de los siguientes tipos de métrica como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

>[!NOTE]
>
>Después de seleccionar [!UICONTROL Use an Analytics Metric], seleccione [!UICONTROL Maximize Unique Visitor Conversion Rate] para ver las métricas de conversión de [!DNL Adobe Analytics] disponibles y [!UICONTROL Maximize Metric Value per Visitor] para explorar [!DNL Adobe Analytics] eventos personalizados.

[!DNL Target] le permite elegir métricas basadas en eventos binomiales o en métricas basadas en eventos continuos al usar [!UICONTROL A4T] para [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] actividades.

* **Métricas basadas en eventos binomiales**: Un evento binomial ocurre o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. A veces, estos tipos de eventos también se denominan eventos Bernoulli, binarios o discretos.

* **Métricas basadas en eventos continuos**. Las métricas continuas incluyen ingresos, cantidad de productos pedidos, duración de la sesión, cantidad de vistas de página en la sesión, etc. Estos tipos de eventos también se denominan a veces métricas no binomiales o no Bernoulli.

>[!IMPORTANT]
>
>A partir de la versión de [!DNL Adobe Target Standard/Premium] 22.15.1 (8 y 9 de marzo de 2023), [!DNL Target] sigue admitiendo las actividades existentes con las métricas que ahora no son compatibles (enumeradas en las tablas siguientes). Sin embargo, a partir del 9 de septiembre de 2023, estas métricas ya no serán compatibles con las actividades existentes y todas las actividades que utilicen métricas no compatibles se suspenderán para forzar la migración de la actividad existente al nuevo comportamiento.

### Impacto en [!UICONTROL Auto-Allocate] actividades

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL averagetimespentonsite] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL bouncerate] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL bounces] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL entries] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL exits] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL reloads] | Maximizar valor de métrica |
| [!UICONTROL visitors] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL visits] | Maximizar valor de métrica |

### Impacto en [!UICONTROL Auto-Target] actividades

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL cartremovals] | Maximizar valor de métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL visitors] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL visits] | Maximizar valor de métrica |

## Limitaciones y notas

Algunas limitaciones y notas se aplican a las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]. Se aplican otras limitaciones y notas a un tipo de actividad u otro.

### Asignación automática y segmentación automática {#both}

* Cuando se usa [!DNL Adobe Analytics] como el origen de informes de [!UICONTROL Auto-Allocate] o [!UICONTROL Auto-Target], siempre se deben ver los informes en [!DNL Analytics].
* No se puede cambiar el origen de los informes de [!DNL Analytics] a [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no se admiten como métricas de objetivo principal, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.

### Asignación automática {#aa}

* **Frecuencia de entrenamiento**: [!UICONTROL Auto-Allocate] modelos continúan entrenando cada hora, como de costumbre.
* **Modelos de atribución**: [!DNL Target] utiliza el modelo de atribución predeterminado de [!DNL Adobe Analytics] para [!UICONTROL  Auto-Allocate] actividades que utilizan A4T.
* **Confianza**: La fórmula de confianza utilizada por las actividades [!UICONTROL Auto-Allocate] es diferente de la fórmula mostrada de forma predeterminada en el panel [!DNL Adobe Analytics] [!UICONTROL A4T]. [Como se describe aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] usa intervalos de confianza más conservadores que las actividades de [!UICONTROL A/B Test] normales. Estos niveles de confianza conservadores compensan las evaluaciones repetidas (picos) de los datos. Como resultado, el informe predeterminado de [!DNL Adobe Analytics] muestra intervalos de confianza más estrechos en comparación con los intervalos que utiliza el algoritmo [!UICONTROL Auto-Allocate]. Sin embargo, puede determinar qué experiencia se ve favorecida por los algoritmos en función de qué experiencia se le envían más visitantes únicos.
* **Estado del ganador**: Actualmente, las insignias [&quot;Ningún ganador aún&quot; y &quot;Ganador&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) no están disponibles en el panel [!UICONTROL A4T] de [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se ve el mismo informe en [!DNL Target]. Se debe ignorar un distintivo de &quot;estrella&quot; ganador que se muestra en un informe [!DNL Target] para una actividad [!UICONTROL Auto-Allocate] que usa A4T. Este distintivo refleja los cálculos de confianza normales y no los cálculos utilizados por [!UICONTROL Auto-Allocate].

### Segmentación automática {#at}

* [!UICONTROL Auto-Target] modelos continúan entrenándose cada 24 horas, como de costumbre. Sin embargo, los datos de evento de conversión procedentes de [!DNL Analytics] se retrasan de seis a 24 horas más. Este retraso significa que la distribución del tráfico por [!DNL Target] rastrea los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez. El rendimiento de la actividad refleja con mayor precisión el comportamiento de conversión de [!DNL Analytics] después de cinco días.

  Considere la posibilidad de utilizar [!UICONTROL Auto-Allocate] en lugar de [!UICONTROL Auto-Target] para actividades de corta duración en las que la mayor parte del tráfico se produce dentro de los primeros cinco días de vida de la actividad.

* Cuando se usa [!DNL Analytics] como origen de datos de una actividad [!UICONTROL Auto-Target], las sesiones finalizan al cabo de seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en la *Guía de herramientas de Analytics*.

## Tutoriales

Aunque las funcionalidades de análisis enriquecidas están disponibles en [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], se requieren algunas modificaciones en el panel predeterminado [!UICONTROL Analytics for Target] para interpretar correctamente las actividades [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]. Estas modificaciones son necesarias debido a diferencias entre las actividades de experimentación (A/B manual y [!UICONTROL Auto-Allocate]) y las actividades de personalización ([!UICONTROL Auto-Target]).

### Configurando informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Auto-Allocate] actividades

Este tutorial lo guiará por las modificaciones recomendadas para analizar [!UICONTROL Auto-Allocate] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Cómo configurar informes de A4T en Analysis Workspace para actividades de asignación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank} en *Tutoriales de Adobe Target*.

### Configurando informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Auto-Target] actividades

Este tutorial lo guiará por las modificaciones recomendadas para analizar [!UICONTROL Auto-Target] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Cómo configurar informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank} en *Tutoriales de Adobe Target*.


