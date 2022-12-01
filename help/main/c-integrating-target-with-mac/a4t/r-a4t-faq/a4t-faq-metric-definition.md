---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;métrica;definiciones de métricas
description: Encuentre respuestas a preguntas sobre definiciones de métricas y uso de Analytics para [!DNL Target] (A4T). A4T le permite utilizar los informes de Analytics con Adobe [!DNL Target] actividades.
title: ¿Dónde puedo encontrar información sobre las definiciones de métricas con A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 29%

---

# Definiciones de métricas: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## ¿Cuándo caduca la pertenencia a la actividad? ¿Cuánto tiempo tiene que pasar después de que los visitantes entren a la actividad para que sus acciones se contabilicen en ella si no vuelven a verla? {#section_41B4958F33534E4B96DEE0C981227A79}

+++Respuesta La caducidad predeterminada de la actividad es de 90 días después de la última interacción de un visitante con la actividad. ClientCare puede ajustar esta configuración si es necesario. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

+++

## Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada? {#adv-settings}

+++Responder A La [!UICONTROL Configuración avanzada] no están disponibles para las actividades que usan [!DNL Analytics] como fuente de informes (A4T).

Para las actividades que utilizan A4T, la métrica de objetivo siempre usa la variable[!UICONTROL Aumentar recuento y mantener al usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Esta configuración es *not* configurable.

Para actividades que no son de A4T, puede usar la variable [Opciones de Configuración avanzada](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para administrar la forma de medir el éxito. Las opciones incluyen añadir dependencias, elegir si mantener al usuario en la actividad o eliminarlo, y si contar la métrica una vez por visitante o en cada impresión. Puede acceder a la [!UICONTROL Configuración avanzada] opciones de una actividad que no es de A4T haciendo clic en las elipses verticales > [!UICONTROL Configuración avanzada], como se muestra a continuación:

![Configuración avanzada](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## ¿Qué son las métricas calculadas y cómo sustituyen el mbox SiteCatalyst:Event que yo usaba antes?   {#section_D59F4719E6B94758A2187427C17F8EF3}

+++Respuesta Las métricas calculadas permiten crear métricas personalizadas que se derivan de segmentos o cálculos matemáticos. En el pasado, en las situaciones en las que quizá usaba el mbox de `SiteCatlayst:Event` donde `evar27=shoes` y el evento es `purchase`, ahora crearía un segmento con `evar27=shoes` y después crearía una métrica calculada en la que el evento es `purchase` con el segmento aplicado. Estas métricas se pueden crear en cualquier momento, incluso después de que la actividad esté en curso. Después se pueden usar en cualquier informe de Analytics.

+++

## ¿A4T atribuye conversiones a varias campañas?   {#section_7F15C727206440CD86B3A8CE77087DF9}

+++Responda Sí, con la configuración &quot;Asignación completa&quot;.

+++