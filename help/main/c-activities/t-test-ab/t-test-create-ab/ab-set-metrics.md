---
keywords: A/B;métricas de actividad;métricas;definir métricas;métrica de objetivo;métrica de éxito;configuración de actividades;conversión;ingresos;participación
description: Descubra cómo establecer métricas en una actividad A/B, de segmentación de experiencias o de prueba multivariable para determinar el éxito de la visita, como [!UICONTROL Conversión], [!UICONTROL Ingresos] y [!UICONTROL Participación].
title: ¿Cómo configuro las métricas de objetivo en una actividad A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 24%
---
# Definir métricas {#ab-set-metrics}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información sobre cómo establecer la métrica de objetivo y las métricas adicionales de una actividad A/B, de segmentación de experiencias (XT) o de prueba multivariable (MVT), y qué caracteres no están permitidos en los nombres de métricas.

>[!ENDSHADEBOX]

Use métricas en una actividad [!DNL Adobe Target] A/B, [!UICONTROL Segmentación de experiencias] (XT) o [!UICONTROL Prueba multivariable] (MVT) para determinar si una visita es satisfactoria. Para obtener información detallada sobre las métricas de éxito, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

>[!NOTE]
>
>Esta página se aplica cuando [!DNL Adobe Target] es el origen de informes. Para las otras fuentes de informes, vea [[!DNL Adobe Analytics] como fuente de informes para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [[!DNL Target] informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## Definir una métrica {#set-a-metric}

1. En la sección **[!UICONTROL Configuración de informes]** de la página **[!UICONTROL Objetivos y configuración]**, seleccione una [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

   La opción **[!UICONTROL Seleccionar métricas]** enumera las métricas de éxito que puede elegir para su actividad. Las métricas de éxito se dividen en las categorías siguientes:

   * **[!UICONTROL Conversión]**
   * **[!UICONTROL Ingresos]**
   * **[!UICONTROL Participación]**

   Puede usar cualquiera de las métricas de éxito predeterminadas o bien crear una métrica de éxito personalizada. También puede marcar una métrica de éxito como una métrica principal. Las tarjetas de informes y de Experience Cloud muestran la métrica principal de forma predeterminada, si se configura una.

   ![](../../assets/metric-1.png)

1. Especificar la configuración de las métricas. La configuración disponible depende de la métrica de éxito que utilice.

1. Si está habilitado, el **[!UICONTROL Valor estimado de la conversión]** proporciona un valor para el objetivo:

   * El valor permite que [!DNL Target] calcule un alza estimada de ingresos.
   * El campo es opcional; sin embargo, los ingresos incrementales de cualquier métrica que no sea de ingresos no se pueden calcular sin él.
   * El campo no está disponible para las métricas **[!UICONTROL Puntuación de página]**.
   * El tipo de datos es moneda.
   * El campo se muestra progresivamente después de que el usuario indique la acción realizada para satisfacer el objetivo.

   Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). La configuración correcta de las métricas de éxito es crítica para asegurarse de obtener los datos esperados.

   ![](../../assets/metric-2.png)

1. (Opcional) Para realizar un seguimiento de más de la métrica de objetivo, haga clic en **[!UICONTROL Agregar una nueva métrica]** y, a continuación, seleccione y configure cada métrica adicional como se describe en los pasos anteriores.

1. Cuando termine de configurar las métricas, haga clic en **[!UICONTROL Continuar]** en una actividad de XT o en **[!UICONTROL Guardar y cerrar]** en una actividad de MVT.

## Caracteres no permitidos en los nombres de métricas {#metric-name-rules}

![](../../assets/metric-3.png)

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
