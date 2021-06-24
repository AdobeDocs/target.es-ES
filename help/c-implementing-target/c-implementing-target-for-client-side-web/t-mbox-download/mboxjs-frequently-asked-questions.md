---
keywords: preguntas frecuentes sobre mbox.js;faq;mbox.js;document.write;tt.omtrdc.net;analizador bloqueado
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Cuáles son las preguntas más frecuentes sobre [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# Preguntas más frecuentes de mbox.js

Respuestas a las preguntas más frecuentes sobre mbox.js.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución para las que se mostrará contenido predeterminado.
>
>Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## ¿Por qué no se activan los mboxes en mis páginas web? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Los clientes de [!DNL Target] utilizan en ocasiones instancias basadas en la nube para realizar pruebas o simplemente exponer conceptos. Estos dominios, y muchos otros, son parte de la [Lista pública de sufijos](https://publicsuffix.org/list/public_suffix_list.dat).

Los navegadores modernos no guardan las cookies si se utilizan estos dominios, a no ser que se personalice el ajuste `cookieDomain` mediante targetGlobalSettings(). Para obtener más información, consulte [Uso de instancias basadas en la nube con Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## ¿Cuál es el dominio tt.omtrdc.net al que se dirigen las llamadas al servidor [!DNL Target]? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] es el nombre de dominio de la red EDGE de Adobe, que se utiliza para recibir todas las llamadas de servidor para Target.

## ¿Por qué at.js y mbox.js no utilizan los indicadores de cookies HttpOnly y Secure? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly solo se puede establecer mediante código del servidor. Las cookies de Target, como mbox, se crean y guardan mediante código JavaScript, de modo que Target no puede utilizar el indicador de cookie HttpOnly.

Secure se puede establecer mediante JavaScript solo cuando la página se carga mediante HTTPS. Si la página se carga inicialmente mediante HTTP, JavaScript no puede establecer este indicador. Además, si se utiliza el indicador Secure, la cookie estará disponible solo en páginas HTTPS.

Para garantizar que Target pueda rastrear correctamente a los usuarios, y dado que las cookies se generan en el cliente, Target no utiliza ninguno de estos indicadores.
