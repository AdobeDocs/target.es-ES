---
keywords: a4t;A4T;Analytics como fuente de informes para Target;analytics para Target
description: Aprenda a crear actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] en [!DNL Target] que usen [!DNL Analytics] como fuente de informes (A4T).
title: ¿Admite A4T actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
TQID: https://experienceleague.adobe.com/VVbjMp7jYDyslZ8ubn8ntPufLK8nKGI9k3ZGh1DLWWs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1509
ht-degree: 6%

---

# Compatibilidad de A4T con [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] actividades

La integración de [!DNL Adobe Target] a [!DNL Adobe Analytics], conocida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), admite las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

La integración con A4T le permite:

* Usa la capacidad de bandido multibrazo de [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para dirigir el tráfico a las experiencias ganadoras.
* Use el algoritmo de aprendizaje automático de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para elegir la mejor experiencia para cada visitante. [!UICONTROL La segmentación automática] elige la mejor experiencia en función del perfil, el comportamiento y el contexto de cada usuario, todo ello con una métrica de objetivos de [!DNL Adobe Analytics] y las abundantes capacidades de análisis e informes de [!DNL Adobe Analytics].

Asegúrese de que ha [implementado A4T para su uso con pruebas A/B y actividades de segmentación de experiencias](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Si usa `analyticsLogging = client_side`, también debe pasar el valor `sessionId` a [!DNL Analytics]. Para obtener más información, consulte [Informes de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} en la *Guía para desarrolladores de Adobe Target*.

En primer lugar:

1. Mientras [crea una actividad [!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), en la página **[!UICONTROL Segmentación]**, haga clic en el control **[!UICONTROL Asignación de tráfico]** y, a continuación, elija el método de asignación de tráfico que desee en el panel derecho.

   ![Configuración del método de asignación de tráfico](/help/main/c-activities/assets/auto-target.png)

   Los métodos de asignación de tráfico disponibles son los siguientes:

   * **[!UICONTROL Manual (predeterminado)]**: especifique el porcentaje de visitantes que quiere que vean cada experiencia. Puede dividir los porcentajes de manera uniforme entre todas las experiencias, o especificar porcentajes superiores o inferiores para cada experiencia. El total de todas las experiencias debe ser igual al 100%.

   * **[!UICONTROL Asignar automáticamente a la mejor experiencia]**: La mayoría de los visitantes de la actividad son dirigidos automáticamente a experiencias de mejor rendimiento. Algunos visitantes se asignan a todas las experiencias para mantener la exploración de las experiencias y para detectar cambios en las tendencias de rendimiento. Para obtener más información, consulte [[!UICONTROL Información general sobre la asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Segmentación automática para experiencias personalizadas]**: [!DNL Target] utiliza aprendizaje automático avanzado para personalizar el contenido y dirigir las conversiones al identificar varias experiencias de alto rendimiento definidas por expertos en marketing; a continuación, ofrece a los visitantes la experiencia más adaptada en función de su perfil de cliente y del comportamiento pasado de visitantes similares. Para obtener más información, consulte [Información general sobre la segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Para obtener más información e instrucciones paso a paso, consulte [Crear una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) y [Crear una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md).

1. Seleccione **[!UICONTROL Adobe Analytics]** para su **[!UICONTROL Source de informes]** en la página **[!UICONTROL Objetivos y configuración]**, seleccione la empresa y el grupo de informes que corresponda a su objetivo de optimización deseado.

   ![Sección Reporting Source en la página Objetivos y configuración](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Especifique el servidor de seguimiento y la zona protegida.

1. Elija una métrica de [!UICONTROL Objetivo principal].

   * Para usar [!DNL Adobe Target] para especificar el objetivo de optimización, elija **[!UICONTROL Conversión]** .
   * Elija **[!UICONTROL Usar una métrica de Analytics]** y, a continuación, seleccione una métrica de [!DNL Analytics] para usarla como objetivo de optimización. Puede usar una métrica de conversión [!DNL Analytics] lista para usar o un evento personalizado [!DNL Analytics].

   Consulte [Métricas de objetivo admitidas](#supported) a continuación para obtener más información.

1. Guarde y active la actividad.

   [!UICONTROL Asignación automática] usa la métrica que seleccionaste para optimizar la actividad y lleva a los visitantes a la experiencia que maximiza tu métrica de objetivo.

   O

   [!UICONTROL Segmentación automática] usa la métrica que seleccionaste para optimizar la actividad y así los visitantes obtendrán una mejor experiencia personalizada.

1. Use la pestaña **[!UICONTROL Informes]** para ver los informes de su actividad según su elección de [!DNL Adobe Analytics] métricas. Haga clic en **[!UICONTROL Ver en Analytics]** para profundizar y segmentar aún más los datos de informes.

## Métricas de objetivo admitidas {#supported}

[!UICONTROL A4T] para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] le permite elegir cualquiera de los siguientes tipos de métricas como métrica de objetivo principal para la optimización:

* [!DNL Adobe Target] métricas de conversión
* [!DNL Adobe Analytics] métricas de conversión
* [!DNL Adobe Analytics] eventos personalizados

>[!NOTE]
>
>Después de seleccionar [!UICONTROL Usar una métrica de Analytics], seleccione [!UICONTROL Maximizar tasa de conversión de visitantes únicos] para ver las métricas de conversión de [!DNL Adobe Analytics] disponibles y [!UICONTROL Maximizar valor de métrica por visitante] para explorar [!DNL Adobe Analytics] eventos personalizados.

[!DNL Target] le permite elegir métricas basadas en eventos binomiales o en métricas basadas en eventos continuos al usar [!UICONTROL A4T] para actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].

* **Métricas basadas en eventos binomiales**: Un evento binomial ocurre o no. Los eventos binomiales incluyen un clic, una conversión, un pedido, etc. A veces, estos tipos de eventos también se denominan eventos Bernoulli, binarios o discretos.

* **Métricas basadas en eventos continuos**. Las métricas continuas incluyen ingresos, cantidad de productos pedidos, duración de la sesión, cantidad de vistas de página en la sesión, etc. Estos tipos de eventos también se denominan a veces métricas no binomiales o no Bernoulli.

>[!IMPORTANT]
>
>A partir de la versión de [!DNL Adobe Target Standard/Premium] 22.15.1 (8 y 9 de marzo de 2023), [!DNL Target] sigue admitiendo las actividades existentes con las métricas que ahora no son compatibles (enumeradas en las tablas siguientes). Sin embargo, a partir del 9 de septiembre de 2023, estas métricas ya no serán compatibles con las actividades existentes y todas las actividades que utilicen métricas no compatibles se suspenderán para forzar la migración de la actividad existente al nuevo comportamiento.

### Impacto en [!UICONTROL actividades de asignación automática]

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL averagetimespentonsite] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL rebotar] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL devoluciones] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL entradas] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL salidas] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL vistas de página] | Maximizar valor de métrica |
| [!UICONTROL recargas] | Maximizar valor de métrica |
| [!UICONTROL visitantes] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL visitas] | Maximizar valor de métrica |

