---
description: Información sobre la implementación de Adobe Target para la web del lado del cliente.
title: Implementación de Adobe Target para la web del lado del cliente
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 100%

---


# Información general: implementación de Target para la web del lado del cliente

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, se puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), para crear experiencias de actividad y personalización.

Para implementar [!DNL Adobe Target] del lado del cliente, debe utilizar [la biblioteca at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) o mbox.js.

>[!NOTE]
>
>La biblioteca mbox.js ya no está en desarrollo. Todos los clientes [deben implementar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) o [migrar de mbox.js a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
