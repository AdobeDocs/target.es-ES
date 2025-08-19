---
keywords: personalización automatizada;ofertas;target;audiencia;reglas de segmentación;segmentación
description: Descubra cómo dirigir ofertas individuales a audiencias específicas mediante actividades [!UICONTROL Automated Personalization] (AP).
title: ¿Cómo Puedo Segmentar [!UICONTROL Automated Personalization] Ofertas?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 19%

---

# Ofertas de Target [!UICONTROL Automated Personalization]

En una actividad [!DNL Adobe Target] [!DNL Automated Personalization] (AP), puede segmentar ofertas para audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una actividad [!UICONTROL Automated Personalization] con tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Calificación de audiencia | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En esta situación, el Visitante 1 ve la Oferta 1 (porque este visitante cumple los requisitos para formar parte de la Audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el Visitante 2 ve la Oferta 2 aunque la puntuación más alta sea para la Oferta 1, ya que el Visitante 2 no forma parte de la Audiencia A. Este ejemplo demuestra por qué las reglas de segmentación deben utilizarse con moderación para satisfacer las necesidades comerciales. Agregar estas reglas puede reducir la eficacia de [!DNL Target] modelos de personalización.

## Configure las reglas de segmentación

1. Cree o edite una [actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) que contenga las ofertas que quiera segmentar.
1. Después de configurar las ofertas para la actividad en [!UICONTROL Visual Experience Composer], haga clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) ).

   Se muestra el cuadro de diálogo [!UICONTROL Manage Content].

1. Haga clic en la ficha **[!UICONTROL Offers]**.

1. Seleccione las ofertas que desee y, a continuación, elija las audiencias a las que desee permitir que vean la oferta.

   Para configurar la segmentación de una sola oferta, haga clic en el icono Más información ( ![icono Más información](/help/main/assets/icons/MoreSmallList.svg) ) junto a la oferta deseada y, a continuación, haga clic en **[!UICONTROL Target Audience]** para mostrar el cuadro de diálogo [!UICONTROL Add Audiences].

   Para configurar la segmentación de varias ofertas, seleccione las casillas de verificación de las ofertas que desee y haga clic en el vínculo **[!UICONTROL Target Audience]** que aparece en la parte inferior de la lista.

1. En el cuadro de diálogo [!UICONTROL Add Audiences], seleccione las audiencias que desee para las ofertas y haga clic en **[!UICONTROL Assign Audience]** para volver al cuadro de diálogo [!UICONTROL Manage Content].

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas bajo demanda en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Done]**.

>[!NOTE]
>
>Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.
