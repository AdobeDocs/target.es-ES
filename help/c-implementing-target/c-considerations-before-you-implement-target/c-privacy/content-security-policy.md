---
keywords: directiva de seguridad de contenido;csp;at.js;lista de elementos permitidos;parpadeo;ocultar previamente;ocultar previamente;ocultar previamente
description: Información sobre las directivas de Content Security Policy (CSP) que debe agregar al usar Adobe Target at.js 2.1 o posterior.
title: Directivas de seguridad de contenido (CSP)
subtopic: Primeros pasos
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Directivas de directiva de seguridad de contenido (CSP)

Si utiliza la directiva [de seguridad](https://en.wikipedia.org/wiki/Content_Security_Policy) del contenido (CSP) para la implementación de Target, debe agregar las siguientes directivas CSP al usar [at.js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con `*.tt.omtrdc.net` lista blanca. Necesario para permitir la solicitud de red al [!DNL Target] borde.
* `style-src unsafe-inline`. Necesario para la ocultación previa y el control de parpadeo.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta HTML.
