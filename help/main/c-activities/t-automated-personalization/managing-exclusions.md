---
keywords: desduplicar;permitir duplicados;excluir ofertas duplicadas;personalización automatizada;no permitir ofertas duplicadas;excluir;contenido predeterminado;grupo de exclusión;
description: Administración de exclusiones en [!DNL Adobe Target] [!UICONTROL Automated Personalization] Actividades de (AP). Cree grupos de exclusión y excluya ofertas duplicadas, experiencias específicas y contenido predeterminado.
title: ¿Cómo administro las exclusiones en [!UICONTROL Automated Personalization] ¿Actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 58%

---

# Gestión de exclusiones

Administre exclusiones creando grupos de exclusión, excluyendo ofertas duplicadas, experiencias específicas y el contenido predeterminado en [!UICONTROL Automated Personalization] Actividades de (AP) en [!DNL Adobe Target].

## Creación de grupos de exclusión {#task_AAAA6C7239A84F7696C8492F04B575A2}

Creación de grupos de exclusión en [!UICONTROL Automated Personalization] (AP) actividades para garantizar que las experiencias con las ofertas designadas se excluyan automáticamente.

Los grupos de exclusión son un modo excelente de asegurar que no se presenten ofertas incompatibles en la misma experiencia en distintas ubicaciones. Por ejemplo, supongamos que tiene dos ofertas: una es para un descuento del 20 % en toda la mercancía y otra para un descuento del 15 %. Nunca desea que estas dos ofertas se presenten a los visitantes en la misma experiencia. Si añade estas dos ofertas a un grupo de exclusión, puede asegurarse de que esta situación nunca sea el caso.

