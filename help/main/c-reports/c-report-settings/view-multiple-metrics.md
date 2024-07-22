---
keywords: Target;informes;configuración de informes;varias métricas;métricas mostradas;métricas ocultas
description: Obtenga información sobre cómo seleccionar varias métricas para verlas en un informe mediante Adobe Target.
title: ¿Cómo puedo ver varias métricas en un informe?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 12%

---

# Ver varias métricas en un informe

Puede seleccionar varias métricas para verlas en un informe de [!DNL Adobe Target].

Tenga en cuenta la siguiente información cuando trabaje con varias métricas en los informes:

* La capacidad para ver varias métricas solo está disponible para las actividades de [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) y [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md) (XT).
* No se permite agregar más de 20 métricas a un informe para una actividad que use [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Puede agregar tantas métricas como tenga en su actividad a informes para actividades que *no* usen A4T.
* No puede usar la [opción de descarga](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para descargar informes a CSV si ha seleccionado varias métricas. Debe seleccionar una sola métrica solamente para habilitar la opción [!UICONTROL Download].
* No puede ver varias métricas para las actividades creadas antes de la versión de julio de 2015 [!DNL Target] (30 de julio de 2015).

**Para seleccionar varias métricas que se mostrarán en el informe:**

1. Para mostrar un informe, haga clic en **[!UICONTROL Activities]**, haga clic en la actividad que quiera en la lista y luego haga clic en la ficha **[!UICONTROL Reports]**.
1. Haga clic en la lista desplegable **[!UICONTROL Report Metric]** para mostrar las listas [!UICONTROL Shown Metrics] y [!UICONTROL Hidden Metrics].

   ![imagen multiple_metrics](assets/multiple_metrics.png)

   Puede usar el cuadro [!UICONTROL Search] para buscar rápidamente las métricas disponibles y agregarlas a la lista [!UICONTROL Shown Metrics].

   Tenga en cuenta que puede seleccionar varias métricas de los modos [!UICONTROL Table View] y [!UICONTROL Graph View] del informe.

1. Pase el puntero del ratón sobre las métricas deseadas en la lista [!UICONTROL Hidden Metrics] y, a continuación, haga clic en **[!UICONTROL Select]** para moverlas a la lista [!UICONTROL Shown Metrics].

   O

   Arrastre y suelte las métricas deseadas de la lista [!UICONTROL Hidden Metrics] a la lista [!UICONTROL Shown Metrics].

   Debe haber al menos una métrica en la lista [!UICONTROL Shown Metrics].

   Puede reorganizar las métricas arrastrándolas y soltándolas en el orden deseado en la lista [!UICONTROL Shown Metrics]. El orden seleccionado se reflejará en [!UICONTROL Table View] y [!UICONTROL Graph View]. Para quitar una métrica de la lista [!UICONTROL Shown Metrics], pase el puntero del mouse (ratón) sobre la métrica y, a continuación, haga clic en el icono **X**.

1. Haga clic en **[!UICONTROL Save]** cuando termine.
1. (Condicional) Mientras ve el informe en [!UICONTROL Table View], coloque el puntero del mouse (ratón) sobre el encabezado de columna de cualquier métrica para mostrar una flecha azul. Haga clic en la flecha para expandir la tabla y mostrar [!UICONTROL Lift] y [!UICONTROL Confidence] para esa métrica.

   ![imagen multiple_metrics_table](assets/multiple_metrics_table.png)

   Solo puede expandir una métrica/coluna a la vez. Vuelva a hacer clic en la flecha para contraer las columnas.

1. (Condicional) Mientras ve el informe en la vista de gráfico, puede seleccionar métricas individuales para mostrarlas en la lista desplegable:

   ![imagen multiple_metrics_graph](assets/multiple_metrics_graph.png)
