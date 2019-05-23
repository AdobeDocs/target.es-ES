---
description: En una actividad de Personalización automatizada, puede segmentar las ofertas a audiencias específicas.
seo-description: En una actividad de Personalización automatizada, puede segmentar las ofertas a audiencias específicas.
seo-title: Ofertas de personalización automatizada de Target
solution: Target,Analytics
title: Ofertas de personalización automatizada de Target
title-outputclass: Premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: Premium
translation-type: tm+mt
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# ![PREMIUM](/help/assets/premium.png) Ofertas de personalización automatizada de Target{#target-automated-personalization-offers}

En una actividad de Personalización automatizada, puede segmentar las ofertas a audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una actividad de Personalización automatizada (AP) con tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad de AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Clasificación de audiencia | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En este caso, el visitante 1 vería la oferta 1 (porque cuenta como parte de la audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el visitante 2 vería la oferta 2 aunque su mayor puntuación sea para la oferta 1, ya que no forma parte de la audiencia A. Este ejemplo demuestra por qué, para satisfacer las necesidades comerciales, las reglas de segmentación deben utilizarse con moderación. El uso de estas reglas puede reducir la eficacia de los modelos de personalización de Target.

## Configure las reglas de segmentación

1. Cree una actividad de personalización automatizada que contenga las ofertas que quiera segmentar.
1. Después de configurar las ofertas para la actividad en el Compositor de experiencias visuales, haga clic en **[!UICONTROL Contenido]**.

   Se abre el cuadro de diálogo Administrar contenido.

   ![](assets/ap_content.png)

   >[!NOTE]
   >
   >Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.

1. En la columna **[!UICONTROL Contenido]**, seleccione la oferta, haga clic en **[!UICONTROL Segmentación]** y elija las audiencias a las que desea permitir que vean la oferta.

   Esa oferta solo se mostrará a las audiencias seleccionadas.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Finalizado]**.
