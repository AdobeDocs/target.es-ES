---
keywords: Destinatario;informes;configuración del informe;varias métricas;métricas;métricas mostradas;métricas ocultas
description: Seleccione varias métricas para la vista en un informe mediante Adobe Target.
title: Visualización de varias métricas en un informe
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 62%

---


# Ver varias métricas en un informe{#view-multiple-metrics-in-a-report}

Puede seleccionar varias métricas para la vista en un informe [!DNL Adobe Target].

Tenga en cuenta la siguiente información cuando trabaje con varias métricas en los informes:

* La capacidad de vista de varias métricas está disponible únicamente para actividades [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md), [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Destinatario automático](/help/c-activities/auto-target/auto-target-to-optimize.md) y [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) (XT).
* No puede agregar más de 20 métricas a un informe para una actividad que utilice [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Puede agregar tantas métricas como tenga en la actividad a los informes de actividades que *no* utilicen A4T.
* Si selecciona varias métricas, no puede utilizar la opción [](/help/c-reports/downloading-data-in-csv-file.md)Descargar para descargar informes a CSV. Para habilitar la opción [!UICONTROL Descargar], seleccione una única métrica.
* No se pueden realizar vistas de varias métricas para actividades creadas antes de la versión [!DNL Target] de julio de 2015 (30 de julio de 2015).

**Para seleccionar varias métricas que se mostrarán en el informe:**

1. Para mostrar un informe, haga clic en **[!UICONTROL Actividades]**, en la actividad que quiera de la lista y luego en la ficha **[!UICONTROL Informes.]**
1. Haga clic en la lista desplegable **[!UICONTROL Métrica de informes]** para ver las listas [!UICONTROL Métricas mostradas] y [!UICONTROL Métricas ocultas].

   ![](assets/multiple_metrics.png)

   Puede utilizar el cuadro [!UICONTROL Buscar] para encontrar rápidamente métricas disponibles que se añadirán a la lista [!UICONTROL Métricas mostradas].

   Tenga en cuenta que puede seleccionar varias métricas tanto en la [!UICONTROL Visualización de tabla] como en la [!UICONTROL Visualización de gráfico] del informe.

1. Pase el puntero del ratón sobre la métrica deseada en la lista [!UICONTROL Métricas ocultas] y, a continuación, haga clic en **[!UICONTROL Seleccionar]** para moverlas a la lista [!UICONTROL Métricas mostradas].

   O

   Arrastre y suelte las métricas deseadas de la lista [!UICONTROL Métricas ocultas] a la lista [!UICONTROL Métricas mostradas].

   Debe haber al menos una métrica en la lista [!UICONTROL Métricas mostradas].

   Puede reorganizar las métricas arrastrándolas y soltándolas en el orden deseado en la lista [!UICONTROL Métricas mostradas]. El orden seleccionado se reflejará en la [!UICONTROL Vista de tabla] y [!UICONTROL Vista de gráfico]. Para eliminar una métrica de la lista [!UICONTROL Métricas mostradas], pase el puntero del ratón sobre ella y, a continuación, haga clic en el icono **X**.

1. Haga clic en **[!UICONTROL Guardar]** cuando termine.
1. (Condicional) Mientras ve el informe en la [!UICONTROL Vista de tabla], coloque el puntero del ratón en el encabezado de columna de cualquier métrica para mostrar una flecha azul. Haga clic en la flecha para expandir la tabla y mostrar el [!UICONTROL Alza] y la [!UICONTROL Confianza] para esa métrica.

   ![](assets/multiple_metrics_table.png)

   Solo puede expandir una métrica/coluna a la vez. Vuelva a hacer clic en la flecha para contraer las columnas.

1. (Condicional) Al ver el informe en la Vista Gráfico, puede seleccionar métricas individuales para mostrarlas en la lista desplegable:

   ![](assets/multiple_metrics_graph.png)

