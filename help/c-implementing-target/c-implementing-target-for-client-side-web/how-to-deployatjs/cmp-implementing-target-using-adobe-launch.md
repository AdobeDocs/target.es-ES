---
keywords: implementar;implementación;adobe launch;launch;race;redireccionamiento;experience platform launch;platform launch;etiquetas;adobe platform
description: Obtenga información sobre cómo implementar la biblioteca at.js de  [!DNL Adobe Target]  mediante  [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target].
title: ¿Cómo puedo implementar  [!DNL Target]  utilizando  [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: ht
source-wordcount: '417'
ht-degree: 100%

---

# Implementación [!DNL Target] mediante [!DNL Adobe Experience Platform]

Las etiquetas de [!DNL Adobe Experience Platform] son la siguiente generación de funcionalidades de administración de etiquetas de [!DNL Adobe]. Las etiquetas ofrecen a los clientes una forma sencilla de implementar y administrar todas las etiquetas de análisis, marketing y publicidad necesarias para potenciar las importantes experiencias del cliente.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] se ha convertido en un conjunto de tecnologías de recopilación de datos en [!DNL Adobe Experience Platform]. Como resultado, se han implementado varios cambios terminológicos en la documentación del producto. Consulte el siguiente [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=es) para obtener una referencia consolidada de los cambios terminológicos.

En la siguiente tabla se enumeran distintos recursos donde puede obtener más información:

| Recurso | Detalles |
|--- |--- |
| [Añadir [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html?lang=es#implement-solutions) | Este tutorial proporciona instrucciones paso a paso para implementar [!DNL Target] en un sitio web con etiquetas en [!DNL Adobe Experience Platform]. Los temas incluyen añadir la biblioteca JavaScript at.js, activar el mbox global, añadir parámetros e integrar con otras soluciones. Este artículo forma parte de un tutorial más amplio que muestra cómo implementar [!DNL Adobe Experience Platform] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Guía de inicio rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=es) | Información acerca de la implementación y administración de las etiquetas de análisis, marketing y publicidad necesarias para lograr experiencias de cliente relevantes. |
| Información general de la [extensión de Adobe  [!DNL Target] ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=es) | Información acerca de la implementación de [!DNL Target] mediante [!DNL Adobe Experience Platform]. |

## Ventajas de implementar at.js con la extensión [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Las siguientes ventajas se aplican únicamente si utiliza etiquetas en [!DNL Adobe Experience Platform] para implementar at.js. Por este motivo, [!DNL Adobe] recomienda encarecidamente que utilice etiquetas en [!DNL Adobe Experience Platform] en lugar de una implementación manual de at.js.

* **Soluciona la condición Race de [!DNL Adobe Analytics] y [!DNL Target]:** Como la llamada a [!DNL Analytics] podría activarse antes de la llamada a [!DNL Target], la llamada [!DNL Target] no se “une” a la llamada de [!DNL Analytics]. Esta secuencia puede generar datos incorrectos. La extensión [!DNL Target] garantiza que la llamada de señalización [!DNL Analytics] espera hasta que la llamada [!DNL Target] se complete, tenga éxito o no. El uso de etiquetas en [!DNL Adobe Experience Platform] resuelve la incoherencia de datos que los clientes pueden experimentar al implementar manualmente.

   >[!NOTE]
   >
   >Utilice la acción [!UICONTROL Enviar señalización] en la extensión de [!DNL Adobe Analytics] para que la llamada a [!DNL Analytics] espere a que se realice la llamada a [!DNL Target]. Si llama directamente a `s.t()` o `s.tl()` utilizando código personalizado, las llamadas de [!DNL Analytics] no esperan hasta que se hayan completado las llamadas de [!DNL Target].

* **Evita la gestión de ofertas de redireccionamiento incorrectas:** si una página contiene tanto [!DNL Target] como [!DNL Analytics], y [!DNL Target] ejecuta una oferta de redirección, puede darse el caso de que el rastreador de [!DNL Analytics] active una solicitud cuando no debería, (ya que el usuario se redirige a una dirección URL diferente). Si implementa [!DNL Target] y [!DNL Analytics] con etiquetas en [!DNL Adobe Experience Platform], no tendrá este problema. Utilizando etiquetas en [!DNL Adobe Experience Platform], [!DNL Target] ordena a [!DNL Analytics] que interrumpa la solicitud de señalización de [!DNL Analytics].
