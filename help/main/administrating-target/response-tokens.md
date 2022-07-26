---
keywords: tokens de respuesta;tokens;complementos;complementos;at.js;respuesta;sdk web de plataforma
description: Aprenda a utilizar tokens de respuesta en [!DNL Adobe Target] para obtener información específica sobre la salida para la depuración y la integración con herramientas de terceros.
title: ¿Qué son los tokens de respuesta y cómo se utilizan?
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 26%

---

# Tokens de respuesta

Los tokens de respuesta le permiten generar automáticamente información específica de [!DNL Adobe Target] a la página web de su marca. Esta información puede incluir detalles sobre la actividad, la oferta, la experiencia, el perfil de usuario, la información geográfica, etc. Estos detalles proporcionan datos de respuesta adicionales para compartirlos con herramientas internas o de terceros, o para usarlos para la depuración.

Los tokens de respuesta le permiten elegir qué variables (en pares de valor clave) utilizar y, a continuación, habilitarlas para que se envíen como parte de una [!DNL Target] respuesta. Se habilita una variable mediante el conmutador y la variable se envía con [!DNL Target] respuestas, que pueden validarse en llamadas de red. Los tokens de respuesta también funcionan en [!UICONTROL Vista previa] en el menú contextual.

Una diferencia clave entre complementos y tokens de respuesta es que los complementos envían JavaScript a la página que se ejecuta al realizar el envío. Sin embargo, los tokens de respuesta envían un objeto que luego se puede leer y sobre el que se puede actuar utilizando detectores de eventos. El enfoque de token de respuesta es más seguro y permite un desarrollo y mantenimiento más sencillos de las integraciones de terceros.

>[!NOTE]
>
>Los tokens de respuesta están disponibles con la versión 1.1 o posterior de at.js.

