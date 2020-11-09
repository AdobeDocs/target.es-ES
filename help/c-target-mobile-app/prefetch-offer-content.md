---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: La función de recuperación previa de Adobe Target usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.
title: Recuperación previa de contenido de ofertas
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 63%

---


# Recuperación previa de contenido de ofertas{#prefetch-offer-content}

La función de recuperación previa de [!DNL Target] usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.

Este proceso reduce el tiempo de carga, evita múltiples llamadas de red y permite que se notifique a [!DNL Target] sobre qué mbox visitó el usuario de una aplicación móvil. Todo el contenido se recupera y almacena en caché durante la llamada de recuperación previa, y se recupera de la memoria caché para todas las llamadas futuras que incluyan este contenido para el nombre de mbox especificado.

Tenga en cuenta las siguientes limitaciones al utilizar el método de recuperación previa con los SDK para móviles de iOS y Android:

* El contenido de recuperación previa no persiste de un inicio a otro. El contenido de recuperación previa se guarda en caché mientras la aplicación esté activa o hasta que se realice una llamada al método `clearPrefetchCache()`.
* La funcionalidad de recuperación previa no es compatible con los métodos de asignación de tráfico de asignación  automática y de Destinatario  automático, para los tipos de actividad de [!UICONTROL Automated Personalization] o [!UICONTROL Recommendations] , o para las ofertas de [recomendaciones dentro de una actividad](/help/c-recommendations/recommendations-as-an-offer.md)A/B o XT.

Para obtener más información, incluidos los métodos de recuperación previa, las clases públicas y ejemplos de código, consulte:

* **iOS:**  [Recuperación previa de contenido de oferta en iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) en la Ayuda *del SDK para iOS de* Mobile Services.
* **Android:**  [Recuperación previa de contenido de oferta en Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) en la Ayuda *del SDK para Android de* Mobile Services.
