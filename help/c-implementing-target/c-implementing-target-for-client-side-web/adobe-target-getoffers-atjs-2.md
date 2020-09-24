---
keywords: adobe.target.getOffers;getOffers;getoffers;get offers;at.js;functions;function
description: Información sobre la función adobe.target.getOffers(options) para la biblioteca de JavaScript at.js de Adobe Target.
title: Información sobre la función adobe.target.getOffers() para la biblioteca de JavaScript at.js de Adobe Target.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 998579315ce8390cc9e2eb25434be19337724526
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 95%

---


# adobe.target.getOffers(options): at.js 2.x

Esta función le permite recuperar varias ofertas pasando varios mboxes. Además, se pueden recuperar varias ofertas para todas las vistas de actividades activas.

>[!NOTE]
>
>Esta función se introdujo en at.js 2.x. Esta función no está disponible para la at.js versión 1.*x*.

| Clave | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| consumerId | Cadena | No | Si no se proporciona, el valor predeterminado es el mbox global del cliente. Esta clave se utiliza para generar el ID de datos suplementario utilizado para la integración de A4T. Esta clave es una cadena única por visitante. |
| de eventos | Objeto | Sí | Consulte la tabla Solicitudes a continuación. |
| timeout | Número | No | Tiempo de espera de solicitud. Si no se especifica, se usará el tiempo de espera predeterminado en at.js. |

## Solicitud

>[!NOTE]
>
>Consulte la documentación [de la API de](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) Envío para obtener información sobre los tipos aceptables de todos los campos que se enumeran a continuación.

| Nombre del campo | ¿Requerido? | Limitaciones | Descripción |
| --- | --- | --- | --- |
| solicitud > id | No |  | Uno de `tntId`, `thirdPartyId` o `marketingCloudVisitorId` es obligatorio. |
| Solicitud > ID > thirdPartyId | No | Tamaño máximo = 128 |  |  |
| Request > experienceCloud | No |  |  |
| Request > experienceCloud > analytics | No |  | Integración de Adobe Analytics |
| Request > experienceCloud > analytics > logging | No | Se debe implementar lo siguiente en la página:<ul><li>Servicio de ID de visitante</li><li>AppMeasurement.js</li></ul> | Se admiten los siguientes valores:<br>**client_side**: Cuando se especifique, se devolverá una carga útil de Analytics al que ha realizado la llamada, que debe utilizarse para enviar a Adobe Analytics mediante la API de inserción de datos.<br>**server_side**: Este es el valor predeterminado en el que el backend de Target y Analytics usará el SDID para unir las llamadas con fines de informes. |
| Solicitud > Captura previa | No |  |  |
| Solicitud > Captura previa > Vistas | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe empezar con “perfil”<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Pase parámetros para utilizarlos para recuperar vistas relevantes en actividades activas. |
| Solicitud > Captura previa > Vistas > profileParameters | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud de nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe empezar con “perfil” | Pase parámetros de perfil para utilizarlos para recuperar vistas relevantes en actividades activas. |
| Solicitud > Captura previa > Vistas > Producto | No |  |  |
| Solicitud > Captura previa > Vistas > Producto > Id. | No | Tamaño máximo<br>no vacío = 128 | Pase los ID de producto para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud > Captura previa > Vistas > Producto > categoryId | No | Tamaño máximo<br>no vacío = 128 | Pase los ID de categoría de producto para que se utilicen para recuperar vistas relevantes en las actividades. |
| Solicitud > Captura previa > Vistas > Pedido | No |  |  |
| Solicitud > Captura previa > Vistas > Pedido > Id. | No | Longitud máxima = 250 | Pase los ID de pedido para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud > Captura previa > Vistas > Pedido > Total | No | Total `>=` 0 | Pase los totales del pedido para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud > Captura previa > Vistas > Pedido > purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor 50<br><br>Longitud total del ID de producto concatenado y separado por una coma `<=` 250 | Pase los ID de productos comprados para que se utilicen para recuperar vistas relevantes en actividades activas. |
| Solicitud > Ejecutar | No |  |  |
| Solicitud > Ejecutar > pageLoad | No |  |  |
| Solicitud > Ejecutar > pageLoad > Parámetros | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre`<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe comenzar con “perfil”.<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Recupere ofertas con parámetros especificados cuando se carga la página. |
| Solicitar > Ejecutar > pageLoad > profileParameters | No | Recuento máximo 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=`256<br>El nombre no debe comenzar con “perfil”. | Recupere ofertas con parámetros de perfil especificados cuando se carga la página. |
| Solicitar > Ejecutar > pageLoad > Producto | No |  |  |
| Solicitud > Ejecutar > pageLoad > Producto > Id. | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas con ID de productos especificadas cuando se carga la página. |
| Solicitud > Ejecutar > pageLoad > Producto > categoryId | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas con ID de categoría de productos especificadas cuando se carga la página. |
| Solicitar > Ejecutar > pageLoad >Pedido | No |  |  |
| Solicitar > Ejecutar > pageLoad > Pedido > ID | No | Longitud máxima = 250 | Recupere ofertas con ID de pedidos especificados cuando se carga la página. |
| Solicitar > Ejecutar > pageLoad > Pedido > Total | No | `>=` 0 | Recupere ofertas con totales de pedidos especificados cuando se carga la página. |
| Solicitud > Ejecutar > pageLoad > Pedido > purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor 50<br><br>Longitud total del ID de producto concatenado y separado por una coma `<=` 250 | Recupere ofertas con ID de productos comprados cuando se carga la página. |
| Solicitud > Ejecutar > mboxes | No | Tamaño máximo = 50<br>Sin elementos nulos |  |
| Solicitud > Ejecutar > mboxes > mbox | Sí | Tamaño máximo<br>Sin sufijo “-clicked”<br>no vacío = 250<br>Caracteres permitidos: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nombre del mbox. |
| Solicitud > Ejecutar > mboxes > mbox > Índice | Sí | Sin<br>Único<br>`>=` 0 | Tenga en cuenta que el índice no representa el orden en que se procesarán los mboxes. Al igual que en una página web con varios mboxes regionales, no se puede especificar el orden en que se procesarán. |
| Solicitud > Ejecutar > mboxes > mbox > Parámetros | No | Recuento máximo = 50<br>Nombre no en blanco<br>Longitud del nombre `<=` 128<br>Valor de longitud `<=` 5000<br>El nombre no debe comenzar con “perfil”.<br>Nombres no permitidos: “orderId”, “orderTotal”, “productPurchasedId” | Recupere ofertas para un mbox determinado con los parámetros especificados. |
| Solicitud > Ejecutar > mboxes > mbox > profileParameters | No | Recuento máximo = 50<br>Nombre no en blanco<br>Longitud del nombre`<=` 128<br>Valor de longitud `<=`256<br>El nombre no debe comenzar con “perfil”. | Recupere ofertas para un mbox determinado con los parámetros de perfil especificados. |
| Solicitud > Ejecutar > mboxes > mbox > Producto | No |  |  |
| Solicitud > Ejecutar > mboxes > mbox > Producto > ID | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas para un mbox determinado con los ID de producto especificados. |
| Solicitud > Ejecutar > mboxes > mbox > Producto > categoryId | No | Tamaño máximo<br>no vacío = 128 | Recupere ofertas para un mbox determinado con los ID de categoría de producto especificados. |
| Solicitar > Ejecutar > mboxes > mbox > Pedido | No |  |  |
| Solicitud > Ejecutar > mboxes > mbox > Pedido > ID | No | Longitud máxima = 250 | Recupere ofertas para un mbox determinado con los ID de pedidos especificados. |
| Solicitud > Ejecutar > mboxes > mbox > Pedido > Total | No | `>=` 0 | Recupere ofertas para un mbox determinado con los totales de pedidos especificados. |
| Solicitud > Ejecutar > mboxes > mbox > Pedido > purchasedProductIds | No | Valores no vacíos<br>Longitud máxima de cada valor = 50<br><br>Longitud total de ID de productos concatenados y separados por comas `<=` 250 | Recupere ofertas para un mbox determinado con los ID de pedido especificada del producto comprado. |

