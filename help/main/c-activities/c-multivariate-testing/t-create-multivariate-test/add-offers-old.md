---
keywords: mvt;prueba multivariable;ofertas;combinaciones
description: Aprenda a usar el [!UICONTROL Visual Experience Composer] (VEC) en Adobe [!DNL Target] para crear las ofertas que desee incluir en su [!UICONTROL Multivariate Test] (MVT).
title: ¿Cómo se crean combinaciones en una [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 56%

---

# Crear combinaciones

Use [!UICONTROL Visual Experience Composer] (VEC) en [!DNL Adobe Target] para crear las ofertas que desea incluir en su [!UICONTROL Multivariate Test] (MVT).

Para obtener más información sobre el uso del VEC para crear y editar ofertas, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Puede hacer clic en **[!UICONTROL Expand Selection]** al seleccionar objetos en la página para seleccionar el elemento principal además del elemento seleccionado originalmente. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.
>
>También puede utilizar la [ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) para navegar por elementos.

## Ofertas de imágenes  {#section_A48333211DB149ED926AE467D0032914}

Pruebe varias ofertas de imágenes en una ubicación para determinar qué imagen logra un mayor éxito.

1. Haga clic en una imagen de la página y seleccione **[!UICONTROL Change Image]**.

   ![Opción Cambiar imagen](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. Seleccione todas las imágenes que desee incluir en la prueba y haga clic en **[!UICONTROL Save]**.

   ![Cuadro de diálogo Seleccionar contenido, utilizado para agregar imágenes](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

Cada imagen se convierte en una experiencia independiente en esa ubicación.

## Ofertas HTML  {#section_DF016101AFA9412C9B99862C23DE77B1}

Pruebe varias ofertas de texto/HTML en una ubicación para determinar qué oferta logra un mayor éxito.

1. Haga clic en una oferta de texto/HTML de su página y, a continuación, haga clic en **[!UICONTROL Change Text/HTML]**.

   ![Cambiar texto/HTML](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. Haga clic en **[!UICONTROL Add Text/HTML Offer]**, asigne un nombre a la oferta y escriba o pegue el código de la oferta Texto/HTML.

   ![Editar ofertas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Repita este proceso para cualquier otra oferta de HTML que quiera incluir.

1. Haga clic en **[!UICONTROL Save]**.

Cada oferta de texto/HTML se convierte en una experiencia independiente en esa ubicación.

## Prácticas recomendadas   {#section_2E98C23D2F1A460FA732A31799CE6291}

* No incluya en la prueba más ubicaciones de las necesarias. Cada experiencia que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene elementos de página con tres ofertas cada uno, hay nueve combinaciones posibles (3x3). Cuando hay tres elementos, de los cuales dos contienen tres ofertas posibles y uno tiene dos ofertas, se generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada elemento y oferta adicional.
* Al crear pruebas multivariable, puede excluir más del 10 % de las experiencias de la prueba, siempre y cuando tenga en cuenta la advertencia de utilizar la creación de informes sin conexión para el análisis.
* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas. Por ejemplo, es posible que tenga dos imágenes que ofrezcan descuentos distintos en el mismo artículo o servicio. Mostrar las dos imágenes en la misma página no sería lógico y es probable que genere confusión.
* Use [Estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página. Asegúrese de que el Estimador de tráfico dé luz verde a la configuración de la prueba para que pueda obtener los resultados que desea.
* Debe contar con un mínimo de tres elementos que probar. Si tiene menos, ejecute una serie de pruebas A/B.
* Las alternativas de cada elemento deben ser significativamente diferentes entre sí.
* Aunque no es necesario, es aconsejable que cada elemento tenga el mismo número de alternativas.

