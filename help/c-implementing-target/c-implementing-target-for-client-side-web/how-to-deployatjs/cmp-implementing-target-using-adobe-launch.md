---
keywords: implementar;implementación;adobe launch;launch;race;redireccionamiento;platform launch de experiencias;platform launch
description: Aprenda a implementar la biblioteca Adobe [!DNL Target] at.js mediante Adobe Experience Platform Launch, el método preferido para implementar Adobe [!DNL Target].
title: ¿Cómo puedo implementar [!DNL Target] utilizando Launch de Adobe?
feature: Implementación del lado del servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 10%

---

# Implementar [!DNL Target] utilizando [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] es la plataforma de administración de etiquetas de próxima generación de  [!DNL Adobe] y es el método preferido para implementar  [!DNL Adobe Target]. [!DNL Platform Launch] ofrece a los clientes una alternativa sencilla para implementar y gestionar las etiquetas de análisis, marketing y publicidad necesarias para ofrecer al cliente experiencias más relevantes.

## Implementar [!DNL Target] utilizando [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

En la siguiente tabla se enumeran distintos recursos donde puede obtener más información sobre [!DNL Platform Launch]:

| Recurso | Detalles |
|--- |--- |
| [ [!DNL Target] Tutorial sobre implementación con la extensión de  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Este tutorial proporciona instrucciones paso a paso para implementar [!DNL Target] en un sitio web con [!DNL Platform Launch]. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar [!DNL Platform Launch] y otras soluciones [!DNL Adobe Experience Cloud]. |
| [[!DNL Adobe Platform Launch] Documentación](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | Información sobre la implementación y administración de las etiquetas de análisis, marketing y publicidad necesarias para ofrecer al cliente experiencias más relevantes. |
| [ [!DNL Target] Documentación de Adobe Extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Información sobre la implementación de [!DNL Target] mediante [!DNL Platform Launch]. |

## Ventajas de implementar at.js utilizando la extensión [!DNL Target] [!DNL Platform Launch] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas se aplican únicamente si utiliza [!DNL Platform Launch] para implementar at.js. Por este motivo, [!DNL Adobe] sugiere encarecidamente que utilice [!DNL Platform Launch] en lugar de una implementación manual de at.js.

* **Condiciones de solución  [!DNL Adobe Analytics] y  [!DNL Target] carrera:** Dado que la  [!DNL Analytics] llamada podría activarse antes de la  [!DNL Target] llamada, la  [!DNL Target] llamada no se une a la  [!DNL Analytics] llamada. Esta secuenciación puede dar lugar a datos incorrectos. A partir de 0.6.0, la extensión [!DNL Platform Launch] garantiza que la llamada de señalización [!DNL Analytics] espera hasta que la llamada [!DNL Target] se complete, tenga éxito o no. El uso de [!DNL Platform Launch] resuelve la incoherencia de datos que los clientes pueden experimentar al implementar manualmente.
* **Evita la gestión de ofertas de redireccionamiento incorrectas:** Si tiene  [!DNL Target] y  [!DNL Analytics] en la página y hay una oferta de redireccionamiento ejecutada por  [!DNL Target], puede darse el caso de que el  [!DNL Analytics] rastreador active una solicitud cuando no debería (porque el usuario se está redireccionando a una dirección URL diferente). Si implementa [!DNL Target] y [!DNL Analytics] mediante [!DNL Platform Launch], no tendrá este problema. Al usar [!DNL Platform Launch], [!DNL Target] ordena a [!DNL Analytics] que interrumpa la solicitud de señalización [!DNL Analytics].
