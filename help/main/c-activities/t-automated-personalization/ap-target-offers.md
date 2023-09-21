---
keywords: personalización automatizada;ofertas;target;audiencia;reglas de segmentación;segmentación
description: Aprenda a segmentar ofertas individuales para audiencias específicas mediante una [!UICONTROL Automated Personalization] Actividad de (AP) en [!DNL Adobe Target].
title: ¿Cómo Puedo Hacer Target? [!UICONTROL Automated Personalization] ¿Ofertas?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 34%

---

# Target [!UICONTROL Automated Personalization] ofertas

En un [!DNL Adobe Target] [!DNL Automated Personalization] (AP) , puede segmentar ofertas para audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una [!UICONTROL Automated Personalization] actividad que tiene tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad de 

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Calificación de audiencia | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En esta situación, el Visitante 1 ve la Oferta 1 (porque este visitante cumple los requisitos para formar parte de la Audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el Visitante 2 ve la Oferta 2 aunque la puntuación más alta sea para la Oferta 1, ya que el Visitante 2 no forma parte de la Audiencia A. Este ejemplo demuestra por qué las reglas de segmentación deben utilizarse con moderación para satisfacer las necesidades comerciales. Añadir estas reglas puede reducir la eficacia de [!DNL Target] modelos de personalización.

## Configure las reglas de segmentación

1. Crear un [Actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) que contenga las ofertas que desee segmentar.
1. Después de configurar las ofertas para la actividad en [!UICONTROL Compositor de experiencias visuales], haga clic en **[!UICONTROL Administrar contenido]**.

   ![Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   El [!UICONTROL Administrar contenido] aparece el cuadro de diálogo.

1. Haga clic en **[!UICONTROL Ofertas]** pestaña.

   ![Página de ofertas](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Seleccione las ofertas que desee y, a continuación, elija las audiencias a las que desee permitir que vean la oferta.

   Para configurar la segmentación de una sola oferta, pase el ratón sobre la oferta que quiera y haga clic en el icono **[!UICONTROL Objetivo]**.

   Para configurar la segmentación de varias ofertas, seleccione las casillas de verificación de las ofertas que desee y haga clic en **[!UICONTROL Segmentación]** que se muestra en la parte superior derecha de la lista.

1. En el [!UICONTROL Elegir audiencia] , seleccione las audiencias que desee para las ofertas y haga clic en **[!UICONTROL Listo]** para volver a la [!UICONTROL Administrar contenido] Cuadro de diálogo.

   >[!NOTE]
   >
   >Además de seleccionar una audiencia existente, puede combinar varias audiencias para crear audiencias combinadas específicas en lugar de crear una nueva. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Finalizado]**.

>[!NOTE]
>
>Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.
