---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;métrica;definiciones de métricas
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de Analytics como fuente de informes para Target (A4T).
title: 'Definiciones de métricas: Preguntas más frecuentes sobre A4T'
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 67%

---


# Definiciones de métricas: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de Analytics como fuente de informes para Target (A4T).

## ¿Cuándo caduca la pertenencia a la actividad? ¿Cuánto tiempo tiene que pasar después de que los visitantes entren a la actividad para que sus acciones se contabilicen en ella si no vuelven a verla?    {#section_41B4958F33534E4B96DEE0C981227A79}

La caducidad predeterminada para la actividad es de 90 días después de la última interacción de un visitante con la actividad. Si es necesario, se puede cambiar en ClientCare. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

## Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada? {#adv-settings}

Las opciones [!UICONTROL Configuración avanzada] no están disponibles para actividades que utilizan [!DNL Analytics] como fuente de sistema de informes (A4T).

En el caso de actividades que utilicen A4T, la métrica de objetivos siempre usará la configuración &quot;[!UICONTROL Aumentar recuento y mantener al usuario en Actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Esto *no se puede configurar*.

Para actividades que no son de A4T, puede utilizar las [opciones de Configuración avanzada](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para administrar la forma en que mide el éxito. Las opciones incluyen la adición de dependencias, la elección de mantener al usuario en la actividad o eliminarlo, y la contabilización de la métrica una vez por visitante o en cada impresión. Para acceder a las opciones [!UICONTROL Configuración avanzada] en una actividad que no es de A4T, haga clic en las elipses verticales > [!UICONTROL Configuración avanzada], como se muestra a continuación:

![Configuración avanzada](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## ¿Qué son las métricas calculadas y cómo sustituyen el mbox SiteCatalyst:Event que yo usaba antes?    {#section_D59F4719E6B94758A2187427C17F8EF3}

Las métricas calculadas le permiten crear métricas personalizadas que se derivan de segmentos o de cálculos matemáticos. En el pasado, en las situaciones en las que quizá usaba el mbox de `SiteCatlayst:Event` donde `evar27=shoes` y el evento es `purchase`, ahora crearía un segmento con `evar27=shoes` y después crearía una métrica calculada en la que el evento es `purchase` con el segmento aplicado. La ventaja de la nueva situación es que estas métricas se pueden crear en cualquier momento, incluso después de que la actividad se haya puesto en marcha. Después se pueden usar en cualquier informe de Analytics.

## ¿A4T atribuye conversiones a varias campañas?    {#section_7F15C727206440CD86B3A8CE77087DF9}

Sí. Esto se lleva a cabo con la configuración “Asignación completa”.
