---
keywords: parpadeo;at.js;implementación;asincrónicamente;asincrónico;sincrónico;sincrónico
description: Descubra cómo at.js y Adobe [!DNL Target] evite el parpadeo (el contenido predeterminado aparece momentáneamente antes de ser reemplazado por contenido de actividad) durante la carga de la página o la aplicación.
title: ¿Cómo gestiona at.js el parpadeo?
feature: at.js
role: Developer
exl-id: f6c26973-e046-42ed-91db-95c8a4210a9d
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 60%

---

# Cómo gestiona at.js el parpadeo

Información sobre cómo la biblioteca de JavaScript de at.js de Target evita el parpadeo mientras se carga una página o una aplicación.

El parpadeo tiene lugar cuando se muestra momentáneamente el contenido predeterminado a los visitantes antes de que lo reemplace el contenido de la actividad. El parpadeo no es deseable porque confunde a los visitantes.

## Uso de un mbox global creado automáticamente {#section_C502170D551C4F52AAFD8E82C41BB63A}

Si activa la variable [Crear automáticamente mbox global](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/global-mbox-overview/){target=_blank} al configurar at.js, at.js gestiona el parpadeo cambiando la configuración de opacidad mientras la página se carga. Cuando at.js se carga, cambia la configuración de opacidad de la variable `<body>` elemento a &quot;0&quot;, lo que hace que la página sea invisible inicialmente para los visitantes. Después de recibir una respuesta de Target (o si se detecta un error en la solicitud de Target), at.js restablece la opacidad a “1”. Esto garantiza que el visitante solo vea la página después de haberse aplicado el contenido de sus actividades.

Si activa el ajuste al configurar at.js, at.js establece la opacidad del estilo HTML BODY en 0. Tras recibir la respuesta de Target, at.js vuelve a establecer la opacidad de HTML BODY en 1.

La opacidad establecida en 0 mantiene el contenido de la página oculto para evitar el parpadeo, pero el navegador sigue procesando la página y carga todos los activos necesarios, como CSS, imágenes, etc.

Si la opacidad 0 no funciona en su implementación, también puede gestionar el parpadeo personalizando `bodyHiddenStyle` y estableciéndolo en `body {visibility:hidden !important}`. Puede utilizar cualquiera de los valores body `{opacity:0 !important}` o `body {visibility:hidden !important}`, lo que funcione mejor para sus circunstancias específicas.

La ilustración siguiente muestra las llamadas a Ocultar cuerpo y Mostrar cuerpo en at.js 1.*x* y at.js 2.x.

**at.js 2.x**

![Flujo de Target: Solicitud de carga de página de at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***  

![](assets/target-flow2.png)

Para obtener más información sobre la anulación de `bodyHiddenStyle`, consulte [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

## Administración del parpadeo al cargar at.js de forma asíncrona

Cargar at.js de forma asíncrona es un modo excelente de evitar el bloqueo de presentación por parte del navegador; sin embargo, esta técnica puede producir parpadeos en la página web.

Puede evitar el parpadeo utilizando un fragmento de ocultamiento previo que será visible después de que [!DNL Target] personalice los elementos HTML relevantes. 

at.js se puede cargar de forma asíncrona, ya sea directamente incrustado en la página o a través de un administrador de etiquetas (por ejemplo [!DNL Adobe Experience Platform Launch]).

Si at.js está incrustado en la página, se debe agregar el fragmento antes de cargar at.js. Si carga at.js a través de un administrador de etiquetas, que también se carga asincrónicamente, debe añadir el fragmento antes de cargar el administrador de etiquetas. Si el administrador de etiquetas se carga sincrónicamente, el script podría incluirse en el administrador de etiquetas antes de at.js.

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

## Administrar parpadeo en at.js 2.x para triggerView()

La preocultación de DOM se aplica solo a la carga inicial de la página. Por SPA, el DOM se actualiza cuando `triggerView()` se llama. Puede haber un breve parpadeo entre el momento en que el SPA procesa el contenido en las actualizaciones DOM y at.js [!DNL Target] ofertas.  Para minimizar el parpadeo, si utiliza `triggerView` para modificar el contenido de carga de la página, se debe llamar a &quot;triggerView&quot; en cuanto se represente la página.

## Administrar parpadeo con getOffer() y applyOffer()

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
