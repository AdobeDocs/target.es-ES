---
description: Notas de la versión relacionadas con el SDK Node.js de Adobe Target
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
seo-description: Notas de la versión relacionadas con las API del servidor de Adobe Target.
seo-title: Notas de la versión relacionadas con el SDK Node.js de Adobe Target.
solution: Target
title: 'Notas de la versión: SDK de Node.js de Target'
topic: Standard
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# Notas de la versión: SDK de Node.js de Target

Notas de la versión relacionadas con el SDK Node.js de Adobe Target.

## Versión 1.0.0 (9 de octubre de 2019)

Las siguientes secciones proporcionan más información sobre la versión 1.0.0 del SDK de Target Node.js:

### Se ha agregado

* Compatibilidad con la API de Target View Delivery v1, incluidas la carga de página y la recuperación previa de la vista.
* Compatibilidad total con la entrega de todo tipo de ofertas creadas en el Compositor de experiencias visuales (VEC).
* Compatibilidad con la recuperación previa y las notificaciones para la optimización del rendimiento almacenando en caché el contenido recuperado previamente.
* Compatibilidad para optimizar el rendimiento en integraciones híbridas [!DNL Target] mediante `serverState` cuando [!DNL Target] se implementa tanto en el servidor como en el cliente.

   Estamos introduciendo una configuración llamada `serverState` que contiene experiencias recuperadas a través del servidor, de modo que at.js v2.2+ no realice una llamada al servidor adicional para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.

* Abrir código fuente en GitHub como SDK [](https://github.com/adobe/target-nodejs-sdk)de Node.js de Target.
* Nuevo método [de API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) sendNotifications() para enviar notificaciones mostradas/en las que se hace clic [!DNL Target] para contenido recuperado previamente mediante [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Generación de solicitudes de API de envío de vista simplificada, con finalización automática de campo interno con valores predeterminados (por ejemplo, `request.id`, `request.context`, etc.).
* Validación de los argumentos del método API de SDK.
* Se han actualizado las pruebas README, muestras y unidades.
* Se ha configurado un nuevo flujo de CI mediante las acciones de GitHub.
* Se han agregado las plantillas de preguntas y respuestas de CoC, las directrices de contribución, las relaciones públicas y los números

### Se ha cambiado

* Se ha cambiado el nombre del proyecto a `target-nodejs-sdk`.
* Refactorización importante, reemplazo de la API de Target BatchMbox v2 por la API de envío de vista de destino v1.
* [se han modificado los argumentos del método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) API create(), eliminando el anidado redundante (consulte la declaración de método antigua [aquí](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [Se han modificado los argumentos del método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) API getOffers() (consulte la declaración de método antigua [aquí](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* El método `getTargetCookieName()` API se ha sustituido por `TargetCookieName` descriptor de acceso. Consulte [Accesores](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)a la utilidad TargetClient.
* El método `getTargetLocationHintCookieName()` API se ha sustituido por `TargetLocationHintCookieName` descriptor de acceso.  Consulte [Accesores](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)a la utilidad TargetClient.

### Eliminado

* Compatibilidad con la API de Target BatchMbox v2.
* Se ha eliminado el método [de API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() y, en su lugar, utilice el método [de API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

