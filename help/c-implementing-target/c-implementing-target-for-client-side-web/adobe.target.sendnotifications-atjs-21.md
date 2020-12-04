---
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;functions;function
description: Información sobre la función adobe.target.sendNotifications(options) para la biblioteca JavaScript at.js de Adobe Target.
title: adobe.target.sendNotifications(options)
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---


# adobe.target.sendNotifications(options)

Esta función envía una notificación a Target Edge cuando se procesa una experiencia sin utilizar `adobe.target.applyOffer()` o `adobe.target.applyOffers()`.

>[!NOTE]
>
>Esta función se ha introducido en at.js 2.1.0 y estará disponible para todas las versiones posteriores a 2.1.0.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| consumerId | Cadena | No | Si no se proporciona, el valor predeterminado es el mbox global del cliente. Esta clave se utiliza para generar el ID de datos suplementario utilizado para la integración de A4T. |
| Solicitud | Objeto | Sí | Consulte la tabla Solicitudes a continuación. |
| timeout | Número | No | Tiempo de espera de la solicitud. Si no se especifica, se usará el tiempo de espera predeterminado en at.js. |

## Solicitud

| Nombre del campo | Tipo | ¿Requerido? | Limitación | Descripción |
| --- | --- | --- | --- | --- |
| Request > notifications | Matriz de objetos | Sí |  | Notificaciones para el contenido mostrado, selectores en los que se hizo clic y/o vistas o mboxes visitados. |
| Request > notifications > address | Objeto | No |  |  |
| Request > notifications > address > url | Cadena | No |  | URL desde la cual se activó la notificación. |
| Request > notifications > address > referringUrl | Cadena | No |  | Dirección URL de referencia desde la que se activó la notificación. |
| Request > notifications > parameters | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con “perfil”.</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Request > notifications > profileParameters | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con “perfil”.</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Request > notifications > order | Objeto | No |  | Objeto que describe los detalles del pedido. |
| Request > notifications > order > id | Cadena | No | `<=` 250 caracteres. | ID de pedido. |
| Request > notifications > order > total | Cadena | No | `>=` 0 | Total de pedido. |
| Request > notifications > order > purchasedProductIds | Matriz de cadena | No | <ul><li>No se permiten valores en blanco.</li><li>La longitud máxima de la ID de producto es 50.</li><li>Los ID de producto, separados por comas y concatenados, no deben superar los 250.</li></ul> | Ordenar ID de productos. |
| Request > notifications > product | Objeto | No |  |  |
| Request > notifications > product > id | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID del producto. |
| Request > notifications > product > categoryId | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID de categoría. |
| Request > notifications > id | Cadena | Sí | `<=` 200 caracteres. | La ID de notificación se devolverá en respuesta e indicará que la notificación se ha procesado correctamente. |
| Request > notifications > impressionId | Cadena | No | `<= 128` caracteres. | La ID de impresión se utiliza para unir (vincular) la notificación actual con una notificación anterior o ejecutar la solicitud. Si ambas coinciden, la segunda y las demás solicitudes posteriores no generarán una impresión nueva para la actividad o experiencia. |
| Solicitud > notificaciones > tipo | Cadena | Sí | Se admite “clic” o “visualización”. | Tipo de notificación. |
| Request > notifications > timestamp | Número`<int64>` | Sí |  | Marca de tiempo de la notificación en milisegundos transcurridos desde UNIX epoch. |
| Request > notifications > tokens | Matriz de cadena | Sí |  | Lista de tokens para el contenido mostrado o selectores en los que se hizo clic, según el tipo de notificación. |
| Request > notifications > mbox | Objeto | No |  | Notificaciones para el mbox. |
| Request > notifications > mbox > name | Cadena | No | No se permiten valores en blanco.<br>Caracteres permitidos: Consulte la nota que sigue esta tabla. | nombre de mbox. |
| Request > notifications > mbox > state | Cadena | No |  | Token de estado de mbox. |
| Request > notifications > view | Objeto | No |  |  |
| Request > notifications > view > id | Número entero `<int64>` | No |  | Ver id. ID que se asignó a la vista cuando la vista se creó mediante la API de visualización. |
| Request > notifications > view > name | Cadena | No | `<= 128` caracteres. | Nombre de la vista. |
| Request > notifications > view > key | Cadena | No | `<=` 512 caracteres. | Ver clave. La clave que se configuró con la vista a través de la API. |
| Request > notifications > view > state | Cadena | No |  | Ver token de estado. |

**Nota**: Los caracteres siguientes están permitidos para `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## Llamada sendNotifications() después de procesar mboxes de recuperación previa

```javascript
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>Si utiliza Adobe Analytics, `getOffers()` solo con recuperación previa y `sendNotifications()`, la solicitud de Analytics se debe activar después de ejecutar `sendNotifications()`. El propósito de esto es garantizar que el SDID generado por `sendNotifications()` coincidirá con el SDID enviado a Analytics y Target.