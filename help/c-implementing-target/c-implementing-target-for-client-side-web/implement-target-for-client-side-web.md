---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: Información sobre la implementación de Adobe Target para la Web del cliente mediante at.js.
title: Implementación de Adobe Target para la web del lado del cliente
feature: at.js
translation-type: tm+mt
source-git-commit: bffda8c3461998767a002d66fd9340252237ae5d
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 20%

---


# Información general: implementación de Target para la web del lado del cliente

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, se puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), para crear experiencias de actividad y personalización.

Para implementar [!DNL Adobe Target] en el lado del cliente, debe utilizar una de las siguientes bibliotecas de JavaScript:

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Biblioteca JavaScript de destinatario at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

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
