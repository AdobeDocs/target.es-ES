---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;métrica;definiciones de métricas
description: Encuentre respuestas a preguntas sobre definiciones de métricas y uso de Analytics para actividades [!DNL Target] (A4T). A4T lets you use Analytics reporting with Adobe [!DNL Target] .
title: ¿Dónde puedo encontrar información sobre las definiciones de métricas con A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 40%

---

# Definiciones de métricas: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Cuándo caduca la pertenencia a la actividad? ¿Cuánto tiempo tiene que pasar después de que los visitantes entren a la actividad para que sus acciones se contabilicen en ella si no vuelven a verla? {#section_41B4958F33534E4B96DEE0C981227A79}

La caducidad predeterminada para la actividad es de 90 días después de la última interacción de un visitante con la actividad. ClientCare puede ajustar esta configuración si es necesario. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

## Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada? {#adv-settings}

Las opciones de [!UICONTROL Configuración avanzada] no están disponibles para actividades que usan [!DNL Analytics] como fuente de informes (A4T).

Para las actividades que utilizan A4T, la métrica de objetivo siempre utiliza las opciones &quot;[!UICONTROL Aumentar recuento y mantener al usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Estos ajustes *no* se pueden configurar.

Para las actividades que no son de A4T, puede utilizar las [opciones de Configuración avanzada](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para administrar cómo medir el éxito. Las opciones incluyen añadir dependencias, elegir si mantener al usuario en la actividad o eliminarlo, y si contar la métrica una vez por visitante o en cada impresión. Para acceder a las opciones de [!UICONTROL Configuración avanzada] en una actividad que no es de A4T, haga clic en los puntos verticales > [!UICONTROL Configuración avanzada], como se muestra a continuación:

![Configuración avanzada](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## ¿Qué son las métricas calculadas y cómo sustituyen el mbox SiteCatalyst:Event que yo usaba antes?    {#section_D59F4719E6B94758A2187427C17F8EF3}

Las métricas calculadas le permiten crear métricas personalizadas que se derivan de segmentos o de cálculos matemáticos. En el pasado, en las situaciones en las que quizá usaba el mbox de `SiteCatlayst:Event` donde `evar27=shoes` y el evento es `purchase`, ahora crearía un segmento con `evar27=shoes` y después crearía una métrica calculada en la que el evento es `purchase` con el segmento aplicado. Estas métricas se pueden crear en cualquier momento, incluso después de que la actividad esté en curso. Después se pueden usar en cualquier informe de Analytics.

## ¿A4T atribuye conversiones a varias campañas?    {#section_7F15C727206440CD86B3A8CE77087DF9}

Sí, se utiliza la configuración &quot;Asignación completa&quot;.
