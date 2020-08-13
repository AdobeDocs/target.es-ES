---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: Notas de la versión relacionadas con el SDK de Java de Adobe Target.
title: Notas de la versión relacionadas con el SDK de Java de Adobe Target.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# Notas de la versión: SDK de Java de Destinatario

Notas de la versión relacionadas con el SDK [de Java de](https://github.com/adobe/target-java-sdk)Destinatario.

El SDK de [!DNL Target] Java permite implementar [!DNL Target] el servidor. Este SDK de Java le ayuda a integrarse fácilmente [!DNL Target] con otras [!DNL Adobe Experience Cloud] soluciones, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]y [!DNL Adobe Audience Manager].

El SDK de Java presenta prácticas recomendadas y elimina las complejidades al integrarlo con [!DNL Target] nuestra API de envío, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial.

Obtenga más información sobre el SDK de Java de Destinatario en el blog técnico de Adobe: Optimización del lado del [servidor con el nuevo SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)de Java de Destinatario.

## Versión 1.1.0 (16 de diciembre de 2019)

La siguiente sección proporciona más información sobre la versión 1.1.0 del SDK de Java de Destinatario:

### Se ha agregado

* Se agregó compatibilidad con la configuración proxy debido a una contribución de código abierto de @hisham-hassan.

## Versión 1.0.1 (11 de noviembre de 2019)

La siguiente sección proporciona más información sobre la versión 1.0.1 del SDK de Java de Destinatario:

### Fijo

* Envíe un ID de datos suplementario en una solicitud de Destinatario incluso cuando no haya una cookie de API de Visitante presente.

## Versión 1.0.0 (31 de octubre de 2019)

Las siguientes secciones proporcionan más información sobre la versión 1.0.0 del SDK de Java de Destinatario:

### Se ha agregado

* [Compatibilidad con la API](https://developers.adobetarget.com/api/delivery-api/) de Envío de Vista de destinatario v1, incluida la carga de página y la recuperación previa de Vistas.
   * Compatibilidad total con la entrega de todos los tipos de ofertas creadas en el Compositor de experiencias visuales (VEC).
* Compatibilidad con la recuperación previa y las notificaciones que permiten la optimización del rendimiento almacenando en caché el contenido recuperado previamente.
* Compatibilidad para optimizar el rendimiento en integraciones híbridas [!DNL Target] mediante `serverState`, cuando [!DNL Target] se implementa tanto en el servidor como en el cliente.
   * Estamos introduciendo una configuración llamada `serverState` que contiene experiencias recuperadas a través del servidor, de modo que at.js v2.2+ no realice una llamada al servidor adicional para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.
* Open source on GitHub como SDK [de Java de](https://github.com/adobe/target-java-sdk)Destinatario.
* Validación de los argumentos del método API de SDK.
* Pruebas README, muestras y unidades añadidas.
* CoC añadido, directrices de contribución, relaciones públicas y plantillas de publicación.

