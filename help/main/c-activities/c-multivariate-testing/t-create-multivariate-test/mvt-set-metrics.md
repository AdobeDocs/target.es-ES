---
keywords: multivariable;mvt;métricas;definir métricas;métrica de objetivo;configuración de actividades;métrica de éxito;conversión;ingresos;participación
description: Aprenda a especificar métricas en una actividad de  [!DNL Adobe Target] [!UICONTROL Prueba multivariable] para determinar si una visita es satisfactoria, como [!UICONTROL Conversión], [!UICONTROL Ingresos] y [!UICONTROL Participación].
title: ¿Cómo puedo establecer métricas de objetivo en una actividad de [!UICONTROL prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
TQID: https://experienceleague.adobe.com/iJntBcXy4QNgEq0SnzLpqMX6S5HQ6kBy4PMoQivlVxw
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 55%

---

# Definir métricas para una actividad [!UICONTROL Prueba multivariable]

Use métricas en una [!DNL Adobe Target] [!UICONTROL prueba multivariable] para determinar si una visita es satisfactoria.

Para obtener información detallada sobre las métricas de éxito, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especificar el objetivo de la actividad.
1. Seleccionar una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Lista Definir métricas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   La página [!UICONTROL Seleccionar métricas] enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * [!UICONTROL Conversión]
   * [!UICONTROL Ingresos]
   * [!UICONTROL Participación]

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.

1. Especificar la configuración de las métricas.

   La configuración disponible depende de la métrica de éxito que utilice.

   Si se habilita, el campo [!UICONTROL Valor estimado de la conversión] (no disponible para las métricas [!UICONTROL Puntuación de página]) proporciona un valor para el objetivo. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   La configuración correcta de las métricas de éxito es crítica para asegurarse de que obtiene los datos esperados.

   Para obtener más información, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

1. (Opcional) Añada otras métricas.
1. Haga clic en **[!UICONTROL Guardar y cerrar]** cuando termine de configurar las métricas.

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
* Comprenda y cree las métricas [!UICONTROL Conversión], [!UICONTROL Ingresos] y [!UICONTROL Participación]
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
