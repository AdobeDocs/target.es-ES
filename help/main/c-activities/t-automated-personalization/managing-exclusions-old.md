---
keywords: desduplicar;permitir duplicados;excluir ofertas duplicadas;personalización automatizada;no permitir ofertas duplicadas;excluir;contenido predeterminado;grupo de exclusión;
description: Administrar exclusiones en actividades  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP). Cree grupos de exclusión y excluya ofertas duplicadas, experiencias específicas y contenido predeterminado.
title: ¿Cómo administro las exclusiones en las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 41%

---

# Gestión de exclusiones

Administre exclusiones creando grupos de exclusión, excluyendo ofertas duplicadas, experiencias específicas y el contenido predeterminado en las actividades [!UICONTROL Automated Personalization] (AP) en [!DNL Adobe Target].

## Creación de grupos de exclusión {#task_AAAA6C7239A84F7696C8492F04B575A2}

Cree grupos de exclusión en actividades [!UICONTROL Automated Personalization] (AP) para asegurarse de que las experiencias con las ofertas designadas se excluyan automáticamente.

Los grupos de exclusión son un modo excelente de asegurar que no se presenten ofertas incompatibles en la misma experiencia en distintas ubicaciones. Por ejemplo, supongamos que tiene dos ofertas: una es para un descuento del 20 % en toda la mercancía y otra para un descuento del 15 %. Nunca desea que estas dos ofertas se presenten a los visitantes en la misma experiencia. Si añade estas dos ofertas a un grupo de exclusión, puede asegurarse de que esta situación nunca sea el caso.

