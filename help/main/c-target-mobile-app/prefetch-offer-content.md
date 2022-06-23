---
keywords: oferta;recuperación previa;iOS;android;sdk;móvil;sdk móvil
description: Uso del Adobe [!DNL Target] función de recuperación previa en los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.
title: ¿Puedo recuperar previamente contenido de ofertas para aplicaciones móviles?
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 54%

---

# Recuperación previa de contenido de ofertas

La función de recuperación previa de [!DNL Target] usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.

Este proceso reduce el tiempo de carga, evita múltiples llamadas de red y permite que se notifique a [!DNL Target] sobre qué mbox visitó el usuario de una aplicación móvil. Todo el contenido se recupera y almacena en caché durante la llamada de recuperación previa, y se recupera de la memoria caché para todas las llamadas futuras que incluyan este contenido para el nombre de mbox especificado.

Tenga en cuenta las siguientes limitaciones al utilizar el método de recuperación previa con los SDK para móviles iOS y Android:

* El contenido de recuperación previa no persiste de un inicio a otro. El contenido de recuperación previa se guarda en caché mientras la aplicación esté activa o hasta que se realice una llamada al método `clearPrefetchCache()`.

Para obtener más información, incluidos los métodos de recuperación previa, las clases públicas y ejemplos de código, consulte:

* **iOS:**  [Recuperación previa del contenido de ofertas en iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) en el *Ayuda del SDK de iOS de Mobile Services*.
* **Android:**  [Recuperación previa del contenido de ofertas en Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) en el *Ayuda del SDK para Android de Mobile Services*.
