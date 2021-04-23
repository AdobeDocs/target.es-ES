---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;parámetros de página;at.js;funciones;función
description: Utilice la función targetPageParamsAll() para la biblioteca JavaScript  [!DNL Target] at.js de Adobe para adjuntar parámetros a todos los mboxes desde fuera del código de solicitud.
title: ¿Cómo utilizo la función targetPageParamsAll() ?
feature: 'at.js '
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 72%

---

# targetPageParamsAll()

Este método permite adjuntar parámetros a todos los mboxes desde fuera del código de la solicitud.

Resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán a todas las solicitudes de mbox de la página. Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

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
