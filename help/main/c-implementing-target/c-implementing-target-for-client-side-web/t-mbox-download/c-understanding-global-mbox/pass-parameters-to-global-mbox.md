---
keywords: parámetros de mbox global;targetPageParams;cadena de consulta;matriz;json;dtm
description: Aprenda a utilizar la función targetPageParams para pasar información de contexto o segmentación adicional al Adobe [!DNL Target] mbox global.
title: ¿Cómo paso parámetros a un mbox global?
feature: at.js
role: Developer
exl-id: 37d143af-83a8-48fd-91eb-58f21f8c7b94
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 63%

---

# Pasar parámetros a un mbox global

JavaScript `targetPageParams` se usa para pasar parámetros al mbox global en [!DNL Adobe Target]. Esto es necesario en cualquier escenario en el que se vaya a pasar información de segmentación o contexto adicional a [!DNL Target].

Por ejemplo, en un [!DNL Recommendations] , utilice los parámetros para representar el producto o categoría actual que se está viendo.

El código para llamar a la función JavaScript debe estar antes del mbox global en la página, tanto si el mbox global se activa como parte de at.js como si se incluye manualmente en el código de la página.

>[!NOTE]
>
>Si desea agregar parámetros a todos los mboxes de la página, no solo a mbox global, use la variable [targetPageParamsAll()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/)función {target=_blank} .

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
          return "p1=v1&p2=v2&p3=hello%20world";
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
