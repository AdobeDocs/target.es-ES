---
keywords: política de seguridad de contenido;csp;at.js;lista de elementos permitidos;lista de permitidos;parpadeo;ocultar previamente;ocultamiento previo;preocultación
description: Obtenga información sobre las directivas de la política de seguridad de contenido (CSP) que debe agregar al usar Adobe Target.
title: ¿Cómo administra  [!DNL Target]  las políticas de seguridad de contenido (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 29%

---

# Directivas de la política de seguridad de contenido (CSP)

Si está utilizando una [política de seguridad de contenido](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para su implementación de [!DNL Adobe Target], debe agregar las siguientes directivas CSP al utilizar [at.js 2.1 o posterior](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` con `*.tt.omtrdc.net` incluido en la lista de permitidos. Necesario para permitir la solicitud de red al perímetro de [!DNL Target].
* `style-src unsafe-inline`. Necesaria para el control de parpadeo y preocultación.
* `script-src unsafe-inline`.  Necesario para permitir la ejecución de JavaScript que pueda formar parte de una oferta de HTML.

## Preguntas más frecuentes

Consulte las siguientes preguntas frecuentes sobre las políticas de seguridad:

### ¿Las políticas de Flash entre dominios y uso compartido de recursos de origen cruzado presentan problemas de seguridad?

La forma recomendada de implementar la política CORS es permitir el acceso solo a orígenes de confianza que lo requieran a través de una lista de permitidos de dominios de confianza. Lo mismo puede decirse de la política entre dominios de Flash. Algunas [!DNL Adobe Target] a los clientes les preocupa el uso de caracteres comodín para los dominios en [!DNL Target]. El problema es que si un usuario ha iniciado sesión en una aplicación y visita un dominio permitido por la directiva, cualquier contenido malicioso que se ejecute en ese dominio puede recuperar contenido confidencial de la aplicación y llevar a cabo acciones dentro del contexto de seguridad del usuario que ha iniciado sesión. Esto se conoce comúnmente como Falsificación de solicitudes entre sitios (CSRF).

En un [!DNL Adobe Target] sin embargo, estas políticas no deben representar un problema de seguridad.

&quot;adobe.tt.omtrdc.net&quot; es un dominio propiedad del Adobe. [!DNL Adobe Target] es una herramienta de prueba y personalización y se espera que [!DNL Target] puede recibir y procesar solicitudes desde cualquier lugar sin requerir ninguna autenticación. Estas solicitudes contienen pares de clave/valor que se utilizan para pruebas A/B, recomendaciones o personalización de contenido.

[!DNL Adobe] no almacena información de identificación personal (PII) u otra información confidencial sobre [!DNL Adobe Target] servidores Edge a los que señala &quot;adobe.tt.omtrdc.net&quot;.

Se espera que [!DNL Target] se puede acceder a él desde cualquier dominio a través de llamadas de JavaScript. La única manera de permitir este acceso es aprovechando &quot;Access-Control-Allow-Origin&quot; con un comodín.
