---
keywords: configuración;prioridad
description: Descubra cómo [!DNL Adobe Target] determina qué actividad (o actividades) se enviará a una página de forma diferente en función de qué interfaz de [!DNL Target] y de qué función de creación de actividades esté utilizando.
title: ¿Cómo asigna prioridad [!DNL Target] a las diferentes actividades?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 19%
---
# Prioridad {#priority}

>[!BEGINSHADEBOX]

**En esta página:** Descubra cómo [!DNL Adobe Target] decide qué actividades enviar a una página, según el compositor de experiencias y el tipo de solicitud [!DNL Target] en uso.

>[!ENDSHADEBOX]

[!DNL Adobe Target] determina qué actividad (o actividades) se enviará a una página de forma diferente en función de qué interfaz de [!DNL Target] y de qué función de creación de actividades ([**[!UICONTROL Compositor de experiencias visuales (VEC)]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) o [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md)) esté utilizando. En el cuadro siguiente se resumen los tres casos, que se detallan en las secciones siguientes.

| Escenario | Actividades que se pueden entregar | Contenido devuelto |
|---|---|---|
| **[!UICONTROL Compositor de experiencias visuales]** solamente o **[!UICONTROL Compositor de experiencias basadas en formularios]** con una solicitud [!DNL Target] global solamente | Varios | Contenido de todas las actividades coincidentes. Si los selectores se superponen, se muestra el contenido de la actividad de mayor prioridad. |
| **[!UICONTROL Compositor de experiencias basadas en formularios]** y **[!UICONTROL Compositor de experiencias visuales]** | Varios | Si una actividad basada en formularios tiene la prioridad más alta, su contenido y el contenido de todas las actividades del VEC coincidentes. Si una actividad de VEC tiene la prioridad más alta, solo se muestra el contenido de todas las actividades de VEC que coincidan. |
| **[!UICONTROL Compositor de experiencias basadas en formularios]** con solicitudes no globales [!DNL Target] | Uno por llamada | Contenido de la actividad de coincidencia de prioridad más alta. |

## VEC o [!UICONTROL Compositor de experiencias basadas en formularios] con una solicitud global {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si su empresa utiliza el VEC de forma exclusiva, se puede devolver contenido de varias actividades para la misma llamada. Las actividades se ofrecen según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] alcanza [!DNL Target]. La llamada lleva información sobre la dirección URL de la página solicitada.
1. [!DNL Target] extrae todas las actividades que se ejecutan en esa dirección URL. Estas actividades son las candidatas para la entrega.
1. [!DNL Target] intenta hacer coincidir al visitante en las actividades candidatas.

   {{visitor-matching}}

1. Se devuelve a la página el contenido de todas las actividades y experiencias con las que el visitante se ve relacionado, de modo que el contenido de varias actividades se puede entregar para la misma llamada.
1. [!DNL Target] compara los [selectores de CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) a los que hace referencia el contenido de cada actividad. Si las actividades hacen referencia a distintos selectores, se muestra todo el contenido.
1. Si un selector se superpone o está duplicado, se muestra el contenido de la actividad de mayor prioridad.

   >[!IMPORTANT]
   >
   >[!DNL Target] devuelve el contenido de todas las actividades de la página, empezando por el contenido de prioridad más baja, que se sobrescribe con cada actividad (de la más baja a la más alta). Normalmente, esto hace que se muestre el contenido de mayor prioridad. Sin embargo, si una actividad de prioridad inferior altera la estructura del DOM para la página, es posible que la actividad de prioridad superior no reconozca la estructura de la página, por lo que se muestra el contenido de prioridad inferior.

1. Si varias actividades comparten un nivel de prioridad, se aplica un desempate. Si solo una de las actividades tiene segmentación de audiencia, se muestra esa actividad. Si todas o ninguna de las actividades tiene segmentación, se muestra la actividad que se aprobó primero.
1. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

## [!UICONTROL Compositor de experiencias basadas en formularios] y VEC {#section_4620253E1CE942DD830724C7822B175F}

