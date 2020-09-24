---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Información sobre las API de envío del lado del servidor de Adobe Target, el SDK de Node.js y las API de Recommendations de Destinatario.
title: Información sobre las API de envío del lado del servidor de Adobe Target, el SDK de Node.js y las API de Recommendations de Destinatario.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 08ad3291a1f981fbc3963ce403bf19849c358b97
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 11%

---


# Servidor: implementación de Target{#server-side-implement-target}

Información sobre [!DNL Adobe Target] las API de envío del lado del servidor, el SDK de Node.js y [!DNL Target Recommendations] las API.

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. El servidor envía esa solicitud a [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor toma la decisión de la experiencia que se debe ofrecer al dispositivo cliente para que se represente.

No es necesario que la experiencia se muestre en un explorador. La experiencia se puede mostrar en un correo electrónico o en un quiosco, a través de un asistente de voz, o a través de otra experiencia no visual o dispositivo no basado en explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor.

Las siguientes secciones proporcionan más información sobre las distintas API y el SDK de NodeJS:

## API de envío del servidor

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Al crear la API de [!DNL Target] Envío, puede:

* Ofrezca experiencias en la web, incluidos SPA y canales móviles, así como en dispositivos IoT no basados en navegador, como televisores conectados, quioscos o pantallas digitales de la tienda.
* Ofrezca experiencias desde cualquier plataforma o aplicación del lado del servidor que pueda realizar llamadas HTTP/s.
* Ofrezca experiencias coherentes y personalizadas a un visitante independientemente del canal o los dispositivos que el visitante haya utilizado para interactuar con su empresa.
* Almacene experiencias en caché para un visitante dentro de una sesión en el servidor, de modo que se puedan evitar varias llamadas de API, lo que mejora el rendimiento.
* Integre sin problemas con [!DNL Adobe Experience Cloud] los productos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) y [!DNL Experience Cloud ID Service] desde el servidor.

## SDK de Node.js

Vínculo: [SDK de Node.js](https://github.com/adobe/target-nodejs-sdk)

El SDK de Node.js es un sofisticado kit de desarrollo de software que elimina las complejidades de administrar cookies, sesiones e integración con [!DNL Experience Cloud] productos como [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service], y [!DNL Audience Manager]. Entre bastidores, el SDK de Node.js utiliza la `/rest/v1/delivery` API. Estas son algunas de las funciones notables que se admiten en el SDK de Node.js:

* **Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché:** Puede utilizar el SDK de Node.js para recuperar experiencias y almacenarlas en caché localmente en el servidor Node.js con el fin de minimizar las llamadas al servidor [!DNL Target] y optimizar el rendimiento de la aplicación.
* **Capacidad para recuperar actividades creadas por VEC:** Recupere actividades creadas por VEC en el servidor. La respuesta que contiene actividades creadas por VEC tiene selectores que pueden utilizarse para ocultar previamente solo partes de la página que necesitan personalizarse. Esto ayuda a optimizar la [primera métrica](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)de pintura contextual de su página, que es un KPI importante para su empresa a fin de lograr una puntuación alta en el sistema de clasificación de páginas [de](https://en.wikipedia.org/wiki/PageRank) Google.

## SDK de Java de destinatario

Vínculo: [SDK de Java de destinatario](https://github.com/adobe/target-java-sdk)

El SDK de Java es un sofisticado kit de desarrollo de software que elimina las complejidades de administrar cookies, sesiones e integración con [!DNL Adobe Experience Cloud] soluciones como [!DNL Adobe Analytics], el [!DNL Experience Cloud Visitor ID Service], y [!DNL Adobe Audience Manager]. Entre bastidores, el SDK de Java utiliza la `/rest/v1/delivery` API. Estas son algunas de las funciones notables que se admiten en el SDK de Java:

* **Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché**: Puede utilizar el JavaSDK para recuperar experiencias y almacenarlas en caché localmente en el servidor Java con el fin de minimizar las llamadas al servidor [!DNL Target] y optimizar el rendimiento de la aplicación.
* **Capacidad para recuperar actividades** creadas por VEC: Recupere actividades creadas por VEC en el servidor. La respuesta que contiene actividades creadas por VEC tiene selectores que pueden utilizarse para ocultar previamente solo partes de la página que necesitan personalizarse. Esto ayuda a optimizar la [primera métrica de pintura](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) contextual de su página, que es un KPI importante para su empresa a fin de lograr una puntuación alta en el sistema de clasificación de páginas [de](https://en.wikipedia.org/wiki/PageRank) Google.

## Desarrolladores de Adobe Target

Vínculo: [Desarrolladores de Adobe Target](http://developers.adobetarget.com/)

El sitio de desarrolladores de Adobe Target le ayuda a implementar [!DNL Target] en aplicaciones de cliente, aplicaciones de servidor, aplicaciones móviles, IoT y más. También puede exportar sus [!DNL Target] datos a soluciones de terceros.

## API de Recommendations de Target

Vínculo: [Información general sobre las API](https://developers.adobetarget.com/api/recommendations) de destinatario Recommendations y la API de [Adobe Recommendations](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html).

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