También puede limitar qué audiencias pueden ver ofertas específicas en actividades AP. Para obtener más información, consulte [ofertas de Automated Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

**Para crear un grupo de exclusión:**

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en **[!UICONTROL Manage Content]** en la barra de encabezado.

   ![Enlace de Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. En el cuadro de diálogo [!UICONTROL Manage Content], haga clic en **[!UICONTROL Exclusion Groups]**.

   ![Administrar contenido > Cuadro de diálogo de Grupos de exclusión](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Si había creado grupos de exclusión previamente, estos se muestran en la lista. Si todavía no ha creado ningún grupo de exclusión, se le indicará que lo haga.

1. Haga clic **[!UICONTROL Create Exclusion Group.]**

   ![Cuadro de diálogo Crear grupo de exclusión](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obligatorio) Especifique un nombre descriptivo para el grupo de exclusión.

   Un nombre descriptivo le ayuda a usted y a los demás a localizar rápidamente un grupo y comprender su propósito.

1. Localice y seleccione las ofertas que desee agregar al grupo de exclusión.

   Puede seleccionar varias ofertas desde la misma ubicación de un grupo de exclusión.

1. Haga clic en **[!UICONTROL Save]**.

Las ofertas del grupo de exclusión se excluyen automáticamente a partir de ahora de las mismas experiencias.

## Excluir ofertas duplicadas {#concept_4EF78013F80E48EFA024AE0274C9F037}

Impida que las ofertas de la biblioteca de ofertas se dupliquen cuando se usen en distintas ubicaciones en [!UICONTROL Automated Personalization] actividades.

Por ejemplo, puede tener una actividad con seis ubicaciones en una página con 12 ofertas. Una misma oferta podría colocarse en una o varias de las ubicaciones de la actividad. Esta función evita que las ofertas duplicadas se muestren al mismo tiempo en diferentes ubicaciones dentro de la misma actividad.

Haga clic en la opción de engranaje **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]** y luego haga clic en **[!UICONTROL Allow Duplicates]** o **[!UICONTROL Disallow Duplicates]**.

![Opciones de ofertas duplicadas](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Excluir experiencias específicas {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluir experiencias específicas si desea excluir ciertas combinaciones de ofertas de la actividad [!UICONTROL Automated Personalization].

Es posible que haya ciertas combinaciones que no funcionen juntas o que esté limitando el número de experiencias probadas para reducir los requisitos de tráfico de la actividad.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en **Administrar contenido** en la barra de encabezado.

   ![Enlace de Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La lista [!UICONTROL Experiences] muestra cada experiencia generada a partir de las permutaciones de todas las opciones de contenido y ubicación.

1. Excluir experiencias como quiera.

   Puede excluir experiencias específicas pasando el puntero por encima de la experiencia deseada y luego haciendo clic en el icono de exclusión.

   ![Excluir experiencia al pasar el ratón por encima de ella](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   O puede excluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y luego haciendo clic en el icono **[!UICONTROL Exclude]** en la esquina superior derecha del cuadro de diálogo. El icono [!UICONTROL Exclude] se muestra cuando se verifican una o más experiencias.

   ![Excluir experiencias por lotes](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Puede filtrar esta vista de lista para ver solo actividades excluidas o incluidas haciendo clic en la lista desplegable [!UICONTROL Status].

   Las experiencias ahora se excluyen de la actividad y sus [!UICONTROL Status] se muestran como [!UICONTROL Excluded].

   ![Experiencias excluidas](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Excluir contenido predeterminado {#task_DCB4528989DF4C05A3A4729E5891D18F}

En ocasiones, es posible que no quiera incluir el contenido predeterminado como parte de su actividad [!UICONTROL Automated Personalization]. La forma de acceder a esta configuración es diferente a crear grupos de exclusión. Puede utilizar este método para tener una sola oferta (diferente de su contenido predeterminado) en una ubicación como parte de su actividad de AP.

Excluir el contenido predeterminado es una excelente manera de cambiar la apariencia del resto de la página para adaptarla a las ofertas que está probando con su actividad de AP. Por ejemplo, suponga que desea hacer coincidir la paleta de colores de las ofertas que está probando, puede cambiar el color de fondo de su página y excluir el color de fondo predeterminado.

**Para excluir contenido predeterminado usando el [!UICONTROL Visual Experience Composer] (VEC):**

1. Al [crear o editar una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), seleccione el contenido que desea reemplazar y haga clic para acceder a **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]** o **[!UICONTROL Change Background Color]**.
1. En el cuadro de diálogo, cree su nuevo contenido y desmarque **Incluir** a la derecha del contenido predeterminado (o desmarque la Imagen/Vídeo predeterminado en la pantalla [!UICONTROL Select Content]).

   Según el tipo de contenido u oferta, la casilla de verificación [!UICONTROL Include] está en un lugar ligeramente diferente.

   Para el contenido del texto/HTML:

   ![Casilla Incluir en el cuadro de diálogo Editar texto/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Para el contenido de imagen/vídeo:

   ![Casilla Incluir en el cuadro de diálogo Seleccionar contenido](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Para el color de fondo:

   ![Casilla Incluir en el cuadro de diálogo Editar color de fondo](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Haga clic en **[!UICONTROL Save]**.

   Puede ver las experiencias creadas a partir de las ofertas especificadas en [!UICONTROL Manage Content]. Observe que no se crean experiencias en [!UICONTROL Manage Content] con la oferta predeterminada que excluyó.

   ![imagen exclude_content_vec_4](assets/exclude_content_vec_4.png)

**Para excluir contenido predeterminado usando [!UICONTROL Form-Based Experience Composer]:**

1. Al crear o editar una actividad AP, haga clic en **[!UICONTROL Change Text/HTML]** o **[!UICONTROL Change Image Offer]** en **[!UICONTROL Content]**.
1. En el cuadro de diálogo, cree su nuevo contenido y desmarque **[!UICONTROL Include]** a la derecha del contenido predeterminado (o desmarque la Imagen/Vídeo predeterminado en la pantalla [!UICONTROL Select Content]).

   Según el tipo de contenido u oferta, la casilla de verificación [!UICONTROL Include] está en un lugar ligeramente diferente.

   Para el contenido del texto/HTML:

   ![imagen exclude_content_form_1](assets/exclude_content_form_1.png)

   Para el contenido de imagen/vídeo:

   ![imagen exclude_content_form_2](assets/exclude_content_form_2.png)

1. Haga clic en **[!UICONTROL Save]**.

   Puede ver las experiencias creadas a partir de las ofertas especificadas en [!UICONTROL Manage Content]. Observe que no se crean experiencias en [!UICONTROL Manage Content] con la oferta predeterminada que excluyó.

   ![imagen exclude_content_form_3](assets/exclude_content_form_3.png)
