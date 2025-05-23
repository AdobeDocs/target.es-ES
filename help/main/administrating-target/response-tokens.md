---
keywords: tokens de respuesta;tokens;complementos;complementos;at.js;respuesta;sdk web de platform;google analytics
description: Aprenda a utilizar tokens de respuesta en  [!DNL Adobe Target] para generar información específica para la depuración y la integración con herramientas de terceros.
title: ¿Qué son los tokens de respuesta y cómo se utilizan?
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 22%

---

# Tokens de respuesta

Los tokens de respuesta le permiten mostrar automáticamente información específica de [!DNL Adobe Target] en la página web de su marca. Esta información puede incluir detalles sobre la actividad, oferta, experiencia, perfil de usuario, información geográfica y más. Estos detalles proporcionan datos de respuesta adicionales para compartirlos con herramientas internas o de terceros, o para utilizarlos en la depuración.

Los tokens de respuesta le permiten elegir qué variables (en pares de valor clave) usar y luego permitirles enviarse como parte de una respuesta [!DNL Target]. Habilita una variable mediante el modificador y la variable se envía con [!DNL Target] respuestas, que se pueden validar en llamadas de red. Los tokens de respuesta también funcionan en el modo [!UICONTROL Preview].

Una diferencia clave entre los complementos y los tokens de respuesta es que los complementos envían JavaScript a la página que se ejecuta tras la entrega. Sin embargo, los tokens de respuesta envían un objeto que se puede leer y sobre el que se puede actuar utilizando detectores de eventos. El enfoque del token de respuesta es más seguro y facilita el desarrollo y mantenimiento de integraciones de terceros.

{{permissions-update}}

>[!NOTE]
>
>Los tokens de respuesta están disponibles con la versión 1.1 o posterior de at.js.

| Target SDK | Acciones sugeridas |
|--- |--- |
| [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank} | Compruebe que está utilizando la versión 2.6.0 o posterior de Platform Web SDK. Para obtener información sobre cómo descargar la versión más reciente de Platform Web SDK, consulte [Instalar SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=es){target=_blank} en la guía *Información general de Platform Web SDK*. Para obtener información sobre la nueva funcionalidad en cada versión de Platform Web SDK, consulte [Notas de la versión](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) en la guía de *Información general de Platform Web SDK*. |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=es){target=_blank} | Compruebe que está utilizando la versión 1.1 o posterior de at.js. Para obtener información sobre cómo descargar la versión más reciente de at.js, consulte [Descargar at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=es){target=_blank}. Para obtener información sobre la nueva funcionalidad en cada versión de at.js, consulte [Detalles de la versión de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank}.<br>Se recomienda a los clientes que usen at.js utilizar tokens de respuesta y abandonar los complementos. Algunos complementos que dependen de métodos internos y que existían en mbox.js (ahora obsoletos), pero no en at.js, se entregan pero fallan. |

## Uso de tokens de respuesta {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Asegúrese de utilizar la versión 2.6.0 (o posterior) de Platform Web SDK o la versión 1.1 (o posterior) de at.js.

   Para obtener más información:

   * **Platform Web SDK**: consulte [Instalar SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=es) en la guía de *Información general de Platform Web SDK*.
   * **at.js**: Ver [Descargar at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=es){target=_blank}.

1. En [!DNL Target], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**.

