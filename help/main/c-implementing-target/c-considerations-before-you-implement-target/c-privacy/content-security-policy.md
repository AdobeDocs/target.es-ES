---
keywords: política de seguridad de contenido;csp;at.js;lista de elementos permitidos;lista de permitidos;parpadeo;ocultar previamente;ocultamiento previo;preocultación
description: Obtenga información sobre las directivas de la Política de seguridad de contenido (CSP) que debe agregar al usar Adobe Target.
title: How [!DNL Target] ¿Gestionar políticas de seguridad de contenido (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# Directivas de la política de seguridad de contenido (CSP)

Si está utilizando [Política de seguridad de contenido](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para su [!DNL Adobe Target] implementación, debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red a la variable [!DNL Target] borde.
* `style-src unsafe-inline`. Necesaria para el control de parpadeo y preocultación.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta de HTML.
