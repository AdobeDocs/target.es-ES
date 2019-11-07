---
keywords: mbox global;Target Classic;usar mbox global desde Target Classic
description: De manera predeterminada, Target Standard crea un mbox global, denominado target-global-mbox, que se utiliza para ejecutar actividades creadas en Target Standard. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de Target Standard.
title: Uso de un mbox global desde una implementación heredada
subtopic: Primeros pasos
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Uso de un mbox global desde una implementación heredada{#use-a-global-mbox-from-a-legacy-implementation}

De manera predeterminada, Target Standard crea un mbox global, denominado target-global-mbox, que se utiliza para ejecutar actividades creadas en Target Standard. Sin embargo, si ya ha creado un mbox global en sus páginas para implementaciones heredadas, puede usarlo para sus actividades de Target Standard.

>[!NOTE]
>
>Solo se permite tener un mbox global por cuenta.

Para usar un mbox global existente tanto para [!DNL Target Standard] como para su implementación heredada, es necesario configurar algunos parámetros.

1. Vaya a [!DNL Target Standard] y haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]**.

   De manera predeterminada, la opción [!UICONTROL Crear automáticamente mbox global] está desactivada y el nombre del mbox global personalizado es `target-global-mbox`.
1. Si desea usar un mbox existente, deshabilite [!UICONTROL Crear automáticamente mbox global] y especifique el nombre de un mbox global que ya esté creado en el campo [!UICONTROL Mbox global personalizado.]

   La lista desplegable [!UICONTROL Mbox global personalizado] reúne todos los mboxes de la cuenta. Si desea utilizar un mbox nuevo, que aún no ha sido creado, créelo en Target Classic.
1. Haga clic en **[!UICONTROL Guardar]**.

   Se actualiza la configuración de mbox.js de la cuenta.
1. Descargue el nuevo archivo mbox.js y haga referencia a él en su sitio.

   Cuando haya cargado el sitio de producción con el nuevo archivo mbox.js, podrá configurar las preferencias.
1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Preferencias]**.
1. En el campo [!UICONTROL Mbox global personalizado], especifique el nombre del mbox global que seleccionó en la página Implementación.
1. Haga clic en **[!UICONTROL Enviar]**.

   Se actualizarán todas las actividades existentes para utilizar el mbox global especificado, incluidas las actividades que haya creado e implementado hasta ese momento.
   **Solución de problemas de implementación de Mbox Global** *Razones por las que no está cargando mbox global, o por las que hay una latencia en la carga del mbox global cuando se carga la página*

Asegúrese de que la referencia de mbox.js sea la primera llamada JavaScript en la página. Puede consultar otras soluciones a este problema en   [Implementación de mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
