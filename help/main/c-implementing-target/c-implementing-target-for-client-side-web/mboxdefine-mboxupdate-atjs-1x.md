---
keywords: mboxDefine;mboxdefine;definir mbox;mboxUpdate;mboxupdate;actualización de mbox;at.js;funciones;función
description: Uso de las funciones mboxDefine() y mboxUpdate() para el Adobe [!DNL Target] Biblioteca JavaScript at.js para definir o actualizar un mbox. (at.js 1.x)
title: ¿Cómo utilizo las funciones mboxDefine() y mboxUpdate() ?
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 63%

---

# mboxDefine() and mboxUpdate(): at.js 1.x

Defina y actualice un mbox en Adobe Target.

>[!NOTE]
>
>Estas funciones están disponibles para las versiones 1 de at.js.Solamente *x*. Estas funciones quedaron obsoletas con el lanzamiento de at.js 2.x. Estas funciones devuelven contenido predeterminado si se utilizan con at.js 2.x.

`mboxDefine()` y `mboxCreate()` están vinculados a elementos HTML DIV donde la oferta debería mostrarse. Estos elementos DIV HTML deberían tener la clase `mboxDefault`. Si los elementos HTML no tendrán esta clase adjunta, usted podría ver un notable parpadeo.

## mboxDefine   {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Crea una asignación interna entre un nombre de mbox y nodeId, pero no excluye la solicitud. Se usa en conjunto con `mboxUpdate()`. Integrado en [!DNL at.js] principalmente para facilitar la transición de [!DNL mbox.js] (ahora obsoleto) a [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Ejecuta la solicitud y aplica la oferta al elemento identificado por el `nodeId` en `mboxDefine()`. También se puede usar para actualizar un mbox iniciado por `mboxCreate`. Integrado en [!DNL at.js] principalmente para facilitar la transición de [!DNL mbox.js] (ahora obsoleto) a [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` se puede reemplazar por [adobe.target.getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} y [adobe.target.applyOffer(){target=_blank}](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/){target=_blank} utilizando la opción de selector.

## Ejemplo {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
