---
keywords: adobe.target.getOffer;getOffer;getoffer;obtener oferta;at.js;funciones;función
description: Información sobre la función adobe.target.getOffer(options) para la biblioteca JavaScript at.js de Adobe Target.
title: Información sobre la función adobe.target.getOffer(options) para la biblioteca JavaScript at.js de Adobe Target.
subtopic: Primeros pasos
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.getOffer(options)

Esta función activa una solicitud para obtener una oferta de Target.

Use con `adobe.target.applyOffer()` para procesar la respuesta o use su propia administración de éxito. El parámetro de opciones es obligatorio y tiene la siguiente estructura:

| Clave | Tipo | Requerido | Descripción |
|--- |--- |--- |--- |
| mbox | Cadena | Sí | Nombre de mbox |
| params | Objeto | No | Parámetros de mbox. Un objeto de pares de clave-valor que tiene la siguiente estructura:<br>`{ "param1": "value1", "param2": "value2"}` |
| success | Función | Sí | La llamada de retorno que se ejecutará cuando tengamos una respuesta del servidor. La función de llamada de retorno de éxito recibirá un solo parámetro que representa una matriz de objetos de oferta. Este es un ejemplo de llamada de retorno de éxito:<br>`function handleSuccess(response){......}`<br>Consulte las Respuestas a continuación para obtener más detalles. |
| error | Función | Sí | Llamada de retorno que se ejecutará cuando tengamos un error. Hay un par de casos que se consideran erróneos:<ul><li>Código de estado HTTP diferente a 200 OK</li><li>No se puede analizar la respuesta. Por ejemplo, hemos construido mal JSON o HTML en lugar de JSON.</li><li>La respuesta contiene la clave de “error”. Por ejemplo, se arrojó una excepción en el borde donde no se pudo procesar correctamente una solicitud. Obtuvimos un error cuando se bloquea un mbox y no pudimos recuperar ningún contenido, etc. La función de llamada de retorno de error recibirá dos parámetros: estado y error. Aquí puede ver un ejemplo de llamada de retorno de error:   `function handleError(status, error){......}`</li></ul>Consulte Respuestas de error más adelante para conocer los detalles. |
| timeout | Número | No | Tiempo de espera en milisegundos. Si no se especifica, se usará el tiempo de espera predeterminado en at.js.<br>El tiempo de espera predeterminado puede establecerse desde [!DNL Target]la interfaz de usuario de dentro de [!UICONTROL Configuración &gt; Implementación &gt; Editar la configuración de mbox.js &gt; Tiempo de espera]. |

## Ejemplos {#section_97C2D2E03E6549BEA7F4873E3F5E4A0D}

Añadir parámetros con getOffer() y utilizar applyOffer() para la gestión del éxito:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Añadir parámetros y parámetros de perfil con getOffer() y utilizar applyOffer() para la gestión del éxito:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2, 
     "profile.age": 27, 
     "profile.gender": "male" 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Utilizar el tiempo de espera personalizado y la gestión del éxito personalizada con getOffer():

"YOUR_OWN_CUSTOM_HANDLING_FUNCTION" es un marcador de posición para una función que tiene que definir el cliente.

```
adobe.target.getOffer({     
  "mbox": "target-global-mbox",   
  "success": function(offer) { 
    YOUR_OWN_CUSTOM_HANDLING_FUNCTION(offer);   
  }, 
  "error": function(status, error) {                 
    console.log('Error', status, error);   
  },   
  "timeout": 2000 
});
```

## Respuestas {#section_CF9FD236EF794620BCBF84EB80160183}

El parámetro de respuesta que se pasa a la llamada de retorno de éxito será una matriz de acciones. Una acción es un objeto que suele tener el siguiente formato:

| Nombre | Tipo | Descripción |
|--- |--- |--- |
| action | Cadena | Tipo de acción a aplicar al elemento identificado. |
| selector | Cadena | Representa un selector de Sizzle. |
| cssSelector | Cadena | Selector DOM nativo, empleado para pre-ocultar elementos. |
| content | Cadena | El contenido a aplicar al elemento identificado. |

## Ejemplo

```
{ 
    "sessionId": "1444512212156-384616", 
    "tntId": "1444512212156-384616.17_35", 
    "offers": [{ 
        "plugins": ["<script type=\"text/javascript\">\r\n/*mboxHighlight+ (1of2) v1 ==> Response Plugin*/\r\nwindow.ttMETA=(typeof(window.ttMETA)!='undefined')?window.ttMETA:[];window.ttMETA.push({'mbox':'target-global-mbox','campaign':'at: redirect ootb','experience':'Experience B','offer':'/at_redirect_ootb/experiences/1/pages/0/1442082890250'});window.ttMBX=function(x){var mbxList=[];for(i=0;i<ttMETA.length;i++){if(ttMETA[i].mbox==x.getName()){mbxList.push(ttMETA[i])}}return mbxList[x.getId()]}\r\n</script>"], 
        "actions": { 
            "content": [{ 
                "passMboxSession": false, 
                "selector": "body", 
                "action": "redirect", 
                "url": "https://example.com/04.html", 
                "includeAllUrlParameters": true 
            }] 
        } 
    }] 
}
```

## Respuestas de error {#section_1ACCE79AF2CB4FA2AD1371EA06AF129F}

Los parámetros de “estado” y “error” pasados a la llamada de retorno de error tendrán el siguiente formato:

| Nombre | Tipo | Descripción |
|--- |--- |--- |
| status | Cadena | Representa el estado de error. Este parámetro puede tener los siguientes valores:<ul><li>timeout: indica que se ha agotado el tiempo de espera de la solicitud.</li><li>parseerror: indica que no se pudo analizar la respuesta, por ejemplo, si recibimos HTML o texto sin formato en lugar de JSON.</li><li>error: indica un error general como el que recibimos con estado HTTP diferente a 200 OK.</li></ul> |
| error | Cadena | Contiene datos adicionales como mensaje de excepción o cualquier otra cuestión que podría resultar útil para resolución de problemas. |