---
keywords: dynamic data;assets;data;offers;personalized offers;personal offers;token replace
description: Puede mostrar valores de perfil de e información de la actividad directamente en una oferta HTML o JSON.
title: Transmisión dinámica de datos en ofertas
feature: offers
translation-type: tm+mt
source-git-commit: 431ccc937a3ad4aaf735b31b4790ead43a6fc4d9
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 94%

---


# Transferir datos dinámicos en ofertas{#pass-dynamic-data-into-offers}

Puede mostrar, de forma dinámica, la información del visitante almacenada en el perfil de Target. Del mismo modo, la información de la actividad (como el nombre de la actividad o el de la experiencia) también se puede utilizar para crear una sola oferta que devuelva contenido personalizado de forma dinámica en función de los intereses, el comportamiento anterior y el perfil general del visitante.

**Casos de uso**

* Promocione una oferta de descuento para reorganizar o reponer el último producto comprado. En lugar de crear una oferta separada para cada elemento del catálogo, puede crear una oferta con texto dinámico que indique el último producto comprado del perfil y muestre un vínculo en la oferta.
* Un visitante llega a su página de destino con `keyword=world` `cup`. El término *World cup* aparece en la oferta.
* Personalice una etiqueta de recomendaciones con información como (1) el último elemento agregado al carro de compras de un visitante (Nike Air Max 1000 s), (2) la preferencia de color del visitante (negro) y (3) la categoría favorita del visitante, sin tener en cuenta los zapatos (sudaderas). Ejemplo: «Use estas fantásticas sudaderas con capucha negra para complementar sus Nike Air Max 1000.»


**Ventajas técnicas**

Puesto que las preferencias, los comportamientos, el estado, etc. específicos del usuario se pueden almacenar en el perfil del usuario, puede repetir este mensaje en sus próximas visitas. Las ofertas dinámicas permiten una mayor escala al permitirle configurar una sola oferta dentro de una actividad que muestra mensajes personalizados para todos los visitantes. A medida que la intención del visitante cambia, el contenido del sitio web refleja automáticamente dichos cambios.

**Ejemplo**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Código de oferta HTML: `Get your ${profile.keyword} information here!`
* El usuario verá: Get your World Cup information here!

Los siguientes valores se pueden “sustituir con testigos”:

| Valor | Ejemplos |
|--- |--- |
| Parámetros de perfil en mbox | `${profile.age}` |
| Parámetros de perfil de secuencia de comandos | `${user.lifetimeSpend}` |
| Parámetros de mbox | `${mbox.favoriteColor}` |
| Información de la campaña | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}` y `${campaign.recipe.trafficType}` |
| ID de visitante único | `${user.pcId}` |
| ID de sesión único | `${user.sessionId}` |
| Primera sesión del visitante (verdadero o falso) | `${user.isFirstSession}` |
| Comportamiento anterior | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

Información de registro en la consola con fines de depuración, como `${campaign.name}`, `${campaign.id}`, `${campaign.recipe.name}`, `${campaign.recipe.id}`, `${offer.name}`, `${offer.id}`, `${campaign.name}`

Para ver los diseños de Recommendations, consulte los ejemplos adicionales en [Información general de diseño](/help/c-recommendations/c-design-overview/design-overview.md).

**Implementación**

Para los parámetros de perfil transferidos a un mbox, utilice la sintaxis: `${profile.parameter}` Para los parámetros de perfil creados en un script de perfil, utilice la sintaxis:

`${user.parameter}`

Al utilizar atributos dinámicos en un diseño de Recommendations, debe insertar una barra invertida ( \ ) antes del signo de dólar ( $ ) para que el valor dinámico se procese correctamente: `\${user.endpoint.lastViewedEntity}`

Estas variables se sustituyen por el valor que hay en el servidor, así que no es necesario usar comillas ni ningún otro JavaScript para la visualización correcta.

Los valores predeterminados también pueden ser específicos para valores que desee exponer a ofertas. La sintaxis es similar a esta:

`${user.testAttribute default="All Items!"}`

Si `testAttribute` no existe o está en blanco, “All Items!” se escribirá. Si un valor de atributo vacío es válido y desea escribirlo en lugar de mostrar el valor predeterminado, puede usar:

`${user.testAttribute default="All Items!" show_blank="true"}`

También puede introducir y extraer valores para mostrar. Si los valores tienen, por ejemplo, un apóstrofo, es posible que desee extraer el valor para que no interrumpa el JavaScript de la página. (Las ofertas de se escriben en JavaScript, por lo que un solo apóstrofo se puede confundir con las comillas). Por ejemplo:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`