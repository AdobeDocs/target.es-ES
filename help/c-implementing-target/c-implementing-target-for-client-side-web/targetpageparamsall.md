---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;parámetros de página;at.js;funciones;función
description: Información sobre la función targetPageParamsAll() para la biblioteca JavaScript at.js de Adobe Target.
title: Targetpageparamsall()
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 87%

---


# targetPageParamsAll()

Este método permite adjuntar parámetros a todos los mboxes desde fuera del código de la solicitud.

Resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán a todas las solicitudes de mbox de la página. Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Editar]** > **[!UICONTROL Configuración de código]** > **[!UICONTROL Encabezado de biblioteca]**.

Puede pasar parámetros a target-global-mbox mediante la función targetPageParamsAll() de cualquiera de estas formas:

* Una lista delimitada por Y comerciales
* Una matriz
* Un objeto JSON

## Ejemplos

Una lista delimitada por Y comerciales (los valores deben tener codificación de dirección URL):

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (los valores no necesitan tener codificación de dirección URL):

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (los valores no necesitan tener codificación de dirección URL):

```javascript
targetPageParamsAll = function() { 
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
