---
keywords: compositor de experiencias basadas en formularios;compositor basado en formularios;refinamientos
description: Aprenda a utilizar el Compositor de experiencias basadas en formularios de Adobe [!DNL Target] para crear experiencias no visuales. Utilice este compositor cuando el VEC no esté disponible o su uso no sea práctico.
title: ¿Cómo utilizo el Compositor de experiencias basadas en formularios?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 33%

---

# Compositor de experiencias basadas en formularios

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en las actividades [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] y [!UICONTROL Recommendations] cuando el [!UICONTROL Visual Experience Composer] (VEC) no está disponible o su uso no es práctico. Por ejemplo, puede utilizar el Compositor de experiencias basadas en formularios para crear experiencias y ofertas para su envío en correos electrónicos, kioscos y asistentes de voz.

Si está creando una actividad [!UICONTROL Recommendations], no hay experiencias. Elija sus criterios y su diseño. Si elige varios criterios o diseños, [!UICONTROL Target] genera automáticamente las experiencias.

1. Haga clic en **[!UICONTROL Create Activity]** y luego seleccione el tipo de actividad que desee crear.

   [!UICONTROL Form-Based Experience Composer] está disponible para las actividades [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] y [!UICONTROL Recommendations].

1. Seleccione **[!UICONTROL Form]** del cuadro de diálogo [!UICONTROL Create Activity].

