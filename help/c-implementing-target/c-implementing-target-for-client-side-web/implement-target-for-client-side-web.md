---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: Información sobre la implementación de Adobe Target para la web del lado del cliente.
title: Implementación de Adobe Target para la web del lado del cliente
feature: client-side
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 66%

---


# Información general: implementación de Target para la web del lado del cliente

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, se puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), para crear experiencias de actividad y personalización.

Para implementar [!DNL Adobe Target] en el lado del cliente, debe utilizar la biblioteca [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) o mbox.js.

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes deben implementar el [SDK web de AEP](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) o [migrar de mbox.js a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
