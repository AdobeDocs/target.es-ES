---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Información sobre la función targetGlobalSettings() para la biblioteca JavaScript at.js de Adobe Target.
title: targetGlobalSettings()
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 38%

---


# targetGlobalSettings()

En lugar de definir la configuración en la interfaz de usuario Standard/Premium de [!DNL Target], puede reemplazar la configuración de la biblioteca at.js mediante `targetGlobalSettings()` o mediante las API de REST.

Hay casos de uso, especialmente cuando at.js se entrega a través de la [!DNL Dynamic Tag Management] (DTM), en que se necesita anular algunas de estas configuraciones.

## Configuración {#section_42C759AE9B524A43B8659018677224B8}

Las configuraciones que se pueden anular son las siguientes:

### bodyHiddenStyle

* **Tipo**: String
* **Valor** predeterminado: body { opacity: 0 }
* **Descripción**: Se utiliza únicamente cuando  `globalMboxAutocreate === true` se minimiza la posibilidad de parpadeo.

   Para obtener más información, consulte [Cómo gestiona at.js el parpadeo](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

### bodyHidingEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Se utiliza para controlar el parpadeo cuando  `target-global-mbox` se utiliza para entregar ofertas creadas en el Compositor de experiencias visuales, también conocidas como ofertas visuales.

### clientCode

* **Tipo**: String
* **Valor** predeterminado: Valor definido mediante la interfaz de usuario.
* **Descripción**: Representa el código de cliente.

### cookieDomain

* **Tipo**: String
* **Valor** predeterminado: Si es posible, configure el dominio de nivel superior.
* **Descripción**: Representa el dominio utilizado al guardar cookies.

### crossDomain

* **Tipo**: String
* **Valor** predeterminado: Valor definido mediante la interfaz de usuario.
* **Descripción**: Indica si el seguimiento entre dominios está habilitado o no. Los valores permitidos son: deshabilitada, habilitada o x-solamente.

### cspScriptNonce

* **Tipo**: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.
* **Valor** predeterminado: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.
* **Descripción**: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.

### cspStyleNonce

* **Tipo**: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.
* **Valor** predeterminado: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.
* **Descripción**: Consulte  [Content Security ](#content-security) Policy (Política de seguridad del contenido) a continuación.

### dataProviders

* **Tipo**: Consulte  [Proveedores ](#data-providers) de datos a continuación.
* **Valor** predeterminado: Consulte  [Proveedores ](#data-providers) de datos a continuación.
* **Descripción**: Consulte  [Proveedores ](#data-providers) de datos a continuación.

### defaultContentHiddenStyle

* **Tipo**: String
* **Valor** predeterminado: visibility: hidden
* **Descripción**: Solo se utiliza para ajustar mboxes que utilizan DIV con el nombre de clase &quot;mboxDefault&quot; y se ejecutan mediante  `mboxCreate()`,  `mboxUpdate()`o  `mboxDefine()` para ocultar contenido predeterminado.

### defaultContentVisibleStyle

* **Tipo**: String
* **Valor** predeterminado: visibility: visible
* **Descripción**: Solo se utiliza para ajustar mboxes que utilizan DIV con el nombre de clase &quot;mboxDefault&quot; y que se ejecutan mediante  `mboxCreate()`,  `mboxUpdate()`o  `mboxDefine()` para mostrar la oferta aplicada, si existe contenido predeterminado.

### deviceIdLifetime

* **Tipo**: Número
* **Valor** predeterminado: 63244800000 ms = 2 años
* **Descripción**: La cantidad de tiempo que  `deviceId` se conserva en las cookies.

>[!NOTE]
>
>La configuración de deviceIdLifetime se puede sobrescribir en la versión 2.3.1 o posterior de at.js.

### enabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando está habilitada, se ejecuta automáticamente una  [!DNL Target] solicitud para recuperar experiencias y la manipulación DOM para procesar las experiencias. Además, las llamadas [!DNL Target] se pueden ejecutar manualmente mediante `getOffer(s)` / `applyOffer(s)`.

   Cuando se deshabilita, las solicitudes [!DNL Target] no se ejecutan de forma automática o manual.

### globalMboxAutoCreate

* **Tipo**: Número
* **Valor** predeterminado: Valor definido mediante la interfaz de usuario.
* **Descripción**: Indica si la solicitud de mbox global debe activarse o no.

### imsOrgId

* **Tipo**: Cadena
* **Valor** predeterminado: true
* **Descripción**: Representa el identificador de organización de IMS.

### optoutEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: false
* **Descripción**: Indica si Destinatario debe llamar a la  `isOptedOut()` función de API de Visitante. Esto forma parte de la habilitación de Device Graph.

### overrideMboxEdgeServer

* **Tipo**: Booleano
* **Valor** predeterminado: true (true a partir de la versión 1.6.2 de at.js)
* **Descripción**: Indica si deberíamos usar  `<clientCode>.tt.omtrdc.net` dominio o  `mboxedge<clusterNumber>.tt.omtrdc.net` dominio.

   Si este valor es true, el dominio `mboxedge<clusterNumber>.tt.omtrdc.net` se guardará en una cookie. Actualmente no funciona con [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) cuando se utilizan versiones de at.js anteriores a at.js 1.8.2 y at.js 2.3.1. Si este es un problema para usted, considere [actualizar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) a una versión más reciente y compatible.

### overrideMboxEdgeServerTimeout

* **Tipo**: Número
* **Valor** predeterminado: 1860000 => 31 minutos
* **Descripción**: Indica la duración de la cookie que contiene el  `mboxedge<clusterNumber>.tt.omtrdc.net` valor.

### pageLoadEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando está habilitada, recupera automáticamente experiencias que deben devolverse al cargar la página.

### secureOnly

* **Tipo**: Booleano
* **Valor** predeterminado: false
* **Descripción**: Indica si at.js debe utilizar solo HTTPS o si se le debe permitir cambiar entre HTTP y HTTPS según el protocolo de la página.

### selectorsPollingTimeout

* **Tipo**: Número
* **Valor** predeterminado: 5000 ms = 5 s
* **Descripción**: En at.js 0.9.6,  [!DNL Target] se ha introducido esta nueva configuración que se puede anular mediante  `targetGlobalSettings`.

   La configuración `selectorsPollingTimeout` representa cuánto tiempo está dispuesto el cliente a esperar a que aparezcan en la página todos los elementos identificados por selectores.

   Las actividades creadas por medio del Compositor de experiencias visuales (VEC) tienen ofertas que contienen selectores.

### serverDomain

* **Tipo**: String
* **Valor** predeterminado: Valor definido mediante la interfaz de usuario.
* **Descripción**: Representa el servidor Edge de Destinatario.

### serverState

* **Tipo**: Consulte  [Personalización ](#server-state) híbrida a continuación.
* **Valor** predeterminado: Consulte  [Personalización ](#server-state) híbrida a continuación.
* **Descripción**: Consulte  [Personalización ](#server-state) híbrida a continuación.

### timeout

* **Tipo**: Número
* **Valor** predeterminado: Valor definido mediante la interfaz de usuario.
* **Descripción**: Representa el tiempo de espera de solicitud  [!DNL Target] Edge.

### viewsEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando está habilitada, recupera automáticamente vistas que deben devolverse al cargar la página. Las vistas se admiten en at.js 2.Solamente *x.*

### visitorApiTimeout

* **Tipo**: Número
* **Valor** predeterminado: 2000 ms = 2 s
* **Descripción**: Representa el tiempo de espera de  [!UICONTROL Visitante ] APIrequest.

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** > **[!UICONTROL Editar la configuración de at.js]** > **[!UICONTROL Configuración de código]** > **[!UICONTROL Encabezado de biblioteca]**.

En el campo Encabezado de la biblioteca se puede introducir JavaScript de formato libre. El código de personalización debe parecerse al del ejemplo siguiente:

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Proveedores de datos {#data-providers}

Esta configuración permite a los clientes recopilar información de proveedores de datos de terceros, como Demandbase, BlueKai y servicios personalizados, y pasar los datos a Target como parámetros de mbox en la solicitud global de mbox. Admite la recopilación de datos de múltiples proveedores a través de solicitudes de desincronización y sincronización. El uso de este enfoque facilita la administración del parpadeo del contenido predeterminado de la página, al tiempo que incluye tiempos de espera independientes para cada proveedor para limitar el impacto en el rendimiento de la página.

>[!NOTE]
>
>Proveedores de datos requiere [!DNL at.js] 1.3 o posterior.

Los vídeos siguientes contienen más información:

| Vídeo | Descripción |
|--- |--- |
| [Uso de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-feature-video-use.html) | Proveedores de datos es una funcionalidad que permite pasar fácilmente datos de terceros a Target. Un tercero podría ser un servicio de pronóstico del clima, un DMP o incluso su propio servicio web. Puede usar estos datos para crear audiencias, dirigir contenido y enriquecer el perfil del visitante. |
| [Implementación de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Detalles de implementación y ejemplos de cómo usar la función dataProviders de Adobe Target para recuperar datos de proveedores de datos de terceros y pasarlos en la solicitud de Target. |

La configuración `window.targetGlobalSettings.dataProviders` es una matriz de proveedores de datos.

Cada proveedor de datos tiene la siguiente estructura:

| Clave | Tipo | Descripción |
|--- |--- |--- |
| name | Cadena | Nombre del proveedor |
| version | Cadena | Versión del proveedor. Esta clave se usará para la evolución del proveedor. |
| timeout | Número | Representa el tiempo de espera del proveedor si se trata de una solicitud de red.  Esta clave es opcional. |
| provider | Función | La función que contiene la lógica de búsqueda de datos del proveedor.<br>La función tiene un solo parámetro requerido: `callback`. El parámetro de llamada de retorno es una función que debe invocarse solo cuando los datos se han recuperado correctamente o si hay un error.<br>La devolución de llamada espera dos parámetros:<ul><li>error: indica si ocurrió un error. Si todo está bien, entonces este parámetro debe establecerse en nulo.</li><li>params: un objeto JSON, que representa los parámetros que se enviarán en una solicitud de Target.</li></ul> |

El siguiente ejemplo muestra dónde está utilizando la ejecución de sincronización el proveedor de datos:

```javascript
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

Después de que at.js procese `window.targetGlobalSettings.dataProviders`, la solicitud de Target contiene un nuevo parámetro: `t1=1`.

El siguiente es un ejemplo de si los parámetros que desea agregar a la solicitud de Target se obtienen de un servicio de terceros, como BlueKai, Demandbase, y así sucesivamente:

```javascript
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

Después de que at.js procese `window.targetGlobalSettings.dataProviders`, la solicitud de Target contiene parámetros adicionales: `t1=1`, `t2=2` y `t3=3`.

El siguiente ejemplo utiliza proveedores de datos para recopilar datos de la API meteorológica y enviarlos como parámetros en una solicitud de Target. La solicitud de Target tendrá parámetros adicionales, como `country` y `weatherCondition`.

```javascript
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

Tenga en cuenta lo siguiente al trabajar con la configuración `dataProviders`:

* Si los proveedores de datos agregados a `window.targetGlobalSettings.dataProviders` son asincrónicos, se ejecutarán en paralelo. La solicitud de API del visitante se ejecutará en paralelo con las funciones agregadas a `window.targetGlobalSettings.dataProviders` para permitir un tiempo de espera mínimo.
* at.js no intentará almacenar en caché los datos. Si el proveedor de datos obtiene datos solo una vez, el proveedor de datos debe asegurarse de que los datos estén en caché y, cuando se invoque la función del proveedor, sirva los datos de caché para la segunda invocación.

## Directiva de seguridad de contenido {#content-security}

at.js 2.3.0+ admite la configuración de las funciones de la directiva de seguridad de contenido en las etiquetas SCRIPT y STYLE que se anexan a la página DOM al aplicar ofertas de Destinatario entregadas.

Las funciones de SCRIPT y STYLE deben configurarse en `targetGlobalSettings.cspScriptNonce` y `targetGlobalSettings.cspStyleNonce` en consecuencia, antes de cargar at.js 2.3.0+. Vea un ejemplo a continuación:

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

Una vez especificadas las configuraciones `cspScriptNonce` y `cspStyleNonce`, at.js 2.3.0+ las establece como atributos nonce en todas las etiquetas SCRIPT y STYLE que anexa al DOM al aplicar ofertas de Destinatario.

## Personalización híbrida {#server-state}

`serverState` es una configuración disponible en at.js v2.2+ que puede utilizarse para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Destinatario. La integración híbrida significa que se utiliza at.js v2.2+ en el cliente y la API de envío o un SDK de Destinatario en el servidor para ofrecer experiencias. `serverState` proporciona a at.js v2.2+ la capacidad de aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está ofreciendo.

### Requisitos previos

Debe tener una integración híbrida de [!DNL Target].

* **Del lado** del servidor: Debe utilizar la nueva  [API ](https://developers.adobetarget.com/api/delivery-api/) de envío o los SDK de  [Destinatario](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Cliente**: Debe utilizar  [at.js versión 2.2 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### Ejemplos de código

Para comprender mejor cómo funciona esto, vea los ejemplos de código siguientes que tendría en su servidor. El código supone que está utilizando el [SDK de Node.js de Destinatario](https://github.com/adobe/target-nodejs-sdk).

```javascript
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

Un objeto JSON de muestra `serverState` para la recuperación previa de vistas tiene el siguiente aspecto:

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

Después de cargar la página en el explorador, at.js aplica todas las [!DNL Target] ofertas de `serverState` inmediatamente, sin activar ninguna llamada de red contra el borde [!DNL Target]. Además, at.js sólo oculta los elementos DOM para los que hay ofertas [!DNL Target] disponibles en el servidor de recuperación de contenido, lo que tiene un impacto positivo en el rendimiento de carga de página y en la experiencia del usuario final.

### Notas importantes

Tenga en cuenta lo siguiente al utilizar `serverState`:

* En este momento, at.js v2.2 solo admite la entrega de experiencias mediante serverState para:

   * Actividades creadas por VEC que se ejecutan al cargar la página.
   * Vistas prebuscadas.

      En el caso de SPA que utilice [!DNL Target] Vistas y `triggerView()` en la API de at.js, at.js v2.2 almacena en caché el contenido de todas las Vistas recuperadas previamente en el servidor y lo aplica tan pronto como se activa cada Vista mediante `triggerView()`, de nuevo sin activar ninguna llamada de recuperación de contenido adicional al Destinatario.

   * **Nota**: Actualmente, los mboxes recuperados en el servidor no son compatibles con  `serverState`.

* Al aplicar `serverState `ofertas, at.js tiene en cuenta las configuraciones `pageLoadEnabled` y `viewsEnabled`, por ejemplo: las ofertas de carga de página no se aplicarán si la configuración `pageLoadEnabled` es falsa.

   Para activar esta configuración, habilite el conmutador en **[!UICONTROL Administración] > [!UICONTROL Implementación] > [!UICONTROL Editar] > [!UICONTROL Carga de página habilitada]**.

   ![Configuración habilitada de carga de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Si utiliza `serverState` y etiquetas `<script>` en el contenido devuelto, asegúrese de que el contenido HTML utilice `<\/script>` en lugar de `</script>`. Si utiliza `</script>`, el explorador interpreta `</script>` como el final de un SCRIPT en línea y podría romper la página HTML.

### Recursos adicionales

Para obtener más información sobre cómo `serverState` funciona, consulte los siguientes recursos:

* [Código de muestra](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Aplicación de una sola página (SPA) aplicación de ejemplo con  `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
