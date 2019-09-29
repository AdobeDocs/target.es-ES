---
description: 'Información sobre la función targetPageParams() para at.js. '
keywords: targetPageParams;targetpageparams;pageParams;pageparams;page params;page parameters;page parameters;at.js;funciones;function
seo-description: Información sobre la función targetPageParams() para la biblioteca JavaScript at.js de Adobe Target.
seo-title: Información sobre la función targetPageParams() para la biblioteca JavaScript at.js de Adobe Target.
solution: Target
subtopic: Primeros pasos
title: targetPageParams()
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Este método permite adjuntar parámetros al mbox global desde fuera del código de la solicitud.

Esta función resulta muy útil para incluir el mismo conjunto de parámetros en varias llamadas de mbox. El cliente debe definir la función. Debería devolver una matriz de parámetros que se pasarán solamente a la solicitud de mbox global. Esta función puede definirse antes de que se cargue at.js o en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación**] &gt; **[!UICONTROL Editar la configuración de at.js**] &gt; **[!UICONTROL Configuración del código]** &gt; **[!UICONTROL Encabezado de la biblioteca]**.

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