También puede limitar qué audiencias pueden ver ofertas específicas en actividades AP. Para obtener más información, consulte [ofertas de Automated Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

**Para crear un grupo de exclusión:**

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en **[!UICONTROL Administrar contenido]** en la barra de encabezado.

   ![Enlace de Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. En el [!UICONTROL Administrar contenido] , haga clic en **[!UICONTROL Grupos de exclusión]**.

   ![Administrar contenido > Cuadro de diálogo de Grupos de exclusión](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Si había creado grupos de exclusión previamente, estos se muestran en la lista. Si todavía no ha creado ningún grupo de exclusión, se le indicará que lo haga.

1. Haga clic en **[!UICONTROL Crear grupo de exclusión]**.

   ![Cuadro de diálogo Crear grupo de exclusión](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obligatorio) Especifique un nombre descriptivo para el grupo de exclusión.

   Un nombre descriptivo le ayuda a usted y a los demás a localizar rápidamente un grupo y comprender su propósito.

1. Localice y seleccione las ofertas que desee agregar al grupo de exclusión.

   Puede seleccionar varias ofertas desde la misma ubicación de un grupo de exclusión.

1. Haga clic en **[!UICONTROL Guardar]**.

Las ofertas del grupo de exclusión se excluyen automáticamente a partir de ahora de las mismas experiencias.

## Excluir ofertas duplicadas {#concept_4EF78013F80E48EFA024AE0274C9F037}

Impida que las ofertas de la biblioteca de ofertas se dupliquen cuando se utilicen en distintas ubicaciones en las actividades de [!UICONTROL Personalización automatizada].

Por ejemplo, puede tener una actividad con seis ubicaciones en una página con 12 ofertas. Una misma oferta podría colocarse en una o varias de las ubicaciones de la actividad. Esta función evita que las ofertas duplicadas se muestren al mismo tiempo en diferentes ubicaciones dentro de la misma actividad.

Haga clic en **[!UICONTROL Configurar]** opción de engranaje > **[!UICONTROL Ofertas duplicadas]**, luego haga clic en **[!UICONTROL Permitir duplicados]** o **[!UICONTROL No permitir duplicados]**.

![Opciones de ofertas duplicadas](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Excluir experiencias específicas {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Excluir experiencias específicas si desea excluir ciertas combinaciones de ofertas de su [!UICONTROL Automated Personalization] actividad.

Es posible que haya ciertas combinaciones que no funcionen juntas o que esté limitando el número de experiencias probadas para reducir los requisitos de tráfico de la actividad.

1. Mientras [crea o edita una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), haga clic en **Administrar contenido** en la barra de encabezado.

   ![Enlace de Administrar contenido](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La lista de [!UICONTROL Experiencias] muestra cada experiencia generada a partir de las permutaciones de todas las opciones de contenido y ubicación.

1. Excluir experiencias como quiera.

   Puede excluir experiencias específicas pasando el puntero sobre la experiencia deseada y luego haciendo clic en el icono de exclusión.

   ![Excluir experiencia al pasar el ratón por encima de ella](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   O puede excluir experiencias por lotes seleccionando la casilla de las experiencias relevantes y haciendo clic en **[!UICONTROL Excluir]** en la esquina superior derecha del cuadro de diálogo. El [!UICONTROL Excluir] El icono se muestra cuando se verifican una o más experiencias.

   ![Excluir experiencias por lotes](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Puede filtrar esta vista de lista para ver solo actividades excluidas o incluidas haciendo clic en la lista desplegable [!UICONTROL Estado].

   Las experiencias ahora se excluyen de la actividad y sus [!UICONTROL Estado] mostrar como [!UICONTROL Excluido].

   ![Experiencias excluidas](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Excluir contenido predeterminado {#task_DCB4528989DF4C05A3A4729E5891D18F}

En ocasiones, es posible que no desee incluir el contenido predeterminado como parte de su [!UICONTROL Automated Personalization] actividad. La forma de acceder a esta configuración es diferente a crear grupos de exclusión. Puede utilizar este método para tener una sola oferta (diferente de su contenido predeterminado) en una ubicación como parte de su actividad de AP.

Excluir el contenido predeterminado es una excelente manera de cambiar la apariencia del resto de la página para adaptarla a las ofertas que está probando con su actividad de AP. Por ejemplo, suponga que desea hacer coincidir la paleta de colores de las ofertas que está probando, puede cambiar el color de fondo de su página y excluir el color de fondo predeterminado.

**Para excluir el contenido predeterminado usando Visual Experience Composer (VEC):**

1. While [creación o edición de una actividad AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), seleccione el contenido que desea reemplazar y haga clic en para acceder a **[!UICONTROL Cambiar texto/HTML]**, **[!UICONTROL Cambiar imagen]**, o **[!UICONTROL Cambiar color de fondo]**.
1. En el cuadro de diálogo, cree su nuevo contenido y desmarque **Incluir** a la derecha del contenido predeterminado (o desmarque la Imagen/Vídeo predeterminado en la pantalla Seleccionar contenido).

   Según el tipo de oferta o contenido, la variable [!UICONTROL Incluir] La casilla de verificación de está en un lugar ligeramente diferente.

   Para el contenido del texto/HTML:

   ![Casilla Incluir en el cuadro de diálogo Editar texto/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Para el contenido de imagen/vídeo:

   ![Casilla Incluir en el cuadro de diálogo Seleccionar contenido](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Para el color de fondo:

   ![Casilla Incluir en el cuadro de diálogo Editar color de fondo](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   Puede ver las experiencias creadas a partir de las ofertas que especificó en [!UICONTROL Administrar contenido]. Verá que no se crean experiencias en [!UICONTROL Administrar contenido] uso de la oferta predeterminada que ha excluido.

   ![imagen exclude_content_vec_4](assets/exclude_content_vec_4.png)

**[!UICONTROL Para excluir el contenido predeterminado utilizando el Compositor basado en la experiencia del formulario]:**

1. Al crear o editar una actividad de AP, haga clic en **[!UICONTROL Cambiar texto/HTML]** o **[!UICONTROL Cambiar oferta de imagen]** en el **[!UICONTROL Contenido]**.
1. En el cuadro de diálogo, cree su nuevo contenido y desmarque **[!UICONTROL Incluir]** a la derecha del contenido predeterminado (o desmarque la Imagen/Vídeo predeterminado en la pantalla Seleccionar contenido).

   Según el tipo de oferta o contenido, la variable [!UICONTROL Incluir] La casilla de verificación de está en un lugar ligeramente diferente.

   Para el contenido del texto/HTML:

   ![imagen exclude_content_form_1](assets/exclude_content_form_1.png)

   Para el contenido de imagen/vídeo:

   ![imagen exclude_content_form_2](assets/exclude_content_form_2.png)

1. Haga clic en **[!UICONTROL Guardar]**.

   Puede ver las experiencias creadas a partir de las ofertas que especificó en [!UICONTROL Administrar contenido]. Verá que no se crean experiencias en [!UICONTROL Administrar contenido] uso de la oferta predeterminada que ha excluido.

   ![imagen exclude_content_form_3](assets/exclude_content_form_3.png)
