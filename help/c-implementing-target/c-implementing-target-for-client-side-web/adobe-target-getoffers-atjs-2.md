---
description: 'Información sobre la función adobe. target. getoffers (options) para at. js. '
keywords: adobe.target.notification;elemento;selector;notificación;extensión
seo-description: Información sobre la función adobe. target. getoffers (options) para la biblioteca JavaScript de Adobe Target at. js.
seo-title: Información sobre la función adobe. target. getoffers (options) para la biblioteca JavaScript de Adobe Target at. js.
solution: Target
subtopic: Primeros pasos
title: adobe.target.getOffer(options)
topic: Standard
translation-type: tm+mt
source-git-commit: cc7dc21321816e7f71b67e31abc0855184a285c6

---


# adobe. target. getoffers (options) - at. js 2. x

Esta función le permite recuperar varias ofertas pasando varios mboxes. Además, se pueden recuperar varias ofertas para todas las vistas de actividades activas.

>[!NOTE]
>
>Esta función se introdujo en at. js 2. x. Esta función no está disponible para la versión 1 de at. js.*x*.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| consumerId | Cadena | No | Si no se proporciona, el valor predeterminado es el mbox global del cliente. Esta clave se utiliza para generar el ID de datos suplementario utilizado para la integración de A4T. |
| de eventos | Objeto | Sí | Consulte la tabla Solicitudes a continuación. |
| timeout | Número | No | Tiempo de espera de solicitud. Si no se especifica, se usará el tiempo de espera predeterminado en at.js. |

## Solicitud

| Nombre del campo | ¿Requerido? | Limitaciones | Descripción |
| --- | --- | --- | --- |
| solicitud &gt; id | No |  | Uno de `tntId`, `thirdPartyId` o `marketingCloudVisitorId` es obligatorio. |
| Solicitud &gt; ID &gt; thirdPartyId | No | Tamaño máximo = 128 |  |  |
| Solicitud &gt; experiencecloud | No |  |  |
| Solicitud &gt; experiencecloud &gt; analytics | No |  | Integración de Adobe Analytics |
| Solicitud &gt; experiencecloud &gt; analytics &gt; registro | No | Se debe implementar lo siguiente en la página:<ul><li>Servicio de ID de visitante</li><li>Appmeasurement. js</li></ul> | Se admiten los siguientes valores:<br>**client_ side**: Cuando se especifique, se devolverá una carga útil de Analytics al llamador que debe utilizarse para enviarse a Adobe Analytics mediante la API de inserción de datos.<br>**server_ side**: Este es el valor predeterminado en el que el back-backend de Target y Analytics usará el SDID para unir las llamadas con fines de informes. |
| Solicitud &gt; Captura previa | No |  |  |
| Solicitud &gt; Captura previa &gt; Vistas | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe empezar con “perfil”<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Pase parámetros para utilizarlos para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; profileParameters | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud de nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe empezar con “perfil” | Pase parámetros de perfil para utilizarlos para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Producto | No |  |  |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Producto &gt; Id. | No | Tamaño máximo<br>no vacío = 128 | Pase las ID de producto para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Producto &gt; categoryId | No | Tamaño máximo<br>no vacío = 128 | Pase las ID de categoría de producto para que se utilicen para recuperar vistas relevantes en las actividades. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Pedido | No |  |  |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Pedido &gt; Id. | No | Longitud máxima = 250 | Pase las ID de pedido para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Pedido &gt; Total | No | Total `>=` 0 | Pase los totales del pedido para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Captura previa &gt; Vistas &gt; Pedido &gt; purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor 50<br><br>Longitud total de la ID de producto concatenado y separado por una coma `<=` 250 | Pase las ID de productos comprados para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud &gt; Ejecutar | No |  |  |
| Solicitud &gt; Ejecutar &gt; pageLoad | No |  |  |
| Solicitud &gt; Ejecutar &gt; pageLoad &gt; Parámetros | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre`<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe comenzar con “perfil”.<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Recupere ofertas con parámetros especificados cuando se carga la página. |
| Solicitar &gt; Ejecutar &gt; pageLoad &gt; profileParameters | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=`256<br>El nombre no debe comenzar con “perfil”. | Recupere ofertas con parámetros de perfil especificados cuando se carga la página. |
| Solicitar &gt; Ejecutar &gt; pageLoad &gt; Producto | No |  |  |
| Solicitud &gt; Ejecutar &gt; pageLoad &gt; Producto &gt; Id. | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas con ID de productos especificadas cuando se carga la página. |
| Solicitud &gt; Ejecutar &gt; pageLoad &gt; Producto &gt; categoryId | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas con ID de categoría de productos especificadas cuando se carga la página. |
| Solicitar &gt; Ejecutar &gt; pageLoad &gt;Pedido | No |  |  |
| Solicitar &gt; Ejecutar &gt; pageLoad &gt; Pedido &gt; ID | No | Longitud máxima = 250 | Recupere ofertas con ID de pedidos especificados cuando se carga la página. |
| Solicitar &gt; Ejecutar &gt; pageLoad &gt; Pedido &gt; Total | No | `>=` 0 | Recupere ofertas con totales de pedidos especificados cuando se carga la página. |
| Solicitud &gt; Ejecutar &gt; pageLoad &gt; Pedido &gt; purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor 50<br><br>Longitud total de la ID de producto concatenado y separado por una coma `<=` 250 | Recupere ofertas con ID de productos comprados cuando se carga la página. |
| Solicitud &gt; Ejecutar &gt; mboxes | No | Tamaño máximo = 50<br>Sin elementos nulos |  |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox | Sí | Tamaño máximo<br>Sin sufijo “-clicked”<br>no vacío = 250<br>Caracteres permitidos: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nombre del mbox. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Índice | Sí | Sin<br>Único<br>`>=` 0 | Tenga en cuenta que el índice no representa el orden en que se procesarán los mboxes. Al igual que en una página web con varios mboxes regionales, no se puede especificar el orden en que se procesarán. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Parámetros | No | Recuento máximo = 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe comenzar con “perfil”.<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Recupere ofertas para un mbox determinado con los parámetros especificados. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; profileParameters | No | Recuento máximo = 50<br>Nombre no en blanco<br>Longitud del nombre`<=` 128<br>Valor de longitud `<=`256<br>El nombre no debe comenzar con “perfil”. | Recupere ofertas para un mbox determinado con los parámetros de perfil especificados. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Producto | No |  |  |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Producto &gt; ID | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas para un mbox determinado con los ID de producto especificados. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Producto &gt; categoryId | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas para un mbox determinado con las ID de categoría de producto especificados. |
| Solicitar &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Pedido | No |  |  |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Pedido &gt; ID | No | Longitud máxima = 250 | Recupere ofertas para un mbox determinado con las ID de pedidos especificados. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Pedido &gt; Total | No | `>=` 0 | Recupere ofertas para un mbox determinado con los totales de pedidos especificados. |
| Solicitud &gt; Ejecutar &gt; mboxes &gt; mbox &gt; Pedido &gt; purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor = 50<br><br>Longitud total de ID de productos concatenados y separados por comas `<=` 250 | Recupere ofertas para un mbox determinado con las ID de pedido especificada del producto comprado. |

