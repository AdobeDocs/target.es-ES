---
description: La URL de actividad determina la página que se utiliza en la actividad de segmentación de experiencias y que se abre en el Compositor de experiencias visuales (VEC) o Compositor de experiencias basadas en formularios cuando se diseña la actividad.
keywords: Segmentación
seo-description: La URL de actividad determina la página que se utiliza en la actividad de segmentación de experiencias y que se abre en el Compositor de experiencias visuales de Adobe Target (VEC) o Compositor de experiencias basadas en formularios cuando se diseña la actividad.
seo-title: Dirección URL de actividad
solution: Target
title: Dirección URL de actividad
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL de actividad{#activity-url}

La URL de actividad determina la página que se utiliza en la actividad de segmentación de experiencias (XT) y que se abre en el Compositor de experiencias visuales (VEC) o Compositor de experiencias basadas en formularios cuando se diseña la actividad.

1. When prompted while [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), specify the activity URL. Escriba la URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Puede especificar una página diferente durante la creación de la actividad.
   >
   >Si especifica una URL para un sitio que no incluye el código JavaScript de Target Standard, no podrá seleccionar elementos de página.

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![Cuadro de diálogo Entrega de página](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox
   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Guardar]cuando haya finalizado.**