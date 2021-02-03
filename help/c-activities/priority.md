---
keywords: configuración;prioridad
description: Adobe Target determina la actividad (o actividades) que se va a enviar a una página de forma diferente según la interfaz de Destinatario y la función de creación de actividades (Compositor de experiencias visuales o Compositor basado en formularios) que se esté utilizando.
title: Prioridad
feature: Activities
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 88%

---


# Prioridad

Target determina qué actividad (o actividades) ofrece en una página de forma diferente en función de qué interfaz de Target y de qué función de creación de actividades (Compositor de experiencias visuales o Compositor basado en formularios) esté usando.

## Solo el Compositor de experiencias visuales de Target Standard/Premium o el Compositor basado en formularios que utiliza solo la solicitud de Destinatario global {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si en su empresa se utiliza Target Standard/Premium y únicamente el Compositor de experiencias visuales, se puede devolver el contenido de varias actividades para la misma llamada. Las actividades se ofrecen según el siguiente flujo de decisiones:

1. La llamada del servidor de Target llega a Target con información sobre la dirección URL.
1. Target recupera todas las actividades que se están realizando en esa dirección URL.
1. Target intenta relacionar al visitante con actividades.

   Si el visitante ya se encuentra en una prueba A/B o multivariable, se relacionará con esa prueba hasta que genere una conversión. Si anteriormente se encontraba en una actividad de segmentación de experiencias, se tiene que volver a relacionar con esta. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Se devuelve a la página el contenido de todas las actividades y experiencias con las que el visitante se ve relacionado.
1. Si el contenido de cada actividad hace referencia a diferentes.  [selectores CSS](/help/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), se muestra todo el contenido.

   Si se produce solapamiento o si hay un selector CSS duplicado, se muestra el contenido de la actividad con mayor prioridad. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

   >[!IMPORTANT]
   >
   >Target devuelve el contenido de todas las actividades que hay en la página, empezando por el contenido con prioridad más baja, que se sobrescribe con cada actividad (de la más baja a la más alta). En la mayoría de los casos, el resultado es que se muestra el contenido con la prioridad más alta. Sin embargo, si una actividad con prioridad menor altera la estructura del DOM de la página, es posible que la actividad con prioridad mayor no reconozca la estructura de la página y se muestre el contenido de menor prioridad. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

1. Si varias actividades comparten el mismo nivel de prioridad, hay dos factores que deshacen el empate:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todas o ninguna tienen segmentación, se muestra la actividad que se aprobó en primer lugar.

## Compositor basado en formularios de Target Standard/Premium y Compositor de experiencias visuales de Target Standard/Premium.   {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Esta información también se aplica a cualquier campaña en ejecución creada en [!DNL Target Classic].

Si en su empresa se utiliza el compositor basado en formularios en Target Standard/Premium y el Compositor de experiencias visuales en Target Standard/Premium, se puede ofrecer el contenido de varias actividades del Compositor de experiencias visuales, pero solo una actividad del flujo de trabajo basado en formularios. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor de destinatario llega al Destinatario con información sobre la solicitud [!DNL Target] y la dirección URL.
1. Destinatario Classic y Standard obtienen todas las actividades que se ejecutan en esa solicitud [!DNL Target].
1. Target intenta relacionar al visitante con actividades.

   Si el visitante ya se encuentra en una prueba A/B o multivariable, se relacionará con esa prueba hasta que genere una conversión. Si anteriormente se encontraba en una actividad de segmentación de experiencias, se tiene que volver a relacionar con esta. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si la máxima prioridad es una actividad basada en formularios, se devuelve el contenido de esa actividad junto con todo el contenido de actividad coincidente de las actividades del Compositor de experiencias visuales.
1. Si la prioridad más alta corresponde a una actividad del Compositor de experiencias visuales, se devuelve el contenido de todas las actividades del Compositor de experiencias visuales, pero no el contenido de las actividades de Target Classic o basadas en formularios.

   Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

**Ejemplo**

Si tiene dos actividades, una que segmenta por la palabra clave de búsqueda por marca “Nike” y una segunda actividad que segmenta por la palabra clave sin marca “zapatillas”, se comprobarán las prioridades de las dos actividades. Si la actividad de “Nike” tiene una prioridad mayor, se muestra ese contenido. Del mismo modo, si la actividad de “zapatillas” tiene una prioridad mayor, se muestra ese contenido.

Si ambas actividades segmentadas tienen la misma prioridad, se muestra la última actividad que se vio. Si el visitante es nuevo en la página, se muestra la última actividad que se activó.

## Compositor basado en formularios de Target Standard/Premium con solicitudes de Destinatario no globales {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Esta información también se aplica a cualquier campaña en ejecución creada en Target Classic.

Si su compañía utiliza [!DNL Target] solicitudes distintas de la solicitud [!DNL Target] global en el compositor basado en formularios, sólo se puede devolver el contenido de una actividad por llamada. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] llega a [!DNL Target] con información sobre la solicitud [!DNL Target] y la dirección URL.
1. [!DNL Target] extrae todas las actividades que se ejecutan en esa  [!DNL Target] solicitud.
1. [!DNL Target] intenta relacionar al visitante con la actividad de mayor prioridad.

   Si el visitante ya se encuentra en una prueba A/B o multivariable, se relacionará con esa prueba hasta que genere una conversión. Si anteriormente se encontraba en una actividad de segmentación de experiencias, se tiene que volver a relacionar con esta. Si cumple las reglas de la audiencia, entra dentro de esas actividades y en experiencias concretas.

1. Si varias actividades comparten el mismo nivel de prioridad, hay dos factores que deshacen el empate:

   * Si solo una actividad tiene segmentación de la audiencia, se muestra esa actividad.
   * Si todas o ninguna tienen segmentación, se muestra la actividad que se aprobó en primer lugar.

## Ejemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Los valores de prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999. Para obtener más información, consulte  [Configuración de actividades](/help/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Dos campañas de Destinatario Classic utilizan solicitudes de Destinatario no globales**

* Campaña 1: homePageHero, offer1, prioridad alta
* Campaña 2: homePageHero, offer2, prioridad baja

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
>Es la misma respuesta que en el segundo caso de uso descrito anteriormente, porque Target Classic no gestiona los conflictos de selectores. Target Standard detecta ese comportamiento y otros casos de uso en los que los selectores pueden entrar en conflicto tanto en DOM como visualmente (normalmente, se lleva a cabo en el nivel de editor de experiencias o en el modo de simulación de campañas).

**Dos actividades utilizan ofertas creadas en el Compositor de experiencias visuales y dos emplean campañas de Target Classic**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad media
* Actividad 2: target-global-mbox, selector2, visualExpCompOffer2, prioridad baja
* Campaña 1: target-global-mbox, oferta1, prioridad alta
* Campaña 2: target-global-mbox, oferta2, prioridad baja

Respuesta: oferta1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>En el orden de las respuestas combinadas, el contenido clásico va antes (solo se ofrecerá una respuesta clásica como en el primer caso de uso) y, después, el Compositor de experiencias visuales ofrece respuestas en orden inverso de prioridad.

## Vídeo de formación: Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)