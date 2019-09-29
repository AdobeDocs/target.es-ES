---
description: 'Información sobre la función targetGlobalSettings() para at.js. '
keywords: targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders
seo-description: Información sobre la función targetGlobalSettings() para la biblioteca JavaScript at.js de Adobe Target.
seo-title: Información sobre la función targetGlobalSettings() para la biblioteca JavaScript at.js de Adobe Target.
solution: Target
subtopic: Primeros pasos
title: targetGlobalSettings()
topic: Standard
translation-type: tm+mt
source-git-commit: bc5acc09c1bc8e412929ad9a0ede8a80b6405d5d

---


# targetGlobalSettings()

En lugar de definir la configuración en la interfaz de usuario Standard/Premium de [!DNL Target], puede reemplazar la configuración de la biblioteca at.js mediante `targetGlobalSettings()` o mediante las API de REST.

Hay casos de uso, especialmente cuando at.js se entrega a través de la [!DNL Dynamic Tag Management] (DTM), en que se necesita anular algunas de estas configuraciones.

## Configuración {#section_42C759AE9B524A43B8659018677224B8}

Las configuraciones que se pueden anular son las siguientes:

| Configuración | Tipo | Valor predeterminado | Descripción |
|--- |--- |--- |--- |
| clientCode | Cadena | Valor definido en la interfaz de usuario | Representa el código de cliente |
| serverDomain | Cadena | Valor definido en la interfaz de usuario | Representa el servidor Edge de Target |
| cookieDomain | Cadena | Si es posible, definirlo en el dominio de primer nivel | Representa el dominio que se usa al guardar las cookies |
| crossDomain | Cadena | Valor definido en la interfaz de usuario | Indica si el seguimiento entre dominios está activado o no.<br>Los valores posibles son:<ul><li>disabled</li><li>enabled</li><li>x-solamente</li></ul> |
| timeout | Número | Valor definido en la interfaz de usuario | Representa el tiempo de espera de la solicitud Edge de Target |
| globalMboxAutoCreate | Booleano | Valor definido en la interfaz de usuario | Indica si la solicitud de mbox global se debe activar o no |
| visitorApiTimeout | Número | 2000 ms = 2 s | Representa el tiempo de espera de la solicitud de la API de visitante |
| enabled | Booleano | true | Indica si la biblioteca at.js está activada, es decir, si debe ejecutar algo o no. El caso de uso principal de esta configuración son las cookies de exclusión u otras decisiones personalizadas que podrían desactivar las funciones de at.js |
| defaultContentHiddenStyle | Cadena | visibility: hidden | Solo se usa para ajustar mboxes que utilizan DIV con el nombre de clase “mboxDefault” y que se ejecutan a través de `mboxCreate()`, `mboxUpdate()` o `mboxDefine()` para ocultar contenido predeterminado. |
| defaultContentVisibleStyle | Cadena | visibility: visible | Solo se usa para ajustar mboxes que utilizan DIV con el nombre de clase “mboxDefault” y que se ejecutan a través de `mboxCreate()`, `mboxUpdate()` o `mboxDefine()` para mostrar la oferta aplicada o el contenido predeterminado. |
| bodyHiddenStyle | Cadena | body { opacity: 0 } | Solo se usa cuando `globalMboxAutocreate === true` para minimizar los parpadeos.<br>Para obtener más información, consulte [Cómo gestiona at.js el parpadeo](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md). |
| bodyHidingEnabled | Booleano | true | Se usa para controlar los parpadeos cuando `target-global-mbox` se utiliza para publicar ofertas creadas en el Compositor de experiencias visuales, también denominadas ofertas visuales |
| imsOrgId | Cadena | IMS ORG ID | Representa el id. de organización de IMS |
| secureOnly | Booleano | false | Indica si at.js debería utilizar solo HTTPS o se le debería permitir alternar entre HTTP y HTTPS según el protocolo de la página. |
| overrideMboxEdgeServer | Booleano | true (verdadero desde la versión 1.6.2 de at.js) | Indica si se debe utilizar el dominio `<clientCode>.tt.omtrdc.net` o el `mboxedge<clusterNumber>.tt.omtrdc.net`.<br>Si este valor es “true”, el dominio `mboxedge<clusterNumber>.tt.omtrdc.net` se guarda en una cookie. |
| overrideMboxEdgeServerTimeout | Número | 1860000 =&gt; 31 minutos | Indica la duración de la cookie que contiene el valor `mboxedge<clusterNumber>.tt.omtrdc.net`. |
| optoutEnabled | Booleano | false | Indica si Target debe llamar a la función `isOptedOut()` de la API del visitante. Esto forma parte de la habilitación de Device Graph. |
| selectorsPollingTimeout | Número | 5000 ms = 5 s | En la versión 0.9.6 de at.js, Target introdujo este nuevo ajuste que se puede anular mediante `targetGlobalSettings`.<br>`selectorsPollingTimeout` representa cuánto está dispuesto a esperar el cliente para que todos los elementos identificados por selectores aparezcan en la página.<br>Las actividades creadas por medio del Compositor de experiencias visuales (VEC) tienen ofertas que contienen selectores. |
| dataProviders | Consulte “Proveedores de datos” a continuación. | Consulte “Proveedores de datos” a continuación. | Consulte “Proveedores de datos” a continuación. |

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Esta función puede definirse antes de que se cargue at.js o en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación**] &gt; **[!UICONTROL Editar la configuración de at.js**] &gt; **[!UICONTROL Configuración del código]** &gt; **[!UICONTROL Encabezado de la biblioteca]**.

En el campo Encabezado de la biblioteca se puede introducir JavaScript de formato libre. El código de personalización debe parecerse al del ejemplo siguiente:

```
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
| [Uso de Proveedores de datos en Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | Proveedores de datos es una funcionalidad que permite pasar fácilmente datos de terceros a Target. Un tercero podría ser un servicio de pronóstico del clima, un DMP o incluso su propio servicio web. Puede usar estos datos para crear audiencias, dirigir contenido y enriquecer el perfil del visitante. |
| [Implementación de Proveedores de datos en Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Detalles de implementación y ejemplos de cómo usar la función dataProviders de Adobe Target para recuperar datos de proveedores de datos de terceros y pasarlos en la solicitud de Target. |

La configuración `window.targetGlobalSettings.dataProviders` es una matriz de proveedores de datos.

Cada proveedor de datos tiene la siguiente estructura:

| Clave | Tipo | Descripción |
|--- |--- |--- |
| name | Cadena | Nombre del proveedor |
| version | Cadena | Versión del proveedor. Esta clave se usará para la evolución del proveedor. |
| timeout | Número | Representa el tiempo de espera del proveedor si se trata de una solicitud de red.  Esta clave es opcional. |
| provider | Función | La función que contiene la lógica de búsqueda de datos del proveedor.<br>La función tiene un solo parámetro requerido: `callback`. El parámetro de llamada de retorno es una función que debe invocarse solo cuando los datos se han recuperado correctamente o si hay un error.<br>La devolución de llamada espera dos parámetros:<ul><li>error: indica si ocurrió un error. Si todo está bien, entonces este parámetro debe establecerse en nulo.</li><li>params: un objeto JSON, que representa los parámetros que se enviarán en una solicitud de Target.</li></ul> |

El siguiente ejemplo muestra dónde está utilizando la ejecución de sincronización el proveedor de datos:

```
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

```
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

```
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
