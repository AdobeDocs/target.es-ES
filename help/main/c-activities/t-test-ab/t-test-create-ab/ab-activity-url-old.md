---
keywords: url de actividad;url;url diferente
description: Obtenga información sobre cómo especificar la dirección URL de actividad que determina la página que se usa en la prueba y que se abre cuando se diseña la prueba con  [!DNL Adobe Target].
title: ¿Qué es la URL de actividad en una actividad A/B?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 44%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña con Adobe Target.

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] coinciden.

## Especifique una dirección URL diferente

De manera predeterminada, [!UICONTROL Visual Experience Composer] abre la página especificada en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. Para mostrar una página diferente después de que se abra [!UICONTROL Visual Experience Composer], en la página **[!UICONTROL Experiences]**, haga clic en el icono de engranaje **[!UICONTROL Configure]** y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

1. Especifique la dirección URL en el campo **[!UICONTROL URL]**.

   ![Cuadro de diálogo Entrega de páginas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. (Condicional) Haga clic en **[!UICONTROL Add Template Rule]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox

   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Save]** cuando haya finalizado.

Si introduce una dirección URL de un sitio que no incluye el código estándar [!DNL Target] de JavaScript, no podrá seleccionar elementos de la página.

De manera predeterminada, [!UICONTROL Visual Experience Composer] no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Render using JavaScript]** si desea poder modificar esos elementos usando [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.
