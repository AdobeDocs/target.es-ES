---
keywords: multivariable;mvt;métricas;definir métricas;métrica de objetivo;configuración de actividades;métrica de éxito;conversión;ingresos;participación
description: Obtenga información sobre cómo especificar métricas en una actividad  [!DNL Adobe Target] [!UICONTROL Multivariate Test] para determinar si una visita es satisfactoria, como [!UICONTROL Conversion], [!UICONTROL Revenue] y [!UICONTROL Engagement].
title: ¿Cómo configuro las métricas de objetivo en una actividad [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 59%

---

# Definir métricas para una actividad [!UICONTROL Multivariate Test]

Use métricas en un(a) [!DNL Adobe Target] [!UICONTROL Multivariate Test] para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Lista Definir métricas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   La página [!UICONTROL Select Metrics] enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.

1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si está habilitado, el campo [!UICONTROL Estimated Value of the Conversion] (no disponible para las métricas [!UICONTROL Page Score]) proporciona un valor para el objetivo. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

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
