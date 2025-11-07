---
keywords: datos dinámicos;activos;datos;ofertas;ofertas personalizadas;ofertas personales;reemplazo del token
description: Aprenda a pasar datos dinámicos a Ofertas en  [!DNL Adobe Target].
title: ¿Cómo paso datos dinámicos a las ofertas?
feature: Experiences and Offers
exl-id: b8f9c6eb-1000-41a2-aa3f-bc42c1ef5669
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 52%

---

# Transmisión dinámica de datos en ofertas

Puede mostrar dinámicamente la información del visitante almacenada en el perfil [!DNL Adobe Target]. Del mismo modo, la información de la actividad (como el nombre de la actividad o el de la experiencia) también se puede utilizar para crear una sola oferta que devuelva contenido personalizado de forma dinámica en función de los intereses, el comportamiento anterior y el perfil general del visitante.

## Casos comerciales

* Promocione una oferta de descuento para reorganizar o reponer el último producto comprado. En lugar de crear una oferta separada para cada elemento del catálogo, puede crear una oferta con texto dinámico que indique el último producto comprado del perfil y muestre un vínculo en la oferta.
* Un visitante llega a su página de destino con `keyword=world` `cup`. El término *World cup* aparece en la oferta.
* Personalice una etiqueta de recomendaciones con información como (1) el último elemento agregado al carro de compras de un visitante (Nike Air Max 1000 s), (2) la preferencia de color del visitante (negro) y (3) la categoría favorita del visitante, sin tener en cuenta los zapatos (sudaderas). Ejemplo: «Use estas fantásticas sudaderas con capucha negra para complementar sus Nike Air Max 1000.»

## Ventajas técnicas

Dado que las preferencias, los comportamientos y el estado específicos del visitante se pueden almacenar en el perfil del visitante, puede repetir este mensaje en sus próximas visitas. Las ofertas dinámicas permiten una mayor escala al permitirle configurar una sola oferta dentro de una actividad que muestra mensajes personalizados para todos los visitantes. A medida que la intención del visitante cambia, el contenido del sitio web refleja automáticamente dichos cambios.

## Ejemplo

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Código de oferta HTML: `Get your ${profile.keyword} information here!`
* Visitante ve: ¡Obtenga su información de la Copa del Mundo aquí!

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

Para diseños de [!DNL Recommendations], vea ejemplos adicionales en [Información general de diseño](/help/main/c-recommendations/c-design-overview/design-overview.md).

## Implementación

Para los parámetros de perfil transferidos a un mbox, utilice la sintaxis:

`${profile.parameter}`

Para los parámetros de perfil creados en un script de perfil, utilice la sintaxis:

`${user.parameter}`

Cuando utilice atributos dinámicos en un diseño [!DNL Recommendations], debe insertar una barra invertida ( \ ) antes del signo de dólar ( $ ) para que el valor dinámico se represente correctamente:

`\${user.endpoint.lastViewedEntity}`

Estas variables se sustituyen por el valor que hay en el servidor, así que no es necesario usar comillas ni ningún otro JavaScript para la visualización correcta.

También se pueden especificar valores predeterminados para los valores que desea exponer a las ofertas. La sintaxis es similar a esta:

`${user.testAttribute default="All Items!"}`

Cuando `testAttribute` no existe o está en blanco, &quot;¡Todos los elementos!&quot; está escrito. Si un valor de atributo vacío es válido y desea escribirlo en lugar de mostrar el valor predeterminado, puede usar:

`${user.testAttribute default="All Items!" show_blank="true"}`

También puede introducir y extraer valores para mostrar. Si su valor tiene un apóstrofo, por ejemplo, puede aplicar un escape al valor para que no interrumpa el JavaScript en la página. (Las ofertas se escriben en JavaScript, por lo que un solo apóstrofo puede confundirse con una cotización). Por ejemplo:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

Para parámetros de oferta (offer.name, offer.id) utilizados en el contenido de una oferta:

Si esa oferta es una de las varias establecidas en una experiencia, el valor de la última oferta añadida rellena el valor del parámetro. Es decir, estos parámetros se evalúan en el nivel de experiencia.