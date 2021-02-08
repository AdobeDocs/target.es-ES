---
keywords: mbox global;Target Classic;usar mbox global desde Target Classic
description: Aprenda a utilizar un mbox global heredado para sus actividades de Adobe Target si ya ha creado un mbox global en sus páginas para sus implementaciones heredadas.
title: ¿Puedo usar un mbox global de una implementación heredada?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---


# Usar un mbox global de una implementación heredada

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
