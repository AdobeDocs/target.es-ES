---
keywords: A/B;métricas de actividad;métricas;definir métricas;métrica de objetivo;métrica de éxito;configuración de actividades;conversión;ingresos;participación
description: Obtenga información sobre cómo especificar métricas en un Adobe [!DNL Target] Actividad A/B para determinar si una visita es satisfactoria; por ejemplo, en el caso de la conversión, los ingresos y la participación.
title: ¿Cómo configuro las métricas de objetivo en una actividad A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 85%

---

# Definir métricas

Uso de métricas en una [!DNL Adobe Target] Actividad A/B para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte  [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Seleccionar métrica de éxito](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   En la página [!UICONTROL Seleccionar métricas] se muestra una lista de todas las métricas de éxito que puede elegir para la actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * Conversión
   * Ingresos
   * Participación

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.
1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si se habilita, el [!UICONTROL Valor estimado del campo] Conversión (no disponible para las métricas Puntuación de página) proporciona un valor para el objetivo. Este valor permite a Target calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).
1. (Opcional) Añada otras métricas.
1. Haga clic en **[!UICONTROL Continuar]** cuando termine de configurar las métricas. 

Tenga en cuenta que cuando nombra o renombra una métrica, no se permiten los siguientes caracteres:

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

## Vídeo de formación: Métricas de actividad (7:43) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre cómo trabajar con métricas de éxito.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de Conversión, Ingresos y Participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
