---
description: Si quiere usar Target Standard o Target Premium, añada una línea de código para llamar a mbox.js.
keywords: Implementación;Mbox;descargar mbox.js;descargar API;API de mbox.js
seo-description: Si quiere usar Target Standard o Target Premium, añada una línea de código para llamar a mbox.js.
seo-title: Implementación de mbox.js
solution: Target
subtopic: Primeros pasos
title: Implementación de mbox.js
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: b45a1a141e9e1d229ed3f92b8124d3edf3bc3042

---


# Implementación de mbox.js{#mbox-js-implementation}

Si quiere usar Target Standard o Target Premium, añada una línea de código para llamar a mbox.js.

Puede usar cualquiera de estas dos referencias de biblioteca: [!DNL mbox.js] o [!DNL at.js]. [En Las bibliotecas de Target JavaScript](../../../c-implementing-target/c-considerations-before-you-implement-target/target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB) se explica la diferencia entre estas dos bibliotecas.

>[!NOTE]
>
>La biblioteca mbox.js se sigue admitiendo, pero sus características ya no se actualizarán. Todos los clientes deberían migrar a at.js. Para obtener más información, consulte [Migrar a at.js desde mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

La única referencia a [!DNL mbox.js] en cada página proporciona las bibliotecas necesarias para todas las actividades. [!DNL mbox.js] llama a [!DNL Target] desde todas las páginas que hacen referencia al archivo [!DNL mbox.js]. Esto permite a [!DNL Target] hacer lo siguiente:

* Entregar actividades de Target
* Rastrear clics
* Rastrear la mayoría de las métricas de éxito

>[!TIP]
>
>Para simplificar la implementación podría hacer referencia a [!DNL mbox.js] en el encabezado global.

No es necesario que mantenga una versión del archivo para cada actividad.

1. Haga referencia a [!DNL mbox.js] en la sección `<head>` de cada página del sitio.

   `<script src="/ *`scripts `*/ *`de directorio`*/mbox.js"></script>`

   El ` *`script de `*/ *`directorio`*` es el directorio donde guardó el archivo [!DNL mbox.js] después de descargarlo.
Si ya tiene mboxes en la página de una implementación heredada, podrá usarlos en la nueva interfaz. El archivo [!DNL mbox.js] actualizado sigue siendo necesario, pero estos mboxes pueden seleccionarse para actividades y modificarse con el [!UICONTROL Compositor de experiencias visuales].