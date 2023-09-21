---
keywords: A/B;métricas de actividad;métricas;definir métricas;métrica de objetivo;métrica de éxito;configuración de actividades;conversión;ingresos;participación
description: Obtenga información sobre cómo especificar métricas en una [!DNL Adobe Target] Actividad A/B para determinar si una visita es satisfactoria, como [!UICONTROL Conversión], [!UICONTROL Ingresos], y [!UICONTROL Participación].
title: ¿Cómo configuro las métricas de objetivo en una actividad A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: 2d5272a852dc879e7307695744b70afe7fee9a38
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 68%

---

# Definir métricas

Uso de métricas en una [!DNL Adobe Target] Actividad A/B para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte  [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. En el **[!UICONTROL Configuración de informes]** de la sección **[!UICONTROL Objetivos y configuración]** página, seleccione una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Seleccionar métrica de éxito](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   El [!UICONTROL Seleccionar métricas] Esta opción enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversión]
   * [!UICONTROL Ingresos]
   * [!UICONTROL Participación]

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.

1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si se habilita, el [!UICONTROL Valor estimado del campo] Conversión (no disponible para las métricas Puntuación de página) proporciona un valor para el objetivo.  Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

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

## Vídeo de formación: Métricas de actividad (7:43) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre cómo trabajar con métricas de éxito.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de Conversión, Ingresos y Participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
