---
keywords: a4t;A4T;Analytics como fuente de informes para Target
description: Aprenda a crear [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades en [!DNL Target] que utilizan [!DNL Analytics] como fuente de informes (A4T).
title: ¿Admite A4T? [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] ¿Actividades?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 2%

---

# Compatibilidad de A4T con [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades

El [!DNL Adobe Target]-a-[!DNL Adobe Analytics] integración, conocida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) admite [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades.

La integración con A4T le permite:

* Uso [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)La capacidad de bandido multiarmado de para dirigir el tráfico a las experiencias ganadoras.
* Uso [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)Configure el algoritmo de aprendizaje automático de para elegir la mejor experiencia para cada visitante. [!UICONTROL Segmentación automática] elige la mejor experiencia en función de los perfiles, comportamientos y contextos de los usuarios, todo mientras utiliza una [!DNL Adobe Analytics] métrica de objetivo y [!DNL Adobe Analytics]&#39; capacidades enriquecidas de análisis y creación de informes.

Asegúrese de que tiene [A4T implementado para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si está utilizando `analyticsLogging = client_side`, también debe pasar el `sessionId` valor hasta [!DNL Analytics]. Para obtener más información, consulte [Creación de informes en Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} en el *SDK para Adobe Target* guía.

En primer lugar:

1. Al crear un [!UICONTROL Prueba A/B] actividad, en **[!UICONTROL Segmentación]** , seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

   * [!UICONTROL Asignación automática a la mejor experiencia]
   * [!UICONTROL Segmentación automática para experiencias personalizadas]

   ![Opciones de métodos de asignación de tráfico: manual, asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obtener más información e instrucciones paso a paso, consulte [Creación de una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Creación de una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md).

1. Seleccionar **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Fuente de informes]** en el **[!UICONTROL Objetivos y configuración]** y seleccione el grupo de informes correspondiente a su objetivo de optimización deseado.

   ![Sección Fuente de informes en la página Objetivos y configuración](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Elija una [!UICONTROL Objetivo principal] métrica.

   * Para usar [!DNL Adobe Target] para especificar el objetivo de optimización, elija **[!UICONTROL Conversión]** .
   * Elegir **[!UICONTROL Uso de una métrica de Analytics]** y, a continuación, seleccione una métrica de [!DNL Analytics] para su uso como objetivo de optimización. Puede utilizar un de forma predeterminada [!DNL Analytics] métrica de conversión o una [!DNL Analytics] Evento personalizado.

   Consulte [Métricas de objetivo admitidas](#supported) para obtener más información.

1. Guarde y active la actividad.

   [!UICONTROL Asignación automática] utiliza la métrica seleccionada para optimizar la actividad, lo que lleva a los visitantes a la experiencia que maximiza la métrica de objetivo.

   O

   [!UICONTROL Segmentación automática] utiliza la métrica seleccionada para optimizar la actividad, lo que lleva a los visitantes a una mejor experiencia personalizada.

1. Utilice el **[!UICONTROL Informes]** para ver los informes de su actividad según su elección de [!DNL Adobe Analytics] métricas. Clic **[!UICONTROL Ver en Analytics]** para profundizar y segmentar aún más los datos de informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] le permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] requiere que elija una métrica basada en un evento binomial. Un evento binomial se produce o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. A veces, estos tipos de eventos también se denominan eventos Bernoulli, binarios o discretos.

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] no admite la optimización de métricas continuas. Las métricas continuas incluyen ingresos, cantidad de productos pedidos, duración de la sesión, cantidad de vistas de página en la sesión, etc. Estos tipos de métricas no compatibles también se denominan a veces métricas no binomiales o no Bernoulli.

Los siguientes tipos de métricas no son compatibles como métricas de objetivo principal:

* [!DNL Adobe Target] métricas de participación e ingresos
* [!DNL Adobe Analytics] métricas de participación e ingresos

   Es posible seleccionar una [!DNL Analytics] métrica de participación o ingresos como métrica de objetivo principal porque [!DNL Target] no puede identificar y excluir todas las métricas de participación e ingresos de [!DNL Analytics]. Seleccione solo métricas de conversión binomiales o eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitaciones y notas

Algunas limitaciones y notas se aplican a ambas [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades. Se aplican otras limitaciones y notas a un tipo de actividad u otro.

### Asignación automática y segmentación automática {#both}

* Al utilizar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], siempre debe ver los informes en [!DNL Analytics].
* La fuente de informes no se puede cambiar de [!DNL Analytics] hasta [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no se admiten como métricas de objetivo principal, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.
* Al utilizar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática] actividades, siempre debe ver los informes en [!DNL Analytics].
* La fuente de informes no se puede cambiar de [!DNL Analytics] hasta [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no se admiten como métricas de objetivo principal, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visitante para [!UICONTROL Asignación automática] actividades, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.

### Asignación automática {#aa}

* **Frecuencia de formación**: [!UICONTROL Asignación automática] los modelos siguen entrenando cada hora, como de costumbre.
* **Modelos de atribución**: [!DNL Target] utiliza el [!DNL Adobe Analytics] modelo de atribución predeterminado para[!UICONTROL  Asignación automática] actividades que utilizan A4T.
* **Confianza**: la fórmula de confianza utilizada por [!UICONTROL Asignación automática] actividades es diferente a la fórmula que se muestra de forma predeterminada en la [!DNL Adobe Analytics] [!UICONTROL A4T] panel. [Como se describe aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Asignación automática] utiliza intervalos de confianza más conservadores que los habituales [!UICONTROL Prueba A/B] actividades. Estos niveles de confianza conservadores compensan las evaluaciones repetidas (picos) de los datos. Como resultado, el informe predeterminado en [!DNL Adobe Analytics] muestra intervalos de confianza más estrechos en comparación con los que utiliza el [!UICONTROL Asignación automática] algoritmo. Sin embargo, puede determinar qué experiencia se ve favorecida por los algoritmos en función de qué experiencia se le envían más visitantes únicos.
* **Estado del ganador**: Actualmente, la variable [Insignias de &quot;Ningún ganador aún&quot; y &quot;Ganador&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) no están disponibles en el [!UICONTROL A4T] panel en [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se visualiza el mismo informe en [!DNL Target]. Una insignia de &quot;estrella&quot; ganadora que se muestra en una [!DNL Target] informe para un [!UICONTROL Asignación automática] La actividad de mediante A4T debe ignorarse. Este distintivo refleja los cálculos de confianza habituales, y no los utilizados por [!UICONTROL Asignación automática].

### Segmentación automática {#at}

* [!UICONTROL Segmentación automática] los modelos siguen entrenando cada 24 horas, como de costumbre. Sin embargo, los datos de evento de conversión procedentes de [!DNL Analytics] se retrasa entre seis y 24 horas más. Este retraso significa la distribución del tráfico por [!DNL Target] rastrea los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez. El rendimiento de la actividad se refleja más estrechamente [!DNL Analytics] comportamiento de conversión después de cinco días.

   Considere utilizar [!UICONTROL Asignación automática] en lugar de [!UICONTROL Segmentación automática] para actividades de corta duración en las que la mayor parte del tráfico se produce dentro de los primeros cinco días de vida de la actividad.

* Al utilizar [!DNL Analytics] como fuente de datos para un [!UICONTROL Segmentación automática] actividad, las sesiones finalizan al cabo de seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en el *Guía de herramientas de Analytics*.

## Tutoriales

Aunque las funcionalidades de análisis enriquecidas están disponibles en [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algunas modificaciones en el valor predeterminado [!UICONTROL Analytics for Target] Los paneles deben interpretar correctamente [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades. Estas modificaciones son necesarias debido a las diferencias entre las actividades de experimentación (A/B manual y [!UICONTROL Asignación automática]) y actividades de personalización ([!UICONTROL Segmentación automática]).

### Configuración de informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Asignación automática] actividades

Este tutorial le guiará por las modificaciones recomendadas para analizar [!UICONTROL Asignación automática] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de asignación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank} in *Tutorials de Adobe Target*.

### Configuración de informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL Segmentación automática] actividades

Este tutorial le guiará por las modificaciones recomendadas para analizar [!UICONTROL Segmentación automática] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank} in *Tutorials de Adobe Target*.


