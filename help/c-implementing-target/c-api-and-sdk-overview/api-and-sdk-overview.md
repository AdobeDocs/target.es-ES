---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Información sobre las API de envío de Adobe Target de parte del servidor, los SDK y las API de Recommendations de Destinatario.
title: Información sobre las API de envío del lado del servidor de Adobe Target, el SDK de Node.js y las API de Recommendations de Destinatario.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 20%

---


# Servidor: implementación de Target{#server-side-implement-target}

Información sobre las API, los SDK y [!DNL Adobe Target] las API de envío del lado del servidor [!DNL Target Recommendations] .

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. El servidor envía esa solicitud a [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor toma la decisión de la experiencia que se debe ofrecer al dispositivo cliente para que se represente.

No es necesario que la experiencia se muestre en un explorador. La experiencia se puede mostrar en un correo electrónico o en un quiosco, a través de un asistente de voz, o a través de otra experiencia no visual o dispositivo no basado en explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor.

>[!NOTE]
>
>Un visitante por primera vez solo se puede inicializar en el lado del cliente. Un visitante por primera vez *no se puede* inicializar en el servidor.

Las siguientes secciones proporcionan más información sobre las distintas API y el SDK de NodeJS:

## API de envío del servidor

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Al crear la API de [!DNL Target] Envío, puede:

* Ofrezca experiencias a través de la web, incluidos los canales SPA y móviles, así como dispositivos IoT no basados en explorador, como televisores conectados, quioscos o pantallas digitales de las tiendas.
* Ofrezca experiencias desde cualquier plataforma o aplicación del lado del servidor que pueda realizar llamadas HTTP/s.
* Ofrezca experiencias coherentes y personalizadas a un visitante independientemente del canal o los dispositivos que el visitante haya utilizado para interactuar con su empresa.
* Almacene experiencias en caché para un visitante dentro de una sesión en el servidor, de modo que se puedan evitar varias llamadas de API, lo que mejora el rendimiento.
* Integre sin problemas con [!DNL Adobe Experience Cloud] los productos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) y [!DNL Experience Cloud ID Service] desde el servidor.

## SDK del servidor

Vínculo: [SDK de Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)

El portal de documentación del SDK del lado del [!DNL Adobe Target] servidor le ayuda a implementar [!DNL Target] en los servidores en el idioma que elija.

## API de Recommendations de Target

Vínculo: [Información general sobre las API](https://developers.adobetarget.com/api/recommendations) de destinatario Recommendations y la API de [Adobe Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
