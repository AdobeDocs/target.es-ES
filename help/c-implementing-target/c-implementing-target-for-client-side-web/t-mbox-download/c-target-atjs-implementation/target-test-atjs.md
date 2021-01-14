---
keywords: at.js;non-production;non production;deploy
description: Información sobre cómo implementar de forma segura at.js en un entorno que no sea de producción.
title: Implementar at.js en un Entorno que no sea de producción
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 90%

---


# Implementar at.js en un entorno que no sea de producción

Información sobre las técnicas para implementar de forma segura at.js en un entorno que no sea de producción.

## Implementar en ensayo de DTM

Si usa DTM, puede guardar fácilmente at.js en la configuración de herramienta de Adobe Target.

Una vez que haya guardado la biblioteca, use la herramienta de cambio de DTM para probarla con su código de producción. Esto también facilitará que los consultores de Adobe le proporcionen soporte técnico.

Para obtener más información, consulte [Opción 3: Implementar Target manualmente con la biblioteca de JavaScript de Target alojada en DTM](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) en la guía *Prácticas recomendadas para implementar Adobe Target mediante Dynamic Tag Management*.

## Usar la extensión “Requestly” de Chrome para asignar a otro archivo

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la [extensión del explorador Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) es una extensión gratuita de Chrome que le permite redirigir las solicitudes a una URL alternativa.

Se implementa at.js en una dirección URL y luego se usa Requestly para asignar la dirección URL del archivo mbox.js actual a la nueva dirección URL de at.js. A continuación, cada vez que el sitio web intente cargar mbox.js, cargará at.js en su lugar. Este enfoque también facilita que Adobe proporcione soporte técnico.

## Implementar en un entorno de desarrollo, ensayo o control de calidad

Si aloja mbox.js en la base de códigos y puede actualizar con facilidad los entornos de código, implemente at.js en uno de los entornos más bajos.

Para obtener mejor soporte técnico de Adobe, implemente el archivo en un entorno al que Adobe pueda tener acceso.

## Usar Charles o Fiddler para asignar a un archivo local

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) es una aplicación disponible para Mac y Windows cuya característica Map Local puede usarse para asignar la carga del archivo mbox.js de producción a una copia local de at.js. Se puede descargar una versión de prueba gratuita para Mac y Windows.

[Fiddler](https://www.telerik.com/fiddler) es una herramienta similar que está disponible como descarga gratuita para Windows.

## Implementar en el entorno de otro administrador de etiquetas

Si está usando otro administrador de etiquetas, posiblemente tenga una forma de implementar at.js de manera segura sin afectar el tráfico de producción.