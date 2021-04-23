---
keywords: multivariable;mvt;métricas;definir métricas;métrica de objetivo;configuración de actividades;métrica de éxito;conversión;ingresos;participación
description: Aprenda a especificar métricas en una actividad de prueba multivariable de Adobe [!DNL Target] para determinar si una visita es satisfactoria, como Conversión, Ingresos y Participación.
title: ¿Cómo establezco métricas de objetivo en una actividad de prueba multivariable (MVT)?
feature: Pruebas multivariable
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 83%

---

# Definir métricas para pruebas multivariable

Utilice métricas en una prueba multivariable de Adobe Target para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte  [Métricas de éxito](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Lista Definir métricas](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   En la página [!UICONTROL Seleccionar métricas] se muestra una lista de todas las métricas de éxito que puede elegir para la actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * Conversión
   * Ingresos
   * Participación

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.
1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si se habilita, el [!UICONTROL Valor estimado del campo] Conversión (no disponible para las métricas Puntuación de página) proporciona un valor para el objetivo. Este valor permite a Target calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte  [Métricas de éxito](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Opcional) Añada otras métricas.
1. Haga clic en **[!UICONTROL Continuar]** cuando termine de configurar las métricas. Tenga en cuenta que cuando nombra o renombra una métrica, no se permiten los siguientes caracteres:

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

## Vídeo de formación: Métricas de actividad (7:43)  ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre cómo trabajar con métricas de éxito.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de conversión, ingresos y participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
