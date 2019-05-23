---
description: La función targetPageParams de JavaScript se usa para pasar parámetros al mbox global. Esto es necesario en cualquier escenario en el que se vaya a pasar información de segmentación o contexto adicional a Target.
keywords: parámetros de mbox global;targetPageParams;cadena de consulta;matriz;json;dtm;dynamic tag management
seo-description: La función targetPageParams de JavaScript se usa para pasar parámetros al mbox global. Esto es necesario en cualquier escenario en el que se vaya a pasar información de segmentación o contexto adicional a Target.
seo-title: Pasar parámetros a un mbox global
solution: Target
subtopic: Primeros pasos
title: Pasar parámetros a un mbox global
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: b45a1a141e9e1d229ed3f92b8124d3edf3bc3042

---


# Pasar parámetros a un mbox global{#pass-parameters-to-a-global-mbox}

La función targetPageParams de JavaScript se usa para pasar parámetros al mbox global. Esto es necesario en cualquier escenario en el que se vaya a pasar información de segmentación o contexto adicional a Target.

Por ejemplo, en una actividad de Recommendations, use los parámetros para representar el producto o la categoría actual que se está viendo.

El código para llamar a la función de JavaScript debe estar antes del mbox global en la página, tanto si el mbox global se activa como parte de mbox.js como si se incluye manualmente en el código de la página.

>[!NOTE]
>
>Si quiere añadir parámetros a todos los mboxes de la página, no solo a mbox global, utilice la función [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) (solo at.js).

Puede pasar parámetros a `target-global-mbox` mediante la función `targetPageParams()` de cualquiera de estas formas:

* Una matriz
* Un objeto JSON
* Una lista delimitada por Y comerciales

Use estos tres métodos para verificar que los parámetros se estén pasando correctamente. También podría verificar el paso de parámetros con [Adobe Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html).

Debe definir la función de JavaScript antes de añadir el mbox global a la página. El nombre debe ser `targetPageParams`.

**Cadena de consulta**

```
p1=v1&p2=v2&p3=hello%20world
```

* Nombre: `targetPageParams`
* Valor devuelto: parámetros delimitados por “&amp;”, con valores de parámetro codificados con la dirección URL.

   Ejemplo:  

   En este ejemplo, p3 tiene el valor `hello world`, que está codificado con la dirección URL.

A continuación se muestra un ejemplo del aspecto que podría tener el código de la página:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

Este ejemplo envía los siguientes datos al edge de mbox:

* p1=v1
* p2=v2
* p3=hello world

**Matriz**

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

Los valores no necesitan tener codificación de dirección URL. Por ejemplo, si un valor contiene un espacio, no es necesario codificar el espacio.

Este ejemplo envía los siguientes datos al edge de mbox:

* a=1
* b=2
* c=hello world

**JSON**

JSON es una manera eficaz de pasar parámetros. Target usa las claves de objeto JSON para convertir estructuras complicadas en parámetros simples.

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

Los valores no necesitan tener codificación de dirección URL. Por ejemplo, “San Francisco” no requiere que se codifique el espacio. Un espacio es suficiente.

Este ejemplo envía los siguientes datos al edge de mbox:

* a=1
* b=2
* `profile.age`=26
* `profile.country.city`=San Francisco