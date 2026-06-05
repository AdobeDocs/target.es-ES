---
keywords: compositor de experiencias basadas en formularios;compositor basado en formularios;refinamientos
description: Aprenda a utilizar el Compositor de experiencias basadas en formularios de Adobe [!DNL Target] para la creación de experiencias no visuales. Utilice este compositor cuando el VEC no esté disponible o su uso no sea práctico.
title: ¿Cómo utilizo el Compositor de experiencias basadas en formularios?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 39%

---

# Compositor de experiencias basadas en formularios

[!DNL Adobe Target] [!UICONTROL Compositor de experiencias basadas en formularios] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en [!UICONTROL pruebas A/B], [!UICONTROL Segmentación de experiencias], [!UICONTROL Automated Personalization] y actividades [!UICONTROL Recommendations] cuando el [!UICONTROL Compositor de experiencias visuales] (VEC) no está disponible o su uso no es práctico. Por ejemplo, puede utilizar el Compositor de experiencias basadas en formularios para crear experiencias y ofertas para su envío en correos electrónicos, kioscos y asistentes de voz.

Si está creando una actividad [!UICONTROL Recommendations], no hay experiencias. Elija sus criterios y su diseño. Si elige varios criterios o diseños, [!UICONTROL Target] genera automáticamente las experiencias.

1. Haga clic en **[!UICONTROL Crear actividad]** y, a continuación, seleccione el tipo de actividad que desee crear.

   El [!UICONTROL Compositor de experiencias basadas en formularios] está disponible para las actividades de [!UICONTROL Prueba A/B], [!UICONTROL Segmentación de experiencias], [!UICONTROL Automated Personalization] y [!UICONTROL Recommendations].

1. Seleccione **[!UICONTROL Formulario]** del cuadro de diálogo [!UICONTROL Crear actividad].

1. (Condicional) Elija un espacio de trabajo y una propiedad.

1. Haga clic en **[!UICONTROL Siguiente]**.

   Se abre [!UICONTROL Compositor de experiencias basadas en formularios].

   ![imagen location_refinements](assets/location_refinements.png)

   Esta pantalla es diferente si está creando una actividad de [!UICONTROL Recommendations]. Las actividades de [!UICONTROL Recommendations] no incluyen experiencias.

1. Asigne un nombre a la actividad haciendo clic en &quot;[!UICONTROL Actividad sin título]&quot;.
1. Seleccione una ubicación.

   Al hacer clic en el cuadro [!UICONTROL Seleccionar ubicación], aparece una lista de ubicaciones disponibles. Seleccione una de esas ubicaciones.

   También puede especificar una ubicación que no aparece en esta lista. Esto puede ser útil si el mbox todavía no se ha creado ni visto en una página. Escriba el nombre de la ubicación. Tenga cuidado al especificar una ubicación que no existe aún. Si la ortografía o las mayúsculas no coinciden con las que se usaron cuando se creó el mbox, la actividad no se publicará. Las ubicaciones introducidas manualmente se guardan en la lista de ubicaciones disponibles. La próxima vez que intente seleccionar una ubicación ingresada manualmente, estará disponible en la lista desplegable [!UICONTROL Seleccionar ubicación] para esa actividad.

   >[!NOTE]
   >
   >La creación de una ubicación introducida manualmente durante la creación de la actividad no crea automáticamente una nueva ubicación. El nombre de la ubicación solo se guarda en el contexto de la actividad. La ubicación se crea cuando hay una llamada de envío de contenido. Una vez creada la ubicación, estará disponible para su uso en otras actividades, para crear audiencias, etc., en la lista desplegable de ubicaciones disponibles.

1. Haga clic en **[!UICONTROL Agregar refinamientos de audiencia]**, elija una o más [audiencias](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta actividad y luego haga clic en **[!UICONTROL Listo]**.

   ![imagen location_refinements_2](assets/location_refinements_2.png)

   En el [!UICONTROL Compositor de experiencias basadas en formularios], los refinamientos se han reemplazado con funcionalidad de audiencia completa. Los refinamientos para las actividades existentes se han migrado a [audiencias solo de actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Seleccione el tipo de contenido que desea que aparezca en esa ubicación.

   ![imagen form_content](assets/form_content.png)

1. Para el tipo de contenido seleccionado, especifique el contenido.

   **Cambiar oferta HTML:** Elija una oferta HTML.

   **Cambiar oferta de imagen:** elija una imagen guardada en la biblioteca de contenido en Target.

   También puede agregar un vínculo a una imagen (clic, destino, aterrizaje, etc.).

   1. Haga clic en [!UICONTROL Cambiar oferta de imagen].
   1. Seleccione la imagen que quiera y luego haga clic en [!UICONTROL Editar vínculos].
   1. Indique la dirección URL o la página de su sitio y haga clic en [!UICONTROL Actualizar].

   **Cambiar oferta JSON:** Elija una oferta json.

   **Cambiar fragmento de experiencia:** Elija un fragmento de experiencia. Para obtener más información, consulte [Fragmento de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Cambiar oferta de redireccionamiento:** Elija una oferta de redireccionamiento. Para obtener más información, consulte [Crear ofertas de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Cambiar oferta remota:** Elija una oferta remota. Para obtener más información, consulte [Crear ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Crear oferta HTML:**

   1. Haga clic en [!UICONTROL Ofertas] y seleccione la pestaña [!UICONTROL Ofertas de código].
   1. Haga clic en [!UICONTROL Crear] > [!UICONTROL Oferta de HTML].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código HTML en el recuadro Código.
   1. Haga clic en [!UICONTROL Guardar].

   **Crear ofertas JSON:**

   1. Haga clic en [!UICONTROL Ofertas] y seleccione la pestaña [!UICONTROL Ofertas de código].
   1. Haga clic en [!UICONTROL Crear] > [!UICONTROL Oferta JSON].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código JSON en el recuadro Código.
   1. Haga clic en [!UICONTROL Guardar].

   **Agregar recomendación:**

   Para una actividad de Recommendations, la lista desplegable Contenido le ofrece la opción [!UICONTROL Agregar recomendación]. Haga clic en **[!UICONTROL Agregar recomendación]** y, a continuación, seleccione el tipo de página. Después siga los pasos habituales que se definen en la interfaz para [crear una actividad de Recomendaciones](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Cuando se seleccionan los criterios de Recommendations en el Compositor de experiencias basadas en formularios, ahora existe un vínculo directo a la tarjeta de criterios seleccionada de modo que pueda editarlos de forma rápida y sencilla.

   ![imagen change_criteria](assets/change_criteria.png)

   En la página Segmentación del flujo de trabajo guiado de tres pasos de Target:

   ![imagen change_criteria_2](assets/change_criteria_2.png)

   **Agregar decisión de oferta:**

   Agregue una oferta creada en [!DNL Adobe Journey Optimizer] (AJO) a una actividad [!DNL Adobe Target] para presentar la mejor oferta dinámica y experiencia a los visitantes de su sitio web o sitio móvil mediante Offer Decisioning. Esta opción solo está disponible para las actividades manuales de [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT).

   Para obtener más información, consulte [Usar decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Opcional, para [!UICONTROL Prueba A/B], [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación de experiencias] actividades) Para repetir este proceso para ubicaciones adicionales, haga clic en **[!UICONTROL Agregar ubicación]** y configure la ubicación y el contenido.
1. Haga clic en **[!UICONTROL Siguiente]** y complete los pasos de creación de actividad como de costumbre para su tipo de actividad.

* [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Crear una actividad de Recomendaciones](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
