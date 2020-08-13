---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: Notas de la versión relacionadas con las API de servidor de Adobe Target.
title: Notas de la versión relacionadas con el SDK de Node.js de Adobe Target.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---


# Notas de la versión: SDK de Node.js de Destinatario

Notas de la versión relacionadas con el SDK [de Node.js de](https://github.com/adobe/target-nodejs-sdk)Adobe Target.

El SDK de Node.js de Destinatario le permite implementar [!DNL Target] en el servidor.

Este SDK de Node.js le ayuda a integrarse fácilmente [!DNL Target] con otras [!DNL Adobe Experience Cloud] soluciones, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]y [!DNL Adobe Audience Manager].

El SDK de Node.js presenta prácticas recomendadas y elimina las complejidades al integrarlas con [!DNL Target] nuestra API de envío, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial.

Obtenga más información sobre el SDK de Node.js de Destinatario en el blog técnico de Adobe: [Open Sourcing the New Adobe Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc).

## Versión 1.0.0 (9 de octubre de 2019)

Las siguientes secciones proporcionan más información sobre la versión 1.0.0 del SDK de Destinatario Node.js:

### Se ha agregado

* Compatibilidad con la API de Envío de Vista de destinatario v1, incluida la carga de página y la recuperación previa de Vistas.
* Compatibilidad total con la entrega de todos los tipos de ofertas creadas en el Compositor de experiencias visuales (VEC).
* Compatibilidad con la recuperación previa y las notificaciones para la optimización del rendimiento almacenando en caché el contenido recuperado previamente.
* Compatibilidad para optimizar el rendimiento en integraciones híbridas [!DNL Target] mediante `serverState` cuando [!DNL Target] se implementa tanto en el servidor como en el cliente.

   Estamos introduciendo una configuración llamada `serverState` que contiene experiencias recuperadas a través del servidor, de modo que at.js v2.2+ no realice una llamada al servidor adicional para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.

* Abra el código fuente en GitHub como SDK [](https://github.com/adobe/target-nodejs-sdk)Destinatario Node.js.
* Nuevo método [de API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) sendNotifications() para enviar notificaciones mostradas/en las que se hace clic [!DNL Target] para contenido recuperado previamente mediante [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Generación simplificada de solicitudes de API de Envío de Vista, con finalización automática de campos internos con valores predeterminados (por ejemplo, `request.id`, `request.context`, etc.).
* Validación de los argumentos del método API de SDK.
* Se han actualizado las pruebas README, muestras y unidades.
* Se ha configurado un nuevo flujo de CI mediante las acciones de GitHub.
* CoC añadida, directrices de contribución, relaciones públicas y plantillas de publicación

### Se ha cambiado

* Se ha cambiado el nombre del proyecto a `target-nodejs-sdk`.
* Refactorización importante, reemplazo de la API de Destinatario BatchMbox v2 por la API de Envío de Vista de Destinatario v1.
* [se han modificado los argumentos del método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) API create(), eliminando el anidado redundante (consulte la declaración de método antigua [aquí](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [Se han modificado los argumentos del método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) API getOffers() (consulte la declaración de método antigua [aquí](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* El método `getTargetCookieName()` API se ha sustituido por `TargetCookieName` descriptor de acceso. Consulte [Accesores](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)de utilidades de TargetClient.
* El método `getTargetLocationHintCookieName()` API se ha sustituido por `TargetLocationHintCookieName` descriptor de acceso.  Consulte [Accesores](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)de utilidades de TargetClient.

### Eliminado

* Compatibilidad con la API de destinatario BatchMbox v2.
* Se ha eliminado el método [de API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() y, en su lugar, utilice el método [de API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

