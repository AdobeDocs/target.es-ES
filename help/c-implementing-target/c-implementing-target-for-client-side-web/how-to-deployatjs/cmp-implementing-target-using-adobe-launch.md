---
description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
keywords: implementar;implementación;adobe launch;launch;race;redirigir
seo-description: Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.
seo-title: Implementar Target utilizando Adobe Launch
title: Implementar Target utilizando Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

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

* **Resuelve la condición de carrera de Analytics y Target:** Como la llamada de Analytics se puede activar antes de la llamada de Target, la llamada de Target no se vincula a la llamada de Analytics. Esto puede generar datos incorrectos. A partir de la versión 0.6.0, la extensión de inicio de Target garantiza que la llamada de señalización de Analytics espere hasta que se complete la llamada de Target, correctamente o no. De este modo debería resolverse cualquier inconsistencia de datos que los clientes puedan experimentar.
* **Evita el manejo de ofertas de redireccionamiento incorrecto:** Si tiene Target y Analytics en la página, y existe una oferta de redireccionamiento ejecutada por Target, puede experimentar una situación en la que el rastreador de Analytics active una solicitud cuando no debería (porque el usuario se está redireccionando a una URL diferente). Si implementa Target y Analytics mediante Launch, no tendrá este problema. Con Launch, Target ordena a Analytics que anule la solicitud de señalización de Analytics.