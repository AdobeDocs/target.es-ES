---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;parámetros de página;at.js;funciones;función
description: Utilizar la función targetPageParams() para el Adobe [!DNL Target] Biblioteca JavaScript at.js para adjuntar parámetros al mbox global desde fuera del código de solicitud.
title: ¿Cómo utilizo la función targetPageParams() ?
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 72%

---

# targetPageParams()

Este método permite adjuntar parámetros al mbox global desde fuera del código de la solicitud.

Esta función resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán solamente a la solicitud de mbox global. Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Editar]** > **[!UICONTROL Encabezado de la biblioteca]**.

Puede pasar parámetros a target-global-mbox mediante la función `targetPageParams()` de cualquiera de estas formas:

* Una lista delimitada por Y comerciales
* Una matriz
* Un objeto JSON

## Ejemplos

Una lista delimitada por Y comerciales (los valores deben tener codificación de dirección URL):

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (los valores no necesitan tener codificación de dirección URL):

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (los valores no necesitan tener codificación de dirección URL):

```javascript
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
