---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Para utilizar Adobe Target Standard o Destinatario Premium, agregue una línea de código para llamar a mbox.js.
title: Implementación de mbox.js
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 52%

---


# Implementación de mbox.js

Para utilizar [!DNL Adobe Target Standard] o [!DNL Target Premium], agregue una línea de código para llamar a mbox.js.

Puede utilizar cualquiera de las dos referencias de biblioteca: el [!DNL Adobe Experience Platform Web SDK] o [!DNL at.js]. [Las ventajas de at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexplica las diferencias entre las bibliotecas mbox.js y at.js.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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