### Impacto en [!UICONTROL actividades de Segmentación automática]

| Nombre de la métrica | Ya no es compatible con: |
| --- | --- |
| [!UICONTROL movimientos de carro] | Maximizar valor de métrica |
| [!UICONTROL vistas de página] | Maximizar valor de métrica |
| [!UICONTROL visitantes] | Tasa de conversión, Maximizar valor de métrica |
| [!UICONTROL visitas] | Maximizar valor de métrica |

## Limitaciones y notas

Algunas limitaciones y notas se aplican a las actividades [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]. Se aplican otras limitaciones y notas a un tipo de actividad u otro.

### Asignación automática y segmentación automática {#both}

* Al usar [!DNL Adobe Analytics] como fuente de informes para [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], siempre debería ver los informes en [!DNL Analytics].
* No se puede cambiar el origen de los informes de [!DNL Analytics] a [!DNL Target] o viceversa después de activar una actividad.
* Aunque las métricas calculadas no se admiten como métricas de objetivo principal, a menudo es posible lograr el resultado deseado seleccionando un evento personalizado como métrica de objetivo principal. Por ejemplo, si desea optimizar para una métrica como &quot;finalizaciones de formulario por visitante&quot;, seleccione un evento personalizado que corresponda a &quot;finalizaciones de formulario&quot; como métrica de objetivo principal. [!DNL Target] normaliza automáticamente las métricas de conversión por visita para tener en cuenta la distribución desigual del tráfico, por lo que no es necesario utilizar una métrica calculada para realizar la normalización.

