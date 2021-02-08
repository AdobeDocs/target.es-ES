---
keywords: implementación;mbox.js;biblioteca de manipulación de dom;target.js;compositor de experiencias visuales;visual experience composer;iframe;sitios angulares;aplicaciones de una sola página;app de una sola página;SPA
description: Obtenga información sobre la implementación heredada de mbox.js de Adobe Target. Migrar al SDK web de Adobe Experience Platform (AEP Web SDK) o a la versión más reciente de at.js.
title: ¿Qué hace la biblioteca mbox.js de Destinatario?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 73%

---


# Qué hace mbox.js{#what-mbox-js-does}

Información útil para el personal técnico sobre el proceso de implementación de mbox.js y cómo podría afectar a su sitio.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Target Standard requiere un [!DNL mbox.js] versión 58 o posterior. Encontrará las instrucciones para descargar y actualizar [!DNL mbox.js] en [Implementación Mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

Para Target Standard, [!DNL mbox.js] ejecuta otro archivo de JavaScript, [!DNL target.js]. [!DNL Target.js] está alojado por Adobe, quien lo actualiza automáticamente. No es necesario que haga nada para actualizar [!DNL target.js]; los clientes no pueden modificarlo.

[!DNL Target.js] crea un mbox llamado `target-global-mbox` en la sección `<head>` de la página.

[!DNL Target.js] es invocado por [!DNL mbox.js] mediante una línea de código de JavaScript que se añade en el campo [!UICONTROL JavaScript extra] del [!DNL mbox.js]. La única forma de deshabilitar [!DNL target.js] es no incluir esta línea de código, aunque esto también deshabilitará [!DNL Target].

[!DNL Target.js] tiene dos funciones en [!DNL Target]:

* Manipulación de DOM
* Habilitación de elementos visuales del [!UICONTROL Compositor de experiencias visuales]

## Manipulación de DOM {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] controla la biblioteca de manipulación de DOM usada por Standard. Para mostrar el contenido de la página, [!DNL target.js] hace referencia a [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] habilita los selectores de elementos HTML. Al contrario que [!DNL sizzle.js], solo se usa JavaScript nativo. No se requiere jQuery.

Además, se utiliza el siguiente fragmento de código para sondear el DOM:

 
`https://github.com/dperini/ContentLoaded`

## Target.js y el Compositor de experiencias visuales {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

Al usar el [!UICONTROL Compositor de experiencias visuales] para configurar una experiencia en una actividad, la página web se abrirá en un iFrame. Una vez cargado el iFrame, Standard realiza una llamada API `postMessage` de HTML5. [!DNL Target.js] detecta las llamadas `postMessage` e incluye las siguientes bibliotecas de JavaScript en el sitio web:

* Para la generación de miniaturas: [!DNL https://html2canvas.hertzen.com/]
* Para la consulta entre dominios: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], se usan para enviar mensajes entre los iFrames. Estas secuencias permiten a Adobe enviar datos entre las páginas.

## Consideraciones para sitios angulares y aplicaciones de una sola página    {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Si va a implementar Target en un sitio angular o en una aplicación de una sola página (SPA), tiene que usar la biblioteca at.js en lugar de mbox.js.

Para obtener más información, consulte [Implementación at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).
