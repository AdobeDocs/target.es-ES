---
keywords: directiva de seguridad de contenido;csp;at.js;lista de elementos permitidos;lista de permitidos;parpadeo;pre-ocultar;pre-ocultar;ocultamiento previo
description: Obtenga información sobre las directivas de directiva de seguridad de contenido (CSP) que debe agregar al usar Adobe Target.
title: ¿Cómo gestiona Destinatario las políticas de seguridad del contenido (CSP)?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# Directivas de directiva de seguridad de contenido (CSP)

Si está utilizando [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para su implementación [!DNL Adobe Target], debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con  `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al borde [!DNL Target].
* `style-src unsafe-inline`. Necesario para la ocultación previa y el control de parpadeo.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta HTML.
