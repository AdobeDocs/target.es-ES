---
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;page parameters;at.js;functions;function
description: Información sobre la función targetPageParams() para la biblioteca JavaScript at.js de Adobe Target.
title: Información sobre la función targetPageParams() para la biblioteca JavaScript at.js de Adobe Target.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 89%

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Este método permite adjuntar parámetros al mbox global desde fuera del código de la solicitud.

Esta función resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán solamente a la solicitud de mbox global. This function can be defined before at.js is loaded or in **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Library Header]**.

Puede pasar parámetros a target-global-mbox mediante la función `targetPageParams()` de cualquiera de estas formas:

* Una lista delimitada por Y comerciales
* Una matriz
* Un objeto JSON

## Ejemplos

Una lista delimitada por Y comerciales (los valores deben tener codificación de dirección URL):

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (los valores no necesitan tener codificación de dirección URL):

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (los valores no necesitan tener codificación de dirección URL):

```
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
