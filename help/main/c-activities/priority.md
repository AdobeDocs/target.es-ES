---
keywords: configuración;prioridad
description: Descubra cómo [!DNL Adobe Target] determina qué actividad (o actividades) se envía a una página de forma diferente en función de qué [!DNL Target] y qué función de creación de actividades está utilizando.
title: ¿Cómo [!DNL Target] ¿Asignar prioridad a diferentes actividades?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: 18765a82b5dca94654a412e2012a3f6c1a7b5128
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 40%

---

# Prioridad

[!DNL Adobe Target] determina qué actividad (o actividades) se envía a una página de forma diferente en función de qué [!DNL Target] y qué función de creación de actividades ([[!UICONTROL Compositor de experiencias visuales]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md)) que está utilizando.

## [!DNL Target Standard/Premium] [!UICONTROL Compositor de experiencias visuales] solo o [!UICONTROL Compositor de experiencias basadas en formularios] uso de un global [!DNL Target] solo solicitar {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si su empresa utiliza [!DNL Target Standard/Premium] y el [!UICONTROL Compositor de experiencias visuales] exclusivamente, el contenido de varias actividades se puede devolver para la misma llamada. Las actividades se ofrecen según el siguiente flujo de decisiones:

1. El [!DNL Target] la llamada al servidor llega a [!DNL Target] con información sobre la dirección URL.
1. [!DNL Target] recupera todas las actividades que se están realizando en esa dirección URL.
1. [!DNL Target] intenta relacionar al visitante con actividades.

   Si el visitante ya está en un [!UICONTROL Prueba A/B] o [!UICONTROL Prueba multivariable] actividad, coinciden con esa actividad hasta que se convierten. Si anteriormente estaban en un [!UICONTROL Segmentación de experiencias] actividad, deben coincidir de nuevo con ella. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Se devuelve a la página el contenido de todas las actividades y experiencias con las que el visitante se ve relacionado.
1. Si el contenido de cada actividad hace referencia a diferentes.  [selectores CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), se muestra todo el contenido.

   Si se produce solapamiento o si hay un selector CSS duplicado, se muestra el contenido de la actividad con mayor prioridad. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

   >[!IMPORTANT]
   >
   >[!DNL Target] devuelve el contenido de todas las actividades que hay en la página, empezando por el contenido con prioridad más baja, que se sobrescribe con cada actividad (de la más baja a la más alta). Normalmente, esto hace que se muestre el contenido de mayor prioridad. Sin embargo, si una actividad de prioridad inferior altera la estructura del DOM para la página, es posible que la actividad de prioridad superior no reconozca la estructura de la página, por lo que se muestra el contenido de prioridad inferior. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

1. Si varias actividades comparten un nivel de prioridad, existen dos desempates:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todos o ninguno tiene segmentación, se muestra la actividad que se aprobó primero.

## [!DNL Target Standard/Premium] [!UICONTROL Compositor de experiencias basadas en formularios] y [!DNL Target Standard/Premium] [!UICONTROL Compositor de experiencias visuales] {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Esta información también se aplica a cualquier campaña en ejecución creada en [!DNL Target Classic].

Si su empresa utiliza [!UICONTROL Compositor de experiencias basadas en formularios] in [!DNL Target Standard/Premium] y el [!DNL Target Standard/Premium] [!UICONTROL Compositor de experiencias visuales], luego contenido de varios [!UICONTROL Compositor de experiencias visuales] Las actividades de pueden entregar, pero solo una actividad del flujo de trabajo basado en formularios. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. [!DNL Target] la llamada al servidor llega a [!DNL Target] con información acerca de [!DNL Target] solicitud y URL.
1. [!DNL Target Classic] y [!DNL Target Standard/Premium] extraiga todas las actividades que se ejecuten en ese [!DNL Target] solicitud.
1. [!DNL Target] intenta relacionar al visitante con actividades.

   Si el visitante ya está en un [!UICONTROL Prueba A/B] o [!UICONTROL Prueba multivariable] actividad, coinciden en esa prueba hasta que se convierten. Si anteriormente estaban en un [!UICONTROL Segmentación de experiencias] actividad, deben coincidir de nuevo con ella. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si una actividad basada en formularios es la prioridad más alta, se devuelve ese contenido de actividad junto con todo el contenido de actividad coincidente de [!UICONTROL Compositor de experiencias visuales] actividades.
