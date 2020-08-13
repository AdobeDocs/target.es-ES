---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de Analytics como fuente de informes para Target (A4T).
title: 'Definiciones de métricas: preguntas más frecuentes sobre A4T'
feature: a4t troubleshooting
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---


# Definiciones de métricas: preguntas más frecuentes sobre A4T{#metric-definitions-a-t-faq}

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre las definiciones de métricas y el uso de Analytics como fuente de informes para Target (A4T).

## ¿Cuándo caduca la pertenencia a la actividad? ¿Cuánto tiempo tiene que pasar después de que los visitantes entren a la actividad para que sus acciones se contabilicen en ella si no vuelven a verla?   {#section_41B4958F33534E4B96DEE0C981227A79}

La caducidad predeterminada para la actividad es de 90 días después de la última interacción de un visitante con la actividad. Si es necesario, se puede cambiar en ClientCare. Sin embargo, esta configuración es global para todas las actividades, por lo que no se debería cambiar para un caso.

## ¿Las opciones avanzadas para las métricas de éxito de Target funcionan con A4T?   {#section_F060E3438F4144258BB95813EDEABDAA}

Actualmente estas opciones no funcionan con A4T.

## ¿Qué son las métricas calculadas y cómo sustituyen el mbox SiteCatalyst:Event que yo usaba antes?   {#section_D59F4719E6B94758A2187427C17F8EF3}

Las métricas calculadas le permiten crear métricas personalizadas que se derivan de segmentos o de cálculos matemáticos. En el pasado, en las situaciones en las que quizá usaba el mbox de `SiteCatlayst:Event` donde `evar27=shoes` y el evento es `purchase`, ahora crearía un segmento con `evar27=shoes` y después crearía una métrica calculada en la que el evento es `purchase` con el segmento aplicado. La ventaja de la nueva situación es que estas métricas se pueden crear en cualquier momento, incluso después de que la actividad se haya puesto en marcha. Después se pueden usar en cualquier informe de Analytics.

## ¿A4T atribuye conversiones a varias campañas?   {#section_7F15C727206440CD86B3A8CE77087DF9}

Sí. Esto se lleva a cabo con la configuración “Asignación completa”.