## Llame a `getOffers()` para todas las vistas

```
adobe.target.getOffers({
    prefetch: {
      views: []
    }
  }
});
```

## Llame a `getOffers()` para recuperar las vistas más recientes con los parámetros pasado y de perfil

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## Llame a `getOffers()` para recuperar mboxes con parámetros y parámetros de perfil pasados.

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## Realice una llamada a getoffers () para recuperar la carga útil de Analytics desde el lado del cliente

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**Respuesta**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

La carga útil se puede reenviar a Adobe Analytics a través de [la API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Buscar y procesar datos de varios mboxes mediante getoffers () y applyoffers () {#multiple}

at. js 2. x le permite recuperar varios mboxes mediante `getOffers()` la API. También puede recuperar datos para varios mboxes y, a continuación, utilizar `applyOffers()` para procesar los datos en diferentes ubicaciones identificadas por un selector de CSS.

El siguiente ejemplo muestra una página HTML sencilla con at. js 2. x implementada:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

Supongamos que tiene tres contenedores que desea modificar mediante el contenido recibido [!DNL Target]. Puede construir una sola solicitud para tres mboxes en los que cada mbox tiene contenido que procesar en el contenedor respectivo.

La solicitud y el código de procesamiento pueden tener el aspecto siguiente:

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

En `request > prefetch > mboxes` la sección, hay tres mboxes diferentes. Si la solicitud se completó correctamente, recibirá la respuesta de cada mbox de `response > prefetch > mboxes`. Una vez que tenga las respuestas y las ubicaciones que desee utilizar para procesar, puede invocar `applyOffers()` para procesar el contenido obtenido [!DNL Target]. En este ejemplo tenemos la siguiente asignación:

* mbox 1 &gt; selector CSS # container 1
* mbox 2 &gt; selector CSS # container 2
* mbox 3 &gt; selector CSS # container 3

Este ejemplo utiliza la variable count para construir los selectores CSS. En un escenario real, podría utilizar una asignación diferente entre el selector y el mbox CSS.

Tenga en cuenta que este ejemplo utiliza `prefetch > mboxes`, pero también puede `execute > mboxes`utilizarlo. Asegúrese de que, si utiliza la precarga en `getOffers()`, también debe utilizar la precarga en `applyOffers()` la invocación.
