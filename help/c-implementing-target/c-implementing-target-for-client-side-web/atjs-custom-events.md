---
keywords: eventos personalizados;at.js;solicitud fallida;solicitud correcta;error de procesamiento de contenido;procesamiento de contenido correcto;biblioteca cargada;solicitar inicio;inicio de procesamiento de contenido;contenido no procesa ofertas;redirección de representación de contenido
description: Utilice eventos personalizados para que la biblioteca JavaScript de Adobe [!DNL Target] at.js reciba notificaciones cuando una oferta o una solicitud de mbox se procesen correcta o incorrectamente.
title: ¿Cómo utilizo los eventos personalizados de at.js?
feature: 'at.js '
role: Developer
exl-id: 4073210b-b782-48a7-8b69-29eb5cd98fd5
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 87%

---

# Eventos personalizados de at.js

Información sobre `at.js custom events`, le avisa cuando una oferta o una solicitud de mbox se procesa correcta o incorrectamente.

Históricamente, mbox.js impedía a otros códigos de JavaScript que se ejecutaban en la página saber lo que pasaba entre bastidores. Con el adelanto de at.js, tuvimos una oportunidad única de arreglar este problema.

Nuestros clientes nos han contado que les gustaría recibir notificación sobre varias situaciones, entre otras:

* Cuando una solicitud de mbox falla porque se ha superado el tiempo de espera, porque el código de estado es erróneo, por un error de análisis de JSON, etc.
* Cuando una solicitud de mbox se efectúa correctamente.
* Cuando la representación de ofertas falla porque falta un elemento mbox envolvente, porque no se encuentra el selector, etc.
* Cuando la representación se efectúa correctamente. Los cambios del DOM se han aplicado.

Los eventos predefinidos tienen una estructura que permite extraer los datos necesarios según el tipo de evento.

Para asegurarse de que los eventos se puedan usar en distintos casos, los eventos personalizados tienen un objeto de carga útil que se asigna a la propiedad de detalle del objeto del evento (que se pasa al controlador). Además, para evitar pasar cadenas como nombres de eventos, los eventos se exponen como constantes usando el espacio de nombres de `adobe.target.event`.

## Estructura {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| Clave | Tipo | Descripción |
|--- |--- |--- |
| type | Cadena | Hay varios escenarios en los que le gustaría recibir notificaciones para ayudarlo a rastrear, depurar y personalizar la interacción con at.js.<br>Cada evento personalizado enumerado a continuación tiene dos formatos: una “constante” y un “valor de cadena”.<ul><li>**Constantes**: antepuesto con `adobe.target.event.`, presentado todo en mayúsculas y contiene caracteres subrayados. Para suscribirse a eventos personalizados *después* de cargas at.js pero *antes* de que se haya recibido la respuesta de mbox, use la constante.</li><li>**Valores de cadena**: en minúsculas y contiene guiones. Para suscribirse a eventos personalizados *antes* de cargas at.js, use el valor de cadena.</li></ul>**Solicitud fallida**<br> Constante: `adobe.target.event.REQUEST_FAILED`<br>Valor de cadena: `at-request-failed`<br>Descripción: Una solicitud de mbox falla debido al tiempo de espera, el código de estado incorrecto, el error de análisis de JSON, etc.<br>**Solicitud exitosa**<br> Constante: `adobe.target.event.REQUEST_SUCCEEDED`<br>Valor de cadena: `at-request-succeeded`<br>Descripción: se realizó una solicitud de mbox correctamente.<br>**Representación de contenido fallida**<br> Constante: `adobe.target.event.CONTENT_RENDERING_FAILED`<br>Valor de cadena: `at-content-rendering-failed`<br>Descripción: la representación de ofertas falló debido a que falta un elemento mbox envolvente, el selector no se puede encontrar, etc.<br>**Representación de contenido exitosa**<br> Constante: `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>Valor de cadena: `at-content-rendering-succeeded`<br>Descripción: la representación de ofertas se realizó correctamente. Los cambios del DOM se han aplicado.<br>**Biblioteca cargada**<br> Constante: `adobe.target.event.LIBRARY_LOADED`<br>Valor de cadena: `at-library-loaded`<br>Descripción: este evento es ideal para rastrear cuándo at.js se ha cargado completamente. Puede usar este evento para personalizar la ejecución global de mbox. También puede usar este evento para deshabilitar el mbox global y luego escuchar este evento para lanzar el mbox global más tarde.<br>**Inicio de solicitud**<br> Constante: `adobe.target.event.REQUEST_START`<br>Valor de cadena: `at-request-start`<br>Descripción: este evento se activa antes de ejecutar una solicitud HTTP. Puede usar este evento para las mediciones de rendimiento usando API Resource Timing.<br>**Inicio de representación de contenido**<br> Constante: `adobe.target.event.CONTENT_RENDERING_START`<br>Valor de cadena: `at-content-rendering-start`<br>Descripción: este evento se activa antes de que se inicie el selector de sondeos y de que se represente el contenido en la página. Puede usar este evento para seguir el progreso del procesamiento de contenido.<br>**Representación de contenido sin ofertas**<br> Constante: `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>Valor de cadena: `at-content-rendering-no-offers`<br>Descripción: este evento se activa cuando no se devuelven ofertas.<br>**Redireccionamiento de representación de contenido**<br> Constante: `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>Valor de cadena: `at-content-rendering-redirect`<br>Descripción: este evento se activa cuando una oferta es redireccionada y Target la redirecciona a otra URL. |
| mbox | Cadena | nombre de mbox |
| message | Cadena | Contiene una descripción legible por humanos, como lo que sucedió, el mensaje de error, etc. |
| seguimiento | Objeto | Contiene el `sessionId` y `deviceId`. En algunos casos, el `deviceId` podría no estar porque [!DNL Target] no lo pudo recuperar del servidor Edge. |
| type | Cadena | **El artefacto de toma de decisiones en el dispositivo**<br> se ejecuta correctamenteConstante:<br>`adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`<br>Valor de cadena:  `artifactDownloadSucceeded`<br>Descripción: Se llama cuando el artefacto de toma de decisiones en el dispositivo se descarga correctamente.<br>**Fallo del artefacto de toma de decisiones en el dispositivo**<br> Constante:  `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`<br>Valor de cadena:  `artifactDownloadFailed`<br>Descripción: Se llama cuando el artefacto de toma de decisiones en el dispositivo no se puede descargar. |

## Uso {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```javascript
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Vídeo de formación: Tokens de respuesta y eventos personalizados ![ de at.jsDistintivo de tutorial](/help/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

Vea el siguiente vídeo para aprender a utilizar los tokens de respuesta y los eventos personalizados de at.js con el fin de compartir información de perfil de Target con sistemas de terceros.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
