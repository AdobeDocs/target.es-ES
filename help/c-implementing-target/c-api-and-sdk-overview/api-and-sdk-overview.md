---
description: Información sobre las API de envío del servidor de Target, las API de Recommendations y el SDK de NodeJS.
keywords: servidor;api;sdk;nodejs;node js;api de recomendaciones
seo-description: Información sobre las API de entrega del servidor de Adobe Target, las API de Recommendations y el SDK de nodejs.
seo-title: Implementación del servidor en Adobe Target
solution: Target
title: Implementación de Target en el servidor
topic: Las actividades de
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 385864d9daae19468c4557e51043d5b788924658

---


# Servidor: implementación de Target{#server-side-implement-target}

Información sobre [!DNL Adobe Target] las API de entrega del servidor, las API de entrega por lotes del servidor, el SDK de nodejs, [!DNL Target Recommendations] las API y [!DNL Target Classic] las API (retirada).

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. Your server sends that request to [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor toma la decisión sobre la experiencia que se debe ofrecer al dispositivo cliente para que se represente.

La experiencia no necesita mostrarse en un navegador; puede mostrarse en un correo electrónico o quiosco, a través de un ayudante de voz o a través de algún otro dispositivo no visual o no basado en explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad, o tiene procesos back-end complejos que desee ejecutar en el servidor.

En la siguiente sección se enumeran las distintas API y el SDK de NodeJS, y se proporciona información adicional:

## API de envío del servidor

Vínculo: [API de entrega del servidor](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

[!DNL Target] permite que su aplicación realice llamadas de mbox desde cualquier navegador, dispositivo móvil o incluso otro servidor. La API de envío del servidor está diseñada específicamente para integrarse [!DNL Target] con cualquier plataforma del lado del servidor que realice llamadas HTTP/HTTPS.

Puede utilizar la API para integrar su aplicación personalizada con [!DNL Target]. Es especialmente útil para las organizaciones que deseen ofrecer segmentación para un dispositivo IoT no basado en navegador, como un televisor, un quiosco o una pantalla digital.

Este extremo solo puede devolver ofertas para mboxes normales. También puede obtenerse contenido para un solo mbox.

Esta API implementa funciones existentes de mbox al modo RESTful.

Esta API no procesa cookies ni redirige llamadas.

## API de envío por lotes del servidor

Vínculo: [API de entrega por lotes de servidor](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

La API de envío por lotes permite que su aplicación solicite contenido para varios mboxes mediante una sola llamada. También tiene un modo de recuperación previa que permite a clientes como aplicaciones móviles, servidores, etc. recuperar contenido para varios mboxes en una solicitud, almacenarlo en caché localmente y avisar [!DNL Target] después cuando el usuario visita esos mboxes.

Este extremo solo puede devolver ofertas para mboxes normales. Como es posible recuperar contenido para varios mboxes, si desea mejorar el rendimiento es conveniente utilizar la API de mbox por lotes. De este modo evita la ejecución de varias solicitudes HTTP, lo que puede resultar costoso.

## SDK de NodeJS

Vínculo: [SDK de nodejs](https://www.npmjs.com/package/@adobe/target-node-client)

En cuanto a SDK, en este momento tenemos uno solo: el SDK de NodeJS.

El SDK de NodeJS es un envoltorio delgado que rodea el módulo central HTTP/HTTPS de NodeJS. En segundo plano, las API del SDK de NodeJS utilizan las mismas API de entrega del servidor.

Esta es la asignación:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## [!DNL Target Recommendations] API

Vínculo: [API de recomendaciones de Target](https://developers.adobetarget.com/api/recommendations)

Las API de Recommendations le permiten interactuar mediante programación con los servidores de recomendaciones de Target. Estas API se pueden integrar con distintas pilas de aplicaciones para llevar a cabo funciones que normalmente se realizan a través de la interfaz de usuario.

## [!DNL Target Classic] API

La [!DNL Target Classic] interfaz de usuario y las API se han eliminado. Para obtener más información sobre cómo dar el salto a las API modernas de Target, consulte [Transición de las API anteriores de Target a Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2).

>[!NOTE]
>Las API de creación (en las que se crean actividades, ofertas, audiencias, etc.) no admiten el intercambio de recursos de origen cruzado (CORS).

## Diferencias entre las API de entrega del servidor y el SDK de NodeJS {#section_10336B7934F54CE98E35907A4748A4A4}

Muchos clientes no entienden bien las diferencias entre las API de entrega del servidor y el SDK de NodeJS. Este problema se da especialmente en lo que respecta al rendimiento.

Las siguientes preguntas más frecuentes le ayudarán a decidir cuál debe utilizar:

**¿Cuándo se deben utilizar las API del servidor “en bruto” y cuándo el SDK de NodeJS?**

Si está utilizando NodeJS como tecnología de back-end, el SDK de NodeJS es la opción evidente. El SDK se ocupa de muchos detalles, como las cookies, los encabezados, las cargas útiles, etcétera. De este modo, usted puede concentrarse en el núcleo de su aplicación.

**¿Debería percibir mejoras de rendimiento al utilizar el SDK de NodeJS?**

Lamentablemente, carecemos de cifras sobre rendimiento. Sin embargo, y en general, el SDK de NodeJS debería ofrecer un buen rendimiento gracias a la arquitectura orientada a eventos de NodeJS. Tenga en cuenta que la mayor parte del tiempo se invierte en [!DNL Target] el back-end. El SDK de NodeJS realiza muy poco procesamiento. El SDK es básicamente responsable de empaquetar una [!DNL Target] solicitud y analizar una [!DNL Target] respuesta.
