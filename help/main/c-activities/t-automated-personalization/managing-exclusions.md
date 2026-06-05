---
keywords: desduplicar;permitir duplicados;excluir ofertas duplicadas;personalización automatizada;impedir ofertas duplicadas;excluir;contenido predeterminado;
description: Administrar exclusiones en actividades [!UICONTROL Automated Personalization] (AP).
title: ¿Cómo administro las exclusiones en las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3aid: e55547f1-a1ff-40c6-8978-026e40ab7fa4
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 23%

---

# Gestión de exclusiones

Controle su estrategia [!UICONTROL Automated Personalization] (AP) dominando las exclusiones. Tanto si evita ofertas duplicadas, perfecciona combinaciones de experiencias o elimina el contenido predeterminado, las exclusiones le permiten ofrecer experiencias más limpias y relevantes que se alineen con sus objetivos y expectativas de audiencia.

## Permitir o no permitir ofertas duplicadas {#concept_4EF78013F80E48EFA024AE0274C9F037}

Impida que las ofertas de la biblioteca de ofertas se dupliquen cuando se utilicen en distintas ubicaciones en actividades AP.

Por ejemplo, puede tener una actividad con seis ubicaciones en una página con 12 ofertas. Una misma oferta podría colocarse en una o varias de las ubicaciones de la actividad. Esta función permite evitar que las ofertas duplicadas se muestren al mismo tiempo en diferentes ubicaciones dentro de la misma actividad.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en el icono **[!UICONTROL Configurar]** ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ) > haga clic en **[!UICONTROL Permitir ofertas duplicadas]** para activar y desactivar esta característica, según sus necesidades.

## Excluir experiencias específicas {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluya experiencias específicas si desea excluir determinadas combinaciones de ofertas de la actividad de AP.

Es posible que haya ciertas combinaciones que no funcionen juntas o que esté limitando el número de experiencias probadas para reducir los requisitos de tráfico de la actividad.

1. Mientras [crea o edita una actividad de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en el icono **Administrar contenido** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ).

   La lista de [!UICONTROL Experiencias] muestra cada experiencia generada a partir de las permutaciones de todas las opciones de contenido y ubicación.

1. Excluir experiencias como quiera.

   Puede excluir experiencias específicas haciendo clic en el icono [!UICONTROL **Más acciones**] ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) y luego haciendo clic en [!UICONTROL **Excluir**].

   O puede excluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en **[!UICONTROL Excluir]**. El icono [!UICONTROL Excluir] se muestra cuando se verifican una o más experiencias.

   ![Excluir experiencias por lotes](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Las experiencias ahora se excluyen de la actividad y su [!UICONTROL estado] se muestra como [!UICONTROL Excluido].

## Excluir contenido predeterminado {#task_DCB4528989DF4C05A3A4729E5891D18F}

En ocasiones, es posible que no desee incluir el contenido predeterminado como parte de su actividad de AP. Puede utilizar este método para tener una sola oferta (diferente de su contenido predeterminado) en una ubicación como parte de su actividad de.

Excluir el contenido predeterminado es una excelente manera de cambiar la apariencia del resto de la página para adaptarla a las ofertas que está probando con su actividad de AP. Por ejemplo, suponga que desea hacer coincidir la paleta de colores de las ofertas que está probando, puede cambiar el color de fondo de su página y excluir el color de fondo predeterminado.

**Para excluir contenido predeterminado usando el [!UICONTROL Compositor de experiencias visuales] (VEC):**

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), selecciona el contenido que deseas reemplazar y haz clic para acceder a **[!UICONTROL Cambiar texto/HTML]**, **[!UICONTROL Cambiar oferta de imagen]** o **[!UICONTROL Cambiar color de fondo]**. Las opciones disponibles varían en función del tipo de contenido.

   ![Cambiar opciones](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. Cree su nuevo contenido.

1. Haga clic en el icono **[!UICONTROL Más acciones]** (![Icono de más acciones](/help/main/assets/icons/Setting.svg) ) y, a continuación, haga clic en el botón de alternancia **Excluir oferta predeterminada/Incluir oferta predeterminada**/ para excluir o incluir la oferta predeterminada.

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
