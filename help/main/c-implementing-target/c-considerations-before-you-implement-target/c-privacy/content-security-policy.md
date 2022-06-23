---
keywords: política de seguridad de contenido;csp;at.js;lista de elementos permitidos;lista de permitidos;parpadeo;ocultar previamente;ocultamiento previo;preocultación
description: Obtenga información sobre las directivas de la política de seguridad de contenido (CSP) que debe agregar al usar Adobe Target.
title: ¿Cómo administra  [!DNL Target]  las políticas de seguridad de contenido (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 97%

---

# Directivas de la política de seguridad de contenido (CSP)

Si está utilizando una [política de seguridad de contenido](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para su implementación de [!DNL Adobe Target], debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/):

* `connect-src` con `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al perímetro de [!DNL Target].
* `style-src unsafe-inline`. Necesaria para el control de parpadeo y preocultación.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta de HTML.

## Preguntas más frecuentes

Consulte las siguientes preguntas frecuentes sobre las políticas de seguridad:

### ¿Las políticas de Flash entre dominios y uso compartido de recursos de origen cruzado (CORS) presentan problemas de seguridad?

La forma recomendada de implementar la política CORS es permitir el acceso solo a orígenes de confianza que la requieran a través de una lista de dominios permitidos de confianza. Lo mismo puede decirse de la política entre dominios de Flash. A algunos clientes de [!DNL Adobe Target] les preocupa el uso de caracteres comodín para los dominios en [!DNL Target]. El problema es que si un usuario ha iniciado sesión en una aplicación y visita un dominio permitido por la directiva, cualquier contenido malicioso que se ejecute en ese dominio puede recuperar contenido confidencial de la aplicación y llevar a cabo acciones dentro del contexto de seguridad del usuario que ha iniciado sesión. Esto se conoce comúnmente como Falsificación de solicitudes entre sitios (CSRF).

En una implementación de [!DNL Adobe Target], sin embargo, estas políticas no deben representar un problema de seguridad.

“adobe.tt.omtrdc.net” es un dominio propiedad del Adobe. [!DNL Adobe Target] es una herramienta de prueba y personalización y se espera que [!DNL Target] pueda recibir y procesar solicitudes desde cualquier lugar sin requerir ninguna autenticación. Estas solicitudes contienen pares de clave/valor que se utilizan para pruebas A/B, recomendaciones o personalización de contenido.

[!DNL Adobe] no almacena información de identificación personal (PII) u otra información confidencial en servidores perimetrales de [!DNL Adobe Target] a los que señala “adobe.tt.omtrdc.net”.

Se espera que se pueda acceder a [!DNL Target] desde cualquier dominio a través de llamadas de JavaScript. La única manera de permitir este acceso es usando “Access-Control-Allow-Origin” con un comodín.
