---
keywords: segmentación de experiencias;xt;métricas;definir métricas;métrica de segmentación;configuración de actividades;métrica de éxito;conversión;ingresos;participación
description: Obtenga información sobre cómo especificar métricas en una [!DNL Adobe Target] [!UICONTROL Segmentación de experiencias] actividad para determinar si una visita es satisfactoria, como [!UICONTROL Conversión], [!UICONTROL Ingresos], o [!UICONTROL Participación].
title: ¿Cómo configuro las métricas de objetivo en una? [!UICONTROL Segmentación de experiencias] ¿Actividad?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 62%

---

# Definir métricas en [!UICONTROL Segmentación de experiencias] Actividades (XT)

Uso de métricas en una [!DNL Adobe Target] [!UICONTROL Segmentación de experiencias] (XT) para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte  [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Seleccionar métrica de éxito](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   El [!UICONTROL Seleccionar métricas] Esta página enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversión]
   * [!UICONTROL Ingresos]
   * [!UICONTROL Participación]

   Utilice cualquiera de las métricas de éxito creadas previamente o puede crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.
1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si está activada, la variable [!UICONTROL Valor estimado de la conversión] campo (no disponible para [!UICONTROL Puntuación de página] métricas) proporciona un valor para el objetivo. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Añada otras métricas.
1. Haga clic en **[!UICONTROL Continuar]** cuando termine de configurar las métricas. 

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
* Qué son y cómo compilar las métricas de [!UICONTROL Conversión], [!UICONTROL Ingresos] y [!UICONTROL Participación]
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
