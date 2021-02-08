---
keywords: mboxCreate;mboxcreate;crear mbox;at.js;funciones;función
description: Utilice la función mboxCreate() de la biblioteca JavaScript at.js de Adobe Target para aplicar ofertas al DIV más cercano con el nombre de clase mboxDefault. (at.js 1.x)
title: ¿Cómo se usa la función mboxCreate()?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 85%

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