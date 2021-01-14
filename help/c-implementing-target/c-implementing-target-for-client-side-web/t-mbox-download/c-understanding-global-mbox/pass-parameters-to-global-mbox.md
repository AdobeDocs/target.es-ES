---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: La función targetPageParams de JavaScript se usa para pasar parámetros al mbox global. Esto es necesario en cualquier escenario en el que la información de contexto/objetivo adicional se pase a Adobe Target.
title: Pasar parámetros a un mbox global
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Pasar parámetros a un mbox global

La función JavaScript `targetPageParams` se utiliza para pasar parámetros al mbox global en [!DNL Adobe Target]. Esto es necesario en cualquier escenario en el que se vaya a pasar información de segmentación o contexto adicional a [!DNL Target].

Por ejemplo, en una actividad [!DNL Recommendations], utilice los parámetros para representar el producto o la categoría actual que se está viendo.

El código para llamar a la función JavaScript debe estar antes del mbox global de la página, tanto si el mbox global se activa como parte de at.js como si se incluye manualmente en el código de la página.

>[!NOTE]
>
>Si desea agregar parámetros a todos los mboxes de la página, no solo al mbox global, utilice la función [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md).

Puede pasar parámetros a `target-global-mbox` mediante la función `targetPageParams()` de cualquiera de estas formas:

* Una matriz
* Un objeto JSON
* Una lista delimitada por Y comerciales

Use estos tres métodos para verificar que los parámetros se estén pasando correctamente. También podría verificar el paso de parámetros con [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).

Debe definir la función de JavaScript antes de añadir el mbox global a la página. El nombre debe ser `targetPageParams`.

## Cadena de consulta

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

## Matriz

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

## JSON

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
* `profile.memberStatus`=Oro
* `profile.country.city`=San Francisco