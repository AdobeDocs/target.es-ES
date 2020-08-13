---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Información sobre las directivas de directiva de seguridad de contenido (CSP) que debe agregar al usar Adobe Target at.js 2.1 o posterior.
title: Directivas de seguridad de contenido (CSP)
feature: privacy and security
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# Directivas de directiva de seguridad de contenido (CSP)

Si utiliza la directiva [de seguridad](https://en.wikipedia.org/wiki/Content_Security_Policy) del contenido (CSP) para la implementación de Destinatario, debe agregar las siguientes directivas CSP al usar [at.js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al [!DNL Target] borde.
* `style-src unsafe-inline`. Necesario para la ocultación previa y el control de parpadeo.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta HTML.
