---
description: Notas de la versión relacionadas con el SDK de Java de Adobe Target
keywords: at.js;sdk;release;updates;sdks;server side;server-side;server-side;java;java sdk
seo-description: Notas de la versión relacionadas con el SDK de Java de Adobe Target.
seo-title: Notas de la versión relacionadas con el SDK de Java de Adobe Target.
solution: Target
title: 'Notas de la versión: SDK de Java de Target'
topic: Standard
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# Notas de la versión: SDK de Java de Target

Notas de la versión relacionadas con el SDK [de Java de](https://github.com/adobe/target-java-sdk)Target.

El SDK de [!DNL Target] Java permite implementar [!DNL Target] el servidor. Este SDK de Java le ayuda a integrarse fácilmente [!DNL Target] con otras [!DNL Adobe Experience Cloud] soluciones, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]y [!DNL Adobe Audience Manager].

El SDK de Java introduce prácticas recomendadas y elimina las complejidades al realizar la integración con [!DNL Target] mediante nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial.

Obtenga más información sobre el SDK de Java de Target en el blog técnico de Adobe: Optimización del lado del [servidor con el nuevo SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)de Java de Target.

## Versión 1.0.0 (31 de octubre de 2019)

Las siguientes secciones proporcionan más información sobre la versión 1.0.0 del SDK de Java de Target:

### Se ha agregado

* [Compatibilidad con la API](https://developers.adobetarget.com/api/delivery-api/) de Target View Delivery v1, incluidas la carga de página y la recuperación previa de la vista.
   * Compatibilidad total para ofrecer todo tipo de ofertas creadas en el Compositor de experiencias visuales (VEC).
* Compatibilidad con la recuperación previa y las notificaciones que permiten la optimización del rendimiento almacenando en caché el contenido recuperado previamente.
* Compatibilidad para optimizar el rendimiento en integraciones híbridas [!DNL Target] mediante `serverState`, cuando [!DNL Target] se implementa tanto en el servidor como en el cliente.
   * Estamos introduciendo una configuración llamada `serverState` que contiene experiencias recuperadas a través del servidor, de modo que at.js v2.2+ no realice una llamada al servidor adicional para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.
* Abra el código fuente en GitHub como SDK [Java de](https://github.com/adobe/target-java-sdk)Target.
* Validación de los argumentos del método API de SDK.
* Se han añadido pruebas README, muestras y unidades.
* Se han agregado las plantillas CoC, las directrices de contribución, las relaciones públicas y los números.

