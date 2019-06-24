---
description: Información sobre Target y el estándar samesite IETF utilizado con Google Chrome versión 76.
keywords: google; samesite
seo-description: Información sobre Adobe Target y el estándar samesite IETF introducido con Google Chrome versión 76.
seo-title: Políticas de cookies de Adobe Target y samesite
solution: Target
subtopic: Primeros pasos
title: Políticas de cookies de Google Chrome samesite
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: b6b649e31173e80fd0a79b3ce695c130052bf81a

---


# Políticas de cookies de Google Chrome samesite

Google ha anunciado recientemente que a partir de Chrome 76, que se ha marcado para una versión del 30 de julio de 2019, los desarrolladores deben especificar explícitamente qué cookies pueden funcionar en distintos sitios web y qué cookies pueden rastrear a usuarios.

## Información general de samesite

To provide safeguards around when cookies can be sent across sites so that users are protected, Google adds support for an IETF standard called &quot;SameSite&quot; in Google Chrome 76 (and later), which requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

Existen tres valores diferentes que se pueden pasar al atributo samesite: Estricto, Lax o Ninguno.

| Valor | Descripción |
| --- | --- |
| Estricto | Solo se puede acceder a las cookies con este ajuste al visitar el dominio en el que se estableció inicialmente. En otras palabras: Estricto bloquea completamente la cookie para que se utilice entre sitios. Esta opción es mejor para las aplicaciones que requieren mucha seguridad, como bancos. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| Ninguna | Las cookies con este ajuste funcionan de la misma manera que las cookies funcionan hoy. |

Si lo tiene en cuenta, Chrome 76 (y posterior) introduce dos ajustes: &quot; Samesite por cookies predeterminadas &quot;y&quot; Cookies sin samesite debe ser seguro &quot;. Los usuarios pueden habilitar la configuración o ambas opciones.

| Configuración | Descripción |
| --- | --- |
| Samesite por cookies predeterminadas | When set, all cookies that don&#39;t specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| Las cookies sin samesite deben ser seguras | When set, cookies without the SameSite attribute or with `SameSite = None`, need to be Secure. Proteger en este contexto significa que todas las solicitudes del explorador deben seguir el protocolo HTTPS. Las cookies que no respetan este requisito son rechazadas. |

![Página de configuración de samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## Target sigue las optimizaciones de seguridad de Google

Con Target, queremos asegurarnos de tener éxito siempre respaldando las últimas prácticas recomendadas del sector para la seguridad. Nos complace anunciar que Target admite la nueva configuración de seguridad introducida en Google Chrome 76.

Cuando los visitantes han activado el ajuste de cookies predeterminado «samesite», Target continúa ofreciendo personalización sin ningún impacto y sin ninguna intervención por parte de usted. Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

Cuando los visitantes habilitan «Cookies sin samesite debe ser una opción segura», y usted no opta por la función de seguimiento entre dominios de Target, las cookies de origen de Target seguirán funcionando. However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. Esto significa que debe asegurarse de que los sitios utilicen el protocolo HTTPS. Target&#39;s client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## ¿Qué debe hacer?

Revise la siguiente tabla para comprender lo que necesita hacer para que Target siga funcionando para usuarios de Google Chrome 76 +.

La tabla contiene las columnas siguientes:

* **Biblioteca de cliente de Target**: Si utiliza mbox. js, at. js 1.*x*o at. js 2.*x* en sus sitios y cómo afectan los ajustes de Google Chrome
* **Samesite por cookies predeterminadas = Habilitado**: Si los visitantes tienen «samesite por predeterminado cookies habilitadas» en Chrome 76 +,¿cómo le afectará y hay algo que necesita hacer para que Target siga funcionando?
* **Las cookies sin samesite deben ser seguras = Habilitado**: Si los visitantes tienen &quot;Cookies sin samesite debe ser seguro&quot; habilitado en Chrome 76 +,¿cómo le afecta a usted y es algo que necesita hacer para que Target siga funcionando?
* **Seguimiento de dominios cruzados de Adobe Target = Habilitado**: Si los visitantes tienen habilitado el &quot;Mismo sitio por cookies predeterminadas&quot; y &quot;Cookies sin samesite debe ser seguro&quot; habilitado en Chrome 76 +, y está utilizando Target para rastrear entre dominios,¿cómo le afectará a usted y es algo que necesita hacer para que Target siga funcionando?

| Biblioteca de cliente de Target | Samesite by default cookies = Enabled | Las cookies sin samesite deben ser seguras = Habilitado | Seguimiento de dominios cruzados de Adobe Target = Habilitado |
| --- | --- | --- | --- |
| mbox.js | Sin impacto porque mbox. js usa una cookie propia | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | Los clientes deben habilitar el protocolo HTTPS para el sitio.<br>Target usa una cookie de terceros para rastrear usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y para sitios que utilicen el protocolo HTTPS. |
| at.js 1.*x* | Sin impacto porque at. js 1.*x* usa una cookie de origen | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | Los clientes deben habilitar el protocolo HTTPS para el sitio.<br>Target usa una cookie de terceros para rastrear usuarios y Google requiere que las cookies de terceros tengan `SameSite = None` y para sitios que utilicen el protocolo HTTPS |
| at.js 2.*x* | Sin impacto porque at. js 2.*x* usa una cookie de origen | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | El seguimiento entre dominios no se admite en at. js 2.*x* y, por lo tanto, no hay ningún impacto en los clientes |

## ¿Qué necesita hacer Adobe?

| Biblioteca de cliente de Target | Samesite by default cookies = Enabled | Las cookies sin samesite deben ser seguras = Habilitado | Seguimiento de dominios cruzados de Adobe Target = Habilitado |
| --- | --- | --- | --- |
| mbox.js | Sin impacto porque mbox. js usa una cookie propia | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1.*x* | Sin impacto porque at. js 1.*x* usa una cookie de origen | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2.*x* | Sin impacto porque at. js 2.*x* usa una cookie de origen | Sin impacto porque los clientes no utilizan el seguimiento entre dominios | El seguimiento entre dominios no se admite en at. js 2.*x* |

## Conclusión 

Dado que el sector realiza avances para crear una Web más segura para los consumidores, Target está absolutamente comprometido a ofrecer experiencias personalizadas durante la reunión y superar las expectativas de privacidad de los visitantes.
