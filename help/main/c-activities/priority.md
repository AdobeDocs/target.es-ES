---
keywords: configuración;prioridad
description: Aprenda cómo [!DNL Adobe Target] determina qué actividad (o actividades) se enviará a una página de forma diferente en función de qué [!DNL Target] interfaz y de qué función de creación de actividades esté usando.
title: ¿Cómo  [!DNL Target] asigna prioridad a diferentes actividades?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 36%

---

# Prioridad

[!DNL Adobe Target] determina qué actividad (o actividades) se enviará a una página de forma diferente en función de qué interfaz de [!DNL Target] y de qué función de creación de actividades ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md)) esté usando.

## Solo [!UICONTROL Visual Experience Composer] o [!UICONTROL Form-Based Experience Composer] que usa una solicitud global [!DNL Target] solamente {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si su empresa utiliza el VEC de forma exclusiva, se puede devolver contenido de varias actividades para la misma llamada. Las actividades se ofrecen según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] llega a [!DNL Target] con información sobre la dirección URL.
1. [!DNL Target] extrae todas las actividades que se ejecutan en esa dirección URL.
1. [!DNL Target] intenta relacionar al visitante con las actividades.

   Si el visitante ya se encuentra en una actividad [!UICONTROL A/B Test] o [!UICONTROL Multivariate Test], coincidirá con esa actividad hasta que se convierta. Si anteriormente estaban en una actividad [!UICONTROL Experience Targeting], deben coincidir de nuevo. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Se devuelve a la página el contenido de todas las actividades y experiencias con las que el visitante se ve relacionado.
1. Si el contenido de cada actividad hace referencia a [selectores CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) diferentes, se mostrará todo el contenido.

   Si se produce solapamiento o si hay un selector CSS duplicado, se muestra el contenido de la actividad con mayor prioridad. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

   >[!IMPORTANT]
   >
   >[!DNL Target] devuelve el contenido de todas las actividades de la página, empezando por el contenido de prioridad más baja, que se sobrescribe con cada actividad (de la más baja a la más alta). Normalmente, esto hace que se muestre el contenido de mayor prioridad. Sin embargo, si una actividad de prioridad inferior altera la estructura del DOM para la página, es posible que la actividad de prioridad superior no reconozca la estructura de la página, por lo que se muestra el contenido de prioridad inferior. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

1. Si varias actividades comparten un nivel de prioridad, existen dos desempates:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todos o ninguno tiene segmentación, se muestra la actividad que se aprobó primero.

## [!UICONTROL Form-Based Experience Composer] y [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

Si su empresa usa [!UICONTROL Form-Based Experience Composer] *y* el VEC, se puede entregar contenido de varias actividades [!UICONTROL Form-Based Experience Composer] y VEC. Anteriormente, solo se podía entregar una actividad del flujo de trabajo basado en formularios. Ya no hay límite en el número de actividades basadas en formularios que se pueden entregar.

La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] llega a [!DNL Target] con información sobre la solicitud [!DNL Target] y la dirección URL.
1. [!DNL Target] extrae todas las actividades que se ejecutan en esa solicitud [!DNL Target].
1. [!DNL Target] intenta relacionar al visitante con las actividades.

   Si el visitante ya se encuentra en una actividad [!UICONTROL A/B Test] o [!UICONTROL Multivariate Test], coincidirá con esa prueba hasta que realice la conversión. Si anteriormente estaban en una actividad [!UICONTROL Experience Targeting], deben coincidir de nuevo. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si una actividad basada en formularios es la prioridad más alta, ese contenido de actividad se devuelve junto con todo el contenido de actividad coincidente de las actividades VEC.
1. Si una actividad de VEC es la prioridad más alta, se devuelve el contenido de todas las actividades de VEC coincidentes, pero no se devuelve ningún contenido de actividad basado en formularios.

   Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

**Ejemplo**

Si tiene dos actividades, una que segmenta por la palabra clave de búsqueda por marca &quot;Nike&quot; y una segunda actividad que segmenta por la palabra clave sin marca &quot;zapatillas&quot;, se comprobarán las prioridades de ambas actividades. Si la actividad de “Nike” tiene una prioridad mayor, se muestra ese contenido. Del mismo modo, si la actividad de “zapatillas” tiene una prioridad mayor, se muestra ese contenido.

Si ambas actividades segmentadas tienen la misma prioridad, se muestra la última actividad que se vio. Si el visitante es nuevo en la página, se muestra la última actividad que se activó.

## [!UICONTROL Form-Based Experience Composer] con solicitudes no globales [!DNL Target] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Si su empresa utiliza [!DNL Target] solicitudes distintas de la solicitud global [!DNL Target] en el compositor basado en formularios, solo se podrá devolver contenido de una actividad por llamada. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] llega a [!DNL Target] con información sobre la solicitud [!DNL Target] y la dirección URL.
1. [!DNL Target] extrae todas las actividades que se ejecutan en esa solicitud [!DNL Target].
1. [!DNL Target] intenta hacer coincidir al visitante en la actividad de mayor prioridad.

   Si el visitante ya se encuentra en una actividad [!UICONTROL A/B Test] o [!UICONTROL Multivariate Test], coincidirá con esa actividad hasta que se convierta. Si anteriormente estaban en una actividad [!UICONTROL Experience Targeting], deben coincidir de nuevo. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si varias actividades comparten un nivel de prioridad, existen dos desempates:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todos o ninguno tiene segmentación, se muestra la actividad que se aprobó primero.

## Ejemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Los valores de prioridad varían en función de la configuración. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999. Para obtener más información, consulte [Configuración de actividades](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

Respuesta: offer1

**Dos actividades solo usan ofertas creadas en [!UICONTROL Visual Experience Composer] para selectores diferentes**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad baja
* Actividad 2: target-global-mbox, selector2, visualExpCompOffer2, prioridad alta

Respuesta: visualExpCompOffer1, visualExpCompOffer2

**Dos actividades solo utilizan ofertas creadas en [!UICONTROL Visual Experience Composer] para el mismo selector**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad baja
* Actividad 2: target-global-mbox, selector1, visualExpCompOffer2, prioridad alta

Respuesta: visualExpCompOffer1, visualExpCompOffer2

## Vídeo de formación: Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)
