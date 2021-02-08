---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;aplicar oferta;at.js;funciones;función
description: Utilice la función adobe.destinatario.applyOffer() de la biblioteca JavaScript de Adobe Target at.js para aplicar el contenido de respuesta.
title: ¿Cómo se usa la función adobe.destinatario.applyOffer()?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 86%

---


# adobe.target.applyOffer(options)

Esta función es para aplicar el contenido de respuesta.

>[!NOTE]
>
>`applyOffer` requiere el parámetro `mbox`. Si no se especifica un nombre de mbox, se produce un error.

El parámetro de opciones es obligatorio y tiene la siguiente estructura:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | El nombre de mbox<br>con at.js 1.3.0 (y versiones posteriores) Target exige que se use la clave mbox. Esta clave se ha requerido en el pasado, pero Target impone ahora su uso para garantizar que Target tenga la validación adecuada y los clientes usen la función correctamente. |
| selector | Cadena o elemento DOM | No | Elemento HTML o selector de CSS utilizado para identificar el elemento HTML donde Target debería colocar el contenido de la oferta. Si no se proporciona un selector, Target supone que el elemento HTML que deberíamos utilizar es HTML HEAD. |
| oferta | Matriz | Sí | Las acciones de una matriz que deben aplicarse al elemento. |

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
