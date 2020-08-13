---
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
description: Esta página contiene una lista de perfiles, variables y parámetros que son útiles en los scripts de perfil.
title: Glosario de perfiles y variables
feature: visitor profiles
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 93%

---


# Glosario de perfiles y variables{#profile-and-variable-glossary}

Esta página contiene una lista de perfiles, variables y parámetros que son útiles en los scripts de perfil.

## Perfiles integrados {#section_2B694370003C4F8E8E29E0B2F6E52045}

| Perfil | Notas |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | Devuelven el ID de campaña de todas las campañas o actividades en las que se encuentra el usuario aunque este no haya interactuado con la campaña o actividad en cuestión durante la sesión actual. |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | Devuelve una matriz de afinidades que ha rellenado el visitante |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | El agente de usuario |
| user.header | Todos los perfiles `user.header` están integrados en los datos de encabezado de las peticiones de mbox |
| user.header(&#39;x-cluster-client-ip&#39;)<br><br>oruser.header(&#39;x-forwarded-for&#39;) | La dirección IP pública de la conexión de red en que se encuentra el visitante.<br>Se puede consultar de varias maneras, por ejemplo, usando [whatismyip.com](https://www.whatismyip.com/). La dirección IP no es la dirección NAT (dirección interna), que empieza por 10., 192.168. o 172. |
| user.header(&#39;host&#39;) | Nombre de host del visitante |
| user.header(&#39;cookie&#39;) | Datos de cookies del visitante |
| user.header(&#39;user-agent&#39;) | Agente de usuario del navegador del visitante |
| user.header(&#39;accept-language&#39;) | Idioma del visitante |
| user.header(&#39;accept-encoding&#39;) | Codificación de caracteres del visitante |
| user.header(&#39;accept&#39;) | Idioma del visitante y codificación de caracteres |
| user.header(&#39;connection&#39;) | Conexión del servidor. Por ejemplo: keep-live |
| user.header(&#39;referrer&#39;) | Dirección URL del sitio web de la página actual del visitante. No funciona con Internet Explorer. |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | Atributos de perfil persistentes creados desde scripts de perfil. También hace referencia a perfiles del “sistema” como la geolocalización, el recuento de visitas, etc. |
| profile.get(&#39;param_name&#39;) | La forma correcta de obtener un parámetro de perfil para utilizarlo en una secuencia de comandos de perfil es el método perfil.get(&#39;param_name&#39;). |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | Los parámetros de mbox que se vuelven persistentes debido a su prefijo perfil.  prefijo. |
| profile.browserTime | La hora local del navegador del visitante. Para la hora del sistema, cree un nuevo objeto de fecha en la secuencia de comandos del perfil |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| parameter= | Término genérico para los valores adicionales que se transmiten con un mbox, normalmente con el formato de pares de nombre-valor. No es persistente a menos que así se defina con `profile.parameter` o `user.parameter`. |

## Variables URL {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## Perfiles de operador de telefonía móvil y ubicación geográfica {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Variables de mbox {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| Variable | Notas |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| Parámetros que se transfieren automáticamente en todas las peticiones<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| Parámetros transferidos con mboxes de pedidos:<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | Un parámetro de mbox para sincronizar un ID de cliente con el mboxPCID de Target. Un ID de cliente es un ID que su empresa usa para rastrear los visitantes, como pueden ser un ID de administración de la relación con los clientes, un ID de pertenencia u otro similar. A continuación, ese ID se puede usar para agregar información a través de las API de perfil y   [Atributos del cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | En cada llamada de mbox, la página se asigna a un valor. |
| mboxDebug | Solo se utiliza para información de depuración. Se añade a la URL de la página donde el mbox.js lo busca. |
| mboxOverride.browserIp | Establece una configuración geográfica distinta a la ubicación actual para realizar pruebas.<br>**Nota:** Los parámetros mboxOverride solo deben utilizarse al probar la actividad, y no en la fase de producción. El uso de cualquier parámetro mboxOverride puede provocar discrepancias en los informes al usar [Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Utilice el [modo de control de calidad de la actividad](/help/c-activities/c-activity-qa/activity-qa.md) durante las pruebas para asegurarse de que la actividad funciona del modo esperado antes de insertarla en su entorno activo. |

## Atributos del cliente {#section_62B4821EB6564FF4A14159A837AD4EDB}

Se puede hacer referencia a los atributos del cliente en las secuencias de comandos de perfil con el formato `crs.get('<Datasource Name>.<Attribute name>')`.

Estos atributos también están disponibles como tokens en secuencias de comandos de perfil y directamente en ofertas sin que resulte necesario requerir primero una secuencia de comandos de perfil. El token debe presentar el siguiente formato: `${crs.datasourceName.attributeName}`. Tenga en cuenta que los espacios del `datasourceName` se deben eliminar de cualquier llamada de API.
