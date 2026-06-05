---
keywords: mvt;prueba multivariable;ofertas;combinaciones
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) en Adobe [!DNL Target] para crear las ofertas que desee incluir en su [!UICONTROL prueba multivariable] (MVT).
title: ¿Cómo se crean combinaciones en una [!UICONTROL prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 498
ht-degree: 55%

---

# Crear combinaciones

Use el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear las ofertas que desee incluir en su [!UICONTROL prueba multivariable] (MVT).

Para obtener más información sobre el uso del VEC para crear y editar ofertas, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Puede hacer clic en **[!UICONTROL Expandir selección]** al seleccionar objetos en la página para seleccionar el elemento principal además del elemento seleccionado originalmente. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.
>
>También puede utilizar la [ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) para navegar por elementos.

## Ofertas de imágenes {#section_A48333211DB149ED926AE467D0032914}

Pruebe varias ofertas de imágenes en una ubicación para determinar qué imagen logra un mayor éxito.

1. Haz clic en una imagen de la página y selecciona **[!UICONTROL Cambiar oferta de imagen]**.

1. En el cuadro de diálogo [!UICONTROL Oferta de imagen], seleccione todas las imágenes que desee incluir en la prueba y, a continuación, haga clic en **[!UICONTROL Agregar]**.

Cada imagen se convierte en una experiencia independiente en esa ubicación.

## Ofertas HTML {#section_DF016101AFA9412C9B99862C23DE77B1}

Pruebe varias ofertas de HTML en una ubicación para determinar qué oferta logra un mayor éxito.

1. Haga clic en una oferta de HTML de su página y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de HTML]**.

1. Haga clic en **[!UICONTROL Crear oferta]**, haga clic en **[!UICONTROL Oferta HTML]**, asigne un nombre a la oferta, escriba o pegue el código de la oferta HTML y, a continuación, haga clic en **[!UICONTROL Crear]**.

   Repita este proceso para cualquier otra oferta de HTML que quiera incluir.

1. Haga clic en **[!UICONTROL Guardar]**.

Cada oferta de HTML se convierte en una experiencia independiente en esa ubicación.

## Prácticas recomendadas {#section_2E98C23D2F1A460FA732A31799CE6291}

* No incluya en la prueba más ubicaciones de las necesarias. Cada experiencia que incluya en la prueba aumenta considerablemente la cantidad de tráfico y el tiempo necesario para obtener resultados aceptables. Por ejemplo, si tiene elementos de página con tres ofertas cada uno, hay nueve combinaciones posibles (3x3). Cuando hay tres elementos, de los cuales dos contienen tres ofertas posibles y uno tiene dos ofertas, se generan 18 opciones (3x3x2). Los números aumentan considerablemente con cada elemento y oferta adicional.
* Al crear pruebas multivariable, puede excluir más del 10 % de las experiencias de la prueba, siempre y cuando tenga en cuenta la advertencia de utilizar la creación de informes sin conexión para el análisis.
* Aproveche las características de vista previa para evitar combinaciones de contenido no deseadas. Por ejemplo, es posible que tenga dos imágenes que ofrezcan descuentos distintos en el mismo artículo o servicio. Mostrar las dos imágenes en la misma página no sería lógico y es probable que genere confusión.
* Utilice el [Estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para asegurarse de que la prueba está diseñada para la cantidad de tráfico que recibe su página. Asegúrese de que el Estimador de tráfico dé luz verde a la configuración de la prueba para que pueda obtener los resultados que desea.
* Debe contar con un mínimo de tres elementos que probar. Si tiene menos, ejecute una serie de pruebas A/B.
* Las alternativas de cada elemento deben ser significativamente diferentes entre sí.
* Aunque no es necesario, es aconsejable que cada elemento tenga el mismo número de alternativas.
