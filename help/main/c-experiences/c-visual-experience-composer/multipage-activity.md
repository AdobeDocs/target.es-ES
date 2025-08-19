---
keywords: varias páginas;prueba de trayecto;actividad de varias páginas
description: Aprenda a crear una actividad de varias páginas en Adobe [!DNL Target] le permite crear una historia en varias páginas, con un diseño que es específico de cada página.
title: ¿Cómo se crea una actividad de varias páginas?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 54%

---

# Actividad de varias páginas

Una actividad de varias páginas en [!DNL Adobe Target] le permite crear una historia en varias páginas, con un diseño que es específico de cada página.

Por ejemplo, podría querer probar una oferta para envío gratuito con compras superiores a cierto monto. Podría querer que esa oferta apareciera en su página de aterrizaje, una página de categoría y ciertas páginas de producto, pero desea que tenga un tamaño diferente y esté en una ubicación diferente en cada tipo de página. Podría mostrar una oferta destacada en su página de inicio y luego reforzar esa oferta con ofertas más pequeñas en otras páginas relevantes.

También puede usar una actividad de varias páginas para definir diferentes diseños para sus sitios de escritorio y los móviles que no responden. Si el sitio tiene un sitio móvil independiente como [!DNL m.mysite.com] en lugar de [!DNL `www.mysite.com`], debería crear una [actividad multipágina](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), agregar [!DNL m.mysite.com] como páginas separadas y, a continuación, aplicar la edición móvil para realizar los cambios correspondientes en la versión de escritorio y la versión móvil en la misma experiencia. Para sitios móviles adaptables, utilice el [editor de experiencias móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5).

>[!NOTE]
>
>Las actividades de varias páginas están diseñadas para actividades en las que la misma oferta tiene una apariencia diferente en varias páginas. Si la oferta aparece igual en todas las páginas, una [prueba de plantilla](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) es más eficaz.

Puede especificar reglas de plantilla para cada página en la prueba de varias páginas. Por ejemplo, puede ejecutar una prueba de varias páginas en toda la página de inicio y en todas las páginas de categoría al aplicar reglas de plantilla a la página de categoría en la prueba de varias páginas. Ver [Incluir la misma experiencia en páginas similares](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Para agregar páginas a una prueba:

1. Haga clic en el icono **[!UICONTROL Configure]** ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ).
1. Haga clic en **[!UICONTROL Add Additional Pages]**.

   Aparece el panel [!UICONTROL Pages] a la izquierda de la pantalla.

1. Especifique las páginas y establezca la página predeterminada.

   Haga clic en **[!UICONTROL Add Page]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una página adicional, especifique el nombre de página y la dirección URL y, a continuación, haga clic en **[!UICONTROL Save]**.

1. Use [!UICONTROL Visual Experience Composer] para diseñar el aspecto de la oferta en cada página.
