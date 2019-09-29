---
description: 'Información sobre la función adobe.target.sendNotifications(options) para at.js. '
keywords: adobe.target.sendNotifications;sendNotifications;enviar notificaciones;enviar notificaciones;notificaciones;at.js;funciones;función
seo-description: Información sobre la función adobe.target.sendNotifications(options) para la biblioteca JavaScript at.js de Adobe Target.
seo-title: Información sobre la función adobe.target.sendNotifications(options) para la biblioteca JavaScript at.js de Adobe Target.
solution: Target
subtopic: Primeros pasos
title: adobe.target.sendNotifications(options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

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
| Request &gt; notifications | Matriz de objetos | Sí |  | Notificaciones para el contenido mostrado, selectores en los que se hizo clic y/o vistas o mboxes visitados. |
| Request &gt; notifications &gt; address | Objeto | No |  |  |
| Request &gt; notifications &gt; address &gt; url | Cadena | No |  | URL desde la cual se activó la notificación. |
| Request &gt; notifications &gt; address &gt; referringUrl | Cadena | No |  | Dirección URL de referencia desde la que se activó la notificación. |
| Request &gt; notifications &gt; parameters | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con “perfil”.</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Request &gt; notifications &gt; profileParameters | Objeto | No | Los parámetros siguientes no están permitidos en los parámetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tenga en cuenta lo siguiente:<ul><li>Límite máximo de 50 parámetros.</li><li>El nombre del parámetro no debe estar en blanco.</li><li>Longitud máxima del parámetro 128.</li><li>El nombre del parámetro no debe comenzar con “perfil”.</li><li>Longitud máxima del valor del parámetro 5000.</li></ul> |  |
| Request &gt; notifications &gt; order | Objeto | No |  | Objeto que describe los detalles del pedido. |
| Request &gt; notifications &gt; order &gt; id | Cadena | No | `<=` 250 caracteres. | ID de pedido. |
| Request &gt; notifications &gt; order &gt; total | Cadena | No | `>=` 0 | Total de pedido. |
| Request &gt; notifications &gt; order &gt; purchasedProductIds | Matriz de cadena | No | <ul><li>No se permiten valores en blanco.</li><li>La longitud máxima de la ID de producto es 50.</li><li>Los ID de producto, separados por comas y concatenados, no deben superar los 250.</li></ul> | Ordenar ID de productos. |
| Request &gt; notifications &gt; product | Objeto | No |  |  |
| Request &gt; notifications &gt; product &gt; id | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID del producto. |
| Request &gt; notifications &gt; product &gt; categoryId | Cadena | No | `<=` 128 caracteres; no puede estar en blanco. | ID de categoría. |
| Request &gt; notifications &gt; id | Cadena | Sí | `<=` 200 caracteres. | La ID de notificación se devolverá en respuesta e indicará que la notificación se ha procesado correctamente. |
| Request &gt; notifications &gt; impressionId | Cadena | No | `<= 128` caracteres. | La ID de impresión se utiliza para unir (vincular) la notificación actual con una notificación anterior o ejecutar la solicitud. Si ambas coinciden, la segunda y las demás solicitudes posteriores no generarán una impresión nueva para la actividad o experiencia. |
| Solicitud &gt; notificaciones &gt; tipo | Cadena | Sí | Se admite “clic” o “visualización”. | Tipo de notificación. |
| Request &gt; notifications &gt; timestamp | Número`<int64>` | Sí |  | Marca de tiempo de la notificación en milisegundos transcurridos desde UNIX epoch. |
| Request &gt; notifications &gt; tokens | Matriz de cadena | Sí |  | Lista de tokens para el contenido mostrado o selectores en los que se hizo clic, según el tipo de notificación. |
| Request &gt; notifications &gt; mbox | Objeto | No |  | Notificaciones para el mbox. |
| Request &gt; notifications &gt; mbox &gt; name | Cadena | No | No se permiten valores en blanco.<br>Caracteres permitidos: Consulte la nota que sigue esta tabla. | nombre de mbox. |
| Request &gt; notifications &gt; mbox &gt; state | Cadena | No |  | Token de estado de mbox. |
| Request &gt; notifications &gt; view | Objeto | No |  |  |
| Request &gt; notifications &gt; view &gt; id | Número entero `<int64>` | No |  | Ver id. ID que se asignó a la vista cuando la vista se creó mediante la API de visualización. |
| Request &gt; notifications &gt; view &gt; name | Cadena | No | `<= 128` caracteres. | Nombre de la vista. |
| Request &gt; notifications &gt; view &gt; key | Cadena | No | `<=` 512 caracteres. | Ver clave. La clave que se configuró con la vista a través de la API. |
| Request &gt; notifications &gt; view &gt; state | Cadena | No |  | Ver token de estado. |

**Nota**: Los caracteres siguientes están permitidos para `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## Llamada sendNotifications() después de procesar mboxes de recuperación previa

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
>Si utiliza Adobe Analytics, `getOffers()` solo con recuperación previa y `sendNotifications()`, la solicitud de Analytics se debe activar después de ejecutar `sendNotifications()`. El propósito de esto es garantizar que el SDID generado por `sendNotifications()` coincidirá con el SDID enviado a Analytics y Target.