---
description: Lista de las funciones que se pueden usar con at.js.
keywords: adobe.target.notification;elemento;selector;notificación;extensión
seo-description: Lista de funciones que se pueden utilizar con la biblioteca JavaScript at.js en Adobe Target.
seo-title: Funciones at.js de Adobe Target
solution: Target
subtopic: Primeros pasos
title: Funciones de at.js
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: c607b241afb535f324cd1357c8784a88fb183658

---


# Funciones de at.js{#at-js-functions}

Lista de funciones que se pueden utilizar con la biblioteca JavaScript at.js de Adobe Target. Haga clic en los vínculos de la columna Función para obtener más información y ejemplos.

| Función | Detalles |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | Esta función activa una solicitud para obtener una oferta de Target. Use con `adobe.target.applyOffer()` para procesar la respuesta o use su propia administración de éxito. |
| [adobe. target. getoffers (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at. js 2. x) | Esta función le permite recuperar varias ofertas pasando varios mboxes. Además, se pueden recuperar varias ofertas para todas las vistas de actividades activas.<br>**Nota:** Esta función se introdujo en at. js 2. x. Esta función no está disponible para la versión 1 de at. js.*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | Esta función es para aplicar el contenido de respuesta. |
| [adobe. target. applyoffers (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at. js 2. x) | Esta función permite aplicar más de una oferta recuperada por adobe. target. getoffers ().<br>**Nota:** Esta función se introdujo en at. js 2. x. Esta función no está disponible para la versión 1 de at. js.*x*. |
| [adobe. target. triggerview (viewname, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at. js 2. x) | Se puede llamar a esta función cada vez que se carga una página nueva o cuando se vuelve a procesar un componente de una página.<br> Esta función debe implementarse en aplicaciones de una sola página (SPA) para poder utilizar el Compositor de experiencias visuales (VEC) para crear pruebas A/B y actividades de segmentación de experiencias (XT). |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | Esta función activa una solicitud para informar sobre las acciones de los usuarios, como clics y conversiones. No proporciona ninguna actividad en la respuesta. |
| [Mboxcreate (mbox, params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at. js 1. x) | Ejecuta una solicitud y aplica la oferta al DIV más cercano con nombre de clase mboxDefault.<br>**Nota:** Esta función está disponible para las versiones 1 de at. js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at. js 2. x. Esta función devuelve el contenido predeterminado si se utiliza con at. js 2. x. |
| [Mboxdefine (options) y mboxupdate (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at. js 1. x) | Defina y actualice un mbox.<br>**Nota:** Esta función está disponible para las versiones 1 de at. js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at. js 2. x. Esta función devuelve el contenido predeterminado si se utiliza con at. js 2. x. |
| [Targetglobalsettings (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Puede anular la configuración de la biblioteca at. js utilizando `targetGlobalSettings()`, en lugar de configurar la configuración en la interfaz de usuario de Target Standard/Premium o utilizando las API de REST.<ul><li>Proveedores de datos: Esta configuración permite a los clientes recopilar datos de proveedores de datos externos, como Demandbase, bluekai y servicios personalizados, y pasar los datos a Target como parámetros de mbox en la solicitud de mbox global.</li></ul> |
| [Targetpageparams (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | Este método permite adjuntar parámetros al mbox global desde fuera del código de la solicitud. |
| [Targetpageparamsall (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | Este método permite adjuntar parámetros a todos los mboxes desde fuera del código de la solicitud. |
| [Registerextension (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at. js 1. x) | Ofrece una forma estándar de registrar una extensión determinada.<br>**Nota:** Esta función está disponible para las versiones 1 de at. js.Solamente *x*. Esta función quedó obsoleta con el lanzamiento de at. js 2. x. Esta función devuelve el contenido predeterminado si se utiliza con at. js 2. x. |
| [Eventos personalizados de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Los eventos personalizados de at. js le permiten saber cuándo una solicitud o una oferta de mbox tiene éxito o falla. |
