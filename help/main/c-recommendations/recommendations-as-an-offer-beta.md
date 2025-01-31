---
keywords: Recommendations;oferta
description: Aprenda a utilizar Adobe Recommendations como oferta en pruebas A/B (incluida la Asignación automática y la Segmentación automática) y en actividades de direccionamiento de experiencias (XT).
title: ¿Cómo puedo utilizar Recommendations como oferta en otros tipos de actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 84cea4555448caecc079112c1a13bb63472adfbd
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 47%

---

# Recomendaciones como oferta

Ahora puede incluir recomendaciones dentro de las actividades [!UICONTROL A/B Test] (incluidas [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target]) y [!UICONTROL Experience Targeting] (XT).

Esta funcionalidad revela capacidades completamente nuevas, como:

* Recomendaciones de prueba y segmentación y contenido que no sea de recomendación dentro de la misma actividad.
* Experimente fácilmente con la colocación de recomendaciones en la página, incluido el orden de varias recomendaciones.
* Insertar automáticamente tráfico a la experiencia de recomendaciones de mejor rendimiento usando [!UICONTROL Auto-Allocate].
* Asignar de forma dinámica a los visitantes a experiencias de recomendaciones adaptadas según su perfil mediante [!UICONTROL Auto-Target].

Para empezar, cree una actividad [!UICONTROL A/B Test] o [!UICONTROL Experience Targeting] con el [!UICONTROL Visual Experience Composer] y use la acción [!UICONTROL Recommend] para agregar recomendaciones a una experiencia.

## Adición de una recomendación como una oferta en una actividad de prueba A/B o XT

1. Inicie el flujo de trabajo guiado de tres pasos con el Compositor de experiencias visuales (VEC) para crear una actividad [Prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) o una actividad de [Segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >En las pruebas A/B, recuerde que puede elegir la opción [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para insertar automáticamente el tráfico a las recomendaciones de mejor rendimiento o a la opción de [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para asignar visitantes a experiencias de recomendaciones adaptadas según su perfil.

1. Al crear una [experiencia](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), haga clic en el elemento al que desee agregar una recomendación como oferta, haga clic en **[!UICONTROL Replace Content]** ( ![Icono Reemplazar contenido](/help/main/assets/icons/Switch.svg) ) y, a continuación, seleccione **[!UICONTROL Recommendation]**.

   ![Inserción de recomendación como oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. En el carril [!UICONTROL Recommendation] del lado derecho, haga clic en **[!UICONTROL Select a Recommendation]** para mostrar el cuadro de diálogo [!UICONTROL Select Criteria].

1. Haga clic en **[!UICONTROL Create Criteria]** o seleccione un criterio existente.

1. (Opcional) Haga clic en el icono **[!UICONTROL Filter]** ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para seleccionar entre las siguientes opciones y ver los criterios de recomendaciones populares por tipo de página:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de aterrizaje
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento.
   * Otro:

1. Haga clic en **[!UICONTROL Create Criteria]** o seleccione un [criterio](/help/main/c-recommendations/c-algorithms/algorithms.md) existente y, a continuación, haga clic en **[!UICONTROL Next]** para mostrar el cuadro de diálogo [!UICONTROL Select Design].

1. Haga clic en **[!UICONTROL Create Design]** o seleccione un [diseño](/help/main/c-recommendations/c-design-overview/design-overview.md) existente y luego haga clic en **[!UICONTROL  Next]**.

1. En el cuadro de diálogo [!UICONTROL Options], especifique lo siguiente:

   * Elija una [colección](/help/main/c-recommendations/c-products/collections.md).
   * Configure las opciones [Promoción principal y Promoción secundaria](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) según sea necesario.

1. Haga clic en **[!UICONTROL Save]**.
1. Termine de configurar la prueba A/B o la actividad XT utilizando el flujo de trabajo guiado de tres partes.

## Edición de la configuración de una oferta de Recommendations

1. En el carril [!UICONTROL Recommendation], haga clic en el icono **[!UICONTROL Edit]** ( ![Editar icono](/help/main/assets/icons/Edit.svg) ) junto a [!UICONTROL Criteria Name], [!UICONTROL Design Name] o [!UICONTROL Collection Name] para cambiar el elemento.

## Eliminar una oferta de Recommendations

1. Haga clic en el icono **[!UICONTROL Delete]** ( ![Eliminar icono](/help/main/assets/icons/Delete.svg) ) en la parte superior del panel [!UICONTROL Recommendation].

### Visualización del estado de la oferta de recomendaciones {#status}

El estado de ofertas de recomendaciones (algoritmo) aparece en la parte inferior de la página [!UICONTROL Overview] de la actividad para las actividades de prueba A/B y XT que contienen ofertas de Recommendations:

* Resultados preparados
* Resultados no preparados
* Error de fuente
