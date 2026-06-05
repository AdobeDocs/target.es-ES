---
keywords: Target;informes;configuración de informes;varias métricas;métricas mostradas;métricas ocultas
description: Obtenga información sobre cómo seleccionar varias métricas para verlas en un informe mediante Adobe Target.
title: ¿Cómo puedo ver varias métricas en un informe?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
TQID: https://experienceleague.adobe.com/mXLlrS1wwfISfxWxq2c-sMDJP1vqxQjbqM-DsLJK9bY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 439
ht-degree: 55%

---

# Ver varias métricas en un informe

Puede seleccionar varias métricas para verlas en un informe de [!DNL Adobe Target].

Tenga en cuenta la siguiente información cuando trabaje con varias métricas en los informes:

* La capacidad para ver varias métricas solo está disponible para las actividades de [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) y [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md) (XT).
* No se permite agregar más de 20 métricas a un informe para una actividad que use [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Puede agregar tantas métricas como tenga en su actividad a informes para actividades que *no* usen A4T.
* No puede usar la [opción de descarga](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para descargar informes a CSV si ha seleccionado varias métricas. Para habilitar la opción [!UICONTROL Descargar], seleccione una única métrica.
* No puede ver varias métricas para las actividades creadas antes de la versión de julio de 2015 [!DNL Target] (30 de julio de 2015).

**Para seleccionar varias métricas que se mostrarán en el informe:**

1. Para mostrar un informe, haga clic en **[!UICONTROL Actividades]**, en la actividad que quiera de la lista y luego en la ficha **[!UICONTROL Informes]**.
1. Haga clic en la lista desplegable **[!UICONTROL Métrica de informes]** para ver las listas [!UICONTROL Métricas mostradas] y [!UICONTROL Métricas ocultas].

   Puede utilizar el cuadro [!UICONTROL Buscar] para encontrar rápidamente métricas disponibles que se añadirán a la lista [!UICONTROL Métricas mostradas].

   Tenga en cuenta que puede seleccionar varias métricas tanto en la [!UICONTROL Visualización de tabla] como en la [!UICONTROL Visualización de gráfico] del informe.

1. Pase el puntero del ratón sobre la métrica deseada en la lista [!UICONTROL Métricas ocultas] y, a continuación, haga clic en **[!UICONTROL Seleccionar]** para moverlas a la lista [!UICONTROL Métricas mostradas].

   O

   Arrastre y suelte las métricas deseadas de la lista [!UICONTROL Métricas ocultas] a la lista [!UICONTROL Métricas mostradas].

   Debe haber al menos una métrica en la lista [!UICONTROL Métricas mostradas].

   Puede reorganizar las métricas arrastrándolas y soltándolas en el orden deseado en la lista [!UICONTROL Métricas mostradas]. El orden seleccionado se reflejará en [!UICONTROL Visualización de tabla] y [!UICONTROL Visualización de gráfico]. Para eliminar una métrica de la lista [!UICONTROL Métricas mostradas], pase el puntero del ratón sobre ella y, a continuación, haga clic en el icono **X**.

1. Haga clic en **[!UICONTROL Guardar]** cuando termine.
1. (Condicional) Mientras ve el informe en la [!UICONTROL Vista de tabla], coloque el puntero del mouse (ratón) sobre el encabezado de columna de cualquier métrica para mostrar una flecha azul. Haga clic en la flecha para expandir la tabla y mostrar el [!UICONTROL Alza] y la [!UICONTROL Confianza] para esa métrica.

   Solo puede expandir una métrica/coluna a la vez. Vuelva a hacer clic en la flecha para contraer las columnas.

1. (Condicional) Mientras ve el informe en la [!UICONTROL vista de gráfico], puede seleccionar métricas individuales para mostrar en la lista desplegable.
