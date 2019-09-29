---
description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
keywords: implementar;implementación;adobe launch;launch;race;redirigir
seo-description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
seo-title: Implementar Target utilizando Adobe Launch
title: Implementar Target utilizando Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 56bfceba22df830933aa005bf7faf24d4d6c09ba

---


# Implementación de Target mediante Adobe Launch{#implement-target-using-adobe-launch}

Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

## Implementar Target utilizando Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

En la siguiente tabla se enumeran distintos recursos donde puede obtener más información sobre Launch:

| Recurso | Detalles |
|--- |--- |
| [Implementación de Target mediante el tutorial de Adobe Target Extension](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Este tutorial proporciona instrucciones paso a paso para implementar Adobe Target en un sitio web con Launch. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar Adobe Launch, así como otras soluciones de Adobe Experience Cloud. |
| [Documentación de Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html) | Información sobre la implementación y administración de todas las etiquetas de análisis, marketing y publicidad necesarias para lograr experiencias de cliente relevantes. |
| [Documentación de Adobe Target Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Información sobre la implementación de Target con Launch. |

## Ventajas de implementar at.js mediante la extensión Launch de Target {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas se aplican únicamente si utiliza Adobe Launch para implementar at.js. Por este motivo, se recomienda encarecidamente el uso de Adobe Launch en lugar de DTM o una implementación manual de at.js.

* **Soluciona la condición Race de Analytics y Target:** Como la llamada a Analytics podría activarse antes de la llamada a Target, esta no se “une” a la llamada de Analytics. Esto puede generar datos incorrectos. A partir de 0.6.0, la extensión Launch de Target garantiza que la llamada de modelo de Analytics espera hasta que la llamada de Target se complete, tenga éxito o no. De este modo debería resolverse cualquier inconsistencia de datos que los clientes puedan experimentar.
* **Evita la gestión de ofertas de redirección incorrectas:** Si una página contiene tanto Target como Analytics, y Target ejecuta una oferta de redirección, puede darse el caso de que el rastreador de Analytics active una solicitud cuando no debería, (ya que el usuario se redirige a una dirección URL diferente). Si implementa Target y Analytics mediante Launch, no tendrá este problema. Con Launch, Target ordena a Analytics que anule la solicitud de señalización de Analytics.
