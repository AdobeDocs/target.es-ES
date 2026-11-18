---
keywords: desduplicar;permitir duplicados;excluir ofertas duplicadas;personalización automatizada;impedir ofertas duplicadas;excluir;contenido predeterminado;
description: Administrar exclusiones en actividades [!UICONTROL Automated Personalization] (AP).
title: ¿Cómo administro las exclusiones en las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%
---
# Gestión de exclusiones {#manage-exclusions}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a evitar ofertas duplicadas, excluir experiencias específicas y excluir contenido predeterminado en actividades **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Las exclusiones controlan qué ofertas y experiencias sirve una actividad **[!UICONTROL Automated Personalization]** (AP). Evitan que la misma oferta se muestre dos veces, eliminan las combinaciones de ofertas que no funcionan juntas y eliminan el contenido predeterminado, de modo que la actividad ofrezca experiencias más limpias y relevantes que se alineen con los objetivos y la audiencia.

## Permitir o no permitir ofertas duplicadas {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

Impida que las ofertas de la biblioteca de ofertas se dupliquen cuando se utilicen en distintas ubicaciones en actividades AP.

Una actividad puede tener, por ejemplo, seis ubicaciones en una página con 12 ofertas, por lo que la misma oferta podría colocarse en más de una ubicación. Si no se permiten ofertas duplicadas, la misma oferta no se muestra al mismo tiempo en diferentes ubicaciones dentro de la misma actividad.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), haga clic en el icono **[!UICONTROL Configurar]** ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ).

1. Haga clic en **[!UICONTROL Permitir ofertas duplicadas]** para activar o desactivar esta característica, según sus necesidades.

   ![Icono de configuración](../assets/exclusion-1.png)

## Excluir experiencias específicas {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

Excluya experiencias específicas para eliminar determinadas combinaciones de ofertas de la actividad de AP. Es posible que algunas combinaciones no funcionen juntas o que limite el número de experiencias probadas para reducir los requisitos de tráfico de la actividad.

1. Mientras [crea o edita una actividad de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), haga clic en el icono **[!UICONTROL Administrar contenido]** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ).

   La lista de **[!UICONTROL Experiencias]** muestra cada experiencia generada a partir de las permutaciones de todas las opciones de contenido y ubicación.

1. Excluya las experiencias que no desee probar.

   * Para excluir una sola experiencia, haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) y, a continuación, haga clic en **[!UICONTROL Excluir]**.
   * Para excluir varias experiencias a la vez, selecciona la casilla de verificación de cada experiencia y luego haz clic en **[!UICONTROL Excluir]**. El icono **[!UICONTROL Excluir]** se muestra cuando se seleccionan una o más experiencias.

   ![Excluir experiencias por lotes](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Las experiencias ahora se excluyen de la actividad y su **[!UICONTROL estado]** se muestra como **[!UICONTROL Excluido]**.

## Excluir contenido predeterminado {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

Excluya el contenido predeterminado cuando no desee que forme parte de su actividad de AP, de modo que una ubicación contenga solo una oferta que difiera del contenido predeterminado. Este método también permite cambiar el aspecto del resto de la página para adaptarla a las ofertas que pruebe. Por ejemplo, para que coincida con la paleta de colores de las ofertas, puede cambiar el color de fondo de la página y excluir el color de fondo predeterminado.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), selecciona el contenido que deseas reemplazar y luego haz clic en **[!UICONTROL Cambiar texto/HTML]**, **[!UICONTROL Cambiar oferta de imagen]** o **[!UICONTROL Cambiar color de fondo]**. Las opciones disponibles varían según el tipo de contenido.

   ![Cambiar opciones](../assets/exclusion-1.png)

1. Cree su nuevo contenido.

1. Haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/Setting.svg) ) y, a continuación, haga clic en el botón **Excluir oferta predeterminada/Incluir oferta predeterminada** para excluir o incluir la oferta predeterminada.

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->
