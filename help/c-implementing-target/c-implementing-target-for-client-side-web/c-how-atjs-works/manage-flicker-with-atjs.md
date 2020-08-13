---
keywords: flicker;at.js;implementation;asynchronously;asynchronous;synchronously;synchronous
description: Información sobre cómo la biblioteca de JavaScript de at.js de Adobe Target evita el parpadeo mientras se carga una página o una aplicación.
title: Gestión de parpadeos de Adobe Target at.js
feature: client-side
topic: Standard
uuid: 65f67c4a-a931-4e0d-80d9-29ab67b62573
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 83%

---


# Cómo gestiona at.js el parpadeo{#how-at-js-manages-flicker}

Información sobre cómo la biblioteca de JavaScript de at.js de Target evita el parpadeo mientras se carga una página o una aplicación.

El parpadeo tiene lugar cuando se muestra momentáneamente el contenido predeterminado a los visitantes antes de que lo reemplace el contenido de la actividad. El parpadeo no es deseable porque confunde a los visitantes.

## Uso de un mbox global creado automáticamente {#section_C502170D551C4F52AAFD8E82C41BB63A}

Si habilita la función [mbox global creado automáticamente](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) al configurar at.js, éste gestiona el parpadeo cambiando al configuración de opacidad mientras la página carga. Cuando se carga at.js, cambia la configuración de opacidad del <body> elemento a “0”, para que la página sea invisible inicialmente para los visitantes. Después de recibir una respuesta de Target (o si se detecta un error en la solicitud de Target), at.js restablece la opacidad a “1”. Esto garantiza que el visitante solo vea la página después de haberse aplicado el contenido de sus actividades.

Si activa el ajuste al configurar at.js, at.js establece la opacidad del estilo HTML BODY en 0. Tras recibir la respuesta de Target, at.js vuelve a establecer la opacidad de HTML BODY en 1.

La opacidad establecida en 0 mantiene el contenido de la página oculto para evitar el parpadeo, pero el navegador sigue procesando la página y carga todos los activos necesarios, como CSS, imágenes, etc.

Si la opacidad 0 no funciona en su implementación, también puede gestionar el parpadeo personalizando `bodyHiddenStyle` y estableciéndolo en `body {visibility:hidden !important}`. De los valores `{opacity:0 !important` body o `body {visibility:hidden !important}`, puede utilizar el que funcione mejor para sus circunstancias específicas.

La ilustración siguiente muestra las llamadas a Ocultar cuerpo y Mostrar cuerpo en at.js 1.*x* y at.js 2.x.

**at.js 2.x**

![Flujo de Target: Solicitud de carga de página de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

Para obtener más información sobre la anulación de `bodyHiddenStyle`, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Administración del parpadeo al cargar at.js de forma asíncrona

Cargar at.js de forma asíncrona es un modo excelente de evitar el bloqueo de presentación por parte del navegador; sin embargo, esta técnica puede producir parpadeos en la página web.

Puede evitar el parpadeo utilizando un fragmento de ocultamiento previo que será visible después de que [!DNL Target] personalice los elementos HTML relevantes. 

at.js se puede cargar asincrónicamente, ya sea directamente incrustado en la página o a través de un administrador de etiquetas (Inicio de Adobe, Administrador dinámico de etiquetas (DTM), etc.).

Si at.js está incrustado en la página, se debe agregar el fragmento antes de cargar at.js. Si carga at.js a través de un administrador de etiquetas, que también se carga asincrónicamente, debe agregar el fragmento antes de cargar el administrador de etiquetas. Si el administrador de etiquetas se carga sincrónicamente, la secuencia de comandos puede incluirse en el administrador de etiquetas antes de at.js.

El fragmento de código de ocultamiento previo es como sigue:

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

De forma predeterminada, el fragmento oculta previamente el BODY de HTML completo. En algunos casos solo se pueden ocultar previamente determinados elementos HTML y no la página completa. Se puede conseguir personalizando el parámetro de estilo. Se puede reemplazar con algo que oculte previamente únicamente regiones particulares de la página.

Imagine que tiene dos regiones identificadas por los ID container-1 y container-2; el estilo se puede reemplazar de este modo:

```
#container-1, #container-2 {opacity: 0 !important}
```

En lugar del predeterminado:

```
body {opacity: 0 !important}
```

## Administrar parpadeo en at.js 2.x para desencadenadorView()

Al utilizar `triggerView()` para mostrar contenido dirigido en su SPA, la administración de parpadeo se proporciona fuera del cuadro. Esto significa que no es necesario agregar manualmente la lógica de ocultamiento previo. En su lugar, at.js 2.x oculta previamente la ubicación donde debe mostrarse la vista antes de aplicar el contenido objetivo.

## Gestionar el parpadeo con getOffer() y applyOffer()

Dado que tanto `getOffer()` como `applyOffer()` son API de bajo nivel, no hay control integrado de parpadeo. Puede transferir un selector o un elemento HTML como opción para `applyOffer()`, en este caso `applyOffer()` añade el contenido de la actividad a este elemento concreto; sin embargo, debe asegurarse de que el elemento esté oculto previamente de forma correcta antes de invocar a `getOffer()` y `applyOffer()`.

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## Uso de un mbox regional con mboxCreate() en at.js 1.x (no admitido en at.js 2.x)

Si utiliza una implementación de mbox regional, puede usar `mboxCreate()` con su página aprovisionada similar al siguiente código de ejemplo:

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

Si sus páginas están aprovisionadas correctamente, at.js administra el parpadeo cambiando la propiedad “visibilidad” del CSS del elemento por la clase mboxDefault.