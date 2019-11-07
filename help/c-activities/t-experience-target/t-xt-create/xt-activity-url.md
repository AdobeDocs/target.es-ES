---
keywords: Segmentación
description: La URL de actividad determina la página que se utiliza en la actividad de segmentación de experiencias y que se abre en el Compositor de experiencias visuales (VEC) o Compositor de experiencias basadas en formularios de Adobe Target cuando se diseña la actividad.
title: Dirección URL de actividad
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# URL de actividad{#activity-url}

La URL de actividad determina la página que se utiliza en la actividad de segmentación de experiencias (XT) y que se abre en el Compositor de experiencias visuales (VEC) o Compositor de experiencias basadas en formularios cuando se diseña la actividad.

1. Cuando se le pida, al [crear una actividad XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique la URL de la actividad. Escriba la URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear actividad]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `https://www.adobe.com`] como [!DNL `http://www.adobe.com`] coinciden.
   >
   >De manera predeterminada, el VEC o el compositor de experiencias basadas en formularios abre la página que indicada en las [Preferencias de cuenta](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Puede especificar una página diferente durante la creación de la actividad.
   >
   >Si indica una dirección URL de un sitio que no incluye el código de JavaScript de Target Standard, no podrá seleccionar elementos de página.

1. (Condicional) Para mostrar una página diferente después de que se abra el VEC, haga clic en **[!UICONTROL Configurar]**, seleccione **[!UICONTROL Entrega de páginas]** y especifique la URL en el campo [!UICONTROL URL].

   ![Cuadro de diálogo Entrega de páginas](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

1. (Condicional) Haga clic en **[!UICONTROL Agregar regla de plantilla]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox
   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Guardar]cuando haya finalizado.**