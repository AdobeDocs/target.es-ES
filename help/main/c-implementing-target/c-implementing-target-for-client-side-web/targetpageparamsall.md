---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;parámetros de página;at.js;funciones;función
description: Utilizar la función targetPageParamsAll() para el Adobe [!DNL Target] Biblioteca JavaScript at.js para adjuntar parámetros a todos los mboxes desde fuera del código de solicitud.
title: ¿Cómo utilizo la función targetPageParamsAll() ?
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParamsAll()

Este método permite adjuntar parámetros a todos los mboxes desde fuera del código de la solicitud.

Resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán a todas las solicitudes de mbox de la página. Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Editar]** > **[!UICONTROL Configuración de código]** > **[!UICONTROL Encabezado de la biblioteca]**.

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
