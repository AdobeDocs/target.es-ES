---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalSettings;global settings;at.js;funciones;función;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossDomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentContent VisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Utilice la función targetGlobalSettings() para las API de Adobe [!DNL Target] at.js JavaScript library to override settings instead of using the [!DNL Target] UI o REST.
title: ¿Cómo utilizo la función targetGlobalSettings() ?
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: 4fa34643969c1f60ca79e195c1bca4043adadcd9
workflow-type: tm+mt
source-wordcount: '2317'
ht-degree: 30%

---

# targetGlobalSettings()

En lugar de definir la configuración en la interfaz de usuario Standard/Premium de [!DNL Target], puede reemplazar la configuración de la biblioteca at.js mediante `targetGlobalSettings()` o mediante las API de REST.

## Configuración {#section_42C759AE9B524A43B8659018677224B8}

Las configuraciones que se pueden anular son las siguientes:

### bodyHiddenStyle

* **Tipo**: String
* **Valor** predeterminado: body { opacity: 0 }
* **Descripción**: Solo se usa cuando  `globalMboxAutocreate === true` para minimizar el parpadeo.

   Para obtener más información, consulte [Cómo gestiona at.js el parpadeo](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

### bodyHidingEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Se utiliza para controlar el parpadeo cuando  `target-global-mbox` se utiliza para publicar ofertas creadas en el Compositor de experiencias visuales, también denominadas ofertas visuales.

### clientCode

* **Tipo**: String
* **Valor** predeterminado: Valor establecido mediante la interfaz de usuario.
* **Descripción**: Representa el código de cliente.

### cookieDomain

* **Tipo**: String
* **Valor** predeterminado: Si es posible, establezca en el dominio de nivel superior.
* **Descripción**: Representa el dominio utilizado al guardar cookies.

### crossDomain

* **Tipo**: String
* **Valor** predeterminado: Valor establecido mediante la interfaz de usuario.
* **Descripción**: Indica si el seguimiento entre dominios está habilitado o no. Los valores permitidos son: desactivado, habilitado o x-solamente.

### cspScriptNonce

* **Tipo**: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.
* **Valor** predeterminado: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.
* **Descripción**: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.

### cspStyleNonce

* **Tipo**: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.
* **Valor** predeterminado: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.
* **Descripción**: Consulte  [Política de seguridad de ](#content-security) contenido a continuación.

### dataProviders

* **Tipo**: Consulte  [Proveedores de ](#data-providers) datos a continuación.
* **Valor** predeterminado: Consulte  [Proveedores de ](#data-providers) datos a continuación.
* **Descripción**: Consulte  [Proveedores de ](#data-providers) datos a continuación.

### decisioningMethod {#on-device-decisioning}

* **Tipo**: String
* **Valor** predeterminado: del lado del servidor
* **Otros valores**: en el dispositivo, híbrido
* **Descripción**: Consulte Métodos de toma de decisiones a continuación.

   **Métodos de decisión**

   Con la toma de decisiones en dispositivos, Target introduce una nueva configuración denominada [!UICONTROL Método de decisión] que dicta cómo at.js entrega sus experiencias. El `decisioningMethod` tiene tres valores: solo del lado del servidor, solo en el dispositivo e híbrido. Cuando `decisioningMethod` se configura en `targetGlobalSettings()`, actúa como el método de toma de decisiones predeterminado para todas las decisiones [!DNL Target].

   **[!UICONTROL Solo]** del lado del servidor:

   [!UICONTROL Solo en el lado del servidor ] es el método de toma de decisiones predeterminado que se establece de forma predeterminada cuando at.js 2.5+ se implementa e implementa en las propiedades web.

   Usar [!UICONTROL solo del lado del servidor] como configuración predeterminada significa que todas las decisiones se toman en la red perimetral [!DNL Target], lo que implica una llamada al servidor de bloqueo. Este método puede introducir la latencia incremental, pero también ofrece beneficios importantes, como la posibilidad de aplicar las capacidades de aprendizaje automático de Target que incluyen [Recommendations](/help/c-recommendations/recommendations.md), [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) y [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md).

   Además, la mejora de sus experiencias personalizadas mediante el uso del perfil de usuario de Target, que se mantiene en todas las sesiones y canales, puede proporcionar potentes resultados para su empresa.

   Por último, [!UICONTROL server-side only] permite utilizar Adobe Experience Cloud y ajustar las audiencias a las que se puede dirigir mediante segmentos de Audience Manager y Adobe Analytics.

   **[!UICONTROL Solo]** en el dispositivo:

   [!UICONTROL En el dispositivo ] solo es el método de toma de decisiones que debe configurarse en at.js 2.5+ cuando las decisiones en el dispositivo deben utilizarse solo en todas las páginas web.

   La toma de decisiones en dispositivos puede ofrecer sus experiencias y actividades de personalización a una velocidad asombrosa, ya que las decisiones se toman a partir de un artefacto de reglas en caché que contiene todas las actividades que cumplen los requisitos para la toma de decisiones en dispositivos.

   Para obtener más información sobre las actividades que cumplen los requisitos para la toma de decisiones en el dispositivo, consulte la sección Funciones compatibles .

   Este método de toma de decisiones solo debe usarse si el rendimiento es muy crítico en todas las páginas que requieren decisiones de [!DNL Target]. Además, tenga en cuenta que cuando se selecciona este método de toma de decisiones, las actividades [!DNL Target] que no cumplen los requisitos para la toma de decisiones en el dispositivo no se entregarán ni ejecutarán. La biblioteca at.js 2.5+ está configurada para buscar solo el artefacto de reglas en caché para tomar decisiones.

   **Híbrido**:

    Actualice el método de toma de decisiones que debe establecerse en at.js 2.5+ cuando se deben ejecutar tanto la toma de decisiones en el dispositivo como las actividades que requieren una llamada de red a la red de Adobe Target Edge.

   Cuando administra actividades de toma de decisiones en el dispositivo y actividades del lado del servidor, puede resultar un poco complicado y tedioso pensar en cómo implementar y aprovisionar [!DNL Target] en sus páginas. Con hybrid como método de toma de decisiones, [!DNL Target] sabe cuándo debe realizar una llamada del servidor a la red de Adobe Target Edge para actividades que requieren ejecución del lado del servidor y también cuándo ejecutar únicamente decisiones en el dispositivo.

   El artefacto de reglas JSON incluye metadatos para informar a at.js de si un mbox tiene una actividad de servidor en ejecución o una actividad de toma de decisiones en el dispositivo. Este método de toma de decisiones garantiza que las actividades que desea realizar rápidamente se realicen mediante la toma de decisiones en el dispositivo y que, para las actividades que requieren una personalización basada en ML más potente, dichas actividades se realicen a través de la red Adobe Target Edge.

### defaultContentHiddenStyle

* **Tipo**: String
* **Valor** predeterminado: visibilidad: oculto
* **Descripción**: Solo se usa para ajustar mboxes que utilizan DIV con el nombre de clase &quot;mboxDefault&quot; y que se ejecutan a través de  `mboxCreate()`,  `mboxUpdate()` o  `mboxDefine()` para ocultar contenido predeterminado.

### defaultContentVisibleStyle

* **Tipo**: String
* **Valor** predeterminado: visibilidad: visible
* **Descripción**: Solo se usa para ajustar mboxes que utilizan DIV con el nombre de clase &quot;mboxDefault&quot; y que se ejecutan a través de  `mboxCreate()`,  `mboxUpdate()`, o  `mboxDefine()` para mostrar la oferta aplicada, si existe, o el contenido predeterminado.

### deviceIdLifetime

* **Tipo**: Número
* **Valor** predeterminado: 63244800000 ms = 2 años
* **Descripción**: La cantidad de tiempo que  `deviceId` se mantiene en las cookies.

>[!NOTE]
>
>La configuración deviceIdLifetime se puede sobrescribir en la versión 2.3.1 o posterior de at.js.

### enabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando está habilitada, se ejecuta automáticamente una  [!DNL Target] solicitud para recuperar experiencias y la manipulación DOM para procesar las experiencias. Además, las llamadas [!DNL Target] se pueden ejecutar manualmente mediante `getOffer(s)` / `applyOffer(s)`.

   Cuando está desactivado, las solicitudes [!DNL Target] no se ejecutan automática o manualmente.

### globalMboxAutoCreate

* **Tipo**: Número
* **Valor** predeterminado: Valor establecido mediante la interfaz de usuario.
* **Descripción**: Indica si la solicitud de mbox global debe activarse o no.

### imsOrgId

* **Tipo**: Cadena
* **Valor** predeterminado: true
* **Descripción**: Representa el ID de organización de IMS.

### optinEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: false
* **Descripción**:  [!DNL Target] proporciona soporte de funcionalidad opcional a través de  [!DNL Adobe Platform Launch] para ayudar a respaldar su estrategia de gestión de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de [!DNL Target]. También hay una opción a través de [!DNL Platform Launch] para aprobar previamente la etiqueta de [!DNL Target]. Para activar Opt-In en la biblioteca [!DNL Target] at.js, añada la configuración `optinEnabled=true`. En [!DNL Platform Launch] debe seleccionar &quot;habilitar&quot; en la lista desplegable [!UICONTROL Opt-In del RGPD] en la vista de instalación de la extensión de Launch. Consulte la [documentación del Platform launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obtener más información. Para obtener más información sobre esta configuración en relación con las normas de privacidad y protección de datos, incluido el Reglamento General de Protección de Datos (RGPD) de la Unión Europea y la Ley de Privacidad del Consumidor de California (CCPA), consulte [Reglamentos de privacidad y protección de datos](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

### optoutEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: false
* **Descripción**: Indica si Target debe llamar a la  `isOptedOut()` función de la API de visitante. Esto forma parte de la habilitación de Device Graph.

### overrideMboxEdgeServer

* **Tipo**: Booleano
* **Valor** predeterminado: true (verdadero a partir de la versión 1.6.2 de at.js)
* **Descripción**: Indica si se debe utilizar el  `<clientCode>.tt.omtrdc.net` dominio o el  `mboxedge<clusterNumber>.tt.omtrdc.net` dominio.

   Si este valor es true, el dominio `mboxedge<clusterNumber>.tt.omtrdc.net` se guardará en una cookie. Actualmente no funciona con [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) al utilizar versiones de at.js anteriores a at.js 1.8.2 y at.js 2.3.1. Si esto es un problema para usted, considere la posibilidad de [actualizar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) a una versión más reciente y compatible.

### overrideMboxEdgeServerTimeout

* **Tipo**: Número
* **Valor** predeterminado: 1860000 => 31 minutos
* **Descripción**: Indica la duración de la cookie que contiene el  `mboxedge<clusterNumber>.tt.omtrdc.net` valor .

### pageLoadEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando esté habilitado, recupere automáticamente las experiencias que deben devolverse al cargar la página.

### secureOnly

* **Tipo**: Booleano
* **Valor** predeterminado: false
* **Descripción**: Indica si at.js debería utilizar solo HTTPS o se le debería permitir alternar entre HTTP y HTTPS según el protocolo de la página.

### selectorsPollingTimeout

* **Tipo**: Número
* **Valor** predeterminado: 5000 ms = 5 s
* **Descripción**: En la versión 0.9.6 de at.js,  [!DNL Target] se ha introducido esta nueva configuración que se puede anular mediante  `targetGlobalSettings`.

   La configuración `selectorsPollingTimeout` representa cuánto está dispuesto a esperar el cliente para que todos los elementos identificados por selectores aparezcan en la página.

   Las actividades creadas por medio del Compositor de experiencias visuales (VEC) tienen ofertas que contienen selectores.

### serverDomain

* **Tipo**: String
* **Valor** predeterminado: Valor establecido mediante la interfaz de usuario.
* **Descripción**: Representa el servidor Edge de Target.

### serverState

* **Tipo**: Consulte  [Personalización ](#server-state) híbrida a continuación.
* **Valor** predeterminado: Consulte  [Personalización ](#server-state) híbrida a continuación.
* **Descripción**: Consulte  [Personalización ](#server-state) híbrida a continuación.

### timeout

* **Tipo**: Número
* **Valor** predeterminado: Valor establecido mediante la interfaz de usuario.
* **Descripción**: Representa el tiempo de espera de solicitud  [!DNL Target] perimetral.

### viewsEnabled

* **Tipo**: Booleano
* **Valor** predeterminado: true
* **Descripción**: Cuando esté habilitado, recupere automáticamente las vistas que deben devolverse al cargar la página. Las vistas son compatibles con at.js 2.Solamente *x.*

### visitorApiTimeout

* **Tipo**: Número
* **Valor** predeterminado: 2000 ms = 2 s
* **Descripción**: Representa el tiempo de espera de solicitud de  [!UICONTROL API de ] visitante.

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Esta función se puede definir antes de que se cargue at.js o en **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

En el campo Encabezado de la biblioteca se puede introducir JavaScript de formato libre. El código de personalización debe parecerse al del ejemplo siguiente:

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Proveedores de datos   {#data-providers}

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

## Política de seguridad de contenido {#content-security}

at.js 2.3.0+ es compatible con la configuración de nonces de Content Security Policy en las etiquetas SCRIPT y STYLE añadidas al DOM de la página al aplicar ofertas Target entregadas.

Las funciones SCRIPT y STYLE deben configurarse en `targetGlobalSettings.cspScriptNonce` y `targetGlobalSettings.cspStyleNonce` en consecuencia, antes de la carga de at.js 2.3.0+. Vea un ejemplo a continuación:

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

Una vez especificadas las configuraciones `cspScriptNonce` y `cspStyleNonce` , at.js 2.3.0+ las establece como atributos nonce en todas las etiquetas SCRIPT y STYLE que adjunta al DOM al aplicar ofertas de Target.

## Personalización híbrida {#server-state}

`serverState` es una configuración disponible en at.js v2.2+ que se puede utilizar para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Target. La integración híbrida significa que está utilizando at.js v2.2 o posterior del lado del cliente y la API de entrega o un SDK de Target del lado del servidor para ofrecer experiencias. `serverState` permite a at.js v2.2, u otra versión posterior, aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está sirviendo.

### Requisitos previos

Debe tener una integración híbrida de [!DNL Target].

* **Lado del servidor**: Debe utilizar la nueva  [API de envío ](https://developers.adobetarget.com/api/delivery-api/) o los  [SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs) de Target.
* **Lado del cliente**: Debe utilizar la versión 2.2 o posterior de  [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### Ejemplos de código

Para comprender mejor cómo funciona, consulte los ejemplos de código siguientes que tendría en su servidor. El código supone que está utilizando el SDK [Target Node.js](https://github.com/adobe/target-nodejs-sdk).

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

Un objeto JSON de muestra `serverState` para la recuperación previa de vista tiene el siguiente aspecto:

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

Una vez que la página se carga en el explorador, at.js aplica todas las ofertas [!DNL Target] de `serverState` inmediatamente, sin activar ninguna llamada de red contra el perímetro [!DNL Target]. Además, at.js oculta únicamente los elementos DOM para los que las ofertas [!DNL Target] están disponibles en el servidor recuperado de contenido, lo que afecta positivamente al rendimiento de carga de página y a la experiencia del usuario final.

### Notas importantes

Tenga en cuenta lo siguiente al utilizar `serverState`:

* Por el momento, at.js v2.2 solo admite la entrega de experiencias mediante serverState para:

   * Actividades creadas por VEC que se ejecutan al cargar la página.
   * Vistas previamente recuperadas.

      En caso de SPA que utilice [!DNL Target] Vistas y `triggerView()` en la API de at.js, at.js v2.2 almacena en caché el contenido de todas las vistas previamente recuperadas en el servidor y las aplica en cuanto cada vista se activa mediante `triggerView()`, de nuevo sin activar ninguna llamada de recuperación de contenido adicional a Target.

   * **Nota**: Actualmente, los mboxes recuperados en el lado del servidor no son compatibles con  `serverState`.

* Al aplicar `serverState `ofertas, at.js tiene en cuenta la configuración `pageLoadEnabled` y `viewsEnabled`, por ejemplo, las ofertas de carga de página no se aplicarán si la configuración `pageLoadEnabled` es falsa.

   Para activar esta configuración, habilite la opción en **[!UICONTROL Administration] > [!UICONTROL Implementation] > [!UICONTROL Edit] > [!UICONTROL Page Load Enabled]**.

   ![Configuración de carga de página habilitada](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Si utiliza etiquetas `serverState` y `<script>` en el contenido devuelto, asegúrese de que el contenido HTML utiliza `<\/script>` en lugar de `</script>`. Si utiliza `</script>`, el explorador interpreta `</script>` como el final de un SCRIPT en línea y podría romper la página HTML.

### Recursos adicionales

Para obtener más información sobre cómo funciona `serverState`, consulte los siguientes recursos:

* [Código de muestra](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Aplicación de ejemplo de aplicación de una sola página (SPA) con  `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
