---
keywords: implementar;implementación;adobe launch;launch;race;redireccionamiento;platform launch de experiencias
description: Aprenda a implementar la biblioteca Adobe [!DNL Target] at.js mediante Adobe Experience Platform Launch, el método preferido para implementar Adobe [!DNL Target].
title: ¿Cómo puedo implementar [!DNL Target] utilizando Launch de Adobe?
feature: Implementación del lado del servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 75%

---

# Implementar [!DNL Target] utilizando Launch de Adobe

Adobe Experience Platform Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

## Implementar [!DNL Target] utilizando Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch es la plataforma de administración de etiquetas de próxima generación de Adobe y es el método preferido para implementar Adobe Target. Launch ofrece a los clientes una alternativa sencilla para implementar y gestionar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

En la siguiente tabla se enumeran distintos recursos donde puede obtener más información sobre Launch:

| Recurso | Detalles |
|--- |--- |
| [Tutorial sobre implementación de Target con la extensión Adobe Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Este tutorial proporciona instrucciones paso a paso para implementar Adobe Target en un sitio web con Launch. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar Adobe Launch, así como otras soluciones de Adobe Experience Cloud. |
| [Documentación de Adobe Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | Información sobre la implementación y administración de todas las etiquetas de análisis, marketing y publicidad necesarias para lograr experiencias de cliente relevantes. |
| [Documentación de la extensión de Adobe Target](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Información sobre la implementación de Target con Launch. |

## Ventajas de implementar at.js utilizando la [!DNL Target] extensión de Launch {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas se aplican únicamente si utiliza Adobe Launch para implementar at.js. Por este motivo, se recomienda encarecidamente el uso de Adobe Launch en lugar de DTM o una implementación manual de at.js.

* **Soluciona la condición Race de Analytics y Target:** Como la llamada a Analytics podría activarse antes de la llamada a Target, esta no se “une” a la llamada de Analytics. Esto puede generar datos incorrectos. A partir de 0.6.0, la extensión Launch de Target garantiza que la llamada de modelo de Analytics espera hasta que la llamada de Target se complete, tenga éxito o no. De este modo debería resolverse cualquier inconsistencia de datos que los clientes puedan experimentar.
* **Evita la gestión de ofertas de redirección incorrectas:** Si una página contiene tanto Target como Analytics, y Target ejecuta una oferta de redirección, puede darse el caso de que el rastreador de Analytics active una solicitud cuando no debería, (ya que el usuario se redirige a una dirección URL diferente). Si implementa Target y Analytics mediante Launch, no tendrá este problema. Con Launch, Target ordena a Analytics que anule la solicitud de señalización de Analytics.
