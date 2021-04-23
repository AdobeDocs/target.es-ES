---
keywords: oferta;recuperación previa;iOS;android;sdk;móvil;sdk móvil
description: Utilice la función de recuperación previa de Adobe [!DNL Target] en los SDK para móviles iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.
title: ¿Puedo recuperar previamente contenido de ofertas para aplicaciones móviles?
feature: Implementar Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# Recuperación previa de contenido de ofertas

La función de recuperación previa de [!DNL Target] usa los SDK para móviles de iOS y Android a fin de recuperar contenido de ofertas el menor número posible de veces almacenando en caché las respuestas del servidor.

Este proceso reduce el tiempo de carga, evita múltiples llamadas de red y permite que se notifique a [!DNL Target] sobre qué mbox visitó el usuario de una aplicación móvil. Todo el contenido se recupera y almacena en caché durante la llamada de recuperación previa, y se recupera de la memoria caché para todas las llamadas futuras que incluyan este contenido para el nombre de mbox especificado.

Tenga en cuenta las siguientes limitaciones al utilizar el método de recuperación previa con los SDK para móviles iOS y Android:

* El contenido de recuperación previa no persiste de un inicio a otro. El contenido de recuperación previa se guarda en caché mientras la aplicación esté activa o hasta que se realice una llamada al método `clearPrefetchCache()`.
* La funcionalidad de recuperación previa no es compatible con los métodos de asignación de tráfico de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática], los tipos de actividad de [!UICONTROL Automated Personalization] o [!UICONTROL Recommendations] o las ofertas de recomendaciones dentro de una actividad A/B o XT](/help/c-recommendations/recommendations-as-an-offer.md).[

Para obtener más información, incluidos los métodos de recuperación previa, las clases públicas y ejemplos de código, consulte:

* **iOS:**  [Recuperación previa del contenido de ofertas en ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOS en la ayuda del SDK para iOS de  *Mobile Services*.
* **Android:**  [Recuperación previa del contenido de ofertas en ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android en la ayuda del SDK para Android de  *Mobile Services*.
