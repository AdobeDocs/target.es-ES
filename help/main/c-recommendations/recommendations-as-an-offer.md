---
keywords: Recommendations;oferta
description: Aprenda a utilizar Adobe Recommendations como oferta en pruebas A/B (incluida la Asignación automática y la Segmentación automática) y en actividades de direccionamiento de experiencias (XT).
title: ¿Cómo puedo utilizar Recommendations como oferta en otros tipos de actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 60%

---

# Recomendaciones como oferta

Ahora puede incluir recomendaciones dentro de las actividades [!UICONTROL A/B Test] (incluidas [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]) y [!UICONTROL Experience Targeting] (XT).

Esta funcionalidad revela capacidades completamente nuevas, como:

* Recomendaciones de prueba y segmentación y contenido que no sea de recomendación dentro de la misma actividad.
* Experimentar fácilmente con la colocación de recomendaciones en la página, incluido el orden de varias recomendaciones.
* Insertar automáticamente tráfico a la experiencia de recomendaciones de mejor rendimiento usando [!UICONTROL Auto-Allocate].
* Asignar de forma dinámica a los visitantes a experiencias de recomendaciones adaptadas según su perfil mediante [!UICONTROL Auto-Target].

Para empezar, cree una actividad [!UICONTROL A/B Test] o [!UICONTROL Experience Targeting] con la acción [!UICONTROL Visual Experience Composer] y use la acción [!UICONTROL Insert Before], [!UICONTROL Insert After] o [!UICONTROL Replace With] para agregar recomendaciones a una experiencia.

## Adición de una recomendación como una oferta en una actividad de prueba A/B o XT

1. Inicie el flujo de trabajo guiado de tres pasos con el Compositor de experiencias visuales (VEC) para crear una actividad [Prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) o una actividad de [Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >En las pruebas A/B, recuerde que puede elegir la opción [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para insertar automáticamente el tráfico a las recomendaciones de mejor rendimiento o a la opción de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para asignar visitantes a experiencias de recomendaciones adaptadas según su perfil.

1. Al crear una [experiencia](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), haga clic en el elemento al que desee agregar una recomendación como oferta, haga clic en **[!UICONTROL Replace Content]** y, a continuación, seleccione **[!UICONTROL Recommendation]**.

   ![Inserción de recomendación como oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Seleccione entre las siguientes opciones para ver los criterios de recomendaciones populares por tipo de página:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de destino
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento.
   * Otro:

1. Seleccione los [criterios](/help/main/c-recommendations/c-algorithms/algorithms.md) que desee y haga clic en [!UICONTROL Next].
1. Seleccione el [diseño](/help/main/c-recommendations/c-design-overview/design-overview.md) que desee y haga clic en [!UICONTROL Next].
1. En el cuadro de diálogo [!UICONTROL Options], especifique lo siguiente:

   * Elija una [colección](/help/main/c-recommendations/c-products/collections.md).
   * Configure las opciones [Promoción principal y Promoción secundaria](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) según sea necesario.

1. Haga clic en [!UICONTROL Save].
1. Termine de configurar la prueba A/B o la actividad XT utilizando el flujo de trabajo guiado de tres partes.

## Edición de la configuración de una oferta de Recommendations

Hay dos maneras de editar la configuración de una oferta:

* Uso del menú [!UICONTROL Edit]
* Uso del panel [!UICONTROL Modifications]

### Edición de una oferta de Recommendations mediante el menú Edición

1. Haga clic en la oferta que desee editar y luego haga clic en **[!UICONTROL Edit]**.

   ![Editar oferta de recomendaciones](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Elija entre las siguientes opciones:

   * [Cambiar criterios](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Cambiar diseño](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Cambiar colección](/help/main/c-recommendations/c-products/collections.md)
   * [Cambiar promoción](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Realice las modificaciones que desee.

### Edición de una oferta de Recommendations mediante el panel Modificaciones

1. Haga clic en el icono [!UICONTROL Modifications] **( `</>` )** para mostrar el panel [Modificaciones](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pase el ratón sobre la acción que quiera y luego haga clic en el icono **[!UICONTROL Edit]**.

   ![Panel de modificaciones](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Realice las modificaciones que desee.

## Eliminar una oferta de Recommendations

Existen dos maneras de eliminar una oferta de Recommendations:

* Uso del menú [!UICONTROL Edit]
* Uso del panel [!UICONTROL Modifications]

### Eliminar una oferta de Recommendations mediante el menú Edición

1. Haga clic en la oferta que desee eliminar y, a continuación, haga clic en **[!UICONTROL Layout > Remove]**.

   ![Eliminar](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Eliminar una oferta de Recommendations mediante el panel Modificaciones

1. Haga clic en el icono [!UICONTROL Modifications] **( &lt;/> )** para mostrar el panel [Modificaciones](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pase el ratón sobre la acción que quiera y luego haga clic en el icono [!UICONTROL Delete].

   ![Icono Eliminar](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Visualización del estado de la oferta de recomendaciones {#status}

El estado de oferta de las recomendaciones (algoritmo) aparece en la parte inferior de la página [!UICONTROL Overview] para las actividades de prueba A/B y XT que contienen ofertas de Recommendations:

* Resultados preparados
* Resultados no preparados
* Error de fuente

![Estado de la oferta de Recommendations](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vídeo de formación: Recommendations como oferta ![Distintivo de información general](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
