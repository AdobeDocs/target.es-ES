---
description: 'Información sobre la función adobe. target. sendnotifications (options) para at. js. '
seo-description: Información sobre la función adobe. target. sendnotifications (options) para la biblioteca JavaScript de Adobe Target at. js.
seo-title: Información sobre la función adobe. target. sendnotifications (options) para la biblioteca JavaScript de Adobe Target at. js.
solution: Target
subtopic: Primeros pasos
title: adobe. target. sendnotifications (options)
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe. target. sendnotifications (options)

This function sends a notification to Target edge when an experience is rendered without using `adobe.target.applyOffer()` or `adobe.target.applyOffers()`.

>[!NOTE]
>
>Esta función se ha introducido en at. js 2.1.0 y estará disponible para todas las versiones superiores a 2.1.0.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| consumerId | Cadena | No | Si no se proporciona, el valor predeterminado es el mbox global del cliente. Esta clave se utiliza para generar el ID de datos suplementario utilizado para la integración de A4T. |
| Solicitud | Objeto | Sí | Consulte la tabla Solicitudes a continuación. |
| timeout | Número | No | Tiempo de espera de la solicitud. Si no se especifica, se usará el tiempo de espera predeterminado en at.js. |

## Solicitud

| Nombre del campo | Tipo | ¿Requerido? | Limitación | Descripción |
| --- | --- | --- | --- | --- |
| Solicitud &gt; Notificaciones | Matriz de objetos | Sí |  | Notificaciones para el contenido mostrado, selectores en los que se hizo clic y/o vistas o mboxes visitados. |
| Solicitud &gt; notificaciones &gt; dirección | Objeto | No |  |  |
| Solicitud &gt; notificaciones &gt; dirección &gt; url | Cadena | No |  | URL desde la cual se activó la notificación. |
| Request &gt; notifications &gt; address &gt; referringurl | Cadena | No |  | Dirección URL de referencia desde la cual se activó la notificación. |
| Solicitud &gt; notificaciones &gt; parámetros | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con "perfil".</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Solicitud &gt; notificaciones &gt; profileparameters | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con "perfil".</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Solicitud &gt; notificaciones &gt; orden | Objeto | No |  | Objeto que describe los detalles del pedido. |
| Solicitud &gt; notificaciones &gt; orden &gt; id | Cadena | No | `<=` 250 caracteres. | ID de pedido. |
| Solicitud &gt; notificaciones &gt; pedido &gt; total | Cadena | No | `>=` 0 | Total de pedido. |
| Solicitud &gt; notificaciones &gt; pedido &gt; purchasedproductids | Matriz de cadena | No | <ul><li>No se permiten valores en blanco.</li><li>Cada identificación máxima de ID de producto 50.</li><li>Los ID de producto, separados por comas y concatenados, no deben superar los 250.</li></ul> | Ordenar ID de productos. |
| Solicitud &gt; notificaciones &gt; producto | Objeto | No |  |  |
| Solicitud &gt; notificaciones &gt; producto &gt; id | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID del producto. |
| Solicitud &gt; notificaciones &gt; producto &gt; categoryid | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID de categoría. |
| Solicitud &gt; notificaciones &gt; id | Cadena | Sí | `<=` 200 caracteres. | La ID de notificación se devolverá en respuesta e indicará que la notificación se ha procesado correctamente. |
| Solicitud &gt; notificaciones &gt; imsionid | Cadena | No | `<= 128` caracteres. | La ID de impresión se utiliza para unir (vincular) la notificación actual con una notificación anterior o ejecutar la solicitud. Si ambas coinciden, la segunda y otras solicitudes posteriores no generarán una impresión nueva para la actividad o experiencia. |
| Solicitud &gt; notificaciones &gt; tipo | Cadena | Sí | Se admite «clic» o «display». | Tipo de notificación. |
| Solicitud &gt; notificaciones &gt; marca de fecha y hora | Número`<int64>` | Sí |  | Marca de tiempo de la notificación en milisegundos transcurridos desde UNIX epoch. |
| Solicitud &gt; notificaciones &gt; tokens | Matriz de cadena | Sí |  | Lista de tokens para el contenido mostrado o selectores en los que se hizo clic, según el tipo de notificación. |
| Solicitud &gt; notificaciones &gt; mbox | Objeto | No |  | Notificaciones para el mbox. |
| Solicitud &gt; notificaciones &gt; mbox &gt; nombre | Cadena | No | No se permiten valores en blanco.<br>Caracteres permitidos: Consulte la nota siguiente. | nombre de mbox. |
| Solicitud &gt; notificaciones &gt; estado mbox &gt; | Cadena | No |  | Token de estado de mbox. |
| Solicitud &gt; notificaciones &gt; ver | Objeto | No |  |  |
| Solicitud &gt; notificaciones &gt; ver &gt; id | Número entero `<int64>` | No |  | Ver id. ID que se asignó a la vista cuando la vista se creó mediante la API de visualización. |
| Solicitud &gt; notificaciones &gt; ver &gt; nombre | Cadena | No | `<= 128` caracteres. | Nombre de la vista. |
| Solicitud &gt; notificaciones &gt; ver &gt; clave | Cadena | No | `<=` 512 caracteres. | Ver clave. La clave que se configuró con la vista a través de la API. |
| Solicitud &gt; notificaciones &gt; ver &gt; state | Cadena | No |  | Ver token de estado. |

**Nota**: Los caracteres siguientes están `Request > notifications > mbox > name`permitidos para:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## Llamada sendnotifications () después de procesar mboxes prerecuperados

```
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
>If you are using Adobe Analytics, `getOffers()` with prefetch only and `sendNotifications()`, the Analytics request must be fired after `sendNotifications()` is executed. The purpose of this is to ensure that the SDID generated by `sendNotifications()` will match the SDID sent to Analytics and Target.