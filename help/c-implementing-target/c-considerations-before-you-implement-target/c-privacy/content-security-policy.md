---
description: Información sobre las directivas de la Directiva de seguridad de contenido (CSP) que debe agregar al utilizar Adobe Target at. js 2.1 o posterior.
keywords: política de seguridad de contenido; csp; at. js; lista blanca; parpadeo; pre-hide; pre-hide; preocultar
seo-description: Información sobre las directivas de la Directiva de seguridad de contenido (CSP) que debe agregar al utilizar Adobe Target at. js 2.1 o posterior.
seo-title: Políticas de seguridad de contenido (CSP)
solution: Target
subtopic: Primeros pasos
title: Directivas de políticas de seguridad de contenido (CSP)
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Directivas de políticas de seguridad de contenido (CSP)

Si utiliza [la Política](https://en.wikipedia.org/wiki/Content_Security_Policy) de seguridad de contenido (CSP) para la implementación de Target, debe agregar las siguientes directivas CSP al utilizar [at. js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con `*.tt.omtrdc.net` la lista blanca. Necesario para permitir la solicitud de red al [!DNL Target] borde.
* `style-src unsafe-inline`. Necesario para ocultamiento previo y control de parpadeo.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que puede formar parte de una oferta HTML.
