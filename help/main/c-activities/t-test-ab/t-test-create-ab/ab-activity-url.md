---
keywords: url de actividad;url;url diferente
description: Descubra cómo establecer [!UICONTROL Activity URL] para definir páginas de prueba y garantizar un diseño de prueba preciso.
title: ¿Qué es la URL de actividad en una actividad A/B?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 32%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la prueba y que se abre cuando esta se diseña con [!DNL Adobe Target].

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] coinciden.

## Especifique una dirección URL diferente

De manera predeterminada, [!UICONTROL Visual Experience Composer] abre la página especificada en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. (Condicional) Para mostrar una página diferente después de que se abra [!UICONTROL Visual Experience Composer], en la página **[!UICONTROL Experiences]**, haga clic en **[!UICONTROL Configure]** en la parte superior de la página y seleccione **[!UICONTROL Page Delivery]**.

1. Especifique la dirección URL en el campo **[!UICONTROL URL]**.

1. (Condicional) Haga clic en **[!UICONTROL Add Rule]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox
   * Personalizado

   Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con Y.

1. Haga clic en **[!UICONTROL Save]** cuando haya finalizado.

   Si escribe una dirección URL de un sitio que no incluye el código JavaScript de [!DNL Target], no podrá seleccionar elementos de página.

   De manera predeterminada, [!UICONTROL Visual Experience Composer] no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Render using JavaScript]** si desea poder modificar esos elementos mediante [!UICONTROL Visual Experience Composer].—>

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.