1. Active los tokens de respuesta deseados, como `activity.id` y `offer.id`.

   Los siguientes parámetros están disponibles de forma predeterminada:

   | Tipo | Parámetro | Notas |
   |--- |--- |--- |
   | Perfiles integrados | `profile.activeActivities` | Devuelve una matriz de los `activityIds` para los que el visitante está cualificado. Aumenta a medida que los usuarios se cualifican. Por ejemplo, en una página con dos solicitudes [!DNL Target] que entregan dos actividades diferentes, la segunda solicitud incluye ambas actividades. |
   |  | `profile.isFirstSession` | Devuelve “true” o “false”. |
   |  | `profile.isNewSession` | Devuelve “true” o “false”. |
   |  | `profile.daysSinceLastVisit` | Devuelve el número de días desde la última visita del visitante. |
   |  | `profile.tntId` | Devuelve el tntID del visitante. |
   |  | `profile.marketingCloudVisitorId` | Devuelve el ID de visitante de Experience Cloud del visitante. |
   |  | `profile.thirdPartyId` | Devuelve el ID de terceros del visitante. |
   |  | `profile.categoryAffinity` | Devuelve la categoría favorita del visitante. |
   |  | `profile.categoryAffinities` | Devuelve una matriz de las cinco principales categorías del visitante en forma de cadenas. |
   | Actividad | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | Detalles de la actividad actual.<br> Tenga en cuenta que los valores de los parámetros de oferta se evalúan en el nivel de experiencia. |
   | Geografía | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Para obtener más información acerca del uso de la segmentación geográfica en las actividades, consulte [Geografía](/help/main/c-target/c-audiences/c-target-rules/geo.md). |
   | Método de asignación de tráfico <br>(se aplica solo a [!UICONTROL Auto-Target] y [!UICONTROL Automated Personalization] actividades). | `experience.trafficAllocationId` | Devuelve 0 si un visitante recibió una experiencia por estar en tráfico de &quot;control&quot; y 1 si un visitante recibió una experiencia de la distribución de tráfico &quot;segmentada&quot;. |
   |  | `experience.trafficAllocationType` | Devolver &quot;control&quot; o &quot;segmentado&quot;. |

   Los atributos del perfil de usuario y los atributos de cliente también se muestran en la lista.

   >[!NOTE]
   >
   >Los parámetros con caracteres especiales no se muestran en la lista. Se admiten únicamente caracteres alfanuméricos y guiones bajos.

1. (Condicional) Para usar un parámetro de perfil como token de respuesta, pero el parámetro no se ha pasado a través de una solicitud [!DNL Target] y, por lo tanto, no se ha cargado en la interfaz de usuario [!DNL Target], puede usar el botón [!UICONTROL Add Response Token] para agregar el perfil a la interfaz de usuario.

   Haga clic en **[!UICONTROL Add Response Token]**, proporcione el nombre del token y luego haga clic en **[!UICONTROL Activate]**.

1. Cree una actividad.

## Escuchar respuestas y leer tokens de respuesta

El proceso que usa para escuchar [!DNL Target] respuestas y leer tokens de respuesta varía en función de si tiene una implementación de [!DNL Platform Web SDK] o at.js.

### ![distintivo de Adobe Experience Platform Web SDK](/help/main/assets/platform.png) [!DNL Platform Web SDK] que usa la clase de objeto Handle {#platform-web-sdk}

Utilice la clase de objeto Handle, que tiene un objeto de metadatos y un objeto de datos para detectar [!DNL Target] respuestas y leer los tokens de respuesta.

El siguiente ejemplo de respuesta agrega directamente un controlador de eventos personalizado [!DNL Platform Web SDK] a la página HTML (en la tabla se explican los objetos utilizados en el código):

| Objeto | Información |
| --- | --- |
| Tipo: Personalization.decision | Si la decisión fue tomada por el proveedor [!DNL Target] o Offer Decisioning. |
| DecisionProvider - TGT | TGT-[!DNL Target]. [!DNL Target] proporciona los metadatos y valores del token de respuesta a la página. |
| Meta | Metadatos que se pasan a la página. |
| Datos | Valores de los metadatos pasados a la página. |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![distintivo de at.js](/help/main/assets/atjs.png) at.js con eventos personalizados

Use [eventos personalizados de at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=es){target=_blank} para escuchar la respuesta [!DNL Target] y leer los tokens de respuesta.

El siguiente ejemplo de código añade un controlador de evento personalizado [!DNL at.js] directamente a la página HTML:

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## Preguntas frecuentes sobre token de respuesta {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**¿Qué rol se necesita para activar o desactivar tokens de respuesta?**

Solo los usuarios con el rol [!DNL Target] [!UICONTROL Administrator] pueden activar o desactivar los tokens de respuesta.

