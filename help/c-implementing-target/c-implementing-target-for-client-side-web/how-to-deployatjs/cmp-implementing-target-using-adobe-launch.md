---
description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
keywords: implementar;implementación;adobe launch;launch;race;redirigir
seo-description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
seo-title: Implementar Target utilizando Adobe Launch
title: Implementar Target utilizando Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Implementación de Target mediante Adobe Launch{#implement-target-using-adobe-launch}

Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

## Implementar Target utilizando Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

En la siguiente tabla se enumeran distintos recursos donde puede obtener más información sobre Launch:

| Recurso | Detalles |
|--- |--- |
| [Implementación de Target con el tutorial de extensión de Adobe Target](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Este tutorial proporciona instrucciones paso a paso para implementar Adobe Target en un sitio web con Launch. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar Adobe Launch, así como otras soluciones de Adobe Experience Cloud. |
| [Documentación de Adobe Launch](https://docs.adobelaunch.com/getting-started) | Información sobre la implementación y administración de todas las etiquetas de análisis, marketing y publicidad necesarias para lograr experiencias de cliente relevantes. |
| [Documentación de Extension de Adobe Target](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | Información sobre la implementación de Target con Launch. |

## Ventajas de implementar at.js mediante la extensión Launch de Target {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas se aplican únicamente si utiliza Adobe Launch para implementar at.js. Por este motivo, se recomienda encarecidamente el uso de Adobe Launch en lugar de DTM o una implementación manual de at.js.

* **Permite la implementación asincrónica de Target:** para obtener más información, consulte “Extensión de Adobe Target con una implementación asíncrona” en [Documentación de extensión de Adobe Target](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension).
* **Soluciona la condición Race de Analytics y Target:** como la llamada a Analytics podría activarse antes de la llamada a Target, esta no se “cose” a la llamada de Analytics, lo que puede dar como resultado datos incorrectos. A partir de Launch 0.6.0, la extensión Launch de Target garantiza que la llamada de baliza de Analytics esperará hasta que la llamada de Target se complete, tenga éxito o no. De este modo debería resolverse cualquier inconsistencia de datos que los clientes puedan experimentar.
* **Evita la gestión de ofertas de redirección incorrectas:** cuando una página contiene tanto Target como Analytics y Target ejecuta una oferta de redirección, puede darse el caso de que el rastreador de Analytics active una solicitud cuando no debería, ya que el usuario es redirigido a una dirección diferente. No tendrá este problema si implementa Target y Analytics mediante Launch, ya que, de este modo, Target indicará a Analytics que interrumpa la solicitud de baliza.