## Llame a `getOffers()` para todas las vistas

```
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
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

## Realice una llamada a getOffers() para recuperar la carga útil de Analytics desde el lado del cliente

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

La carga útil se puede reenviar a Adobe Analytics mediante la API [de inserción](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)de datos.

## Buscar y procesar datos de varios mboxes a través de getOffers() y applyOffers() {#multiple}

at.js 2.x le permite recuperar varios mboxes a través de la API de `getOffers()`. También puede buscar datos para varios mboxes y, después, utilizar `applyOffers()` para representar los datos en diferentes ubicaciones identificadas por un selector de CSS.

El siguiente ejemplo muestra una página HTML sencilla con at.js 2.x implementado:

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

Supongamos que tiene tres contenedores que desea modificar a través del contenido recibido de [!DNL Target]. Puede construir una sola solicitud para tres mboxes en los que cada uno tiene contenido que procesar en su respectivo contenedor.

La solicitud y el código de procesamiento pueden tener el siguiente aspecto:

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

En la sección `request > prefetch > mboxes`, hay tres mboxes diferentes. Si la solicitud se completó correctamente, recibe la respuesta de `response > prefetch > mboxes` para cada mbox. Una vez que tenga las respuestas y las ubicaciones que desee utilizar para la representación, puede invocar a `applyOffers()` para representar el contenido obtenido de [!DNL Target]. En este ejemplo tenemos la siguiente asignación:

* mbox 1 > selector CSS #contenedor 1
* mbox 2 > selector CSS #contenedor 2
* mbox 3 > selector CSS #contenedor 3

Este ejemplo utiliza la variable de recuento para construir los selectores CSS. En una situación real, podría utilizar una asignación diferente entre el selector CSS y el mbox.

Tenga en cuenta que este ejemplo utiliza `prefetch > mboxes`, pero también puede utilizar `execute > mboxes`. Asegúrese de que, si utiliza la crga previa en `getOffers()`, también debe utilizar la carga previa en la invocación de `applyOffers()`.

## Llamada `getOffers()` para realizar una pageLoad

El siguiente ejemplo muestra cómo realizar una pageLoad usando getOffers() con at.js 2.*x* 

```
adobe.target.getOffers({
    request: {
        execute: {
            pageLoad: {
                parameters: {}
            }
        }
    }
});
```