**¿Qué sucede si estoy ejecutando [!DNL Platform Web SDK] 2.6.0 (o una versión anterior)?**

No tiene acceso a los tokens de respuesta.

**¿Qué sucede si ejecuto at.js 1.0 (o una versión anterior)?**

Verá los tokens de respuesta, pero at.js no puede utilizarlos.

**¿Puedo tener ambos [!DNL Target Classic] complementos y tokens de respuesta activos al mismo tiempo?**

Los complementos y los tokens de respuesta están disponibles en paralelo, pero no se utilizarán en el futuro.

**¿Se entregaron tokens de respuesta a través de todas las respuestas de [!DNL Target] o solo a través de respuestas de [!DNL Target] que entregaron una actividad?**

Los tokens de respuesta se entregan solamente a través de [!DNL Target] respuestas que entregan una actividad.

**Mi complemento [!DNL Target Classic] incluía JavaScript. ¿Cómo replico su funcionalidad mediante tokens de respuesta?**

Al migrar a tokens de respuesta, este tipo de JavaScript debe mantenerse en la base de código o en la solución de administración de etiquetas. Puede almacenar en déclencheur este código mediante [!DNL Platform Web SDK] o [!DNL at.js] eventos personalizados y pasar los valores de token de respuesta a sus funciones de JavaScript.

**¿Por qué mi perfil o el parámetro de atributos de cliente no se muestra en la lista de tokens de respuesta?**

[!DNL Target] normalmente actualiza los parámetros cada 15 minutos. Esta actualización depende de la acción del usuario y los datos solo se actualizan cuando se ve la página de tokens de respuesta. Si los parámetros no se muestran en la lista de token de respuesta, [!DNL Target] aún no ha actualizado los datos.

Además, si el parámetro contiene cualquier carácter que no sea alfanumérico o cualquier símbolo que no sea guiones bajos, el parámetro no aparecerá en la lista. En este momento, solo se admiten caracteres alfanuméricos y guiones bajos.

**¿El token de respuesta sigue entregando contenido si usa un script de perfil eliminado o un parámetro de perfil?**

Los tokens de respuesta extraen y posteriormente envían información de los perfiles de usuario. Que elimine un script o parámetro de perfil no significa que la información se haya eliminado de los perfiles de usuario. Los perfiles de usuario siguen teniendo datos correspondientes al script de perfil. El token de respuesta sigue entregando el contenido. Para los usuarios que no tienen esa información guardada en sus perfiles, o para los nuevos visitantes, ese token no se entrega porque los datos no están presentes en sus perfiles.

[!DNL Target] no desactiva el token automáticamente. Si elimina un script de perfil y ya no quiere que se envíe el token, deberá desactivar este usted mismo.

**He cambiado el nombre del script Mi perfil, ¿por qué el token que utiliza dicho script sigue activo con el nombre antiguo?**

Como se ha mencionado anteriormente, los tokens de respuesta operan con la información de perfil que los usuarios tienen guardada. Aunque ha cambiado el nombre del script de perfil, los usuarios que han visitado el sitio web tienen el valor del script de perfil antiguo guardado en sus perfiles. El token sigue recopilando el valor antiguo que ya se ha guardado en los perfiles de usuario. Si desea enviar contenido con el nuevo nombre, deberá desactivar el token antiguo y activar el nuevo.

**Si mis atributos han cambiado, ¿cuándo se quitarán de la lista?**

[!DNL Target] realiza una actualización de atributos a intervalos regulares. Cualquier atributo que no esté activado se eliminará durante la siguiente actualización. Sin embargo, si tiene un atributo activado y eliminado, dicho script no se elimina de la lista de atributos hasta que lo desactive. Por ejemplo, ha eliminado un script de perfil que se utilizaba como token. [!DNL Target] quita únicamente los atributos desactivados de la lista cuando se eliminan o se les cambia el nombre.

## Envío de datos a Google Analytics

