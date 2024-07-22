---
keywords: segmentación de experiencias;xt;métricas;definir métricas;métrica de segmentación;configuración de actividades;métrica de éxito;conversión;ingresos;participación
description: Obtenga información sobre cómo especificar métricas en una actividad  [!DNL Adobe Target] [!UICONTROL Experience Targeting] para determinar si una visita es satisfactoria, como [!UICONTROL Conversion], [!UICONTROL Revenue] o [!UICONTROL Engagement].
title: ¿Cómo configuro las métricas de objetivo en una actividad de [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 56%

---

# Establecer métricas en actividades [!UICONTROL Experience Targeting] (XT)

Use métricas en una actividad [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Seleccionar métrica de éxito](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   La página [!UICONTROL Select Metrics] enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Utilice cualquiera de las métricas de éxito creadas previamente o puede crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.
1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si está habilitado, el campo [!UICONTROL Estimated Value of the Conversion] (no disponible para [!UICONTROL Page Score] métricas) proporciona un valor para el objetivo. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Añada otras métricas.
1. Haga clic en **[!UICONTROL Continue]** cuando termine de configurar las métricas.

Al asignar un nombre a una métrica o cambiarla por otro, no se permiten los siguientes caracteres:

| Carácter | Descripción |
|--- |--- |
| `/` | Barra oblicua |
| `?` | Signo de interrogación |
| `#` | Signo de número |
| `:` | Dos puntos |
| `=` | Igual a |
| `+` | Más |
| `-` | Menos |
| `@` | Arroba |

## Vídeo de formación: Métricas de actividad (7:43) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre cómo trabajar con métricas de éxito.

* Qué son las métricas de “objetivo”
* Comprender y generar las métricas [!UICONTROL Conversion], [!UICONTROL Revenue] y [!UICONTROL Engagement]
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
