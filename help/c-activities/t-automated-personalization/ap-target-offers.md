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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Ofertas de personalización automatizada de Target{#target-automated-personalization-offers}

En una actividad de Personalización automatizada (AP), puede dirigir ofertas a audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una actividad AP que tiene tres ofertas. La oferta 1 tiene una regla de objetivo que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Clasificación de audiencia | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En este caso, el visitante 1 vería la oferta 1 (porque cuenta como parte de la audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el visitante 2 vería la oferta 2 aunque su mayor puntuación sea para la oferta 1, ya que no forma parte de la audiencia A. Este ejemplo demuestra por qué, para satisfacer las necesidades comerciales, las reglas de segmentación deben utilizarse con moderación. El uso de estas reglas puede reducir la eficacia de los modelos de personalización de Target.

## Configuración de reglas de objetivo

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![Administrar contenido](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   Se abre el cuadro de diálogo Administrar contenido.

1. Haga clic en la ficha Ofertas.

   ![Página Ofertas](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Seleccione las ofertas que desee y elija las audiencias que desee calificar para ver esa oferta.

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Finalizado]**.

>[!NOTE]
>
>Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.
