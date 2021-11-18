---
keywords: implementar;implementación;at.js;sdk web de adobe experience platform;sdk web de aep
description: Obtenga información sobre cómo implementar el Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] Biblioteca JavaScript at.js.
title: ¿Cómo puedo implementar? [!DNL Target] para la web del lado del cliente
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 47%

---

# Información general: implementar [!DNL Target] para la web del lado del cliente

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, se puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), para crear experiencias de actividad y personalización.

Para implementar [!DNL Adobe Target] del lado del cliente, debe utilizar una de las siguientes bibliotecas de JavaScript:

* [SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Biblioteca JavaScript de at.js de Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fin de vida útil de**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado. Adobe recomienda que todos los clientes migren a la versión más reciente del [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier posible problema con sus sitios.
>
>* **SDK web de Adobe Experience Platform**: La variable [!UICONTROL SDK web de Adobe Experience Platform] le permite interactuar con los distintos servicios de la sección [!DNL Experience Cloud] (incluido [!DNL Target]) a través de Adobe Experience Edge Network. Si decide migrar a la variable [!DNL Adobe Experience Platform Web SDK], consulte [¿Qué es el SDK web de Adobe Experience Platform?](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) en el *Guía del SDK web*.
>
>* **at.js**: La biblioteca JavaScript at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación en aplicaciones de una sola página. Si decide migrar a at.js, consulte [Cómo funciona at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skills Builder: Chat del desarrollador, migrar mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).


