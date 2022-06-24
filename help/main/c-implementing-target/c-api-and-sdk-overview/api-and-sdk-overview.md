---
keywords: servidor;api;sdk;node.js;nodejs;node js;api de recomendaciones;api:api
description: Obtenga información sobre el Adobe [!DNL Target] API de envío del lado del servidor, SDK y [!DNL Target] API de Recommendations.
title: ¿Dónde puedo obtener información sobre [!DNL Target] ¿API de envío del lado del servidor y SDK?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 21%

---

# Servidor: implementación de Target 

Información acerca de [!DNL Adobe Target] API de envío del lado del servidor, SDK y [!DNL Target Recommendations] API.

El proceso siguiente se produce en una implementación del lado del servidor de [!DNL Target]:

1. Un dispositivo cliente realiza una solicitud de una experiencia a través del servidor.
1. El servidor envía esa solicitud a [!DNL Target].
1. [!DNL Target] devuelve la respuesta al servidor.
1. El servidor decide qué experiencia se ofrece al dispositivo cliente para que se represente.

La experiencia no necesita mostrarse en un explorador. La experiencia puede mostrarse en un correo electrónico o quiosco, a través de un asistente de voz, o a través de otra experiencia no visual o dispositivo no basado en explorador. Dado que su servidor se encuentra entre el cliente y [!DNL Target], este tipo de implementación también es ideal si necesita mayor control y seguridad o si tiene procesos backend complejos que desee ejecutar en el servidor.

>[!NOTE]
>
>Un visitante nuevo solo se puede inicializar en el lado del cliente. Un visitante nuevo *cannot* en el lado del servidor.

Las secciones siguientes proporcionan más información sobre las distintas API y el SDK de NodeJS:

## API de envío del servidor

Vínculo: [API de envío del servidor](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Al usar la variable [!DNL Target] API de envío, puede:

* Entregue experiencias en la web, incluidos los canales SPA y móviles, así como en dispositivos IoT no basados en navegador, como televisores conectados, quioscos o pantallas digitales de la tienda.
* Ofrecer experiencias desde cualquier plataforma o aplicación del lado del servidor que pueda realizar llamadas HTTP/s.
* Ofrecer experiencias coherentes y personalizadas a un visitante independientemente del canal o los dispositivos que el visitante utilizó para interactuar con su empresa.
* Almacene en caché experiencias para un visitante dentro de una sesión en el servidor, de modo que se puedan evitar múltiples llamadas a la API, lo que mejora el rendimiento.
* Integre sin problemas con [!DNL Adobe Experience Cloud] productos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) y [!DNL Experience Cloud ID Service] del lado del servidor.

## SDK del servidor

Vínculo: [SDK para Adobe Target](https://developer.adobe.com/target/)

La variable [!DNL Adobe Target] portal de documentación de SDK del lado del servidor le ayuda a implementar [!DNL Target] en los servidores en el idioma que elija.

## API de Recommendations de Target

Vínculo: [API de Recommendations de Target](https://developer.adobe.com/target/){target=_blank}.

Las API de Recommendations le permiten interactuar mediante programación con [!DNL Target] servidores de recomendaciones. Estas API se pueden integrar con una serie de pilas de aplicaciones para realizar funciones que normalmente se harían mediante la función [!DNL Target] interfaz de usuario.
