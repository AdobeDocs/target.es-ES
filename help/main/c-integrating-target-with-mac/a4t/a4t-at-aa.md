---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Aprenda a crear actividades de asignación automática y segmentación automática en Adobe [!DNL Target] que utilizan Analytics como fuente de informes (A4T).
title: ¿Admite A4T las actividades de asignación automática y segmentación automática?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 3c64945eb1898457a9d6a3e7bbfa64420bf1250a
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 2%

---

# Compatibilidad de A4T con actividades de asignación automática y segmentación automática

La variable [!DNL Adobe Target]-a-[!DNL Adobe Analytics] integración, conocida como [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) Compatibilidad con (A4T) [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades.

La integración de A4T le permite:

* Uso [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)La capacidad multi-armed bandit de para dirigir el tráfico a las experiencias ganadoras.
* Uso [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)Ensamblar el algoritmo de aprendizaje automático para elegir una mejor experiencia para cada visitante. La segmentación automática elige la mejor experiencia en función de los perfiles, comportamientos y contexto de los usuarios, al mismo tiempo que utiliza un [!DNL Adobe Analytics] métrica de objetivo y [!DNL Adobe Analytics]funcionalidades enriquecidas de informes y análisis.

Asegúrese de que [Se ha implementado A4T para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si está utilizando `analyticsLogging = client_side`, también debe pasar la variable `sessionId` valor [!DNL Analytics]. Para obtener más información, consulte [Creación de informes en Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/) en el *SDK para Adobe Target* guía.

En primer lugar:

1. Al crear una actividad de prueba A/B, en la **[!UICONTROL Segmentación]** seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

   * [!UICONTROL Asignar automáticamente a la mejor experiencia]
   * [!UICONTROL Segmentación automática para experiencias personalizadas]

   ![Opciones de Métodos de asignación de tráfico: Manual, asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obtener más información e instrucciones paso a paso, consulte [Crear una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Crear una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md).

1. Select **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Fuente de informes]** en el **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

   ![Sección Fuente de informes en la página Objetivos y configuración](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Elija una métrica de objetivo principal.

   * Para usar [!DNL Adobe Target] para especificar el objetivo de optimización, elija **[!UICONTROL Conversión]** .
   * Choose **[!UICONTROL Usar una métrica de Analytics]** y, a continuación, seleccione una métrica de [!DNL Analytics] para usar como objetivo de optimización. Puede utilizar una [!DNL Analytics] métrica de conversión o una [!DNL Analytics] evento personalizado.

   Consulte [Métricas de objetivo admitidas](#supported) más abajo para obtener más información.

1. Guarde y active su actividad.

   [!UICONTROL Asignación automática] utiliza la métrica seleccionada para optimizar la actividad, lo que lleva a los visitantes a la experiencia que maximiza la métrica de objetivos.

   O

   [!UICONTROL Segmentación automática] utiliza la métrica seleccionada para optimizar la actividad y llevar a los visitantes a una mejor experiencia personalizada.

1. Utilice la variable **[!UICONTROL Informes]** para ver los informes de su actividad según su elección de [!DNL Adobe Analytics] métricas. Haga clic en **[!UICONTROL Ver en Analytics]** para profundizar y segmentar los datos de los informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] requiere que elija una métrica basada en un evento binomial. Un evento binomial ocurre o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. Estos tipos de eventos también se denominan a veces eventos Bernoulli, binarios o discretos.

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] no admite la optimización para métricas continuas. Las métricas continuas incluyen ingresos, número de productos pedidos, duración de la sesión, número de vistas de página en la sesión, etc. A veces, estos tipos de métricas no compatibles también se denominan métricas no binomiales o no Bernoulli.

Los siguientes tipos de métricas no son compatibles con las métricas de objetivo principales:

* [!DNL Adobe Target] métricas de participación e ingresos
* [!DNL Adobe Analytics] métricas de participación e ingresos

   Es posible seleccionar un [!DNL Analytics] la métrica de participación o ingresos como métrica de objetivo principal porque [!DNL Target] no puede identificar ni excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Seleccione solo las métricas de conversión binomiales o los eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitaciones y notas

Algunas limitaciones y notas se aplican a ambos [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades. Otras limitaciones y notas se aplican a un tipo de actividad o al otro.

### Asignación automática y segmentación automática {#both}

* Al usar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], siempre debe ver los informes en [!DNL Analytics].
* La fuente de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] o a la inversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado correspondiente a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución de tráfico desigual, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* Al usar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática] actividades, siempre debe ver los informes en [!DNL Analytics].
* La fuente de informes no se puede cambiar de [!DNL Analytics] a [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no son compatibles como métricas de objetivo principales, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado correspondiente a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visitante para [!UICONTROL Asignación automática] , por lo que no es necesario utilizar una métrica calculada para realizar la normalización.

### Asignación automática {#aa}

* **Frecuencia de formación**: [!UICONTROL Asignación automática] los modelos siguen entrenándose cada hora, como de costumbre.
* **Modelos de atribución**: [!DNL Target] utiliza la variable [!DNL Adobe Analytics] modelo de atribución predeterminado para[!UICONTROL  Asignación automática] actividades que utilizan A4T.
* **Confianza**: La fórmula de confianza utilizada por [!UICONTROL Asignación automática] actividades es diferente a la fórmula que se muestra de forma predeterminada en la [!DNL Adobe Analytics] [!UICONTROL A4T] panel. [Como se describe aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Asignación automática] utiliza intervalos de confianza más conservadores que los habituales [!UICONTROL Prueba A/B] actividades. Estos niveles de confianza conservadores compensan las evaluaciones repetidas (peeks) en los datos. Como resultado, el informe predeterminado de [!DNL Adobe Analytics] muestra intervalos de confianza más estrechos en comparación con los que usa el [!UICONTROL Asignación automática] algoritmo. Sin embargo, puede determinar qué experiencia es favorita por los algoritmos en función de qué experiencia se le envían más visitantes únicos.
* **Estado ganador**: Actualmente, la variable [Insignias &quot;Ningún ganador aún&quot; y &quot;Ganador&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) no están disponibles en la variable [!UICONTROL A4T] panel en [!DNL Analysis Workspace]. Estos distintivos tampoco están disponibles si se ve el mismo informe en [!DNL Target]. Un distintivo de &quot;estrella&quot; ganador se muestra en una [!DNL Target] para [!UICONTROL Asignación automática] debe ignorarse la actividad que utiliza A4T. Este distintivo refleja cálculos de confianza regulares y no los que utiliza [!UICONTROL Asignación automática].

### Segmentación automática {#at}

* [!UICONTROL Segmentación automática] los modelos siguen entrenándose cada 24 horas, como de costumbre. Sin embargo, los datos de eventos de conversión procedentes de [!DNL Analytics] se retrasa de seis a 24 horas más. Este retraso implica la distribución del tráfico por [!DNL Target] rastrea los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad inicialmente. El rendimiento de la actividad se reflejará más de cerca [!DNL Analytics] comportamiento de conversión después de cinco días. Considere utilizar [!UICONTROL Asignación automática] en lugar de [!UICONTROL Segmentación automática] para actividades de corta duración en las que la mayoría del tráfico se produce dentro de los cinco primeros días de vida de la actividad.
* Al usar [!DNL Analytics] como fuente de datos para un [!UICONTROL Segmentación automática] actividad, las sesiones finalizan después de que hayan transcurrido seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en el *Guía de herramientas de Analytics*.

## Tutorial: Configuración de informes de A4T en Analysis Workspace para actividades de segmentación automática {#tutorial}

Aunque las funciones de análisis enriquecidos están disponibles en [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algunas modificaciones al valor predeterminado [!UICONTROL Analytics para Target] para interpretar correctamente las actividades de segmentación automática. Estas modificaciones son necesarias debido a las diferencias entre las actividades de experimentación (manual A/B y [!UICONTROL Asignación automática]) y actividades de personalización ([!UICONTROL Segmentación automática]).

Este tutorial le guía por las modificaciones recomendadas para el análisis [!UICONTROL Segmentación automática] actividades en [!UICONTROL Espacio de trabajo].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) en *Tutorials de Adobe Target*.
