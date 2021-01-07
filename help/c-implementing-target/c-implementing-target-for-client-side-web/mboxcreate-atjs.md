---
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
description: Información sobre la función mboxCreate(mbox,params) para la biblioteca JavaScript at.js de Adobe Target.
title: mboxCreate(mbox,params) - at.js 1.x
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

Ejecuta una solicitud y aplica la oferta al DIV más cercano con nombre de clase mboxDefault.

>[!NOTE]
>
>Esta función está disponible para las versiones 1 de at.js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at.js 2.x. Esta función devuelve el contenido predeterminado si se utiliza con at.js 2.x.

Esta función está creada en [!DNL at.js] principalmente para facilitar la transición de [!DNL mbox.js] a [!DNL at.js]. Una alternativa nueva a `mboxCreate()` es `adobe.target.getOffer()`/ `adobe.target.applyOffer()`/ o la directiva Angular.

## Ejemplo

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Notas

`mboxCreate()` ahora usa el extremo “json” en lugar del extremo “standard” y se activa asincrónicamente. Debido a ello:

* [Depuración](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) es algo diferente.
* Evite el código de oferta que requiere llamadas sincrónicas de bloqueo.

   Por ejemplo, las ofertas que establecen variables de JavaScript utilizadas por código de sitio u otros mboxes que vienen después en la página.

* Asegúrese de tener `<div class="mboxDefault"></div>` antes de invocar `mboxCreate()`, ya que [!DNL at.js] no lo agregará por usted.

* No se recomiendan funciones `mboxCreate()` vacías que aparecen en la parte superior de la página como mbox global.

   El mbox global creado automáticamente en [!DNL at.js] es una mejor opción porque se activa desde `<head>` y puede devolver contenido más rápido.