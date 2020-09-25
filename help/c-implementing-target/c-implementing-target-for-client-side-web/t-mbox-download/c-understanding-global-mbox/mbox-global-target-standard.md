---
keywords: global mbox;target classic;use global mbox from target classic
description: De manera predeterminada, Target Standard crea un mbox global, denominado target-global-mbox, que se utiliza para ejecutar actividades creadas en Target Standard. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de Target Standard.
title: Uso de un mbox global desde una implementación heredada
feature: null
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 6922b80c88cbd2947c3bfd0cc9d8409ff5dcdcd0
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# Uso de un mbox global desde una implementación heredada{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de [!DNL Target].

>[!NOTE]
>
>Solo se permite tener un mbox global por cuenta.

Para usar un mbox global existente tanto para [!DNL Target] como para su implementación heredada, es necesario configurar algunos parámetros.

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. Si desea utilizar un mbox que aún no existe, cree el mbox.

1. Haga clic en **[!UICONTROL Guardar]**.

   Se actualiza la configuración de mbox.js de la cuenta.

1. Descargue el nuevo archivo at.js y haga referencia a él en su sitio.

   Se actualizarán todas las actividades existentes para utilizar el mbox global especificado, incluidas las actividades que haya creado e implementado hasta ese momento.

## Solución de problemas de implementación global de mbox

Se pueden usar las siguientes preguntas más frecuentes para solucionar problemas en la implementación global de mbox:

### ¿Por qué no se está cargando el mbox global, o por qué hay una latencia en la carga del mbox global cuando se carga la página?

Asegúrese de que la referencia a at.js sea la primera llamada de JavaScript en la página. Para obtener otras soluciones a este problema, consulte Preguntas [más frecuentes sobre mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)global.
