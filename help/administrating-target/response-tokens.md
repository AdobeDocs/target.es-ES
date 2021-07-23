---
keywords: tokens de respuesta;tokens;complementos;complementos;at.js;respuesta
description: Aprenda a utilizar tokens de respuesta en [!DNL Adobe Target] para obtener información específica sobre la salida para depurar e integrar con herramientas de terceros.
title: ¿Qué son los tokens de respuesta y cómo se utilizan?
feature: Administración y configuración
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: d919f1abe634290780fe943286a9149cb0bd7f27
workflow-type: tm+mt
source-wordcount: '1642'
ht-degree: 27%

---

# Tokens de respuesta

Los tokens de respuesta le permiten generar automáticamente información específica de [!DNL Adobe Target] en la página web de su marca. Esta información puede incluir detalles sobre la actividad, la oferta, la experiencia, el perfil de usuario, la información geográfica, etc. Estos detalles proporcionan datos de respuesta adicionales para compartirlos con herramientas internas o de terceros, o para usarlos para la depuración.

Los tokens de respuesta le permiten elegir qué variables (en pares de valor clave) utilizar y, a continuación, habilitarlas para que se envíen como parte de una respuesta [!DNL Target]. Se habilita una variable mediante el conmutador y la variable se envía con respuestas [!DNL Target], que pueden validarse en llamadas de red. Los tokens de respuesta también funcionan en modo [!UICONTROL Preview].

Una diferencia clave entre complementos y tokens de respuesta es que los complementos envían JavaScript a la página que se ejecuta al realizar el envío. Sin embargo, los tokens de respuesta envían un objeto que luego se puede leer y sobre el que se puede actuar utilizando detectores de eventos. El enfoque de token de respuesta es más seguro y permite un desarrollo y mantenimiento más sencillos de las integraciones de terceros.

>[!NOTE]
>
>Los tokens de respuesta están disponibles con la versión 1.1 o posterior de at.js.

>[!IMPORTANT]
>
>El token de respuesta estará disponible con [!DNL Adobe Experience Platform Web SDK] en una versión futura (fecha por determinar). La siguiente documentación sobre los tokens de respuesta y el SDK web de Platform se incluye como punto álgido.

