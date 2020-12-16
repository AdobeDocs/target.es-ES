---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Información sobre las directivas de directiva de seguridad de contenido (CSP) que debe agregar al usar Adobe Target at.js 2.1 o posterior.
title: Directivas de seguridad de contenido (CSP)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# Directivas de directiva de seguridad de contenido (CSP)

Si está utilizando [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para la implementación de Destinatario, debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con  `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al borde [!DNL Target].
* `style-src unsafe-inline`. Necesario para la ocultación previa y el control de parpadeo.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta HTML.
