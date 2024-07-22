---
keywords: audiencia;reglas de audiencia;combinar audiencias;combinación de audiencias;exclusión;añadir exclusión;excluir;audiencia específica
description: Aprenda a combinar varias audiencias (incluidas las de Adobe Experience Cloud y  [!DNL Target] audiencias) sobre la marcha para crear audiencias específicas.
title: ¿Puedo combinar varias audiencias para crear una nueva audiencia?
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 38%

---

# Combinación de varias audiencias

Combine varias audiencias (incluidas las audiencias [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform] y [!DNL Target]) sobre la marcha para crear audiencias específicas. También puede crear reglas de exclusión y excluir audiencias de una regla.

>[!NOTE]
>
>El origen de [!DNL Adobe Experience Platform] está disponible para todos los clientes de [!DNL Target] que utilizan el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=en){target=_blank}. Las audiencias disponibles de [!DNL Adobe Experience Platform] se pueden usar tal cual o combinadas con audiencias existentes, como se explica en este tema.
>
>Para obtener más información, consulte [Usar audiencias de Adobe Experience Platform](/help/main/c-target/c-audiences/audiences.md#aep).

Imagine que tiene las audiencias “Visitantes nuevos” y “Usuarios de Chrome”. Para una actividad concreta, puede combinar estas audiencias existentes para dirigirse a los visitantes nuevos que utilicen navegadores Chrome. En lugar de crear una tercera audiencia y almacenarla en la biblioteca [!UICONTROL Audiences], puede combinar estas dos audiencias durante la creación de la actividad o mientras edita una actividad existente.

Otro ejemplo: puede dirigirse a todos los clientes fieles. Por ejemplo, puede incluir una audiencia [!DNL Audience Manager] específica para el estado de fidelidad y combinarla con una audiencia [!DNL Target] compuesta por personas que se registraron en el programa de fidelidad durante la sesión actual. Combinar estas dos audiencias es más fácil que crear una tercera audiencia permanente.

Puede combinar hasta 20 audiencias utilizando los operadores AND y OR.

Puede crear y usar audiencias combinadas en varios lugares de la interfaz de usuario de [!DNL Target]..

## Crear una audiencia combinada al crear una actividad {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

Puede crear una audiencia combinada ad-hoc en la página [!UICONTROL Target] de la actividad durante el flujo de trabajo guiado de tres pasos.

1. Al crear una [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Targeting]**, haga clic en los tres puntos verticales y luego haga clic en **[!UICONTROL Replace Audience]**.

   ![Resultado del paso](assets/edit_audience.png)

1. En la página **[!UICONTROL Choose Audience]**, active las casillas que están junto a las audiencias que quiera usar como componentes básicos en la audiencia combinada.

   Utilice la casilla [!UICONTROL Search Audiences] para restringir la búsqueda de la audiencia deseada.

   ![Resultado del paso](assets/combine_multiple_audiences1.png)

1. Haga clic en **[!UICONTROL Combine Multiple Audiences]**, en la esquina superior derecha.

   ![Resultado del paso](assets/combine_multiple_audiences2.png)

1. (Condicional) Edite la nueva audiencia combinada si lo desea.

   El cuadro de diálogo [!UICONTROL Edit Audience] le permite arrastrar y soltar bloques de creación de audiencias adicionales del lado izquierdo en la nueva audiencia combinada. También puede añadir reglas de exclusión y excluir audiencias.

   1. Utilice la funcionalidad de arrastrar y soltar para agregar audiencias dentro de una sección existente como un bloque de creación de nivel 2.

      Supongamos que, en el ejemplo anterior, queremos incluir a los usuarios de Safari en la audiencia combinada. Busque y arrastre la audiencia “Explorador Safari” al cuadro “Explorador Firefox” de la derecha, como se ve a continuación:

      ![combinar_múltiples_audiencias3 imagen](assets/combine_multiple_audiences3.png)

      Observe que el operador que separa las dos audiencias de tipo de navegador es “Y”. Seleccione la lista desplegable [!UICONTROL And] y elija el valor &quot;O&quot; para crear una audiencia combinada nueva para los visitantes nuevos que utilizan Firefox o Safari. Tenga cuidado de evitar crear reglas que excluyen todos los miembros potenciales de la audiencia. Por ejemplo, no es posible visitar una página con los navegadores Firefox y Safari simultáneamente.

      >[!NOTE]
      >
      >El operador Y u O (AND u OR) debe ser el mismo durante la combinación de audiencias. No puede combinar distintos operadores.

   1. Para agregar una exclusión a una regla, haga clic en **[!UICONTROL Exclude]**.

      ![combinar_múltiples_audiencias3a imagen](assets/combine_multiple_audiences3a.png)

      Arrastre y suelte una audiencia.

      Por ejemplo, para excluir de los visitantes nuevos a los de Estados Unidos, puede arrastrar la audiencia de Mercado: Estados Unidos al cuadro.

      Esta audiencia combinada incluye a todos los visitantes nuevos que llegan a su sitio usando Safari o Firefox (excepto a los de San Francisco).

   1. Para excluir una audiencia de una regla, haga clic en **[!UICONTROL Exclusion]** > **[!UICONTROL Exclude this Audience.]**.

      Por ejemplo, puede crear una audiencia combinada que incluya a todos los visitantes nuevos que lleguen a su sitio excluyendo a los que lo hagan por medio de Firefox. Excluir a los visitantes que usan Firefox es más fácil y rápido que crear una audiencia combinada que incluya explícitamente varios navegadores (Safari, Chrome e Internet Explorer) y que excluya Firefox.

1. Proporcione un nombre descriptivo para la audiencia combinada y luego haga clic en **[!UICONTROL Done]**.

## Crear una audiencia combinada para usarla en la segmentación de métricas {#section_A42E795AFCBD4575809C5942039910F0}

Puede crear una audiencia combinada ad-hoc en la página [!UICONTROL Goals & Settings] de la actividad para usarla en la segmentación de métricas. Por ejemplo, para crear una segmentación según la conversión empleando una audiencia combinada:

1. Al editar o crear una [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Goals & Settings]**, seleccione **[!UICONTROL Conversion]** para la métrica de éxito y, a continuación, seleccione **[!UICONTROL Viewed an Mbox]** como acción.
1. Seleccione el mbox que desee en el campo **[!UICONTROL Search mbox]**.

   ![combinar_múltiples_audiencias4 imagen](assets/combine_multiple_audiences4.png)

1. Haga clic en el icono de engranaje y luego en **[!UICONTROL Add Audience Targeting]**.
1. Haga clic en **[!UICONTROL Add Audience/Targeting Condition]** para mostrar el cuadro de diálogo [!UICONTROL Choose Audience].

   ![imagen combine_multiple_audiences5](assets/combine_multiple_audiences5.png)

1. Realice el [paso 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.

## Crear una audiencia combinada para usarla en los informes {#section_4682D342EFBB43C38E54B99B3A1E14CD}

Puede crear una audiencia combinada ad-hoc en la página [!UICONTROL Goals & Settings] de la actividad para usarla en los informes.

1. Mientras edita o crea una [actividad](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), en la página **[!UICONTROL Goals & Settings]**, haga clic en el icono **[!UICONTROL Add Audience]** debajo de [!UICONTROL Audiences for Reporting] para mostrar la página [!UICONTROL Choose Audience].

   ![combinar_múltiples_audiencias6 imagen](assets/combine_multiple_audiences6.png)

1. Realice el [paso 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.

## Crear una audiencia combinada al editar una actividad {#section_364A12CE96E04B61B7C18113AA586C2C}

Cuando edita una actividad existente, puede crear una audiencia combinada ad-hoc.

1. En la página [!UICONTROL Activities], pase el ratón sobre la actividad que quiera y luego haga clic en el icono **[!UICONTROL Edit]**.

   O

   Haga clic en la actividad para abrirla y luego haga clic en **[!UICONTROL Edit Activity]**.

1. Haga clic en **[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**.

   ![Configurar > Audiencias > Varias audiencias](assets/combine_multiple_audiences7.png)

1. Haga clic en el icono de más opciones (tres puntos verticales) junto a la audiencia actual de la actividad y, a continuación, haga clic en **[!UICONTROL Change Audience]**.

   ![Cambiar audiencia](assets/combine_multiple_audiences8.png)

1. Realice el [paso 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la sección “Crear una audiencia combinada al crear una actividad” para crear una audiencia combinada.
