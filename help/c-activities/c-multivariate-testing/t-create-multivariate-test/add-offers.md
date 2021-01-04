---
keywords: mvt;multivariate test;offers;combinations
description: Use el Compositor de experiencias visuales (VEC) en Adobe Target para crear las ofertas que desee incluir en la prueba multivariable (MVT).
title: Cree combinaciones en pruebas multivariadas (MVT) con Adobe Target
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 96%

---


# Crear combinaciones

Utilice el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear las ofertas que desee incluir en la [!UICONTROL Prueba multivariada] (MVT).

Para obtener más información sobre el uso del VEC para crear y editar ofertas, consulte [Opciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Cuando seleccione los objetos de la página, puede hacer clic en **[!UICONTROL Expandir selección]** para seleccionar el elemento principal, además del elemento que seleccionó en un principio. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.
>
>También puede utilizar la [ruta DOM](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) para navegar por elementos.

## Ofertas de imágenes   {#section_A48333211DB149ED926AE467D0032914}

Pruebe varias ofertas de imágenes en una ubicación para determinar qué imagen logra un mayor éxito.

1. Haga clic en una imagen de la página y seleccione **[!UICONTROL Cambiar imagen]**.

   ![Opción Cambiar imagen](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. Seleccione todas las imágenes que quiera incluir en la prueba y haga clic en **[!UICONTROL Guardar]**.

   ![Cuadro de diálogo Seleccionar contenido, utilizado para agregar imágenes](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

Cada imagen se convierte en una experiencia independiente en esa ubicación.

## Ofertas HTML   {#section_DF016101AFA9412C9B99862C23DE77B1}

Pruebe varias ofertas de texto/HTML en una ubicación para determinar qué oferta logra un mayor éxito.

1. Haga clic en una oferta de texto/HTML de su página y seleccione **[!UICONTROL Cambiar texto/HTML]**.

   ![Cambiar texto/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. Haga clic en **[!UICONTROL Agregar oferta de texto/HTML]**, asigne un nombre a la oferta y escriba o pegue el código de la oferta.

   ![Editar ofertas](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Repita este proceso para cualquier otra oferta de HTML que quiera incluir.

1. Haga clic en **[!UICONTROL Guardar]**.

Cada oferta de texto/HTML se convierte en una experiencia independiente en esa ubicación.

## Prácticas recomendadas {#section_2E98C23D2F1A460FA732A31799CE6291}

* No incluya en la prueba más ubicaciones de las necesarias. Cada experiencia que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene elementos de página con tres ofertas cada uno, hay nueve combinaciones posibles (3x3). Cuando hay tres elementos, de los cuales dos contienen tres ofertas posibles y uno tiene dos ofertas, se generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada elemento y oferta adicional.
* Ahora, al crear pruebas multivariable, puede excluir más del 10 % de las experiencias de la prueba siempre y cuando tenga en cuenta la advertencia de utilizar la creación de informes sin conexión para el análisis.
* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas. Por ejemplo, es posible que tenga dos imágenes que ofrezcan descuentos distintos en el mismo artículo o servicio. Mostrar las dos imágenes en la misma página no sería lógico y es probable que genere confusión.
* Utilice el Estimador de tráfico para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página. Asegúrese de que el Estimador de tráfico aprueba la configuración de la prueba, para que pueda obtener los resultados que desea.
* Debe contar con un mínimo de tres elementos que probar. Si tiene menos, ejecute una serie de  pruebas A/B.
* Es recomendable que las alternativas de cada elemento sean bastante diferentes entre sí.
* Aunque no es necesario, es aconsejable que cada elemento tenga el mismo número de alternativas.