| SDK de Target | Acciones sugeridas |
|--- |--- |
| [SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Compruebe que está utilizando Platform Web SDK versión 2.6.0 o posterior. Para obtener información sobre la descarga de la última versión del SDK web de Platform, consulte [Instalar el SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) en la guía *Información general del SDK web de Platform*. Para obtener información sobre las nuevas funciones de cada versión del SDK web de Platform, consulte [Notas de la versión](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html) en la guía *Información general del SDK web de Platform*. |
| [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Compruebe que está utilizando la versión 1.1 o posterior de at.js. Para obtener información sobre la descarga de la versión más reciente de at.js, consulte [Descargar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md). Para obtener más información sobre las funcionalidades en cada versión de at.js, consulte [Detalles de la versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).<br>Se recomienda a los clientes que usen at.js utilizar tokens de respuesta y abandonar los complementos. Se envían algunos complementos que dependen de métodos internos existentes en mbox.js, pero no en at.js, pero que no funcionan. |

## Uso de tokens de respuesta {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Compruebe que está utilizando Platform Web SDK versión 2.6.0 (o posterior) o at.js versión 1.1 (o posterior).

   Para obtener más información:

   * **SDK** web de plataforma: Consulte  [Instalar el ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) SDK en la guía de  *descripción general del SDK web de* plataforma .
   * **at.js**: Consulte  [Descargar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2).

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Tokens de respuesta]**.

   ![](assets/response_tokens-new.png)

1. Active los tokens de respuesta deseados, como `activity.id` y `option.id`.

   Los siguientes parámetros están disponibles de forma predeterminada:

   | Tipo | Parámetro | Notas |
   |--- |--- |--- |
   | Perfiles integrados | `profile.activeActivities` | Devuelve una matriz de los `activityIds` para los que el visitante está cualificado. Aumenta a medida que los usuarios se cualifican. Por ejemplo, en una página con dos solicitudes [!DNL Target] que ofrecen dos actividades diferentes, la segunda solicitud incluye ambas actividades. |
   |  | `profile.isFirstSession` | Devuelve “true” o “false”. |
   |  | `profile.isNewSession` | Devuelve “true” o “false”. |
   |  | `profile.daysSinceLastVisit` | Devuelve el número de días desde la última visita del visitante. |
   |  | `profile.tntId` | Devuelve el tntID del visitante. |
   |  | `profile.marketingCloudVisitorId` | Devuelve el ID de visitante de Experience Cloud del visitante. |
   |  | `profile.thirdPartyId` | Devuelve el ID de terceros del visitante. |
   |  | `profile.categoryAffinity` | Devuelve la categoría favorita del visitante. |
   |  | `profile.categoryAffinities` | Devuelve una matriz de las cinco principales categorías del visitante en forma de cadenas. |
   | Actividad | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | Detalles sobre la actividad actual. Tenga en cuenta que “opción” es igual a “oferta”. |
   | Geografía | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Para obtener más información acerca del uso de la segmentación geográfica en las actividades, consulte [Geografía](/help/c-target/c-audiences/c-target-rules/geo.md). |
   | Método de asignación de tráfico<br>(solo se aplica a las actividades [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization]). | `experience.trafficAllocationId` | Devuelve 0 si un visitante ha recibido una experiencia por estar en tráfico de &quot;control&quot; y 1 si un visitante ha recibido una experiencia de la distribución de tráfico &quot;segmentada&quot;. |
   |  | `experience.trafficAllocationType` | Devuelve &quot;control&quot; o &quot;segmentado&quot;. |

   Los atributos del perfil de usuario y los atributos de cliente también se muestran en la lista.

   >[!NOTE]
   >
   >Los parámetros con caracteres especiales no se muestran en la lista. Se admiten únicamente caracteres alfanuméricos y guiones bajos.

1. (Condicional) Para utilizar un parámetro de perfil como token de respuesta, pero el parámetro no se ha pasado a través de una solicitud [!DNL Target] y, por lo tanto, no se ha cargado en la interfaz de usuario [!DNL Target], puede utilizar el botón [!UICONTROL Añadir token de respuesta] para añadir el perfil a la interfaz de usuario.

   Haga clic en **[!UICONTROL Agregar token de respuesta]**, proporcione el nombre del token y haga clic en **[!UICONTROL Activar]**.

   ![](assets/response_token_create.png)

1. Cree una actividad.

## Escuchar respuestas y leer tokens de respuesta

El proceso que utiliza para detectar [!DNL Target] respuestas y leer tokens de respuesta varía en función de si tiene una implementación [!DNL Platform Web SDK] o at.js.

### ![Distintivo del SDK web de Adobe Experience Platform ](/help/assets/platform.png) [!DNL Platform Web SDK] mediante la clase Handle object

Utilice la clase Handle object , que tiene un objeto de metadatos y un objeto de datos para detectar respuestas [!DNL Target] y leer los tokens de respuesta.

En el siguiente ejemplo de respuesta se agrega un controlador de evento personalizado [!DNL Platform Web SDK] directamente a la página HTML (la tabla explica los objetos utilizados en el código):

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

### ![at.js ](/help/assets/atjs.png) badgeat.js mediante eventos personalizados

Utilice [eventos personalizados de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) para detectar la respuesta de y leer los tokens de respuesta.[!DNL Target]

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

Solo los usuarios con la función [!DNL Target] [!UICONTROL Administrator] pueden activar o desactivar los tokens de respuesta.

**¿Qué sucede si ejecuto  [!DNL Platform Web SDK] 2.6.0 (o una versión anterior)?**

No tiene acceso a los tokens de respuesta.

**¿Qué sucede si ejecuto at.js 1.0 (o anterior)?**

Verá los tokens de respuesta, pero at.js no puede utilizarlos.

**[!DNL Target Classic]¿Puedo tener activos a la vez complementos de y tokens de respuesta?**

Los complementos y los tokens de respuesta están disponibles en paralelo; sin embargo, los complementos quedarán obsoletos en el futuro.

**¿Los tokens de respuesta se envían a través de todas las  [!DNL Target] respuestas o solo a través de  [!DNL Target] respuestas que envían una actividad?**

Los tokens de respuesta solo se entregan mediante respuestas [!DNL Target] que envían una actividad.

**Mi  [!DNL Target Classic] complemento incluía JavaScript. ¿Cómo replico su funcionalidad mediante tokens de respuesta?**

Al migrar a tokens de respuesta, este tipo de JavaScript debe mantenerse en la base de código o en la solución de administración de etiquetas. Puede almacenar en déclencheur este código mediante eventos personalizados [!DNL Platform Web SDK] o [!DNL at.js] y pasar los valores de token de respuesta a sus funciones JavaScript.

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

En las secciones siguientes se describe cómo enviar datos [!DNL Target] a los Google Analytics. Los datos enviados por tokens de respuesta también se pueden enviar a otras integraciones de terceros.

### ![Distintivo de AEP](/help/assets/platform.png) Envío de datos a los Google Analytics a través del SDK web de Platform

Se pueden enviar datos a los Google Analytics a través de Platform Web SDK versión 2.6.0 (o posterior) añadiendo el siguiente código en la página HTML.

>[!NOTE]
>
>Asegúrese de que el par de valor de clave de token de respuesta está bajo el objeto `alloy(“sendEvent”` .

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

### ![Insignia at.js ](/help/assets/atjs.png) Envío de datos a los Google Analytics a través de at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

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

### ![Insignia at.js ](/help/assets/atjs.png) Google Analytics y depuración

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
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
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

## ![Vídeo de at.](/help/assets/atjs.png) jsTraining: Tokens de respuesta y eventos personalizados de at.js {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

En el siguiente vídeo se explica cómo usar tokens de respuesta y eventos personalizados de at.js para compartir información de perfil de [!DNL Target] a sistemas de terceros.

>[!NOTE]
>
>La interfaz de usuario del menú [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) se ha rediseñado para proporcionar un rendimiento mejorado, reducir el tiempo de mantenimiento necesario al lanzar nuevas funciones y mejorar la experiencia del usuario en todo el producto. La información contenida en el siguiente vídeo es correcta; sin embargo, las opciones se encuentran en ubicaciones ligeramente diferentes.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