Si su empresa usa [!UICONTROL el Compositor de experiencias basadas en formularios] *y* el VEC, se puede entregar el contenido de varias actividades de [!UICONTROL Compositor de experiencias basadas en formularios] y VEC. Anteriormente, solo se podía entregar una actividad del flujo de trabajo basado en formularios. Ya no hay límite en el número de actividades basadas en formularios que se pueden entregar.

La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] alcanza [!DNL Target]. La llamada lleva información sobre la solicitud [!DNL Target] y la dirección URL.
1. [!DNL Target] extrae todas las actividades que se están ejecutando en esa solicitud [!DNL Target]. Estas actividades son las candidatas para la entrega.
1. [!DNL Target] intenta hacer coincidir al visitante en las actividades candidatas.

   {{visitor-matching}}

1. [!DNL Target] comprueba cuál de las actividades coincidentes tiene la prioridad más alta y si esa actividad se creó en el [!UICONTROL Compositor de experiencias basadas en formularios] o en el VEC.
1. Si una actividad basada en formularios tiene la prioridad más alta, se devuelve su contenido junto con el contenido de todas las actividades del VEC coincidentes.
1. Si una actividad de VEC tiene la prioridad más alta, se devuelve el contenido de todas las actividades de VEC coincidentes, pero no se devuelve ningún contenido de actividad basado en formularios.
1. Los resultados de todas las actividades que se ejecutan en la página se contabilizan y se reflejan en los informes.

**Ejemplo**

Existen dos actividades: una se dirige a la palabra clave de búsqueda con marca &quot;Nike&quot; y la otra, a la palabra clave sin marca &quot;zapatillas&quot;. Se comprueban las prioridades de ambas actividades. Si la actividad &quot;Nike&quot; tiene una prioridad mayor, se muestra su contenido. Del mismo modo, si la actividad de “zapatillas” tiene una prioridad mayor, se muestra ese contenido.

Si ambas actividades segmentadas tienen la misma prioridad, se muestra la última actividad que se vio. Si el visitante es nuevo en la página, se muestra la última actividad que se activó.

## [!UICONTROL Compositor de experiencias basadas en formularios] con solicitudes no globales {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Si su empresa utiliza [!DNL Target] solicitudes distintas de la solicitud global [!DNL Target] en el compositor basado en formularios, solo se podrá devolver contenido de una actividad por llamada. La actividad que se ofrece queda determinada según el siguiente flujo de decisiones:

1. La llamada al servidor [!DNL Target] alcanza [!DNL Target]. La llamada lleva información sobre la solicitud [!DNL Target] y la dirección URL.
1. [!DNL Target] extrae todas las actividades que se están ejecutando en esa solicitud [!DNL Target]. Estas actividades son las candidatas para la entrega.
1. [!DNL Target] intenta hacer coincidir al visitante con la actividad candidata de mayor prioridad.

   {{visitor-matching}}

1. Si varias actividades comparten un nivel de prioridad, se aplica un desempate. Si solo una de las actividades tiene segmentación de audiencia, se muestra esa actividad. Si todas o ninguna de las actividades tiene segmentación, se muestra la actividad que se aprobó primero.
1. El contenido de esa única actividad se devuelve a la página.

## Ejemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Los valores de prioridad varían en función de la configuración. Puede usar la configuración heredada de **[!UICONTROL Low]**, **[!UICONTROL Medium]** o **[!UICONTROL High]**, o bien habilitar prioridades específicas de 0 a 999. Para obtener más información, consulte [Configuración de actividades](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

**Dos actividades solo usan ofertas creadas en el [!UICONTROL Compositor de experiencias visuales] para selectores diferentes**

* Actividad 1: target-global-mbox, selector1, visualExpCompOffer1, prioridad baja
* Actividad 2: target-global-mbox, selector2, visualExpCompOffer2, prioridad alta

Respuesta: visualExpCompOffer1, visualExpCompOffer2

**Dos actividades solo usan ofertas creadas en el [!UICONTROL Compositor de experiencias visuales] para el mismo selector**

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
