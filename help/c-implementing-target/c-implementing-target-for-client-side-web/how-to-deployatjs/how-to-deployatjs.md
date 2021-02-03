---
keywords: implementar;at.js;biblioteca javascript
description: Información sobre cómo implementar la biblioteca de JavaScript de Adobe Target, at.js, mediante Adobe Launch, sin un administrador de etiquetas, o mediante Dynamic Tag Management (DTM) de Adobe.
title: Cómo implementar at.js
feature: Implement Server-side
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 56%

---


# Cómo implementar at.js

Información sobre cómo implementar la biblioteca de JavaScript de Adobe Target, at.js, mediante Adobe Launch, sin un administrador de etiquetas, o mediante Dynamic Tag Management (DTM) de Adobe.

Puede implementar at.js con los métodos siguientes:

* **[Implementar Target utilizando Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
* **[Implementar Target sin un Administrador de etiquetas](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: Puede implementar Target sin utilizar un administrador de etiquetas (Adobe Launch o Dynamic Tag Management).
* **[Implementar Destinatario mediante la administración](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)** dinámica de etiquetas: Puede implementar Destinatario mediante la administración dinámica de etiquetas de Adobe (DTM), el administrador de etiquetas heredado de Adobe. Adobe Launch es el método preferido y actualizado para implementar Target y la biblioteca de at.js. Para nuevas implementaciones de Target, use Launch.
* **Implementar Destinatario con un administrador** de etiquetas de terceros:  [El ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) lanzamiento de Adobe es el método preferido para implementar el Destinatario; sin embargo, también puede implementar Destinatario mediante un administrador de etiquetas de terceros, como por ejemplo Tealium, Ensightly, Google Tag, etc. Para obtener una lista de los beneficios de utilizar Launch, consulte [Ventajas de implementar at.js con la extensión de lanzamiento de Destinatario](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Sin embargo, si sabe cómo implementar Destinatario sin un administrador de etiquetas, puede implementarlo fácilmente con un administrador de etiquetas de terceros en lugar de preprogramar at.js en el código del sitio.

   Estos son dos temas relevantes que le ayudarán a implementar el Destinatario con un administrador de etiquetas de terceros:

   * [Antes de la implementación](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implementación de Target sin un administrador de etiquetas](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Asegúrese de comprobar la documentación de su administrador de etiquetas de terceros para obtener más información.

Para implementar Target al utilizar aplicaciones de una sola página (SPA), consulte [Implementación de aplicación de una sola página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).