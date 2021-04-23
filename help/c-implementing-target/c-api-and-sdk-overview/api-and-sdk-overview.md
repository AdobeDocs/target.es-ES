---
keywords: servidor;api;sdk;node.js;nodejs;node js;api de recomendaciones;api:api
description: Obtenga información sobre las API de Recommendations de Adobe [!DNL Target] server-side delivery APIs, SDKs, and [!DNL Target] .
title: ¿Dónde puedo obtener información sobre las API y los SDK de envío del lado del servidor [!DNL Target] ?
feature: Implementación del lado del servidor
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 20%

---

# Servidor: implementación de Target 

Información sobre las API de envío del lado del servidor [!DNL Adobe Target], los SDK y las API [!DNL Target Recommendations].

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. El servidor envía esa solicitud a [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor decide qué experiencia se ofrece al dispositivo cliente para que se represente.

La experiencia no necesita mostrarse en un explorador. La experiencia puede mostrarse en un correo electrónico o quiosco, a través de un asistente de voz, o a través de otra experiencia no visual o dispositivo no basado en explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor.

>[!NOTE]
>
>Un visitante nuevo solo se puede inicializar en el lado del cliente. Un visitante *no puede* inicializarse por primera vez en el lado del servidor.

Las secciones siguientes proporcionan más información sobre las distintas API y el SDK de NodeJS:

## API de envío del servidor

Vínculo: [API de envío del servidor](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Gracias a la API de envío [!DNL Target], puede:

* Entregue experiencias en la web, incluidos los canales SPA y móviles, así como en dispositivos IoT no basados en navegador, como televisores conectados, quioscos o pantallas digitales de la tienda.
* Ofrecer experiencias desde cualquier plataforma o aplicación del lado del servidor que pueda realizar llamadas HTTP/s.
* Ofrecer experiencias coherentes y personalizadas a un visitante independientemente del canal o los dispositivos que el visitante utilizó para interactuar con su empresa.
* Almacene en caché experiencias para un visitante dentro de una sesión en el servidor, de modo que se puedan evitar múltiples llamadas a la API, lo que mejora el rendimiento.
* Integre sin problemas con productos [!DNL Adobe Experience Cloud], como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) y [!DNL Experience Cloud ID Service] desde el servidor.

## SDK del servidor

Vínculo: [SDK de Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)

El portal de documentación del SDK del lado del servidor [!DNL Adobe Target] le ayuda a implementar [!DNL Target] en sus servidores en el idioma que elija.

## API de Recommendations de Target

Vínculo: [API de Recommendations de Target](https://developers.adobetarget.com/api/recommendations) y [Información general de la API de Adobe Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Las API de Recommendations permiten interactuar mediante programación con los servidores de [!DNL Target] recomendaciones. Estas API se pueden integrar con una serie de pilas de aplicaciones para realizar funciones que normalmente se harían mediante la interfaz de usuario [!DNL Target].
