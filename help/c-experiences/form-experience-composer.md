---
description: El Compositor de experiencias basadas en formularios proporciona una creación de experiencias no visual.
keywords: compositor de experiencias basadas en formularios;compositor basado en formularios;refinamientos
seo-description: El Compositor de experiencias basadas en formularios proporciona una creación de experiencias no visual.
seo-title: Compositor de experiencias basadas en formularios
solution: Target
title: Compositor de experiencias basadas en formularios
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Compositor de experiencias basadas en formularios{#form-based-experience-composer}

El Compositor de experiencias basadas en formularios proporciona una creación de experiencias no visual.

Esta característica permite que las pruebas A/B de Target Standard y las actividades de segmentación de experiencias, personalización automatizada y de Recommendations se entreguen en correos electrónicos, aplicaciones móviles, kioscos y otros lugares que no trabajan con un Compositor de experiencias visuales.

Si va a crear una actividad de Recommendations, no hay experiencias. Elija sus criterios y su diseño. Si elige varios criterios o diseños, Target genera las experiencias automáticamente.

1. Haga clic en **[!UICONTROL Crear actividad]** y luego seleccione el tipo de actividad que desee crear.

   El Compositor de experiencias basadas en formularios está disponible para pruebas A/B y para actividades de segmentación de experiencias, personalización automatizada y de Recommendations.
1. Seleccione **[!UICONTROL Compositor de experiencias basadas en formularios]** del cuadro de diálogo [!UICONTROL Nueva actividad].

   Se abre el Compositor de experiencias basadas en formularios.

   ![](assets/location_refinements.png)

   Esta pantalla es diferente si va a crear una actividad de Recommendations. Las actividades de Recommendations no incluyen experiencias.
1. Asigne un nombre a la actividad.
1. Seleccione una ubicación.

   Cuando hace clic en el cuadro Seleccionar ubicación, aparece una lista con las ubicaciones disponibles. Seleccione una de esas ubicaciones. Para elegir la ubicación global entregada mediante target.js, elija “target-global-mbox”.

   También puede especificar una ubicación que no aparece en esta lista. Esto puede ser útil si el mbox todavía no se ha creado ni visto en una página. Escriba el nombre de la ubicación. Tenga cuidado al especificar una ubicación que no existe aún. Si la ortografía o las mayúsculas no coinciden con las que se usaron cuando se creó el mbox, la actividad no se publicará. Las ubicaciones que se escriben manualmente se guardan en la lista.
1. Haga clic en **[!UICONTROL Agregar refinamientos de audiencia]** y, a continuación, elija una o varias [audiencias](../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta actividad.

   ![](assets/location_refinements_2.png)

   En el Compositor de experiencias basadas en formularios, los refinamientos se han sustituido por funciones de audiencia completas. Los refinamientos para las actividades existentes se han migrado a   [audiencias solo de actividad](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).
1. Seleccione el tipo de contenido que desea que aparezca en esa ubicación.

   ![](assets/form_content.png)

1. Para el tipo de contenido seleccionado, especifique el contenido.

   **Cambiar oferta HTML:** Elija una oferta HTML.

   **Cambiar oferta de imagen:** elija una imagen guardada en la biblioteca de contenido en Target.

   También puede agregar un vínculo a una imagen (pulsación, destino, aterrizaje, etc.).

   1. Haga clic en [!UICONTROL Cambiar oferta de imagen].
   1. Seleccione la imagen que quiera y luego haga clic en [!UICONTROL Editar vínculos].
   1. Indique la dirección URL o la página de su sitio y haga clic en [!UICONTROL Actualizar].
   **Cambiar oferta JSON:** Elija una oferta json.

   **Cambiar fragmento de experiencia:** elija un fragmento de experiencias.

   **Cambiar oferta de redireccionamiento:** elija una oferta de redireccionamiento.

   **Cambiar oferta remota:** elija una oferta remota.

   **Crear oferta HTML:**

   1. Haga clic en [!UICONTROL Ofertas] y seleccione la pestaña [!UICONTROL Ofertas de código].
   1. Haga clic en [!UICONTROL Crear] &gt; [!UICONTROL Oferta HTML].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código HTML en el recuadro Código.
   1. Haga clic en [!UICONTROL Guardar].
   **Crear ofertas JSON:**

   1. Haga clic en [!UICONTROL Ofertas] y seleccione la pestaña [!UICONTROL Ofertas de código].
   1. Haga clic en [!UICONTROL Crear] &gt; [!UICONTROL Oferta JSON].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código JSON en el recuadro Código.
   1. Haga clic en [!UICONTROL Guardar].
   Para una actividad de Recommendations, la lista desplegable Contenido ofrece la opción Agregar recomendación. Haga clic en **[!UICONTROL Agregar recomendación]** y seleccione el tipo de página. Después siga los pasos habituales que se definen en la interfaz para [crear una actividad de Recomendaciones](https://marketing.adobe.com/resources/help/en_US/target/recs/t_create_recs_activity.html).

   Cuando se seleccionan los criterios de Recommendations en el Compositor de experiencias basadas en formularios, ahora existe un vínculo directo a la tarjeta de criterios seleccionada de modo que pueda editarlos de forma rápida y sencilla.

   ![](assets/change_criteria.png)

   En la página Segmentación del flujo de trabajo guiado de tres pasos de Target:

   ![](assets/change_criteria_2.png)

1. (Opcional, para actividades AB, Personalización automatizada y Segmentación de experiencias) Para repetir este proceso para ubicaciones adicionales, haga clic en `Add Location` y configure la ubicación y el contenido.
1. Haga clic en **[!UICONTROL Continuar]** y complete los pasos de creación de actividad como es habitual para su tipo de actividad.

* [Crear una prueba A/B](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [Crear una actividad de segmentación de experiencias](../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Crear una actividad de Recommendations](../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de formación: Compositor basado en formularios

Este vídeo proporciona una demostración del compositor basado en formularios.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)