En las secciones siguientes se describe cómo enviar datos de [!DNL Target] a Google Analytics 4. Los datos enviados por tokens de respuesta también se pueden enviar a otras integraciones de terceros.

### ![distintivo de AEP](/help/main/assets/platform.png): se envían datos a Google Analytics a través de Platform Web SDK.

Se pueden enviar datos a Google Analytics a través de Platform Web SDK versión 2.6.0 (o posterior) agregando el siguiente código en la página de HTML.

>[!NOTE]
>
>Asegúrese de que el par clave-valor del token de respuesta esté en el objeto `alloy("sendEvent"`.

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
<script type="text/javascript">
    alloy("sendEvent", {
 
 
    })
    .then(({ renderedPropositions, nonRenderedPropositions }) => {
        // concatenate all the propositions
        const propositions = [...renderedPropositions, ...nonRenderedPropositions];
        // extractResponseTokens() extract the meta from item -> meta
        const tokens = extractResponseTokens(propositions);
        const activityNames = [];
        const experienceNames = [];
        const uniqueTokens = distinct(tokens);
    
    
        uniqueTokens.forEach(token => {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![distintivo de at.js](/help/main/assets/atjs.png): se envían datos a Google Analytics a través de at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

Es posible enviar datos a Google Analytics mediante at.js añadiendo el siguiente código en la página HTML:

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
        var tokens = e.detail.responseTokens;

        if (isEmpty(tokens)) {
            return;
        }

        var activityNames = [];
        var experienceNames = [];
        var uniqueTokens = distinct(tokens);

        uniqueTokens.forEach(function(token) {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });

    function isEmpty(val) {
        return (val === undefined || val == null || val.length <= 0) ? true : false;
    }

    function key(obj) {
        return Object.keys(obj)
        .map(function(k) { return k + "" + obj[k]; })
        .join("");
    }

    function distinct(arr) {
        var result = arr.reduce(function(acc, e) {
            acc[key(e)] = e;
            return acc;
        }, {});

        return Object.keys(result)
        .map(function(k) { return result[k]; });
    }
</script>
```

## Depuración

Las secciones siguientes proporcionan información sobre la depuración de tokens de respuesta:

### ![distintivo de at.js](/help/main/assets/atjs.png): Google Analytics y depuración

El siguiente código permite depurar con Google Analytics:

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
      var tokens = e.detail.responseTokens;
  
      if (isEmpty(tokens)) {
        return;
      }
  
      var activityNames = [];
      var experienceNames = [];
      var uniqueTokens = distinct(tokens);
  
      uniqueTokens.forEach(function(token) {
        activityNames.push(token["activity.name"]);
        experienceNames.push(token["experience.name"]);
      });
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
      });
    });
  
    function isEmpty(val) {
      return (val === undefined || val == null || val.length <= 0) ? true : false;
    }
  
    function key(obj) {
       return Object.keys(obj)
      .map(function(k) { return k + "" + obj[k]; })
      .join("");
    }
  
    function distinct(arr) {
      var result = arr.reduce(function(acc, e) {
        acc[key(e)] = e;
        return acc;
      }, {});
  
      return Object.keys(result)
      .map(function(k) { return result[k]; });
    }
</script>
```

### Depuración con el equivalente del complemento ttMeta

Puede crearse el equivalente del complemento ttMeta para depuración añadiendo el siguiente código a la página HTML:

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Vídeo de formación de ![at.js](/help/main/assets/atjs.png): tokens de respuesta y eventos personalizados de at.js {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

En el siguiente vídeo se explica cómo utilizar tokens de respuesta y eventos personalizados de at.js para compartir información de perfil de [!DNL Target] con sistemas de terceros.

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas características y mejorar la experiencia del usuario en todo el producto. La información del siguiente vídeo es correcta; sin embargo, las opciones están en ubicaciones ligeramente diferentes.
>
>El vídeo menciona `option.name` y `option.id`, que han sido reemplazados con `offer.name` y `offer.id`, respectivamente.

>[!VIDEO](https://video.tv.adobe.com/v/33709?captions=spa)
