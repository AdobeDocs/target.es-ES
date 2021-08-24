---
keywords: implementar;implementación;adobe launch;launch;race;redireccionamiento;experience platform launch;platform launch;etiquetas;adobe platform
description: Aprenda a implementar la biblioteca Adobe [!DNL Target] at.js mediante Adobe Experience Platform Launch, el método preferido para implementar Adobe [!DNL Target].
title: ¿Cómo puedo implementar [!DNL Target] utilizando Launch de Adobe?
feature: Implementación del lado del servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 82629fb4c543220796fc99d9c034ebb725e1a645
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# Implementar [!DNL Target] utilizando [!DNL Adobe Experience Platform]

Las etiquetas de [!DNL Adobe Experience Platform] son la siguiente generación de funcionalidades de administración de etiquetas de [!DNL Adobe]. Las etiquetas proporcionan a los clientes una alternativa sencilla para implementar y gestionar las etiquetas de análisis, marketing y publicidad necesarias para ofrecer al cliente experiencias más relevantes.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] se ha convertido en un conjunto de tecnologías de recopilación de datos en  [!DNL Adobe Experience Platform]. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obtener una referencia consolidada de los cambios terminológicos.

La tabla siguiente muestra las distintas fuentes en las que puede obtener más información:

| Recurso | Detalles |
|--- |--- |
| [Añadir  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Este tutorial proporciona instrucciones paso a paso para implementar [!DNL Target] en un sitio web con etiquetas en [!DNL Adobe Experience Platform]. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar [!DNL Adobe Experience Platform] y otras soluciones [!DNL Adobe Experience Cloud]. |
| [Guía de inicio rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Información sobre la implementación y administración de las etiquetas de análisis, marketing y publicidad necesarias para ofrecer al cliente experiencias más relevantes. |
| [ [!DNL Target] Información general de Adobeextension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Información sobre la implementación de [!DNL Target] mediante [!DNL Adobe Experience Platform]. |

## Ventajas de implementar at.js con la extensión [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas solo se aplican si utiliza etiquetas en [!DNL Adobe Experience Platform] para implementar at.js. Por este motivo, [!DNL Adobe] sugiere encarecidamente que utilice etiquetas en [!DNL Adobe Experience Platform] en lugar de una implementación manual de at.js.

* **Condiciones de solución  [!DNL Adobe Analytics] y  [!DNL Target] carrera:** Dado que la  [!DNL Analytics] llamada podría activarse antes de la  [!DNL Target] llamada, la  [!DNL Target] llamada no se une a la  [!DNL Analytics] llamada. Esta secuenciación puede dar lugar a datos incorrectos. La extensión [!DNL Target] garantiza que la llamada de señalización [!DNL Analytics] espera hasta que la llamada [!DNL Target] se complete, tenga éxito o no. El uso de etiquetas en [!DNL Adobe Experience Platform] resuelve la incoherencia de datos que los clientes pueden experimentar al implementar manualmente.
* **Evita la gestión de ofertas de redireccionamiento incorrectas:** Si tiene  [!DNL Target] y  [!DNL Analytics] en la página y hay una oferta de redireccionamiento ejecutada por  [!DNL Target], puede darse el caso de que el  [!DNL Analytics] rastreador active una solicitud cuando no debería (porque el usuario se está redireccionando a una dirección URL diferente). Si implementa [!DNL Target] y [!DNL Analytics] mediante etiquetas en [!DNL Adobe Experience Platform], no tendrá este problema. Utilizando etiquetas en [!DNL Adobe Experience Platform], [!DNL Target] ordena a [!DNL Analytics] que interrumpa la solicitud de señalización [!DNL Analytics].
