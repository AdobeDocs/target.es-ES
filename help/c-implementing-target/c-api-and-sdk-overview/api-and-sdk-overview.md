---
description: Información sobre las API de envío del servidor de Target, las API de Recommendations y el SDK de NodeJS.
keywords: servidor;api;sdk;nodejs;node js;api de recomendaciones
seo-description: Información sobre las API de envío del servidor de Adobe Target, las API de Recommendations y el SDK de NodeJS.
seo-title: Implementación de Adobe Target del lado del servidor
solution: Target
title: Implementación de Target en el servidor
topic: Las actividades de
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Servidor: implementación de Target{#server-side-implement-target}

Información sobre las API de envío del servidor de [!DNL Adobe Target], las API de envío por lotes del servidor, el SDK de NodeJS, las API de [!DNL Target Recommendations]y las API de [!DNL Target Classic] (retiradas).

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. El servidor envía esa solicitud a [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor toma la decisión sobre la experiencia más adecuada para el dispositivo del cliente.

La experiencia no necesita mostrarse en un explorador; puede mostrarse en un correo electrónico o quiosco, a través de un asistente de voz o a través de otro dispositivo no visual o no basado en un explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor.

En la siguiente sección se enumeran las distintas API y el SDK de NodeJS, y se proporciona información adicional:

## API de envío del servidor

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

[!DNL Target] permite que su aplicación realice llamadas de mbox desde cualquier navegador, dispositivo móvil o incluso otro servidor. La API de envío del servidor está diseñada específicamente para integrar [!DNL Target] en cualquier plataforma de servidor que realice llamadas HTTP/HTTPS.

Puede utilizar la API para integrar su aplicación personalizada con [!DNL Target]. Es especialmente útil para las organizaciones que deseen ofrecer segmentación para un dispositivo IoT no basado en navegador, como un televisor, un quiosco o una pantalla digital.

Este extremo solo puede devolver ofertas para mboxes normales. También puede obtenerse contenido para un solo mbox.

Esta API implementa funciones existentes de mbox al modo RESTful.

Esta API no procesa cookies ni redirige llamadas.

## API de envío por lotes del servidor

Link: [Server Side Batch Delivery APIs](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

La API de envío por lotes permite que su aplicación solicite contenido para varios mboxes mediante una sola llamada. También cuenta con un modo de recuperación previa que permite a clientes como aplicaciones móviles, servidores, etcétera, recuperar contenido para varios mboxes mediante una única solicitud, almacenar dicho contenido en la caché local y más tarde notificar a [!DNL Target] cuando el usuario visite estos mboxes.

Este extremo solo puede devolver ofertas para mboxes normales. Como es posible recuperar contenido para varios mboxes, si desea mejorar el rendimiento es conveniente utilizar la API de mbox por lotes. De este modo evita la ejecución de varias solicitudes HTTP, lo que puede resultar costoso.

## SDK de NodeJS

Vínculo: SDK [de NodeJS](https://www.npmjs.com/package/@adobe/target-node-client)

En cuanto a SDK, en este momento tenemos uno solo: el SDK de NodeJS.

El SDK de NodeJS es un envoltorio delgado que rodea el módulo central HTTP/HTTPS de NodeJS. En segundo plano, las API del SDK de NodeJS utilizan las mismas API de entrega del servidor.

Esta es la asignación:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## [!DNL Target Recommendations] API

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

Las API de Recommendations le permiten interactuar mediante programación con los servidores de recomendaciones de Target. Estas API se pueden integrar con distintas pilas de aplicaciones para llevar a cabo funciones que normalmente se realizan a través de la interfaz de usuario.

## [!DNL Target Classic] API

Se han retirado la interfaz de usuario y las API de [!DNL Target Classic]. Para obtener más información sobre cómo dar el salto a las API modernas de Target, consulte [Transición de las API anteriores de Target a Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2).

>[!NOTE]
>Las API de creación (en las que se crean actividades, ofertas, audiencias, etc.) no admiten el intercambio de recursos de origen cruzado (CORS).

## Diferencias entre las API de entrega del servidor y el SDK de NodeJS {#section_10336B7934F54CE98E35907A4748A4A4}

Muchos clientes no entienden bien las diferencias entre las API de entrega del servidor y el SDK de NodeJS. Este problema se da especialmente en lo que respecta al rendimiento.

Las siguientes preguntas más frecuentes le ayudarán a decidir cuál debe utilizar:

**¿Cuándo se deben utilizar las API del servidor “en bruto” y cuándo el SDK de NodeJS?**

Si está utilizando NodeJS como tecnología de back-end, el SDK de NodeJS es la opción evidente. El SDK se ocupa de muchos detalles, como las cookies, los encabezados, las cargas útiles, etcétera. De este modo, usted puede concentrarse en el núcleo de su aplicación.

**¿Debería percibir mejoras de rendimiento al utilizar el SDK de NodeJS?**

Lamentablemente, carecemos de cifras sobre rendimiento. Sin embargo, y en general, el SDK de NodeJS debería ofrecer un buen rendimiento gracias a la arquitectura orientada a eventos de NodeJS. Tenga en cuenta que la mayoría del tiempo se pasa en el backend de [!DNL Target]. El SDK de NodeJS realiza muy poco procesamiento. Básicamente se ocupa de empaquetar solicitudes de [!DNL Target] y analizar respuestas de [!DNL Target].