1. Si un [!UICONTROL Compositor de experiencias visuales] la actividad es la prioridad más alta y, a continuación, el contenido de todas las coincidencias [!UICONTROL Compositor de experiencias visuales] se devuelve ninguna actividad, pero no [!DNL Target Classic] o se devuelve el contenido de la actividad basado en formularios.

   Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

**Ejemplo**

Si tiene dos actividades, una que segmenta por la palabra clave de búsqueda por marca &quot;Nike&quot; y una segunda actividad que segmenta por la palabra clave sin marca &quot;zapatillas&quot;, se comprobarán las prioridades de ambas actividades. Si la actividad de “Nike” tiene una prioridad mayor, se muestra ese contenido. Del mismo modo, si la actividad de “zapatillas” tiene una prioridad mayor, se muestra ese contenido.

Si ambas actividades segmentadas tienen la misma prioridad, se muestra la última actividad que se vio. Si el visitante es nuevo en la página, se muestra la última actividad que se activó.

## [!DNL Target Standard/Premium] [!UICONTROL Compositor de experiencias basadas en formularios] con no global [!DNL Target] solicitudes {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Esta información también se aplica a cualquier actividad en ejecución creada en [!DNL Target Classic].

Si su empresa utiliza [!DNL Target] solicitudes distintas de la global [!DNL Target] solicitud en el compositor basado en formularios, solo se puede devolver contenido de una actividad por llamada. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. El [!DNL Target] la llamada al servidor llega a [!DNL Target] con información acerca de [!DNL Target] solicitud y URL.
1. [!DNL Target] extrae todas las actividades que se ejecutan en [!DNL Target] solicitud.
1. [!DNL Target] intenta relacionar al visitante con la actividad de mayor prioridad.

   Si el visitante ya está en un [!UICONTROL Prueba A/B] o [!UICONTROL Prueba multivariable] actividad, coinciden con esa actividad hasta que se convierten. Si anteriormente estaban en un [!UICONTROL Segmentación de experiencias] actividad, deben coincidir de nuevo con ella. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si varias actividades comparten un nivel de prioridad, existen dos desempates:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todos o ninguno tiene segmentación, se muestra la actividad que se aprobó primero.

## Ejemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Los valores de prioridad varían en función de la configuración. Puede utilizar la configuración heredada de [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta]o puede habilitar prioridades específicas de 0 a 999. Para obtener más información, consulte [Configuración de actividades](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Dos [!DNL Target Classic] Las actividades de utilizan variables no globales [!DNL Target] solicitudes**

* Actividad 1: homePageHero, oferta1, prioridad alta
* Actividad 2: homePageHero, offer2, prioridad baja

Respuesta: offer1

**Dos actividades usan solo ofertas creadas en el Compositor de experiencias visuales para diferentes selectores**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad baja
* Actividad 2: target-global-mbox, selector2, visualExpCompOffer2, prioridad alta

Respuesta: visualExpCompOffer1, visualExpCompOffer2

**Dos actividades usan solo ofertas creadas en el Compositor de experiencias visuales para el mismo selector**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad baja
* Actividad 2: target-global-mbox, selector1, visualExpCompOffer2, prioridad alta

Respuesta: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Es la misma respuesta que en el segundo caso de uso anterior porque [!DNL Target Classic] no se han gestionado los conflictos de selectores. [!DNL Target Standard/Premium] detecta ese comportamiento y otros casos de uso en los que los selectores podrían entrar en conflicto tanto en DOM como visualmente (normalmente, se lleva a cabo en el nivel de editor de experiencias o en el modo de simulación de actividades).

**Dos actividades utilizan ofertas creadas en [!UICONTROL Compositor de experiencias visuales] y dos [!DNL Target Classic] actividades**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad media
* Actividad 2: target-global-mbox, selector2, visualExpCompOffer2, prioridad baja
* Actividad 1: target-global-mbox, oferta1, prioridad alta
* Actividad 2: target-global-mbox, offer2, prioridad baja

Respuesta: oferta1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>El orden de las respuestas combinadas es el siguiente [!DNL Target Classic] el contenido es lo primero. Solo uno [!DNL Target Classic] la respuesta se sirve como en el caso de uso 1 y, a continuación, [!UICONTROL Compositor de experiencias visuales] ofrecen respuestas ordenadas por prioridad invertida.

## Vídeo de formación: Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)
