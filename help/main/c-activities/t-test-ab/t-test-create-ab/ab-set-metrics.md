---
keywords: A/B;métricas de actividad;métricas;definir métricas;métrica de objetivo;métrica de éxito;configuración de actividades;conversión;ingresos;participación
description: Descubra cómo establecer métricas en una actividad A/B para determinar el éxito de la visita, incluidas [!UICONTROL Conversion], [!UICONTROL Revenue] y [!UICONTROL Engagement].
title: ¿Cómo configuro las métricas de objetivo en una actividad A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 58%

---

# Definir métricas

Utilice métricas en una actividad A/B de [!DNL Adobe Target] para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. En la sección **[!UICONTROL Reporting Settings]** de la página **[!UICONTROL Goals & Settings]**, seleccione una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

   La opción [!UICONTROL Select Metrics] enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.

1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si está habilitado, el campo [!UICONTROL Estimated Value of the Conversion] (no disponible para las métricas [!UICONTROL Page Score]) proporciona un valor para el objetivo. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de obtener los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Añada otras métricas.

Al asignar un nombre a una métrica o cambiarla por otro, no se permiten los siguientes caracteres:

| Carácter | Descripción |
|--- |--- |
| / | Barra oblicua |
| ? | Signo de interrogación |
| # | Signo de número |
| : | Dos puntos |
| = | Igual a |
| + | Más |
| - | Menos |
| @ | Arroba |