| SDK de Target | Acciones sugeridas |
|--- |--- |
| [SDK web de Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | Compruebe que está utilizando Platform Web SDK versión 2.6.0 o posterior. Para obtener información sobre la descarga de la última versión del SDK web de Platform, consulte [Instalación del SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html){target=_blank} en la sección *Información general del SDK web de plataforma* guía. Para obtener información sobre las nuevas funciones de cada versión del SDK web de Platform, consulte [Notas de la versión](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html) en el *Información general del SDK web de plataforma* guía. |
| [at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/){target=_blank} | Compruebe que está utilizando la versión 1.1 o posterior de at.js. Para obtener información sobre la descarga de la última versión de at.js, consulte [Descargar at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}. Para obtener información sobre las nuevas funciones de cada versión de at.js, consulte [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.<br>Se recomienda a los clientes que usen at.js utilizar tokens de respuesta y abandonar los complementos. Algunos complementos que dependen de métodos internos existentes en mbox.js (ahora obsoletos), pero no en at.js, se entregan pero no funcionan. |

## Uso de tokens de respuesta {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Compruebe que está utilizando Platform Web SDK versión 2.6.0 (o posterior) o at.js versión 1.1 (o posterior).

   Para obtener más información:

   * **SDK web de plataforma**: Consulte [Instalación del SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) en el *Información general del SDK web de plataforma* guía.
   * **at.js**: Consulte [Descargar at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}.

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Tokens de respuesta]**.

   ![response_tokens-new image](assets/response_tokens-new.png)

1. Active los tokens de respuesta deseados, como `activity.id` y `offer.id`.

   Los siguientes parámetros están disponibles de forma predeterminada:

   | Tipo | Parámetro | Notas |
   |--- |--- |--- |
   | Perfiles integrados | `profile.activeActivities` | Devuelve una matriz de los `activityIds` para los que el visitante está cualificado. Aumenta a medida que los usuarios se cualifican. Por ejemplo, en una página con dos [!DNL Target] solicitudes que envían dos actividades diferentes, la segunda solicitud incluye ambas actividades. |
   |  | `profile.isFirstSession` | Devuelve “true” o “false”. |
   |  | `profile.isNewSession` | Devuelve “true” o “false”. |
   |  | `profile.daysSinceLastVisit` | Devuelve el número de días desde la última visita del visitante. |
   |  | `profile.tntId` | Devuelve el tntID del visitante. |
   |  | `profile.marketingCloudVisitorId` | Devuelve el ID de visitante de Experience Cloud del visitante. |
   |  | `profile.thirdPartyId` | Devuelve el ID de terceros del visitante. |
   |  | `profile.categoryAffinity` | Devuelve la categoría favorita del visitante. |
   |  | `profile.categoryAffinities` | Devuelve una matriz de las cinco principales categorías del visitante en forma de cadenas. |
   | Actividad | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | Detalles sobre la actividad actual.<br> Tenga en cuenta que los valores de los parámetros de oferta se evalúan en el nivel de experiencia. |
   | Geografía | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Para obtener más información acerca del uso de la segmentación geográfica en las actividades, consulte [Geografía](/help/main/c-target/c-audiences/c-target-rules/geo.md). |
   | Método de asignación de tráfico<br>(se aplica a [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] solo actividades). | `experience.trafficAllocationId` | Devuelve 0 si un visitante ha recibido una experiencia por estar en tráfico de &quot;control&quot; y 1 si un visitante ha recibido una experiencia de la distribución de tráfico &quot;segmentada&quot;. |
   |  | `experience.trafficAllocationType` | Devuelve &quot;control&quot; o &quot;segmentado&quot;. |

   Los atributos del perfil de usuario y los atributos de cliente también se muestran en la lista.

   >[!NOTE]
   >
   >Los parámetros con caracteres especiales no se muestran en la lista. Se admiten únicamente caracteres alfanuméricos y guiones bajos.

1. (Condicional) Para usar un parámetro de perfil como token de respuesta, pero el parámetro no se ha pasado a través de un [!DNL Target] y, por lo tanto, no se ha cargado en la variable [!DNL Target] La interfaz de usuario de puede usar la variable [!UICONTROL Agregar token de respuesta] para añadir el perfil a la interfaz de usuario.

   Haga clic en **[!UICONTROL Agregar token de respuesta]**, proporcione el nombre del token y haga clic en **[!UICONTROL Activar]**.

   ![response_token_create imagen](assets/response_token_create.png)

1. Cree una actividad.

## Escuchar respuestas y leer tokens de respuesta

El proceso que utiliza para escuchar [!DNL Target] las respuestas y los tokens de respuesta de lectura difieren en función de si tiene un [!DNL Platform Web SDK] o implementación de at.js.

### ![Distintivo del SDK web de Adobe Experience Platform](/help/main/assets/platform.png) [!DNL Platform Web SDK] uso de la clase Handle object {#platform-web-sdk}

Utilice la clase Handle object , que tiene un objeto de metadatos y un objeto de datos que escuchar [!DNL Target] respuestas y lea los tokens de respuesta.

El siguiente ejemplo de respuesta agrega un [!DNL Platform Web SDK] controlador de eventos personalizado directamente en la página HTML (la tabla explica los objetos utilizados en el código):

| Objeto | Información |
| --- | --- |
| Tipo: Personalization.decision | Si la decisión fue tomada por el [!DNL Target] o el proveedor de Offer decisioning. |
| Proveedor de decisiones - TGT | TGT-[!DNL Target]. [!DNL Target] proporciona los metadatos y valores del token de respuesta a la página. |
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

### ![Distintivo de at.js](/help/main/assets/atjs.png) at.js mediante eventos personalizados

Uso [Eventos personalizados de at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/){target=_blank} para escuchar el [!DNL Target] y lea los tokens de respuesta.

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

## Preguntas frecuentes sobre tokens de respuesta {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**¿Qué rol se necesita para activar o desactivar tokens de respuesta?**

Los tokens de respuesta solo los usuarios que utilicen la variable [!DNL Target] [!UICONTROL Administrador] función.

**¿Qué sucede si se ejecuta [!DNL Platform Web SDK] 2.6.0 (o anterior)?**

No tiene acceso a los tokens de respuesta.

**¿Qué sucede si ejecuto at.js 1.0 (o anterior)?**

Verá los tokens de respuesta, pero at.js no puede utilizarlos.

**[!DNL Target Classic]¿Puedo tener activos a la vez complementos de y tokens de respuesta?**

Los complementos y los tokens de respuesta están disponibles en paralelo; sin embargo, los complementos quedarán obsoletos en el futuro.

**Los tokens de respuesta se entregan a través de todas las [!DNL Target] respuestas o solo mediante [!DNL Target] respuestas que envían una actividad**

Los tokens de respuesta solo se entregan mediante [!DNL Target] respuestas que envían una actividad .

**My [!DNL Target Classic] complemento incluido JavaScript. ¿Cómo replico su funcionalidad mediante tokens de respuesta?**

Al migrar a tokens de respuesta, este tipo de JavaScript debe mantenerse en la base de código o en la solución de administración de etiquetas. Puede almacenar en déclencheur este código mediante [!DNL Platform Web SDK] o [!DNL at.js] eventos personalizados y pase los valores de token de respuesta a sus funciones de JavaScript.

**¿Por qué mi perfil o el parámetro de atributos de cliente no se muestra en la lista de tokens de respuesta?**

[!DNL Target] normalmente actualiza los parámetros cada 15 minutos. Esta actualización depende de la acción del usuario y los datos solo se actualizan cuando se ve la página de tokens de respuesta. Si los parámetros no se muestran en la lista de tokens de respuesta, [!DNL Target] aún no ha actualizado los datos.

Además, si el parámetro contiene cualquier cosa excepto caracteres no alfanuméricos o cualquier símbolo que no sea guiones bajos, el parámetro no aparece en la lista. En este momento, solo se admiten caracteres alfanuméricos y guiones bajos.

**¿El token de respuesta sigue ofreciendo contenido si utiliza un script de perfil eliminado o un parámetro de perfil?**

Los tokens de respuesta extraen y posteriormente envían información de los perfiles de usuario. Que elimine un script o parámetro de perfil no significa que la información se haya eliminado de los perfiles de usuario. Los perfiles de usuario siguen teniendo datos correspondientes al script de perfil. El token de respuesta sigue entregando el contenido. Para los usuarios que no tienen esa información guardada en sus perfiles o para visitantes nuevos, ese token no se entrega porque los datos no están presentes en sus perfiles.

[!DNL Target] no desactiva automáticamente el token. Si elimina un script de perfil y ya no quiere que se envíe el token, deberá desactivar este usted mismo.

**He cambiado el nombre del script Mi perfil, ¿por qué el token que utiliza dicho script sigue activo con el nombre antiguo?**

Como se ha mencionado anteriormente, los tokens de respuesta operan con la información de perfil que los usuarios tienen guardada. Aunque haya cambiado el nombre del script de perfil, los usuarios que hayan visitado el sitio web tendrán el antiguo valor de script de perfil guardado en sus perfiles. El token sigue recogiendo el valor antiguo que ya se ha guardado en los perfiles de usuario. Si desea enviar contenido con el nuevo nombre, deberá desactivar el token antiguo y activar el nuevo.

**Si mis atributos han cambiado, ¿cuándo se eliminan de la lista?**

[!DNL Target] realiza una actualización de atributos a intervalos regulares. Cualquier atributo que no esté activado se elimina durante la siguiente actualización. Sin embargo, si tiene un atributo activado que se haya eliminado, ese script no se eliminará de la lista de atributos hasta que lo desactive. Por ejemplo, se ha eliminado un script de perfil que se utilizaba como token. [!DNL Target] solo elimina de la lista los atributos desactivados cuando estos se eliminan o se cambia su nombre.

## Envío de datos a los Google Analytics

Las secciones siguientes describen cómo enviar [!DNL Target] a los Google Analytics. Los datos enviados por tokens de respuesta también se pueden enviar a otras integraciones de terceros.

### ![Distintivo de AEP](/help/main/assets/platform.png) Envío de datos a los Google Analytics mediante el SDK web de Platform

Se pueden enviar datos a los Google Analytics a través de Platform Web SDK versión 2.6.0 (o posterior) añadiendo el siguiente código en la página HTML.

>[!NOTE]
>
>Asegúrese de que el par de valor de clave de token de respuesta está debajo de la variable `alloy(“sendEvent”` objeto.

```
<script type="text/javascript"> 
   (function(i, s, o, g, r, a, m) { 
   i['GoogleAnalyticsObject'] = r; 
   i[r] = i[r] || function() { 
   (i[r].q = i[r].q || []).push(arguments) 
   }, i[r].l = 1 * new Date(); 
   
   
   a = s.createElement(o), 
   m = s.getElementsByTagName(o)[0]; 
   a.async = 1; 
   a.src = g; 
   m.parentNode.insertBefore(a, m) 
   })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
   ga('create', 'Google Client Id', 'auto'); 
</script> 
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
   
   
   ga('send', 'event', { 
   eventCategory: "target", 
   eventAction: experienceNames, 
   eventLabel: activityNames 
   }); 
   
   
   });
</script>
```

### ![Distintivo de at.js](/help/main/assets/atjs.png) Envío de datos a los Google Analytics mediante at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

Es posible enviar datos a Google Analytics mediante at.js añadiendo el siguiente código en la página HTML:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
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
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
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

### ![Distintivo de at.js](/help/main/assets/atjs.png) Google Analytics y depuración

El siguiente código permite depurar mediante Google Analytics:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
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
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
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

## ![at.js](/help/main/assets/atjs.png) Vídeo de formación: Tokens de respuesta y eventos personalizados de at.js {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

En el siguiente vídeo se explica cómo usar tokens de respuesta y eventos personalizados de at.js para compartir información de perfil desde [!DNL Target] a sistemas de terceros.

>[!NOTE]
>
>La interfaz del menú [!UICONTROL Administración] de [!DNL Target] (anteriormente [!UICONTROL Configuración]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información contenida en el siguiente vídeo es correcta; sin embargo, las opciones se encuentran en ubicaciones ligeramente diferentes.
>
>El vídeo menciona `option.name` y `option.id`, que se han sustituido por `offer.name` y `offer.id`, respectivamente.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
