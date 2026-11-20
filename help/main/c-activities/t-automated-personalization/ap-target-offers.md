---
keywords: personalización automatizada;ofertas;target;audiencia;reglas de segmentación;segmentación
description: Descubra cómo segmentar ofertas individuales para audiencias específicas mediante actividades [!UICONTROL Automated Personalization] (AP).
title: ¿Cómo Puedo Segmentar [!UICONTROL Ofertas De Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 8%
---
# Ofertas de Target [!UICONTROL Automated Personalization] {#target-ap-offers}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a segmentar ofertas individuales para audiencias específicas en una actividad de **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

En una actividad [!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP) , las reglas de segmentación le permiten limitar una oferta a audiencias específicas, de modo que solo los visitantes que pertenezcan a esas audiencias puedan verla. Utilice las reglas de segmentación con moderación y solo cuando las necesite una empresa, ya que reducen el número de ofertas que un visitante puede ver y pueden reducir la eficacia de los modelos de personalización de [!DNL Target].

Por ejemplo, considere una actividad de AP con tres ofertas. La oferta 1 tiene una regla de segmentación que limita su exposición a la audiencia A. Dos visitantes ven esta actividad.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Calificación del público | Audiencia A | Audiencia B |
| Puntuación del modelo de personalización de la oferta 1 [!DNL Target] | 90 | 90 |
| Puntuación del modelo de personalización de la oferta 2 [!DNL Target] | 50 | 70 |
| Puntuación del modelo de personalización de la oferta 3 [!DNL Target] | 80 | 60 |

El visitante 1 se califica como parte de la Audiencia A, por lo que este visitante ve la Oferta 1, que tiene la puntuación más alta. El visitante 2 no forma parte de la Audiencia A, por lo que ve la Oferta 2, aunque la puntuación más alta sea para la Oferta 1.

## Configure las reglas de segmentación {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

Las reglas de segmentación de audiencia controlan qué visitantes pueden ver cada oferta, lo que le permite satisfacer una necesidad comercial específica, como reservar una oferta para un segmento de clientes. Cada regla restringe las opciones del modelo de personalización, por lo que las reglas se aplican únicamente a las ofertas que las requieran.

1. Cree o edite una [actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity) que contenga las ofertas que quiera segmentar.

   Puede configurar 50 ubicaciones y hasta 250 ofertas por ubicación.

1. Después de configurar las ofertas para la actividad en **[!UICONTROL Compositor de experiencias visuales]**, haga clic en el icono **[!UICONTROL Administrar contenido]** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ). Se muestra el cuadro de diálogo **[!UICONTROL Administrar contenido]**.

   ![Icono Administrar contenido](../assets/ap-offers-1.png)

1. Haga clic en la ficha **[!UICONTROL Ofertas]**.

1. Elija las ofertas que desea segmentar y, a continuación, elija las audiencias que cumplen los requisitos para verlas.

   * Para configurar la segmentación de una sola oferta, haga clic en el icono Más información ( ![icono Más información](/help/main/assets/icons/MoreSmallList.svg) ) junto a la oferta y, a continuación, haga clic en **[!UICONTROL Audiencia de destino]** para mostrar el cuadro de diálogo **[!UICONTROL Agregar audiencias]**.
   * Para configurar la segmentación de varias ofertas, seleccione las casillas de verificación de las ofertas y haga clic en el vínculo **[!UICONTROL Audiencia de destino]** que aparece al final de la lista.

   ![Icono Administrar contenido](../assets/ap-offers-2.png)

1. En el cuadro de diálogo **[!UICONTROL Agregar audiencias]**, seleccione las audiencias de las ofertas y haga clic en **[!UICONTROL Asignar audiencia]** para volver al cuadro de diálogo **[!UICONTROL Administrar contenido]**.

   >[!NOTE]
   >
   >En lugar de crear una audiencia nueva, puede combinar varias audiencias con las existentes para crear audiencias combinadas bajo demanda. Para obtener más información, consulte [Combinar varios públicos](/help/main/c-target/combining-multiple-audiences.md).

1. Haga clic en **[!UICONTROL Finalizado]**.

Las reglas de segmentación ahora se aplican a las ofertas seleccionadas, por lo que solo los visitantes que pertenecen a las audiencias asignadas pueden verlas.