### Asignación automática {#aa}

* **Frecuencia de entrenamiento**: [!UICONTROL Asignación automática] modelos continúan entrenando cada hora, como de costumbre.
* **Modelos de atribución**: [!DNL Target] usa el modelo de atribución predeterminado de [!DNL Adobe Analytics] para [!UICONTROL &#x200B; actividades de Asignación automática] que usan A4T.
* **Confianza**: La fórmula de confianza utilizada por las actividades [!UICONTROL Asignación automática] es diferente de la fórmula mostrada de forma predeterminada en el panel [!DNL Adobe Analytics] [!UICONTROL A4T]. [Como se describe aquí](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Asignación automática] usa intervalos de confianza más conservadores que las actividades de [!UICONTROL Prueba A/B] normales. Estos niveles de confianza conservadores compensan las evaluaciones repetidas (picos) de los datos. Como resultado, el informe predeterminado de [!DNL Adobe Analytics] muestra intervalos de confianza más estrechos en comparación con los intervalos que usa el algoritmo de asignación automática [!UICONTROL Auto-Allocate]. Sin embargo, puede determinar qué experiencia se ve favorecida por los algoritmos en función de qué experiencia se le envían más visitantes únicos.
* **Estado del ganador**: Actualmente, las insignias [&quot;Ningún ganador aún&quot; y &quot;Ganador&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) no están disponibles en el panel [!UICONTROL A4T] en [!DNL Analysis Workspace]. Estas insignias tampoco están disponibles si se ve el mismo informe en [!DNL Target]. Se debe ignorar un distintivo de &quot;estrella&quot; ganador que se muestra en un informe [!DNL Target] para una actividad de [!UICONTROL Asignación automática] que usa A4T. Este distintivo refleja los cálculos de confianza habituales y no los cálculos utilizados por [!UICONTROL Asignación automática].

### Segmentación automática {#at}

* [!UICONTROL Segmentación automática] modelos continúan entrenando cada 24 horas, como de costumbre. Sin embargo, los datos de evento de conversión procedentes de [!DNL Analytics] se retrasan de seis a 24 horas más. Este retraso significa que la distribución del tráfico por [!DNL Target] rastrea los últimos eventos registrados en [!DNL Analytics]. Este retraso tiene el mayor efecto en las primeras 48 horas después de activar una actividad por primera vez. El rendimiento de la actividad refleja con mayor precisión el comportamiento de conversión de [!DNL Analytics] después de cinco días.

  Considere la posibilidad de usar [!UICONTROL Asignación automática] en lugar de [!UICONTROL Segmentación automática] para actividades de corta duración en las que la mayor parte del tráfico se produce dentro de los primeros cinco días de vida de la actividad.

* Cuando se usa [!DNL Analytics] como origen de datos para una actividad de [!UICONTROL segmentación automática], las sesiones finalizan después de que hayan transcurrido seis horas. No se contabilizan las conversiones que se producen después de seis horas.

Para obtener más información, consulte [Modelos de atribución y ventanas retroactivas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) en la *Guía de herramientas de Analytics*.

## Tutoriales

Aunque hay funcionalidades de análisis enriquecidas disponibles en [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], se requieren algunas modificaciones en el panel predeterminado de [!UICONTROL Analytics for Target] para interpretar correctamente las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]. Estas modificaciones son necesarias debido a diferencias entre las actividades de experimentación (manual A/B y [!UICONTROL Asignación automática]) y las actividades de personalización ([!UICONTROL Segmentación automática]).

### Configurando informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL actividades de asignación automática]

Este tutorial lo guiará por las modificaciones recomendadas para analizar las actividades de [!UICONTROL Asignación automática] en [!DNL Analysis Workspace].

Para obtener más información, consulte [Cómo configurar informes de A4T en Analysis Workspace para actividades de asignación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank} en *Tutoriales de Adobe Target*.

### Configurando informes de A4T en [!DNL Analysis Workspace] para [!UICONTROL actividades de Segmentación automática]

Este tutorial lo guiará por las modificaciones recomendadas para analizar las actividades de [!UICONTROL Segmentación automática] en [!DNL Analysis Workspace].

Para obtener más información, consulte [Cómo configurar informes de A4T en Analysis Workspace para actividades de segmentación automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank} en *Tutoriales de Adobe Target*.


