---
keywords: at.js;agente de usuario del navegador;agente de usuario;sugerencias del cliente;agente de usuario
description: Descubra cómo [!DNL Adobe Target] utiliza el usuario-agente y las sugerencias del cliente para calificar a los visitantes para la segmentación y personalización.
title: Sugerencias del agente de usuario y del cliente
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 3%

---

# Sugerencias del usuario-agente y del cliente

[!DNL Adobe Target] utiliza el usuario-agente para clasificar a los visitantes para la segmentación y personalización.

>[!NOTE]
>
>La información contenida en este artículo se aplica a [Versión 2.9.0 de at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) (o posterior).


Cada vez que un explorador web realiza una solicitud a un servidor, incluida en el encabezado de la solicitud, se incluye información sobre el explorador y el entorno en el que se ejecuta el explorador. Desde los primeros días de Internet, estos datos se han agregado en una sola cadena denominada user-agent.

El siguiente texto es un ejemplo de usuario-agente de un equipo basado en Mac OS X que utiliza un explorador Safari:

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

Desde este agente de usuario, el servidor que recibe la solicitud puede discernir la siguiente información sobre el explorador y el sistema operativo:

| Información | Detalles |
| --- | --- |
| Nombre del software | Chrome |
| Versión de software | 101 |
| Versión completa del software | 101.0.4951.41 |
| Nombre del motor de diseño | AppleWebKit |
| Versión del motor de diseño | 537,36 |
| Sistema operativo | Android |
| Versión del sistema operativo | Android 12 (cono de nieve) |
| Dispositivo | SM-S908E (Samsung Galaxy S22 Ultra) |

A lo largo de los años, la cantidad de información del navegador y del dispositivo incluida en la cadena del usuario-agente ha aumentado.

## Casos de uso del agente de usuario

Los agentes de usuario se han utilizado durante mucho tiempo para proporcionar a los equipos de marketing y de desarrollador información importante sobre cómo navegadores y sistemas operativos. Los dispositivos y muestran el contenido del sitio, así como la forma en que los usuarios interactúan con los sitios web. Los agentes de usuario también se utilizan para bloquear el correo no deseado y filtrar bots que rastrean sitios por distintos motivos adicionales.

Sin embargo, en los últimos años, algunos propietarios de sitios y proveedores de marketing han utilizado el agente de usuario junto con otra información incluida en los encabezados de solicitud para crear huellas digitales que pueden utilizarse como medio para identificar a usuarios sin su conocimiento. A pesar del importante propósito que cumple el usuario-agente para los propietarios del sitio, los desarrolladores de navegadores han decidido realizar cambios en la forma en que los agentes de usuario trabajan para limitar los posibles problemas de privacidad de los visitantes del sitio.

Sugerencias de cliente de agente de usuario es la solución que los desarrolladores de navegadores han desarrollado. Las sugerencias del cliente siguen permitiendo que los sitios recopilen la información necesaria sobre el explorador, el sistema operativo y el dispositivo, a la vez que brindan una mayor protección contra los métodos de seguimiento encubiertos, como la huella digital.

## Sugerencias del cliente

Las sugerencias de cliente de agente de usuario proporcionan a los propietarios de sitios web la capacidad de acceder a gran parte de la misma información disponible en el usuario-agente, pero de una manera que preserva la privacidad. Cuando los navegadores modernos envían un usuario-agente a un servidor web, todo el usuario-agente se envía en cada solicitud, independientemente de si es necesario. Por otro lado, las sugerencias del cliente refuerzan un modelo en el que el servidor debe solicitar al explorador la información adicional que desea conocer sobre el cliente. Al recibir esta solicitud, el explorador puede aplicar sus propias políticas o configuración de usuario para determinar qué datos se devuelven. En lugar de exponer a todo el usuario-agente de forma predeterminada en todas las solicitudes, el acceso ahora se administra de forma explícita y auditable.

Las sugerencias de cliente de agente de usuario han estado disponibles en Chrome desde la versión 89. Las versiones recientes de navegadores basados en Chromium, como Microsoft Edge, Opera, Brave, Chrome Android, Opera Android y Samsung Internet, también admiten la API de sugerencias de cliente.

Las sugerencias del cliente contenidas en los encabezados de la primera solicitud realizada por el explorador a un servidor web contienen la marca del explorador, la versión principal del explorador y un indicador de si el cliente es un dispositivo móvil. Cada fragmento de datos tiene su propio valor de encabezado, en lugar de agruparse en una sola cadena de usuario-agente, como se muestra en el siguiente ejemplo:

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

El siguiente ejemplo es el usuario-agente para el mismo explorador:

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

Aunque la información es similar, la primera solicitud al servidor contiene sugerencias de cliente que contienen solo un subconjunto de lo que está disponible en la cadena usuario-agente. Falta en la solicitud la arquitectura del sistema operativo, la versión completa del sistema operativo, el nombre del motor de diseño, la versión del motor de diseño y la versión completa del explorador. Sin embargo, en solicitudes posteriores, la API de sugerencias de cliente permite que los servidores web soliciten detalles adicionales de alta entropía sobre el dispositivo. Cuando se solicitan estos valores de entropía alta, según la política del explorador o la configuración del usuario, la respuesta del explorador puede incluir esa información.

