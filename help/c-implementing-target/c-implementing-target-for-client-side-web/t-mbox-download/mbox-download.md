---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: Si quiere usar Target Standard o Target Premium, añada una línea de código para llamar a mbox.js.
title: Implementación de mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 55%

---


# Implementación de mbox.js{#mbox-js-implementation}

Si quiere usar Target Standard o Target Premium, añada una línea de código para llamar a mbox.js.

Puede usar cualquiera de estas dos referencias de biblioteca: [!DNL mbox.js] o [!DNL at.js]. [Ventajas de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) explica las diferencias entre las dos bibliotecas.

>[!NOTE]
>
>**Fin de vida útil** de mbox.js: El 18 de enero de 2021, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 18 de enero de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan actividades de Destinatario ejecutándose al proporcionar contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
>
>Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
>
>Al trasladar a todos los clientes a at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta de la asistencia que espera de Adobe.

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