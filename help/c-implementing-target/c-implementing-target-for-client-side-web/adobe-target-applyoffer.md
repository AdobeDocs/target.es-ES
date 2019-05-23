---
description: 'Información sobre la función adobe. target. applyoffer (options) para at. js. '
keywords: adobe.target.notification;elemento;selector;notificación;extensión
seo-description: Información sobre la función adobe. target. applyoffer (options) para la biblioteca JavaScript de Adobe Target at. js.
seo-title: Información sobre la función adobe. target. applyoffer (options) para la biblioteca JavaScript de Adobe Target at. js.
solution: Target
subtopic: Primeros pasos
title: adobe.target.applyOffer(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 15da223709bfceecb094b6c9f9e78ba5ce0d8256

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

Esta función es para aplicar el contenido de respuesta.

>[!NOTE]
>
>`applyOffer` requiere el parámetro `mbox`. Si no se especifica un nombre de mbox, se produce un error.

El parámetro de opciones es obligatorio y tiene la siguiente estructura:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | Nombre de mbox con<br>at. js 1.3.0 (y posterior) Target impone la utilización de la clave de mbox. Esta clave se ha requerido en el pasado, pero Target impone ahora su uso para garantizar que Target tenga la validación adecuada y los clientes usen la función correctamente. |
| selector | Cadena o elemento DOM | No | Elemento HTML o selector de CSS utilizado para identificar el elemento HTML donde Target debería colocar el contenido de la oferta. Si no se proporciona un selector, Target supone que el elemento HTML que deberíamos utilizar es HTML HEAD. |
| oferta | Matriz | Sí | Las acciones de una matriz que deben aplicarse al elemento. |

## Ejemplo {#section_D8D6A17B73DE4542937CDB687193A5CC}

El siguiente ejemplo muestra el uso de `getOffer` y `applyOffer` juntos:

```
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
