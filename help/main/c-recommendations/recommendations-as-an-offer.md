---
keywords: Recommendations;oferta
description: Aprenda a utilizar Adobe Recommendations como oferta en pruebas A/B (incluida la Asignación automática y la Segmentación automática) y en actividades de direccionamiento de experiencias (XT).
title: ¿Cómo puedo utilizar Recommendations como oferta en otros tipos de actividades?
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Recommendations como oferta

Ahora puede incluir recomendaciones dentro de la [!UICONTROL prueba A/B] (incluidas las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) y las actividades de [!UICONTROL Segmentación de experiencias] (XT).

Esta funcionalidad revela capacidades completamente nuevas, como:

* Recomendaciones de prueba y segmentación y contenido que no sea de recomendación dentro de la misma actividad.
* Experimentar fácilmente con la colocación de recomendaciones en la página, incluido el orden de varias recomendaciones.
* Insertar automáticamente tráfico a la experiencia de recomendaciones de mejor rendimiento mediante [!UICONTROL Asignación automática].
* Asignar de forma dinámica a los visitantes a experiencias de recomendaciones adaptadas según su perfil mediante el uso de [!UICONTROL Segmentación automática].

Para empezar, cree una actividad [!UICONTROL Prueba A/B] o de [!UICONTROL Segmentación de experiencias] con el [!UICONTROL Compositor de experiencias visuales] y use la acción [!UICONTROL Insertar antes], [!UICONTROL Insertar después] o [!UICONTROL Reemplazar con] para agregar recomendaciones a una experiencia.

## Adición de una recomendación como una oferta en una actividad de prueba A/B o XT

1. Inicie el flujo de trabajo guiado de tres pasos con el Compositor de experiencias visuales (VEC) para crear una actividad [Prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) o una actividad de [Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >En las pruebas A/B, recuerde que puede elegir la opción [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para insertar automáticamente el tráfico a las recomendaciones de mejor rendimiento o a la opción de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para asignar visitantes a experiencias de recomendaciones adaptadas según su perfil.

1. Cuando cree una [experiencia](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), haga clic en el elemento al que desee agregar una recomendación como oferta, seleccione la acción **[!UICONTROL Insertar antes]**, **[!UICONTROL Insertar después]** o **[!UICONTROL Reemplazar con]** y, a continuación, seleccione [!UICONTROL Recomendación].

   La siguiente ilustración muestra la opción [!UICONTROL Insertar después > Recomendación].

   ![Inserción de recomendación como oferta](/help/main/c-recommendations/assets/replace-after-recommendations.png)

1. Seleccione entre las siguientes opciones para ver los criterios de recomendaciones populares por tipo de página:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de aterrizaje
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento.
   * Otro:

1. Seleccione los [criterios](/help/main/c-recommendations/c-algorithms/algorithms.md) deseados y haga clic en [!UICONTROL Siguiente].
1. Seleccione [el diseño](/help/main/c-recommendations/c-design-overview/design-overview.md) deseado y haga clic en [!UICONTROL Siguiente].
1. En el cuadro de diálogo [!UICONTROL Opciones], especifique lo siguiente:

   * Elija una [colección](/help/main/c-recommendations/c-products/collections.md).
   * Configure las opciones [Promoción principal y Promoción secundaria](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) según sea necesario.

1. Haga clic en [!UICONTROL Guardar].
1. Termine de configurar la prueba A/B o la actividad XT utilizando el flujo de trabajo guiado de tres partes.

## Edición de la configuración de una oferta de Recommendations

Hay dos maneras de editar la configuración de una oferta:

* usando el menú [!UICONTROL Edición].
* usando el panel [!UICONTROL Modificaciones].

### Edición de una oferta de Recommendations mediante el menú Edición

1. Seleccione la oferta que desee editar y luego haga clic en **[!UICONTROL Editar]**.

   ![Editar oferta de recomendaciones](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Elija entre las siguientes opciones:

   * [Cambiar criterios](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Cambiar diseño](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Cambiar colección](/help/main/c-recommendations/c-products/collections.md)
   * [Cambiar promoción](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Realice las modificaciones que desee.

### Edición de una oferta de Recommendations mediante el panel Modificaciones

1. Haga clic en el icono [!UICONTROL Modificaciones] **( `</>` )** para mostrar el panel [Modificaciones](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pase el ratón sobre el entorno que quiera y luego haga clic en el icono **[!UICONTROL Editar]**.

   ![Panel de modificaciones](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Realice las modificaciones que desee.

## Eliminar una oferta de Recommendations

Existen dos maneras de eliminar una oferta de Recommendations:

* usando el menú [!UICONTROL Edición].
* usando el panel [!UICONTROL Modificaciones].

### Eliminar una oferta de Recommendations mediante el menú Edición

1. Haga clic en la oferta que desee eliminar y, a continuación, haga clic en **[!UICONTROL Diseño > Eliminar]**.

   ![Eliminar](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Eliminar una oferta de Recommendations mediante el panel Modificaciones

1. Haga clic en el icono [!UICONTROL Modificaciones] **( &lt;/> )** para mostrar el panel [Modificaciones](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pase el ratón sobre la modificación que quiera y luego haga clic en el icono [!UICONTROL Eliminar].

   ![Icono Eliminar](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Visualización del estado de la oferta de recomendaciones {#status}

El estado de oferta de las recomendaciones (algoritmo) aparece en la página [!UICONTROL Información general] de las actividades de prueba A/B y XT que contienen ofertas de Recommendations:

* Resultados preparados
* Resultados no preparados
* Error de fuente

![Estado de la oferta de Recommendations](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vídeo de formación: Recommendations como oferta ![Distintivo de información general](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
