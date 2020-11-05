---
keywords: mbox.js faq;mbox.js frequently asked questions;document.write;tt.omtrdc.net;parser blocking
description: Respuestas a las preguntas más frecuentes sobre mbox.js.
title: Preguntas más frecuentes de mbox.js
feature: null
subtopic: Getting Started
uuid: af3105ab-87d9-4dbf-a380-b72788928958
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 98%

---


# Preguntas más frecuentes de mbox.js{#mbox-js-frequently-asked-questions}

Respuestas a las preguntas más frecuentes sobre mbox.js.

## ¿Cuál es el impacto de mbox.js en el tiempo de carga de las páginas?{#section_90B3B94FE0BF4B369577FCB97B67F089}

Para obtener más información, consulte [Ventajas de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits).

## ¿Por qué recibo mensajes de advertencia de “Analizador bloqueado” en Google Chrome cuando uso mbox.js y document.write?{#section_355A3A5BF02F42EEB8271C96EF41590A}

Este mensaje de la consola aparece cuando utiliza Chrome en diferentes casos en los que se está usando la función `document.write` en el archivo mbox.js. Este es un mensaje de advertencia y no debe afectar a su proceso de configuración de la actividad.

La mejor manera de evitar esta situación es  [migrar su implementación de Target a la biblioteca de JavaScript de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA), que no utiliza la función `document.write`. El uso de at.js ofrece más ventajas que el uso de mbox.js. Para obtener más información, consulte [Preguntas más frecuentes de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## ¿Por qué no se activan los mboxes en mis páginas web?{#section_4BA5DA424B734324AAB51E4588FA50F5}

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

Los navegadores modernos no guardan las cookies si se utilizan estos dominios, a no ser que se personalice el ajuste `cookieDomain` mediante targetGlobalSettings(). Para obtener más información, consulte [Uso de instancias basadas en la nube con Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## ¿Cuál es el dominio tt.omtrdc.net al cual se dirigen las llamadas del servidor de Target?{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] es el nombre de dominio de la red EDGE de Adobe, que se utiliza para recibir todas las llamadas de servidor para Target.

## ¿Por qué at.js y mbox.js no utilizan los indicadores de cookies HttpOnly y Secure?{#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly solo se puede establecer mediante código del servidor. Las cookies de Target, como mbox, se crean y guardan mediante código JavaScript, de modo que Target no puede utilizar el indicador de cookie HttpOnly.

Secure se puede establecer mediante JavaScript solo cuando la página se carga mediante HTTPS. Si la página se carga inicialmente mediante HTTP, JavaScript no puede establecer este indicador. Además, si se utiliza el indicador Secure, la cookie estará disponible solo en páginas HTTPS.

Para garantizar que Target pueda rastrear correctamente a los usuarios, y dado que las cookies se generan en el cliente, Target no utiliza ninguno de estos indicadores.
