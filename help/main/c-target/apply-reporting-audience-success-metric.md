---
keywords: Segmentación;audiencia;informe;métrica de éxito
description: Aprenda a elegir una métrica de éxito en  [!DNL Adobe Target]  que permita al usuario entrar en la audiencia de informes.
title: ¿Puedo aplicar una audiencia de informes a una métrica de éxito?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: bcbb6dec9d6add07c109b07bf125c1356ad2a8b9
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 36%

---

# Aplicación de una audiencia de informes a una métrica de éxito

Elija una métrica de éxito que permita al usuario entrar en la audiencia de informes en [!DNL Adobe Target].

Para todas las actividades, la lista desplegable [!UICONTROL Applied At] le permite aplicar una audiencia a una métrica de éxito para que pueda ver los números de los informes una vez alcanzada la métrica y para las acciones posteriores.

![imagen de métrica de éxito](assets/success_metric.png)

Por ejemplo, supongamos que ha creado una actividad para todos los visitantes que entran en su página de inicio y alcanzan la página de conversión, pero que también desea obtener más datos sobre los visitantes que añadieron más de 50 $ al carro antes de la conversión.

La lista desplegable [!UICONTROL Applied At] ofrece potencialmente tres categorías:

* Visitantes de la actividad
* Solo los visitantes que alcanzan un determinado paso en la actividad
* Solo los visitantes que alcancen la conversión

O, dicho de otro modo, puede especificar que un visitante debe haber alcanzado un mbox en la página de entrada de la actividad, un mbox que define algún punto en la mitad de la actividad o el mbox de conversión al final de la actividad.

>[!NOTE]
>
>[Las métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) solo están disponibles si las ha configurado para su actividad. Si no ha definido métricas de éxito, solo verá dos opciones en la lista desplegable: [!UICONTROL Campaign Entry] y [!UICONTROL Conversion].


## Consideraciones

Tenga en cuenta la siguiente información al aplicar una audiencia de informes a una métrica de éxito:

* Solo las métricas de éxito que comiencen desde la a la que se aplica la audiencia mostrarán los datos de informes segmentados por la audiencia
* Las métricas de éxito anteriores a aquellas a las que se aplica la audiencia no se segmentarán con la audiencia y mostrarán todos los datos del visitante
* Las métricas se consideran en función de su orden en la definición de la actividad, siendo [!UICONTROL Primary Goal] el último.

## Ver segmentación en informes

Para ver la segmentación en los informes, seleccione la audiencia que desee en la lista desplegable [!UICONTROL Audience] del informe de actividad.

![imagen desplegable de reporting_audience_dropdown](assets/reporting_audience_dropdown.png)

## Ejemplo

Considere una actividad que tenga Métrica de éxito1, Métrica de éxito2, Métrica de éxito3 y el Objetivo principal.

Supongamos que tiene la Audiencia de informes1 configurada en &quot;Entrada&quot; y la Audiencia de informes2 configurada en Métrica de éxito2. Las audiencias filtrarán los datos de los informes de la siguiente manera:

|  | Visitantes | Métrica de éxito1 | Métrica de éxito2 | Métrica de éxito3 | Objetivo principal |
| --- | --- | --- | --- | --- | --- |
| Audience1 | Aplicado | Aplicado | Aplicado | Aplicado | Aplicado |
| Audiencia2 | No aplicado | No aplicado | Aplicado | Aplicado | Aplicado |
