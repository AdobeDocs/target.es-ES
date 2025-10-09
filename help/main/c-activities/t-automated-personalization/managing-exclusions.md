---
keywords: desduplicar;permitir duplicados;excluir ofertas duplicadas;personalización automatizada;impedir ofertas duplicadas;excluir;contenido predeterminado;
description: Administrar exclusiones en actividades [!UICONTROL Automated Personalization] (AP).
title: ¿Cómo administro las exclusiones en las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: a68e7501fbb157a1ac5b0c0cbb3d574abdb747dd
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 21%

---

# Gestión de exclusiones

Controle su estrategia de [!UICONTROL Automated Personalization] (AP) dominando las exclusiones. Tanto si evita ofertas duplicadas, perfecciona combinaciones de experiencias o elimina el contenido predeterminado, las exclusiones le permiten ofrecer experiencias más limpias y relevantes que se alineen con sus objetivos y expectativas de audiencia.

## Permitir o no permitir ofertas duplicadas {#concept_4EF78013F80E48EFA024AE0274C9F037}

Impida que las ofertas de la biblioteca de ofertas se dupliquen cuando se utilicen en distintas ubicaciones en actividades AP.

Por ejemplo, puede tener una actividad con seis ubicaciones en una página con 12 ofertas. Una misma oferta podría colocarse en una o varias de las ubicaciones de la actividad. Esta función permite evitar que las ofertas duplicadas se muestren al mismo tiempo en diferentes ubicaciones dentro de la misma actividad.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en el icono **[!UICONTROL Configure]** ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ) > haga clic en **[!UICONTROL Allow Duplicate Offers]** para activar o desactivar esta característica, según sus necesidades.

## Excluir experiencias específicas {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluya experiencias específicas si desea excluir determinadas combinaciones de ofertas de la actividad de AP.

Es posible que haya ciertas combinaciones que no funcionen juntas o que esté limitando el número de experiencias probadas para reducir los requisitos de tráfico de la actividad.

1. Mientras [crea o edita una actividad de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en el icono **Administrar contenido** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ).

   La lista [!UICONTROL Experiences] muestra cada experiencia generada a partir de las permutaciones de todas las opciones de contenido y ubicación.

1. Excluir experiencias como quiera.

   Puede excluir experiencias específicas haciendo clic en el icono [!UICONTROL **Más acciones**] ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) y luego haciendo clic en [!UICONTROL **Excluir**].

   O puede excluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en **[!UICONTROL Exclude]**. El icono [!UICONTROL Exclude] se muestra cuando se verifican una o más experiencias.

   ![Excluir experiencias por lotes](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Las experiencias ahora se excluyen de la actividad y sus [!UICONTROL Status] se muestran como [!UICONTROL Excluded].

## Excluir contenido predeterminado {#task_DCB4528989DF4C05A3A4729E5891D18F}

En ocasiones, es posible que no desee incluir el contenido predeterminado como parte de su actividad de AP. Puede utilizar este método para tener una sola oferta (diferente de su contenido predeterminado) en una ubicación como parte de su actividad de.

Excluir el contenido predeterminado es una excelente manera de cambiar la apariencia del resto de la página para adaptarla a las ofertas que está probando con su actividad de AP. Por ejemplo, suponga que desea hacer coincidir la paleta de colores de las ofertas que está probando, puede cambiar el color de fondo de su página y excluir el color de fondo predeterminado.

**Para excluir contenido predeterminado usando el [!UICONTROL Visual Experience Composer] (VEC):**

1. Al [crear o editar una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), seleccione el contenido que desea reemplazar y haga clic para acceder a **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image Offer]** o **[!UICONTROL Change Background Color]**. Las opciones disponibles varían en función del tipo de contenido.

   ![Cambiar opciones](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. Cree su nuevo contenido.

1. Haga clic en el icono **[!UICONTROL More Actions]** ( ![icono de más acciones](/help/main/assets/icons/Setting.svg) ) y, a continuación, haga clic en el botón de alternancia **Excluir oferta/incluir predeterminada**/ para excluir o incluir la oferta predeterminada.

   <!-- Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)-->

<!-- 1. Click **[!UICONTROL Save]**.

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

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)-->
