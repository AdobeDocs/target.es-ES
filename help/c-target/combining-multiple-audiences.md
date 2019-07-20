---
description: Combine varias audiencias (incluidas las de Adobe Experience Cloud y las de Target) sobre la marcha para crear audiencias ad-hoc. También puede crear reglas de exclusión y excluir audiencias de una regla.
keywords: audiencia;reglas de audiencia;combinar audiencias;combinación de audiencias;exclusión;añadir exclusión;excluir;audiencia específica
seo-description: Combine varias audiencias (incluidas las de Adobe Experience Cloud y las de Target) sobre la marcha para crear audiencias ad-hoc. También puede crear reglas de exclusión y excluir audiencias de una regla.
seo-title: Combinar varias audiencias en Adobe Target
solution: Target
title: Combinación de varias audiencias
topic: Advanced,Standard,Classic
uuid: aec09341-9b54-400c-a438-60058c52ac2a
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Combinación de varias audiencias{#combine-multiple-audiences}

Combine varias audiencias (incluidas las de Adobe Experience Cloud y las de Target) sobre la marcha para crear audiencias ad-hoc. También puede crear reglas de exclusión y excluir audiencias de una regla.

Imagine que tiene las audiencias “Visitantes nuevos” y “Usuarios de Chrome”. Para una actividad concreta, puede combinar estas audiencias existentes para dirigirse a los visitantes nuevos que utilicen navegadores Chrome. En lugar de crear una tercera audiencia y almacenarla en la biblioteca [!UICONTROL Audiencias], puede combinar las dos audiencias al crear o editar una actividad existente.

Otro ejemplo: puede dirigirse a todos los clientes fieles incluyendo un segmento de [!DNL Audience Manager] para el estado de fidelidad y combinarlo con un segmento de [!DNL Target] constituido por personas que se registraron en el programa de fidelidad durante la sesión actual en lugar de crear una tercera audiencia permanente.

Puede combinar hasta diez audiencias usando los operadores Y y O.

Puede crear y usar audiencias combinadas en varios lugares de la interfaz de usuario de [!DNL Target]. 

## Create a combined audience while creating an activity {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

Puede crear una audiencia combinada ad hoc en la página de [!UICONTROL Target] de la actividad durante el flujo de trabajo guiado de tres pasos.

1. While creating an [activity](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Target]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![Resultado del paso](assets/edit_audience.png)

1. En la página [!UICONTROL Elegir audiencia], marque las casillas de verificación de las audiencias que quiera usar como componentes básicos en la audiencia combinada.

   ![Resultado del paso](assets/combine_multiple_audiences1.png)

1. Haga clic en **[!UICONTROL Combinar varias audiencias], en la esquina superior derecha.**

   ![Resultado del paso](assets/combine_multiple_audiences2.png)

1. (Condicional) Edite la nueva audiencia combinada si lo desea.

   El cuadro de diálogo [!UICONTROL Editar audiencia] permite arrastrar y soltar más componentes básicos de audiencia de la parte de la izquierda a la nueva audiencia combinada, así como añadir reglas de exclusión y excluir audiencias.

   1. Puede usar la funcionalidad de arrastrar y soltar para añadir audiencias dentro de una sección existente como componente básico de nivel 2. Para añadir un componente básico de nivel 1, marque la casilla de verificación de la audiencia que quiera y luego haga clic en **[!UICONTROL Añadir a las reglas]**.

      Por ejemplo, supongamos que en el ejemplo anterior desea incluir a los usuarios de Safari en la audiencia combinada. Busque y arrastre la audiencia «Navegador Safari» al cuadro «Firefox Browser» (Navegador Firefox) de la derecha, como en el ejemplo siguiente:

      ![](assets/combine_multiple_audiences3.png)

      Observe que el operador que separa las dos audiencias de tipo de navegador es “Y”. Seleccione la lista desplegable Y y agréguela a "OR" para crear una audiencia combinada nueva para nuevos visitantes que utilicen Firefox o Safari. Tenga cuidado de evitar crear reglas que excluyen todos los miembros potenciales de la audiencia. Por ejemplo, no es posible visitar una página con Firefox y Safari simultáneamente.

      >[!NOTE]
      >
      >El operador Y u O (AND u OR) debe ser el mismo durante la combinación de audiencias. No puede combinar distintos operadores.

   1. Para añadir una exclusión a una regla, haga clic en **[!UICONTROL Exclusión]** &gt; **[!UICONTROL Añadir exclusión]**.

      ![](assets/combine_multiple_audiences3a.png)

      Arrastre una audiencia y suéltela en el cuadro:

      ![](assets/combine_multiple_audiences3b.png)

      Por ejemplo, para excluir a los visitantes de Estados Unidos de visitantes nuevos, puede arrastrar el Mercado: Audiencia de Estados Unidos en el cuadro, como se muestra a continuación:

      ![](assets/combine_multiple_audiences3b2.png)

      Esta audiencia combinada incluye a todos los visitantes nuevos que llegan a su sitio usando Safari o Firefox (excepto a los de San Francisco).

   1. Para excluir una audiencia de una regla, haga clic en **[!UICONTROL Exclusión]** &gt; **[!UICONTROL Excluir esta audiencia]**.

      Por ejemplo, puede crear una audiencia combinada que incluya a todos los visitantes nuevos que lleguen a su sitio excluyendo a los que lo hagan por medio de Firefox. Excluir a los visitantes que usan Firefox es más fácil y rápido que crear una audiencia combinada que incluya explícitamente varios navegadores (Safari, Chrome e Internet Explorer) y que excluya Firefox.

1. Escriba un nombre descriptivo para la audiencia combinada y haga clic en **[!UICONTROL Guardar]**.

## Create a combined audience for use in metric targeting {#section_A42E795AFCBD4575809C5942039910F0}

Puede crear una audiencia combinada ad-hoc en la página [!UICONTROL Objetivos y configuración] de la actividad para usarla en la segmentación de métrica. Por ejemplo, para crear una segmentación según la conversión empleando una audiencia combinada:

1. Al editar o crear una [actividad](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Objetivos y configuración]**, seleccione **[!UICONTROL Conversión]** para la métrica de éxito y, luego, seleccione **[!UICONTROL Mbox visto]** como la acción.
1. Elija el mbox que quiera en el campo **[!UICONTROL Buscar mbox].**

   ![](assets/combine_multiple_audiences4.png)

1. Haga clic en el icono del engranaje y luego en **[!UICONTROL Añadir destino de la audiencia]**.
1. Haga clic en el vínculo **[!UICONTROL Agregar condición de Público/Objetivo]** para mostrar el cuadro de diálogo [!UICONTROL Elegir audiencia].

   ![](assets/combine_multiple_audiences5.png)

1. Realice el [paso 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.

## Crear una audiencia combinada para usarla en los informes {#section_4682D342EFBB43C38E54B99B3A1E14CD}

Puede crear una audiencia combinada ad-hoc en la página [!UICONTROL Objetivos y configuración] de la actividad para usarla en los informes.

1. Al editar o crear una  [actividad](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Objetivos y configuración]** haga clic en el icono **[!UICONTROL Añadir audiencia]** de [!UICONTROL Audiencias para los informes] para mostrar la página [!UICONTROL Elegir audiencia].

   ![](assets/combine_multiple_audiences6.png)

1. Realice el [paso 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.

## Create a combined audience while editing an activity {#section_364A12CE96E04B61B7C18113AA586C2C}

Cuando edita una actividad existente, puede crear una audiencia combinada ad-hoc.

1. En la página [!UICONTROL Actividades], pase el ratón sobre la actividad que quiera y haga clic en el icono **[!UICONTROL Editar].**

   O

   Haga clic en la actividad para abrirla y luego haga clic en **[!UICONTROL Editar actividad]**.

1. Click the **[!UICONTROL Configure]** &gt; **[!UICONTROL Audiences]** &gt; **[!UICONTROL Multiple Audiences]**.

   ![Configurar &gt; Audiencias &gt; Varias audiencias](/help/c-target/assets/combine_multiple_audiences7.png)

1. Haga clic en el icono de más opciones (tres puntos verticales), junto a la audiencia actual de la actividad y luego haga clic en **[!UICONTROL Cambiar audiencia]**.

   ![Cambiar audiencia](/help/c-target/assets/combine_multiple_audiences8.png)

1. Realice el [paso 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.