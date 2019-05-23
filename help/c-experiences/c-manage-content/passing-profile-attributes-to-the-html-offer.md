---
description: Puede mostrar valores de perfil e información de actividad directamente en una oferta HTML o JSON.
keywords: dynamic data; recursos; data; ofertas; ofertas personalizadas; ofertas personales; sustitución de token
seo-description: Puede mostrar valores de perfil e información de actividad directamente en una oferta HTML o JSON.
seo-title: Transmisión dinámica de datos en ofertas
solution: Target
title: Transmisión dinámica de datos en ofertas
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: f792c0b995e0f4445d3c3849a431d64b6bd60324

---


# Transferir datos dinámicos en ofertas{#pass-dynamic-data-into-offers}

Puede mostrar dinámicamente la información del visitante almacenada en el perfil de Target. Del mismo modo, la información de actividad (como el nombre de la actividad o el nombre de la experiencia) también se puede utilizar para crear una sola oferta que devuelva dinámicamente contenido personalizado en función de los intereses del visitante, el comportamiento anterior y el perfil general.

**Casos de uso**

* Promocione una oferta de descuento para «reorganizar» o «reponer» el último producto comprado. En lugar de crear una oferta separada para cada elemento del catálogo, puede crear una oferta con texto dinámico que lea el «último producto comprado» del perfil y muestra un vínculo en la oferta.
* Un visitante llega a su página de destino con `keyword=world` `cup`. El término *World cup* aparece en la oferta.
* Personalice una etiqueta de recomendaciones con información como (1) el último elemento agregado al carro de compras de un visitante (Nike Air Max 1000 s), (2) la preferencia de color del visitante (negro) y (3) la categoría favorita no zapatos del visitante (hooills). Ejemplo: &quot; Obtenga acceso a su &quot;Nike Air Max 1000 s&quot; con estos fantásticos &quot;black &#39;&quot; hoodies &quot;!&quot;


**Ventajas técnicas**

Puesto que las preferencias, los comportamientos, el estado, etc. de usuario son específicos del usuario. se puede almacenar en el perfil del usuario, puede repetir este mensaje en sus próximas visitas. Las ofertas dinámicas permiten una mayor escala permitiéndole configurar una sola oferta dentro de una actividad que muestre mensajes personalizados para todos los visitantes. A medida que cambia la intención del visitante, el contenido del sitio web refleja automáticamente esos cambios.

**Ejemplo**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Código de oferta HTML: `Get your ${profile.keyword} information here!`
* El usuario verá: Get your World Cup information here!

Los siguientes valores se pueden “sustituir con testigos”:

| Valores | Ejemplos |
|--- |--- |
| Parámetros de perfil en mbox | `${profile.age}` |
| Parámetros de perfil de secuencia de comandos | `${user.lifetimeSpend}` |
| Parámetros de mbox | `${mbox.favoriteColor}` |
| Información de la campaña | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}` y `${campaign.recipe.trafficType}` |
| ID de visitante único | `${user.pcId}` |
| ID de sesión único | `${user.sessionId}` |
| Primera sesión del visitante (verdadero o falso) | `${user.isFirstSession}` |
| Comportamiento anterior | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

Información de registro en la consola con fines de depuración como `${campaign.name}`, `${campaign.id}`por `${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}`ejemplo `${offer.id}`, `${campaign.name}`

Para ver los diseños de Recomendaciones, consulte Ejemplos adicionales en [Información general de diseño](/help/c-recommendations/c-design-overview/design-overview.md).

**Implementación**

Para los parámetros de perfil pasados a un mbox, utilice la sintaxis: `${profile.parameter}` Para los parámetros de perfil creados en un script de perfil, utilice la sintaxis:

`${user.parameter}`

Al utilizar atributos dinámicos en un diseño de Recomendaciones, debe insertar una barra invertida (&#39;\&#39;) antes del signo de dólar (&#39; $&#39;) para que el valor dinámico se represente correctamente: `\${user.endpoint.lastViewedEntity}`

Estas variables se sustituyen por el valor que hay en el servidor, así que no es necesario usar comillas ni ningún otro JavaScript para la visualización correcta.

Los valores predeterminados también pueden ser específicos para valores que desee exponer a ofertas. La sintaxis es similar a esta:

`${user.testAttribute default="All Items!"}`

Si `testAttribute` no existe o está en blanco, “All Items!” se escribirá. Si un valor de atributo vacío es válido y desea escribirlo en lugar de mostrar el valor predeterminado, puede usar:

`${user.testAttribute default="All Items!" show_blank="true"}`

También puede introducir y extraer valores para mostrar. Si los valores tienen, por ejemplo, un apóstrofo, es posible que desee extraer el valor para que no interrumpa el JavaScript de la página. (Las ofertas de se escriben en JavaScript, por lo que un solo apóstrofo se puede confundir con las comillas). Por ejemplo:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`