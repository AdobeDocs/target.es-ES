---
keywords: varias páginas;prueba de trayecto;actividad de varias páginas
description: Aprenda a crear una actividad de varias páginas en Adobe [!DNL Target] para crear una historia en varias páginas, con un diseño específico para cada página.
title: ¿Cómo se crea una actividad de varias páginas?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# Actividad de varias páginas {#multipage-activity}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a utilizar una actividad de varias páginas para crear una historia en varias páginas, con un diseño que sea específico de cada página.

>[!ENDSHADEBOX]

Una actividad de varias páginas en [!DNL Adobe Target] crea una historia en varias páginas, con un diseño que es específico de cada página.

Por ejemplo, se puede probar una oferta de envío gratuito con compras superiores a una determinada cantidad. La oferta puede aparecer en la página de aterrizaje, en una página de categoría y en determinadas páginas de producto, con un tamaño y una ubicación diferentes en cada tipo de página. Una oferta destacada se puede mostrar en la página de inicio y, a continuación, reforzarse con ofertas más pequeñas en otras páginas relevantes.

Una actividad de varias páginas también puede definir diferentes diseños para sitios de escritorio y móviles que no responden. Si el sitio tiene un sitio móvil independiente como [!DNL m.mysite.com] en lugar de [!DNL `www.mysite.com`], cree una actividad de varias páginas, agregue [!DNL m.mysite.com] como páginas separadas y, a continuación, aplique la edición móvil para realizar los cambios correspondientes en la versión de escritorio y en la versión móvil en la misma experiencia. Para sitios móviles adaptables, utilice el [editor de experiencias móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

>[!NOTE]
>
>Las actividades de varias páginas están diseñadas para actividades en las que la misma oferta tiene una apariencia diferente en varias páginas. Si la oferta aparece igual en todas las páginas, una [prueba de plantilla](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages) es más eficaz.

Se pueden especificar reglas de plantilla para cada página de la prueba de varias páginas. Por ejemplo, una prueba de varias páginas se puede ejecutar en la página de inicio y en todas las páginas de categorías aplicando reglas de plantilla a la página de categorías de la prueba de varias páginas. Ver [Incluir la misma experiencia en páginas similares](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages).

## Adición de páginas a una actividad {#add-pages}

Cada página agregada a la actividad puede tener su propio diseño de oferta.

1. Haga clic en el icono **[!UICONTROL Configurar]** ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ).

1. Haga clic en **[!UICONTROL Agregar páginas adicionales]**.

   Aparece el panel **[!UICONTROL Páginas]** a la izquierda de la pantalla.

   ![Icono de configuración](assets/vec_edit_4.png)

1. Especifique las páginas y establezca la página predeterminada.

   Haga clic en **[!UICONTROL Agregar página]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una página adicional, especifique el nombre de página y la dirección URL y haga clic en **[!UICONTROL Guardar]**.

1. Use [!UICONTROL Compositor de experiencias visuales] para diseñar el aspecto de la oferta en cada página.
