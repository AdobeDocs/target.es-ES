---
keywords: at.js;no producción;no producción;implementar
description: Obtenga información sobre la implementación de mbox.js heredada de Adobe Target. Migrar al SDK web de Adobe Experience Platform (SDK web de AEP) o a la versión más reciente de at.js.
title: ¿Cómo implemento at.js en un entorno que no sea de producción?
feature: 'at.js. '
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# Implementar at.js en un entorno que no sea de producción

Información sobre las técnicas para implementar de forma segura at.js en un entorno que no sea de producción.

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
