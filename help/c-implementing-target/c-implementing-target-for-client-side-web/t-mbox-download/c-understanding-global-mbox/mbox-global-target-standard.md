---
keywords: global mbox;target classic;use global mbox from target classic
description: De manera predeterminada, Target Standard crea un mbox global, denominado target-global-mbox, que se utiliza para ejecutar actividades creadas en Target Standard. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de Target Standard.
title: Uso de un mbox global desde una implementación heredada
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# Uso de un mbox global desde una implementación heredada{#use-a-global-mbox-from-a-legacy-implementation}

De forma predeterminada, [!DNL Target] crea un mbox global denominado destinatario-global-mbox, que se utiliza para ejecutar actividades creadas en [!DNL Target]. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de [!DNL Target].

>[!NOTE]
>
>Solo se permite tener un mbox global por cuenta.

Para usar un mbox global existente tanto para [!DNL Target] como para su implementación heredada, es necesario configurar algunos parámetros.

1. Vaya a [!DNL Target] y haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

   De forma predeterminada, **[!UICONTROL Carga de página habilitada (Crear automáticamente mbox global]** está habilitado y el mbox global personalizado se denomina `target-global-mbox`.

1. Si desea utilizar un mbox existente, deshabilite **[!UICONTROL Carga de página habilitada (Crear automáticamente mbox global]** y especifique el nombre de un mbox global creado anteriormente en el campo **[!UICONTROL Mbox global]**.

   La lista desplegable [!UICONTROL Mbox global] lista todos los mboxes de la cuenta. Si desea utilizar un mbox que aún no existe, cree el mbox.

1. Haga clic en **[!UICONTROL Guardar]**.

   Se actualiza la configuración de mbox.js de la cuenta.

1. Descargue el nuevo archivo at.js y haga referencia a él en su sitio.

   Se actualizarán todas las actividades existentes para utilizar el mbox global especificado, incluidas las actividades que haya creado e implementado hasta ese momento.

## Solución de problemas de implementación global de mbox

Se pueden usar las siguientes preguntas más frecuentes para solucionar problemas en la implementación global de mbox:

### ¿Por qué no se está cargando el mbox global, o por qué hay una latencia en la carga del mbox global cuando se carga la página?

Asegúrese de que la referencia a at.js sea la primera llamada de JavaScript en la página. Para obtener otras soluciones a este problema, consulte [Preguntas más frecuentes de mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
