---
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;functions;function
description: Información sobre las funciones mboxDefine() y mboxUpdate() para la biblioteca JavaScript at.js de Adobe Target.
title: 'mboxDefine() and mboxUpdate(): at.js 1.x'
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---


# mboxDefine() and mboxUpdate(): at.js 1.x

Defina y actualice un mbox en Adobe Target.

>[!NOTE]
>
>Estas funciones están disponibles para las versiones 1 de at.js.Solamente *x*. Estas funciones quedaron obsoletas con el lanzamiento de at.js 2.x. Estas funciones devuelven contenido predeterminado si se utilizan con at.js 2.x.

`mboxDefine()` y `mboxCreate()` están vinculados a elementos HTML DIV donde la oferta debería mostrarse. Estos elementos DIV HTML deberían tener la clase `mboxDefault`. Si los elementos HTML no tendrán esta clase adjunta, usted podría ver un notable parpadeo.

## mboxDefine    {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Crea una asignación interna entre un nombre de mbox y nodeId, pero no excluye la solicitud. Se usa en conjunto con `mboxUpdate()`. Integrado en [!DNL at.js] principalmente para facilitar la transición de [!DNL mbox.js] a [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Ejecuta la solicitud y aplica la oferta al elemento identificado por el `nodeId` en `mboxDefine()`. También se puede usar para actualizar un mbox iniciado por `mboxCreate`. Integrado en [!DNL at.js] principalmente para facilitar la transición de [!DNL mbox.js] a [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` se puede reemplazar mediante [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) y [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) utilizando el selector de opción.

## Ejemplo {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
