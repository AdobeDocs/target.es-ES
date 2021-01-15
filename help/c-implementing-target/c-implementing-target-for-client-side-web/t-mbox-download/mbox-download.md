---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Para utilizar Adobe Target Standard o Destinatario Premium, agregue una línea de código para llamar a mbox.js.
title: Implementación de mbox.js
feature: null
translation-type: tm+mt
source-git-commit: a85a5c10c31fb0d7eb00c21ff03b2012d044de45
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 32%

---


# Implementación de mbox.js

Para utilizar [!DNL Adobe Target Standard] o [!DNL Target Premium], agregue una línea de código para llamar a mbox.js.

Puede utilizar cualquiera de las dos referencias de biblioteca: el [!DNL Adobe Experience Platform Web SDK] o [!DNL at.js]. [Las ventajas de at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexplica las diferencias entre las bibliotecas mbox.js y at.js.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado. Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios.
>
>* **Adobe Experience Platform Web SDK**: El  [!UICONTROL Adobe Experience Platform Web ] SDK le permite interactuar con los distintos servicios de la red  [!DNL Experience Cloud] (incluido  [!DNL Target]) a través de Adobe Experience Edge Network. Si decide migrar a [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) en la *Guía del SDK web*.
   >
   >
* **at.js**: La biblioteca JavaScript de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página. Si decide migrar a at.js, consulte [Cómo funciona At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skill Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Aunque actualmente se admite mbox.js (hasta el 31 de marzo de 2021), no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. Al trasladar a todos los clientes al [!UICONTROL SDK web de Adobe Experience Platform] o at.js, nuestros ingenieros y personal de soporte técnico podrán proporcionarle nuevas funcionalidades y oferta del soporte que espera de Adobe.

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