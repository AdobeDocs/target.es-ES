---
keywords: mvt;prueba multivariable;ofertas;combinaciones
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) en Adobe [!DNL Target] para crear las ofertas que desee incluir en su [!UICONTROL prueba multivariable] (MVT).
title: ¿Cómo se crean combinaciones en una [!UICONTROL prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# Crear combinaciones {#create-combinations}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear la imagen y las ofertas de HTML que conforman las combinaciones de una **[!UICONTROL prueba multivariable]**.

>[!ENDSHADEBOX]

En una **[!UICONTROL prueba multivariable]** (MVT), cada ubicación contiene varias ofertas, y cada combinación de ofertas en las ubicaciones es una experiencia. Use el **[!UICONTROL Compositor de experiencias visuales]** (VEC) en [!DNL Adobe Target] para crear las ofertas que desee incluir en la prueba.

Para obtener más información sobre el uso del VEC para crear y editar ofertas, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Puede hacer clic en **[!UICONTROL Expandir selección]** al seleccionar objetos en la página para seleccionar el elemento principal además del elemento seleccionado originalmente. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.
>
>También puede utilizar la [ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) para navegar por elementos.

## Ofertas de imágenes {#image-offers}

Pruebe varias ofertas de imágenes en una ubicación para determinar qué imagen logra un mayor éxito.

1. Haz clic en una imagen de la página y selecciona **[!UICONTROL Cambiar oferta de imagen]**.

   ![Cambiar menú de oferta de imagen](../assets/multivariate-1.png)

1. En el cuadro de diálogo **[!UICONTROL Oferta de imagen]**, seleccione todas las imágenes que desee incluir en la prueba y, a continuación, haga clic en **[!UICONTROL Agregar]**.

   ![Cambiar menú de oferta de imagen](../assets/multivariate-3.png)

Cada imagen se convierte en una experiencia independiente en esa ubicación.

## Ofertas de HTML {#html-offers}

Pruebe varias ofertas de HTML en una ubicación para determinar qué oferta logra un mayor éxito.

1. Haga clic en una oferta de HTML de su página y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de HTML]**.

   ![Cambiar el menú de ofertas de HTML](../assets/multivariate-2.png)

1. Elija su oferta de HTML y haga clic en **[!UICONTROL Crear oferta]** y luego en **[!UICONTROL Oferta de HTML]**.

   ![Cambiar el menú de ofertas de HTML](../assets/multivariate-4.png)

1. Asigne un nombre a la oferta, escriba o pegue el código de la oferta de HTML y haga clic en **[!UICONTROL Crear]**.

   Repita el proceso para cualquier oferta de HTML adicional que desee incluir.

1. Haga clic en **[!UICONTROL Guardar]**.

Cada oferta de HTML se convierte en una experiencia independiente en esa ubicación.

Para obtener recomendaciones sobre cuántas combinaciones incluir y cómo revisarlas antes de iniciar la prueba, vea [Prácticas recomendadas de pruebas multivariable](/help/main/c-activities/c-multivariate-testing/best-practices.md#create).
