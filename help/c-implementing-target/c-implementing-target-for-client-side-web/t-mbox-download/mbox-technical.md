---
keywords: implementación;mbox.js;biblioteca de manipulación de dom;target.js;compositor de experiencias visuales;visual experience composer;iframe;sitios angulares;aplicaciones de una sola página;app de una sola página;SPA
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Qué hace la biblioteca mbox.js [!DNL Target] ?
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 78%

---

# Qué hace mbox.js

Información útil para el personal técnico sobre el proceso de implementación de mbox.js y cómo podría afectar a su sitio.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Manipulación de DOM {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] controla la biblioteca de manipulación de DOM usada por Standard. Para mostrar el contenido de la página, [!DNL target.js] hace referencia a [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] habilita los selectores de elementos HTML. Al contrario que [!DNL sizzle.js], solo se usa JavaScript nativo. No se requiere jQuery.

Además, se utiliza el siguiente fragmento de código para sondear el DOM:

 
`https://github.com/dperini/ContentLoaded`

## Target.js y el Compositor de experiencias visuales {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

Al usar el [!UICONTROL Compositor de experiencias visuales] para configurar una experiencia en una actividad, la página web se abrirá en un iFrame. Una vez cargado el iFrame, Standard realiza una llamada API `postMessage` de HTML5. [!DNL Target.js] detecta las llamadas `postMessage` e incluye las siguientes bibliotecas de JavaScript en el sitio web:

* Para la generación de miniaturas: [!DNL https://html2canvas.hertzen.com/]
* Para la consulta entre dominios: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], se usan para enviar mensajes entre los iFrames. Estas secuencias permiten a Adobe enviar datos entre las páginas.

## Consideraciones para sitios angulares y aplicaciones de una sola página   {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Si va a implementar Target en un sitio angular o en una aplicación de una sola página (SPA), tiene que usar la biblioteca at.js en lugar de mbox.js.
