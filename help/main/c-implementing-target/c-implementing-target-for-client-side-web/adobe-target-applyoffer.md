---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;aplicar oferta;at.js;funciones;función
description: Utilice la función adobe.target.applyOffer() para el Adobe [!DNL Target] Biblioteca JavaScript at.js para aplicar el contenido de respuesta.
title: ¿Cómo utilizo la función adobe.target.applyOffer() ?
feature: at.js
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 72%

---

# adobe.target.applyOffer(options)

Esta función es para aplicar el contenido de respuesta con [!DNL Adobe Target].

>[!NOTE]
>
>`applyOffer` requiere el parámetro `mbox`. Si no se especifica un nombre de mbox, se produce un error.

El parámetro de opciones es obligatorio y tiene la siguiente estructura:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | El nombre de mbox<br>con at.js 1.3.0 (y versiones posteriores) Target exige que se use la clave mbox. Esta clave se ha requerido en el pasado, pero Target impone ahora su uso para garantizar que Target tenga la validación adecuada y los clientes usen la función correctamente. |
| selector | Cadena o elemento DOM | No | Elemento HTML o selector de CSS utilizado para identificar el elemento HTML donde Target debería colocar el contenido de la oferta. Si no se proporciona el selector, Target supone que el elemento HTML debe utilizar el HEAD HTML. |
| Oferta | Matriz | Sí | Las acciones de una matriz que deben aplicarse al elemento. |

## Ejemplo {#section_D8D6A17B73DE4542937CDB687193A5CC}

El siguiente ejemplo muestra el uso de `getOffer` y `applyOffer` juntos:

```javascript
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```