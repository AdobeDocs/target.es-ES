---
keywords: a4t;A4T;Analytics como fuente de informes para Target;analytics para Target
description: Aprenda a crear [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades en [!DNL Target] que utilizan [!DNL Analytics] como fuente de informes (A4T).
title: ¿Admite A4T? [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] ¿Actividades?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# Compatibilidad de A4T con actividades de [!UICONTROL asignación automática] y [!UICONTROL segmentación automática]

El [!DNL Adobe Target]-a-[!DNL Adobe Analytics] integración, conocida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), admite [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades.

La integración con A4T le permite:

* Utilice el [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) capacidad de bandido multiarmado para dirigir el tráfico a las experiencias ganadoras.
* Utilice el [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) Ensamble el algoritmo de aprendizaje automático para elegir la mejor experiencia para cada visitante. [!UICONTROL Segmentación automática] elige la mejor experiencia en función del perfil, el comportamiento y el contexto de cada usuario, todo mientras utiliza una [!DNL Adobe Analytics] métrica de objetivo y las abundantes capacidades de análisis y creación de informes de [!DNL Adobe Analytics].

Asegúrese de que dispone de [A4T implementado para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si utiliza `analyticsLogging = client_side`, también debe pasar el `sessionId` valor hasta [!DNL Analytics]. Para obtener más información, consulte [Creación de informes en Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} en el *Guía para desarrolladores de Adobe Target*.

En primer lugar:

1. While [creación de un [!UICONTROL Prueba A/B] actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), en el **[!UICONTROL Segmentación]** , seleccione una de las siguientes opciones como **[!UICONTROL Método de asignación de tráfico]**:

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

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

[!DNL Target] permite elegir métricas basadas en eventos binomiales o métricas basadas en eventos continuos al utilizar [!UICONTROL A4T] para actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

* **Métricas basadas en eventos binomiales**: Un evento binomial que se produce o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. A veces, estos tipos de eventos también se denominan eventos Bernoulli, binarios o discretos.

* **Métricas basadas en eventos continuos**. Las métricas continuas incluyen ingresos, cantidad de productos pedidos, duración de la sesión, cantidad de vistas de página en la sesión, etc. Estos tipos de eventos también se denominan a veces métricas no binomiales o no Bernoulli.

>[!IMPORTANT]
>
>A partir de [!DNL Adobe Target Standard/Premium] Versión 22.15.1 (8 y 9 de marzo de 2023), [!DNL Target] sigue admitiendo las actividades existentes con las métricas que ahora no son compatibles (enumeradas en las tablas siguientes). Sin embargo, a partir del 9 de septiembre de 2023, estas métricas ya no serán compatibles con las actividades existentes y todas las actividades que utilicen métricas no compatibles se suspenderán para forzar la migración de la actividad existente al nuevo comportamiento.

### Impacto en [!UICONTROL Asignación automática] actividades

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL averagetimespentonsite] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL botar] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL bounces] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL entradas] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL salidas] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL recargas] | Maximizar valor de métrica |
| [!UICONTROL Visitantes] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL Visitas] | Maximizar valor de métrica |

### Impacto en [!UICONTROL Segmentación automática] actividades

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL movimientos del carro] | Maximizar valor de métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL Visitantes] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL Visitas] | Maximizar valor de métrica |

## Limitaciones y notas

Algunas limitaciones y notas se aplican a ambas [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades. Se aplican otras limitaciones y notas a un tipo de actividad u otro.

### Asignación automática y segmentación automática {#both}

* Al utilizar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], siempre debe ver los informes en [!DNL Analytics].
* La fuente de informes no se puede cambiar de [!DNL Analytics] hasta [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no se admiten como métricas de objetivo principal, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.

### Asignación automática {#aa}

* **Frecuencia de formación**: [!UICONTROL Asignación automática] los modelos siguen entrenando cada hora, como de costumbre.
* **Modelos de atribución**: [!DNL Target] utiliza el [!DNL Adobe Analytics] modelo de atribución predeterminado para[!UICONTROL  Asignación automática] actividades que utilizan A4T.
* **Confianza**: la fórmula de confianza utilizada por [!UICONTROL Asignación automática] actividades es diferente de la fórmula que se muestra de forma predeterminada en la [!DNL Adobe Analytics] [!UICONTROL A4T] panel. [Como se describe aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Asignación automática] utiliza intervalos de confianza más conservadores que los habituales [!UICONTROL Prueba A/B] actividades. Estos niveles de confianza conservadores compensan las evaluaciones repetidas (picos) de los datos. Como resultado, el informe predeterminado en [!DNL Adobe Analytics] muestra intervalos de confianza más estrechos en comparación con los intervalos que utiliza el [!UICONTROL Asignación automática] algoritmo. Sin embargo, puede determinar qué experiencia se ve favorecida por los algoritmos en función de qué experiencia se le envían más visitantes únicos.
* **Estado del ganador**: Actualmente, la variable [Insignias de &quot;Ningún ganador aún&quot; y &quot;Ganador&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) no están disponibles en el [!UICONTROL A4T] panel en [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se visualiza el mismo informe en [!DNL Target]. Una insignia de &quot;estrella&quot; ganadora que se muestra en una [!DNL Target] informe para un [!UICONTROL Asignación automática] La actividad de mediante A4T debe ignorarse. Este distintivo refleja los cálculos de confianza habituales y no los cálculos utilizados por [!UICONTROL Asignación automática].

### Segmentación automática {#at}

* [!UICONTROL Segmentación automática] los modelos siguen entrenando cada 24 horas, como de costumbre. Sin embargo, los datos de evento de conversión procedentes de [!DNL Analytics] se retrasa entre seis y 24 horas más. Este retraso significa la distribución del tráfico por [!DNL Target] rastrea los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez. El rendimiento de la actividad se refleja más estrechamente [!DNL Analytics] comportamiento de conversión después de cinco días.

   Considere utilizar [!UICONTROL Asignación automática] en lugar de [!UICONTROL Segmentación automática] para actividades de corta duración en las que la mayor parte del tráfico se produce dentro de los primeros cinco días de vida de la actividad.

* Al utilizar [!DNL Analytics] como fuente de datos para un [!UICONTROL Segmentación automática] actividad, las sesiones finalizan al cabo de seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en el *Guía de herramientas de Analytics*.

## Tutoriales

Aunque las funcionalidades de análisis enriquecidas están disponibles en [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algunas modificaciones en el valor predeterminado [!UICONTROL Analytics for Target] Los paneles deben interpretar correctamente [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades. Estas modificaciones son necesarias debido a las diferencias entre las actividades de experimentación (A/B manual y [!UICONTROL Asignación automática]) y actividades de personalización ([!UICONTROL Segmentación automática]).

### Configuración de informes de A4T en[!DNL Analysis Workspace]para actividades de [!UICONTROL Asignación automática] 

Este tutorial le guiará por las modificaciones recomendadas para analizar [!UICONTROL Asignación automática] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de asignación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank} in *Tutorials de Adobe Target*.

### Configuración de informes de A4T en[!DNL Analysis Workspace]para actividades de [!UICONTROL Segmentación automática]

Este tutorial le guiará por las modificaciones recomendadas para analizar [!UICONTROL Segmentación automática] actividades en [!DNL Analysis Workspace].

Para obtener más información, consulte [Configuración de informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank} in *Tutorials de Adobe Target*.


