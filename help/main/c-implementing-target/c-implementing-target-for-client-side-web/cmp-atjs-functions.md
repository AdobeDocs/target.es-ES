---
keywords: at.js;funciones;biblioteca de javaScript
description: Vea una lista de funciones que se pueden utilizar con las versiones 1.x y 2.x de la biblioteca JavaScript at.js en Adobe Target.
title: ¿Qué funciones puedo usar con at.js?
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 73%

---

# Funciones de at.js

Lista de funciones que se pueden utilizar con la biblioteca JavaScript at.js de Adobe Target. Para obtener más información y ejemplos, haga clic en los vínculos de la columna Función.

| Función | Detalles |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) | Esta función activa una solicitud para obtener una oferta de Target. Use con `adobe.target.applyOffer()` para procesar la respuesta o use su propia administración de éxito. |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)<br>(at.js 2.x) | Esta función le permite recuperar varias ofertas pasando varios mboxes. Además, se pueden recuperar varias ofertas para todas las vistas de actividades activas.<br>**Nota:** Esta función se introdujo en at.js 2.x. Esta función no está disponible para la versión 1 de at.js.*x*. |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) | Esta función es para aplicar el contenido de respuesta. |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/)<br>(at.js 2.x) | Esta función permite aplicar más de una oferta recuperada por adobe.target.getOffers().<br>**Nota:** Esta función se introdujo en at.js 2.x. Esta función no está disponible para la versión 1 de at.js.*x*. |
| [adobe.target.triggerView (viewName, options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/)<br>(at.js 2.x) | Se puede llamar a esta función cada vez que se carga una página nueva o cuando se vuelve a procesar un componente de una página.<br> Esta función debe implementarse para aplicaciones de una sola página (SPA){target=_blank} a fin de usar el Compositor de experiencias visuales (VEC) para crear pruebas A/B y actividades de segmentación de experiencias (XT). |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/) | Esta función activa una solicitud para informar sobre las acciones de los usuarios, como clics y conversiones. No proporciona ninguna actividad en la respuesta. |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/)<br>(at.js 1.x) | Ejecuta una solicitud y aplica la oferta al DIV más cercano con nombre de clase mboxDefault.<br>**Nota:** Esta función está disponible para las versiones 1 de at.js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at.js 2.x. Esta función devuelve el contenido predeterminado si se utiliza con at.js 2.x. |
| [mboxDefine(options) y mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/)<br>(at.js 1.x) | Defina y actualice un mbox.<br>**Nota:** Esta función está disponible para las versiones 1 de at.js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at.js 2.x. Esta función devuelve el contenido predeterminado si se utiliza con at.js 2.x. |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) | En lugar de definir la configuración en la interfaz de usuario de Target Standard/Premium, puede anular la configuración de la biblioteca at.js mediante `targetGlobalSettings()` o usar las API de REST.<ul><li>Proveedores de datos: Esta configuración permite a los clientes recopilar información de proveedores de datos de terceros, como Demandbase, BlueKai y servicios personalizados, así como pasar la información a Target como parámetros mbox y la solicitud mbox global.</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) | Este método permite adjuntar parámetros al mbox global desde fuera del código de la solicitud. |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) | Este método permite adjuntar parámetros a todos los mboxes desde fuera del código de la solicitud. |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/)<br>(at.js 1.x) | Ofrece una forma estándar de registrar una extensión determinada.<br>**Nota:** Esta función está disponible para las versiones 1 de at.js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at.js 2.x. Esta función devuelve el contenido predeterminado si se utiliza con at.js 2.x. |
| [Eventos personalizados de at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/) | Los eventos personalizados de at.js le permiten saber cuándo una solicitud o una oferta de mbox tiene éxito o falla. |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)<br>(at.js 2.1.0) | Esta función envía una notificación a Target Edge cuando se procesa una experiencia sin utilizar `adobe.target.applyOffer()` o `adobe.target.applyOffers()`.<br>**Nota**: Esta función se ha introducido en at.js 2.1.0 y estará disponible para todas las versiones superiores a 2.1.0. |