1. (Condicional) Si eres [cliente de Target Premium](/help/main/c-intro/intro.md#premium), en la lista desplegable **[!UICONTROL Choose Workspace]**, elige [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   La opción [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) es una característica de [Target Premium](/help/main/c-intro/intro.md) y es posible que no se muestre si su organización tiene una licencia de [!UICONTROL Target Standard].

1. Elija una propiedad.

1. Haga clic en **[!UICONTROL Create]**.

   Se abre [!UICONTROL Form-Based Experience Composer].

   Esta pantalla es diferente si está creando una actividad [!UICONTROL Recommendations]. [!UICONTROL Recommendations] actividades no incluyen experiencias.

1. &#x200B;
   1. Haga clic en el icono **[!UICONTROL Rename]** ( ![Cambiar nombre del icono](/help/main/assets/icons/MoreSmallListVert.svg) ), haga clic en **[!UICONTROL Rename]**, especifique un nombre para la actividad y, a continuación, haga clic en **[!UICONTROL Save]**.

   El nombre de la actividad no puede comenzar con ninguno de los siguientes caracteres:

   | Carácter | Descripción |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Más |
   | `-` | Menos |
   | `@` | Arroba |

   El nombre de la actividad no puede contener ninguna de estas secuencias de caracteres:

   | Secuencia de caracteres | Descripción |
   |--- |--- |
   | ;= | Punto y coma, igual a |
   | ;+ | Punto y coma, más |
   | ;- | Punto y coma, menos |
   | ;@ | Punto y coma, signo de arroba |
   | ,= | Coma, igual a |
   | ,+ | Coma, más |
   | ,- | Coma, menos |
   | ,@ | Coma, Signo de arroba |
   | `[`&quot; | Corchete de apertura, comillas dobles |
   | &quot;`]` | Comillas tipográficas dobles, cerrar corchete |

1. Seleccione una ubicación.

   Al hacer clic en el cuadro [!UICONTROL Select Location], aparece una lista de ubicaciones disponibles. Seleccione una de esas ubicaciones.

   También puede especificar una ubicación que no aparece en esta lista. Esto puede ser útil si el mbox todavía no se ha creado ni visto en una página. Escriba el nombre de la ubicación. Tenga cuidado al especificar una ubicación que no existe aún. Si la ortografía o las mayúsculas no coinciden con las que se usaron cuando se creó el mbox, la actividad no se publicará. Las ubicaciones introducidas manualmente se guardan en la lista de ubicaciones disponibles. La próxima vez que intente seleccionar una ubicación ingresada manualmente, estará disponible en la lista desplegable [!UICONTROL Select Location] para esa actividad.

   >[!NOTE]
   >
   >La creación de una ubicación introducida manualmente durante la creación de la actividad no crea automáticamente una nueva ubicación. El nombre de la ubicación solo se guarda en el contexto de la actividad. La ubicación se crea cuando hay una llamada de envío de contenido. Una vez creada la ubicación, estará disponible para su uso en otras actividades, para crear audiencias, etc. en la lista desplegable de ubicaciones disponibles.

1. Haga clic en **[!UICONTROL Add Audience Refinements]**, elija una o más [audiencias](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta actividad y luego haga clic en **[!UICONTROL Done]**.

   En [!UICONTROL Form-based Experience Composer], los refinamientos se han reemplazado con la funcionalidad completa de la audiencia. Los refinamientos para las actividades existentes se han migrado a [audiencias solo de actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Seleccione el tipo de contenido que desea que aparezca en esa ubicación.

1. Para el tipo de contenido seleccionado, especifique el contenido.

   **Cambiar oferta HTML:** Elija una oferta HTML.

   **Cambiar oferta de imagen:** elija una imagen guardada en la biblioteca de contenido en Target.

   También puede agregar un vínculo a una imagen (pulsación, destino, aterrizaje, etc.).

   1. Haga clic en [!UICONTROL Change Image Offer].
   1. Seleccione la imagen que desee y haga clic en [!UICONTROL Edit Links].
   1. Especifique la dirección URL o la página que desee en el sitio y haga clic en [!UICONTROL Update].

   **Cambiar oferta JSON:** Elija una oferta json.

   **Cambiar fragmento de experiencia:** Elija un fragmento de experiencia. Para obtener más información, consulte [Fragmento de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Cambiar oferta de redireccionamiento:** Elija una oferta de redireccionamiento. Para obtener más información, consulte [Crear ofertas de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Cambiar oferta remota:** Elija una oferta remota. Para obtener más información, consulte [Crear ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Crear oferta HTML:**

   1. Haga clic en [!UICONTROL Offers] y luego seleccione la ficha [!UICONTROL Code Offers].
   1. Haga clic en [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código HTML en el recuadro Código.
   1. Haga clic en [!UICONTROL Save].

   **Crear ofertas JSON:**

   1. Haga clic en [!UICONTROL Offers] y luego seleccione la ficha [!UICONTROL Code Offers].
   1. Haga clic en [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Escriba el nombre de una oferta.
   1. Escriba o pegue su código JSON en el recuadro Código.
   1. Haga clic en [!UICONTROL Save].

   **Agregar recomendación:**

   Para una actividad de Recommendations, la lista desplegable Contenido le da la opción [!UICONTROL Add Recommendation]. Haga clic en **[!UICONTROL Add Recommendation]** y luego seleccione el tipo de página. Después siga los pasos habituales que se definen en la interfaz para [crear una actividad de Recomendaciones](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Cuando se seleccionan los criterios de Recommendations en el Compositor de experiencias basadas en formularios, ahora existe un vínculo directo a la tarjeta de criterios seleccionada de modo que pueda editarlos de forma rápida y sencilla.

   Desde la página [!UICONTROL Targeting] del flujo de trabajo guiado de tres pasos [!DNL Target]:

   **Agregar decisión de oferta:**

   Agregue una oferta creada en [!DNL Adobe Journey Optimizer] (AJO) a una actividad [!DNL Adobe Target] para presentar la mejor oferta dinámica y experiencia a los visitantes de su sitio web o sitio móvil mediante offer decisioning. Esta opción solo está disponible para las actividades manuales [!UICONTROL A/B Test] y [!UICONTROL Experience Targeting] (XT).

   Para obtener más información, consulte [Usar decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Opcional, para las actividades [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] y [!UICONTROL Experience Targeting]) Para repetir este proceso para ubicaciones adicionales, haga clic en **[!UICONTROL Add Location]** y configure la ubicación y el contenido.
1. Haga clic en **[!UICONTROL Next]** y complete los pasos de creación de actividad como es habitual para su tipo de actividad.

* [Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Crear una actividad de Recomendaciones](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
