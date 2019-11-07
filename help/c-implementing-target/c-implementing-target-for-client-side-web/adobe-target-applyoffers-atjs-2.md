---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;aplicar oferta;at.js;funciones;función
description: Información sobre la función adobe.target.applyOffers(options) para la biblioteca JavaScript at.js de Adobe Target.
title: Información sobre la función adobe.target.applyOffers(options) para la biblioteca JavaScript at.js de Adobe Target.
subtopic: Primeros pasos
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.applyOffers(options) - at.js 2.x

Esta función permite aplicar más de una oferta recuperada por `adobe.target.getOffers()`.

>[!NOTE]
>
>Esta función se introdujo en at.js 2.x. Esta función no está disponible para la at.js versión 1.*x*.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| selector | Cadena | No | Elemento HTML o selector de CSS utilizado para identificar el elemento HTML donde [!DNL Target] debería colocar el contenido de la oferta. Si no se proporciona un selector, [!DNL Target] supone que el elemento HTML que debería utilizar es HTML HEAD. |
| Respuesta | Objeto | Sí | Objeto de respuesta de `getOffers()`.<br>Consulte la tabla Solicitudes a continuación. |

## Respuesta

>[!NOTE]
>
>Consulte la documentación [de la API de](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) envío para obtener información sobre los tipos aceptables para todos los campos que se enumeran a continuación.

| Nombre del campo | Descripción |
| --- | --- |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Opciones &gt; Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Opciones &gt; Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. El tipo compatible es acciones. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Estado | Un token de estado de vista opaca que debería reenviarse con la notificación de visualización de la vista. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Opciones &gt; responseTokens | Contiene el mapa de `responseTokens` que se recopiló cuando se estaba procesando la opción actual. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Analytics &gt; Carga | Carga útil de Analytics para la integración de cliente que debería enviarse a Analytics después de aplicar la vista. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Seguimiento | El objeto que contiene todos los datos de seguimiento de la llamada de captura previa por vista.<br>El objeto de seguimiento también incluye una versión para el seguimiento.<br>El objeto de seguimiento también incluye detalles de la vista actual. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Opciones &gt; eventToken | El registro de eventos se realiza por opción. Para cada opción aplicada, el token de evento respectivo debe agregarse a la lista de tokens de notificación. Tenga en cuenta que una Vista está compuesta de varias opciones. Si se han aplicado y visto todas las opciones, es necesario incluir todos los `eventTokens` en la notificación. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Nombre | El nombre de vista legible en lenguaje natural. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Métricas | Informes de métricas que deben verse y, a continuación, notificar a [!DNL Target]. Actualmente, solo es compatible la métrica de clic. Si se produce un clic en el elemento, el `eventTokens` adecuado debe recopilarse y debe enviarse una notificación. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; Clave | La clave o huella digital que identifica la vista. |
| Respuesta &gt; Captura previa &gt; Vistas &gt; ID | ID de la vista. |
| Respuesta &gt; Notificaciones &gt; ID | ID de notificación. |
| Respuesta &gt; Notificaciones &gt; Eventos &gt; Tipo | El tipo de notificación, clic o visualización. |
| Respuesta &gt; Notificaciones &gt; Eventos &gt; Seguimiento | El seguimiento del evento de notificación. |
| Respuesta &gt; Notificaciones &gt; Eventos &gt; Token | El token que se envió con el evento de notificación. |
| Respuesta &gt; Notificaciones &gt; Eventos &gt; Marca de tiempo | La marca de tiempo que se envió con el evento de notificación. |
| Respuesta &gt; Notificaciones &gt; Eventos &gt; errorCode | Si la notificación falla, el código indica el motivo del error. |
| Respuesta &gt; Notificaciones &gt; Eventos | Los eventos que se registraron o que no se registraron para la notificación actual. |
| Respuesta &gt; Notificaciones | Indica las notificaciones registradas o fallidas. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Seguimiento | El objeto que contiene todos los datos de seguimiento de la solicitud de mbox individual. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; responseTokens | Contiene el mapa de `responseTokens` para la ejecución de una solicitud de mbox específica. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Opción &gt; Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Opción &gt; Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. Los tipos compatibles son: HTML, redireccionamiento, JSON y dinámico. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Opciones | Opción de respuesta. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Métricas &gt; eventToken | Token de evento de clic. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Métricas &gt; Tipo | “click” |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Métricas | Contiene la lista de métricas `clickThrough`. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; mbox | El nombre del mbox. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Índice | Indica que la respuesta es para mbox con este índice de la solicitud. |
| Respuesta &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Analytics &gt; Carga | Carga útil de Analytics para la integración de cliente que debe enviarse a Analytics después de aplicarse el mbox. (Consulte la sección Campañas habilitadas para A4T). |
| Respuesta &gt; Ejecutar &gt; mboxes | Lista de mboxes ejecutados. |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Opciones &gt; Contenido | Tenga en cuenta que el contenido de la “opción” no está bien definido y depende directamente del tipo de opción o de la estructura de la plantilla. |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Opciones &gt; Tipo | Tipo de opción. Refleja el tipo de campo “contenido”. Los tipos compatibles son: HTML, redireccionamiento, JSON, dinámico y acciones. |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Opciones | Opciones que no se agrupan por vistas (target-global-mbox y opciones de actividades con vistas no agrupadas por vistas). |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Métricas | Métricas de clic que no están configuradas para pertenecer a una vista específica. |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Seguimiento | El objeto que contiene todos los datos de seguimiento de la solicitud pageLoad. |
| Respuesta &gt; Ejecutar &gt; pageLoad &gt; Analytics &gt; Carga | Carga útil de Analytics para la integración de cliente que debe enviarse a Analytics después de aplicar el contenido de carga de página. (Consulte la sección Campañas habilitadas para A4T). |

## Llamada de ejemplo applyOffers()

```
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

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
