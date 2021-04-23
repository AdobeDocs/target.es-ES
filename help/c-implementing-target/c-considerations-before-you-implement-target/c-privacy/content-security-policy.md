---
keywords: política de seguridad de contenido;csp;at.js;lista de elementos permitidos;lista de permitidos;parpadeo;ocultar previamente;ocultamiento previo;preocultación
description: Obtenga información sobre las directivas de la Política de seguridad de contenido (CSP) que debe agregar al usar Adobe Target.
title: ¿Cómo gestiona [!DNL Target] las políticas de seguridad de contenido (CSP)?
feature: Privacidad y seguridad
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# Directivas de directiva de seguridad de contenido (CSP)

Si está utilizando [Política de seguridad de contenido](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para su implementación [!DNL Adobe Target], debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con  `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al borde [!DNL Target].
* `style-src unsafe-inline`. Necesaria para el control de parpadeo y preocultación.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que puede formar parte de una oferta HTML.
