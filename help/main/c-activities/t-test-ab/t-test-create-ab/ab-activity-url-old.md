---
keywords: actividad url; URL; URL diferente
description: Aprenda a especificar el URL de actividad que determina el Página que se utiliza en el prueba y que se abre cuando el prueba se diseña utilizando [!DNL Adobe Target].
title: ¿Cuál es el URL de actividad en una actividad A/B?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 44%

---

# Dirección URL de actividad

El URL actividad determina el Página que se utiliza en el prueba y que se abre cuando el prueba se diseña con Adobe Target.

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba el URL completo (incluido `https://`) y haga clic en **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] ambos coinciden.

## Especifique una dirección URL diferente

De forma predeterminada, se [!UICONTROL Visual Experience Composer] abre el Página especificado en [la configuración](/help/main/administrating-target/visual-experience-composer-set-up.md) del Compositor de experiencias visuales. Puede especificar una página diferente durante la creación de la actividad.

1. Para mostrar un Página diferente después de las [!UICONTROL Visual Experience Composer] aperturas, en el **[!UICONTROL Experiences]** Página, haga clic en el icono de **[!UICONTROL Configure]** engranaje y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

1. Especifique el URL en el **[!UICONTROL URL]** campo.

   ![Cuadro de diálogo Entrega de páginas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. (Condicional) Haga clic **[!UICONTROL Add Template Rule]** para agregar más páginas o secciones al actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox

   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic **[!UICONTROL Save]** cuando haya terminado.

Si introduce una dirección URL de un sitio que no incluye el código estándar [!DNL Target] de JavaScript, no podrá seleccionar elementos de la página.

De forma predeterminada, no permite realizar cambios en los elementos que contengan JavaScript, como los [!UICONTROL Visual Experience Composer] titulares rotativos. Puede desactivarla **[!UICONTROL Render using JavaScript]** si desea poder modificar estos elementos mediante el [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.
