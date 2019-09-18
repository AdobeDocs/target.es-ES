---
description: La función de recuperación previa de Adobe Target usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.
keywords: oferta;recuperación previa;iOS;android;sdk;mobile;mobile sdk
seo-description: La función de recuperación previa de Adobe Target usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.
seo-title: Recuperación previa de contenido de ofertas
solution: Target
title: Recuperación previa de contenido de ofertas
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# Recuperación previa de contenido de ofertas{#prefetch-offer-content}

La función de recuperación previa de [!DNL Target] usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.

Este proceso reduce el tiempo de carga, evita múltiples llamadas de red y permite que se notifique a [!DNL Target] sobre qué mbox visitó el usuario de una aplicación móvil. Todo el contenido se recupera y se almacena en caché durante la llamada de recuperación previa, y este contenido se recupera de la caché para todas las llamadas futuras que contengan contenido en caché para el nombre de mbox especificado.

Tenga en cuenta lo siguiente cuando se utiliza en el método de recuperación previa con los SDK para móviles de iOS y Android:

* El contenido de recuperación previa no persiste de un inicio a otro. El contenido de recuperación previa se guarda en caché mientras la aplicación esté activa o hasta que se realice una llamada al método `clearPrefetchCache()`.
* La funcionalidad de recuperación previa en los SDK para móviles de iOs y Android no es compatible con los tipos de actividad de segmentación automática, asignación automática y personalización automatizada.

Para obtener más información, incluidos los métodos de recuperación previa, las clases públicas y ejemplos de código, consulte:

* **** iOS:  Recuperación [previa de contenido de ofertas en iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) en la Ayuda *del SDK para iOS de* Mobile Services.
* **** Android:  Recuperación [previa de contenido de ofertas en Android](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) en la Ayuda *del SDK para Android de* Mobile Services.
