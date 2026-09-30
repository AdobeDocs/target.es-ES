---
keywords: personalización automatizada;ofertas;target;audiencia;reglas de segmentación;segmentación
description: Aprenda a segmentar ofertas individuales para audiencias específicas mediante la actividad [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target].
title: ¿Cómo Puedo Segmentar [!UICONTROL Ofertas De Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 26%
---
# Ofertas de Target [!UICONTROL Automated Personalization]

En una actividad [!DNL Adobe Target] [!DNL Automated Personalization] (AP), puede segmentar ofertas para audiencias específicas.

El uso de esta funcionalidad reduce el número de ofertas que un visitante específico puede ver. Por ejemplo, considere una actividad [!UICONTROL Automated Personalization] con tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes vieron esta actividad.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Calificación del público | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de Target de la oferta 1 | 90 | 90 |
| Puntuación del modelo de personalización de Target de la oferta 2 | 50 | 70 |
| Puntuación del modelo de personalización de Target de la oferta 3 | 80 | 60 |

En esta situación, el Visitante 1 ve la Oferta 1 (porque este visitante cumple los requisitos para formar parte de la Audiencia A), que tiene la puntuación más alta para ese visitante. Sin embargo, el Visitante 2 ve la Oferta 2 aunque la puntuación más alta sea para la Oferta 1, ya que el Visitante 2 no forma parte de la Audiencia A. Este ejemplo demuestra por qué las reglas de segmentación deben utilizarse con moderación para satisfacer las necesidades comerciales. Agregar estas reglas puede reducir la eficacia de [!DNL Target] modelos de personalización.

## Configure las reglas de segmentación

1. Cree una [actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) que contenga las ofertas que quiera segmentar.
1. Después de configurar las ofertas para la actividad en [!UICONTROL Compositor de experiencias visuales], haga clic en **[!UICONTROL Administrar contenido]**.

   ![Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Se muestra el cuadro de diálogo [!UICONTROL Administrar contenido].

1. Haga clic en la ficha **[!UICONTROL Ofertas]**.

   ![Página de ofertas](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Seleccione las ofertas que desee y, a continuación, elija las audiencias a las que desee permitir que vean la oferta.

   Para configurar la segmentación de una sola oferta, pase el ratón sobre la oferta que quiera y luego haga clic en el icono **[!UICONTROL Segmentación]**.

   Para configurar la segmentación de varias ofertas, selecciona las casillas de verificación de las ofertas que desees y haz clic en el icono **[!UICONTROL Segmentación]** que aparece en la parte superior derecha de la lista.

1. En el cuadro de diálogo [!UICONTROL Elegir audiencia], seleccione las audiencias que desee para las ofertas y haga clic en **[!UICONTROL Listo]** para volver al cuadro de diálogo [!UICONTROL Administrar contenido].

   >[!NOTE]
   >
   >Además de seleccionar un público existente, puede combinar varios públicos para crear públicos combinados específicos en lugar de crear uno nuevo. Para obtener más información, consulte [Combinar varios públicos](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Haga clic en **[!UICONTROL Finalizado]**.

>[!NOTE]
>
>Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.
