---
keywords: Segmentación;audiencia;informe;métrica de éxito
description: Obtenga información sobre cómo elegir una métrica de éxito en [!DNL Adobe Target] que califica al usuario para la audiencia de informes.
title: ¿Puedo aplicar una audiencia de informes a una métrica de éxito?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 52%

---

# Aplicación de una audiencia de informes a una métrica de éxito

Elija una métrica de éxito que permita al usuario entrar en la audiencia de informes de [!DNL Adobe Target].

Para todas las actividades, la lista desplegable [!UICONTROL Aplicado a] le permite aplicar una audiencia a una métrica de éxito, de modo que pueda ver los números del informe una vez que se alcance la métrica y en acciones posteriores.

![imagen success_metric](assets/success_metric.png)

Por ejemplo, supongamos que ha creado una actividad para todos los visitantes que entran en su página de inicio y alcanzan la página de conversión, pero que también desea obtener más datos sobre los visitantes que añadieron más de 50 $ al carro antes de la conversión.

El [!UICONTROL Aplicado a las] La lista desplegable proporciona potencialmente tres categorías: cualquier visitante de la actividad, solo visitantes que alcanzan un determinado paso en la actividad o solo visitantes que alcanzan la conversión. O, dicho de otro modo, puede especificar que un visitante debe haber alcanzado un mbox en la página de entrada de la actividad, un mbox que define algún punto en la mitad de la actividad o el mbox de conversión al final de la actividad.

[Las métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) solo están disponibles si las ha configurado para su actividad. Si no ha definido métricas de éxito, solo verá dos opciones en la lista desplegable: [!UICONTROL Entrada de campaña] y [!UICONTROL Conversión].

Tenga en cuenta la siguiente información al aplicar una audiencia de informes a una métrica de éxito:

* Para las acciones anteriores a la acción con la métrica de éxito aplicada, [!DNL Target] no aplica una audiencia segmentada.
* Para las acciones posteriores a la métrica de éxito aplicada, [!DNL Target] aplica una audiencia segmentada.

Para ver la segmentación en los informes, seleccione la audiencia que desee en la [!UICONTROL Audiencia] lista desplegable en el informe de actividad.

![imagen desplegable reporting_audience_dropdown](assets/reporting_audience_dropdown.png)
