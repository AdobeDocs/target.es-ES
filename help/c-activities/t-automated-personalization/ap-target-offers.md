---
description: En una actividad de Personalización automatizada, puede segmentar las ofertas a audiencias específicas.
title: Ofertas de personalización automatizada de Target
feature: ap
solution: Target,Analytics
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Ofertas de personalización automatizada de Target{#target-automated-personalization-offers}

En una actividad de Automated Personalization (AP) puede segmentar las ofertas para audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una actividad de AP con tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad de AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Clasificación de audiencia | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En este caso, el visitante 1 vería la oferta 1 (porque cuenta como parte de la audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el visitante 2 vería la oferta 2 aunque su mayor puntuación sea para la oferta 1, ya que no forma parte de la audiencia A. Este ejemplo demuestra por qué, para satisfacer las necesidades comerciales, las reglas de segmentación deben utilizarse con moderación. El uso de estas reglas puede reducir la eficacia de los modelos de personalización de Target.

## Configure las reglas de segmentación

1. Cree una [actividad de Automated Personalization](/help/c-activities/t-automated-personalization/create-ap-activity.md) que contenga las ofertas que quiera segmentar.
1. Después de configurar las ofertas para la actividad en el Compositor de experiencias visuales, haga clic en **[!UICONTROL Administrar contenido]**.

   ![Administrar contenido](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   Se abre el cuadro de diálogo Administrar contenido.

1. Haga clic en la pestaña Ofertas.

   ![Página de ofertas](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Seleccione las ofertas y audiencias que desee para esa oferta.

   Para configurar la segmentación de una sola oferta, pase el ratón sobre la oferta que quiera y haga clic en el icono **[!UICONTORL Objetivo]**.

   Para configurar la segmentación de varias ofertas, seleccione las casillas de verificación de las ofertas que desee y haga clic en el icono **[!UICONTROL Segmentación] que aparece en la parte superior derecha de la lista.

1. En el cuadro de diálogo [!UICONTROL Elegir audiencia], seleccione la audiencia que desee para las ofertas y haga clic en **[!UICONTROL Listo]** para volver al cuadro de diálogo [!UICONTROL Administrar contenido].

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Finalizado]**.

>[!NOTE]
>
>Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.