El siguiente ejemplo es un objeto JSON devuelto por la API de sugerencias de cliente cuando se solicitan valores de entropía altos:

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

Los valores de entropía altos incluyen varios fragmentos de información adicionales que no están disponibles en la información de sugerencias del cliente predeterminada. La siguiente tabla contiene detalles de qué datos están disponibles en la solicitud predeterminada frente a la información de sugerencias de cliente de agente de usuario de alta entropía.

| Encabezado HTTP | JavaScript | Agente de usuario | Sugerencia del cliente | Sugerencia de cliente de alta entropía |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | marcas | Sí | Sí | No |
| Sec-CH-UA-Platform | platform | Sí | Sí | No |
| Sec-CH-UA-Mobile | móvil | Sí | Sí | No |
| Sec-CH-UA-Platform-Version | platformVersion | Sí | No | Sí |
| Sec-CH-UA-Arch | arquitectura | Sí | No | Sí |
| Sec-CH-UA-Model | model | Sí | No | Sí |
| Sec-CH-UA-Bitness | Bitness | Sí | No | Sí |
| Sec-CH-UA-Full-Version-List | fullVersionList | Sí | No | Sí |

## Migración a sugerencias del cliente

Actualmente, los exploradores basados en Chromium siguen enviando el usuario-agente junto con las sugerencias del cliente en los encabezados de las solicitudes realizadas a los servidores web. Sin embargo, a partir de abril de 2022 y hasta febrero de 2023, la cantidad de datos contenidos en la cadena usuario-agente se reducirá. Otros exploradores, como Safari y Firefox, seguirán aprovechando la cadena de usuario-agente; sin embargo, también reducirán la cantidad de información que contiene.

## [!DNL Target] casos de uso que requieren

Los siguientes casos de uso en Target requieren sugerencias del cliente:

### Atributos de audiencia

Si usa [!DNL Target] audiencias y utilice cualquiera de los atributos de audiencia siguientes, [!DNL Target] requiere que las sugerencias del cliente realicen la segmentación correcta:

* Explorador
* Sistema operativo
* Móvil

### Scripts de perfil

Si utiliza scripts de perfil y hace referencia a la variable `user.browser` (que hace referencia a user-agent), es posible que tenga que actualizar el script de perfil para comprobar también una o más sugerencias del cliente. Puede acceder a cualquiera de las sugerencias del cliente mediante la función `user.clientHint('sec-ch-ua-xxxxx')`. El nombre del encabezado de Client Hint debe estar en minúscula.

El siguiente ejemplo muestra cómo detectar correctamente un sistema operativo Windows en un script de perfil:

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

Las secciones siguientes muestran los encabezados de Client Hint y la semántica de uso de scripts de perfil correspondiente.

#### Sec-CH-UA

Entropía: Documentación baja: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank} Atributo de audiencia: Uso del script del perfil del explorador: `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

Entropía: Alta documentación: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank} Atributo de audiencia: Expuesto a los usuarios mediante scripts de perfil.
Uso del script de perfil: `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

Entropía: Alta documentación: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank} Atributo de audiencia: Expuesto a los usuarios mediante scripts de perfil.
Uso del script de perfil: `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

Entropía: Alta documentación: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank} Atributo de audiencia: Uso del script del perfil del explorador: `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

Entropía: Documentación baja: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank} Atributo de audiencia: Uso del script del perfil móvil: `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

Entropía: Alta documentación: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank} Atributo de audiencia: Uso del script del perfil móvil: `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

Entropía: Documentación baja: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank} Atributo de audiencia: Sistema operativo Uso de scripts de perfil: `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

Entropía: Alta documentación: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank} Atributo de audiencia: Expuesto a los usuarios mediante scripts de perfil.
Uso del script de perfil: `user.clientHint('sec-ch-ua-platform-version')`

## Pasar sugerencias del cliente a [!DNL Adobe Target]

Las secciones siguientes contienen más información sobre cómo pasar sugerencias del cliente, según el [!DNL Target] implementación.

### at.js versión 2.9.0 (o posterior)

A partir de at.js 2.9.0, las sugerencias del cliente del agente de usuario se recopilarán automáticamente desde el explorador y se enviarán a [!DNL Target] when `getOffer/getOffers()` se llama. De forma predeterminada, at.js recopila solo las sugerencias de cliente de &quot;baja entropía&quot;. Si realiza la segmentación de audiencia o utiliza secuencias de comandos de perfil basadas en datos clasificados como &quot;Alta tropisa&quot; desde las secciones anteriores, debe configurar at.js para que recopile sugerencias del cliente de &quot;Alta tropisa&quot; desde el explorador a través de `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### SDK del lado del servidor

Para obtener más información sobre cómo pasar sugerencias del cliente mediante SDK del lado del servidor, consulte [Sugerencias del cliente](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} en la sección *SDK para Adobe Target* documentación.
