---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;aplicar oferta;at.js;funciones;función
description: Información sobre la función adobe.target.applyOffers(options) para la biblioteca JavaScript at.js de Adobe Target.
title: Adobe.Destinatario.Applyoffer(Options) - at.js 2.x
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 94%

---


# adobe.destinatario.applyOffers(options) - at.js 2.x

Esta función permite aplicar más de una oferta recuperada por `adobe.target.getOffers()`.

>[!NOTE]
>
>Esta función se introdujo en at.js 2.x. Esta función no está disponible para la at.js versión 1.*x*.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| selector | Cadena | No | Elemento HTML o selector de CSS utilizado para identificar el elemento HTML donde [!DNL Target] debería colocar el contenido de la oferta. Si no se proporciona un selector, [!DNL Target] supone que el elemento HTML que se va a utilizar es HEAD HTML. |
| Respuesta | Objeto | Sí | Objeto de respuesta de `getOffers()`.<br>Consulte la tabla Solicitudes a continuación. |

## Respuesta

>[!NOTE]
>
>Consulte la [documentación de API de Envío](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) para obtener información sobre los tipos aceptables para todos los campos que se enumeran a continuación.

| Nombre del campo | Descripción |
| --- | --- |
| Respuesta > Captura previa > Vistas > Opciones > Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta > Captura previa > Vistas > Opciones > Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. El tipo compatible es acciones. |
| Respuesta > Captura previa > Vistas > Estado | Un token de estado de vista opaca que debería reenviarse con la notificación de visualización de la vista. |
| Respuesta > Captura previa > Vistas > Opciones > responseTokens | Contiene el mapa de `responseTokens` que se recopiló cuando se estaba procesando la opción actual. |
| Respuesta > Captura previa > Vistas > Analytics > Carga | Carga útil de Analytics para la integración de cliente que debería enviarse a Analytics después de aplicar la vista. |
| Respuesta > Captura previa > Vistas > Seguimiento | El objeto que contiene todos los datos de seguimiento de la llamada de captura previa por vista.<br>El objeto de seguimiento también incluye una versión para el seguimiento.<br>El objeto de seguimiento también incluye detalles de la vista actual. |
| Respuesta > Captura previa > Vistas > Opciones > eventToken | El registro de eventos se realiza por opción. Para cada opción aplicada, el token de evento respectivo debe agregarse a la lista de tokens de notificación. Tenga en cuenta que una Vista está compuesta de varias opciones. Si se han aplicado y visto todas las opciones, es necesario incluir todos los `eventTokens` en la notificación. |
| Respuesta > Captura previa > Vistas > Nombre | El nombre de vista legible en lenguaje natural. |
| Respuesta > Captura previa > Vistas > Métricas | Informes de métricas que deben verse y, a continuación, notificar a [!DNL Target]. Actualmente, solo es compatible la métrica de clic. Si se produce un clic en el elemento, el `eventTokens` adecuado debe recopilarse y debe enviarse una notificación. |
| Respuesta > Captura previa > Vistas > Clave | La clave o huella digital que identifica la vista. |
| Respuesta > Captura previa > Vistas > ID | ID de la vista. |
| Respuesta > Notificaciones > ID | ID de notificación. |
| Respuesta > Notificaciones > Eventos > Tipo | El tipo de notificación, clic o visualización. |
| Respuesta > Notificaciones > Eventos > Seguimiento | El seguimiento del evento de notificación. |
| Respuesta > Notificaciones > Eventos > Token | El token que se envió con el evento de notificación. |
| Respuesta > Notificaciones > Eventos > Marca de tiempo | La marca de tiempo que se envió con el evento de notificación. |
| Respuesta > Notificaciones > Eventos > errorCode | Si la notificación falla, el código indica el motivo del error. |
| Respuesta > Notificaciones > Eventos | Los eventos que se registraron o que no se registraron para la notificación actual. |
| Respuesta > Notificaciones | Indica las notificaciones registradas o fallidas. |
| Respuesta > Ejecutar > mboxes > mbox > Seguimiento | El objeto que contiene todos los datos de seguimiento de la solicitud de mbox individual. |
| Respuesta > Ejecutar > mboxes > mbox > responseTokens | Contiene el mapa de `responseTokens` para la ejecución de una solicitud de mbox específica. |
| Respuesta > Ejecutar > mboxes > mbox > Opción > Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta > Ejecutar > mboxes > mbox > Opción > Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. Los tipos compatibles son: HTML, redireccionamiento, JSON y dinámico. |
| Respuesta > Ejecutar > mboxes > mbox > Opciones | Opción de respuesta. |
| Respuesta > Ejecutar > mboxes > mbox > Métricas > eventToken | Token de evento de clic. |
| Respuesta > Ejecutar > mboxes > mbox > Métricas > Tipo | “click” |
| Respuesta > Ejecutar > mboxes > mbox > Métricas | Contiene la lista de métricas `clickThrough`. |
| Respuesta > Ejecutar > mboxes > mbox > mbox | El nombre del mbox. |
| Respuesta > Ejecutar > mboxes > mbox > Índice | Indica que la respuesta es para mbox con este índice de la solicitud. |
| Respuesta > Ejecutar > mboxes > mbox > Analytics > Carga | Carga útil de Analytics para la integración de cliente que debe enviarse a Analytics después de aplicarse el mbox. (Consulte la sección Campañas habilitadas para A4T). |
| Respuesta > Ejecutar > mboxes | Lista de mboxes ejecutados. |
| Respuesta > Ejecutar > pageLoad > Opciones > Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta > Ejecutar > pageLoad > Opciones > Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. Los tipos compatibles son: HTML, redireccionamiento, JSON, dinámico y acciones. |
| Respuesta > Ejecutar > pageLoad > Opciones | Opciones que no se agrupan por vistas (target-global-mbox y opciones de actividades con vistas no agrupadas por vistas). |
| Respuesta > Ejecutar > pageLoad > Métricas | Métricas de clic que no están configuradas para pertenecer a una vista específica. |
| Respuesta > Ejecutar > pageLoad > Seguimiento | El objeto que contiene todos los datos de seguimiento de la solicitud pageLoad. |
| Respuesta > Ejecutar > pageLoad > Analytics > Carga | Carga útil de Analytics para la integración de cliente que debe enviarse a Analytics después de aplicar el contenido de carga de página. (Consulte la sección Campañas habilitadas para A4T). |

## Llamada de ejemplo applyOffers()

```javascript
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## Llamada de ejemplo de Promise encadenada con `getOffers()` y `applyOffers()`, ya que estas funciones están localizadas en Promise.

```javascript
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
