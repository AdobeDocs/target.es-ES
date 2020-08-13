---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
title: Implementación de Analytics for Target
feature: a4t implementation
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 63%

---


# Implementación de Analytics for Target{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

Las siguientes secciones describen los pasos necesarios para implementar esta integración en el sitio.

## Paso 1: Solicitud de aprovisionamiento para Analytics y Destinatario

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [Rellene este formulario para solicitar el aprovisionamiento](http://www.adobe.com/go/audiences).

## Paso 2: Configurar los permisos de usuario

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. See [User permission requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de [!DNL Adobe Experience Cloud]. Debe implementar o migrar a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Debe implementar o migrar a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte Introducción [a la implementación de](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) JavaScript en la Guía *de implementación de* Analytics.

Para realizar una migración, consulte [Migración a AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) en la Guía *de implementación de* Analytics.

## Paso 5: Descargar y actualizar at.js o mbox.js

Debe implementar o migrar a la versión requerida de at.js o mbox.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Paso 6: Host at.js o mbox.js

Si ha implementado anteriormente at.js o mbox.js, puede reemplazar el archivo existente con la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

## Paso 7: Agregar la referencia de at.js o mbox.js a todas las páginas del sitio.  {#step7}

Incluya at.js o mbox.js debajo de VisitorAPI.js. Para ello, agregue la siguiente línea de código dentro de la etiqueta de todas las páginas:

Para at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Para mbox.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

Es esencial que VisitorAPI.js se cargue antes que at.js o mbox.js. Si va a actualizar un archivo at.js o mbox.js existente, compruebe el orden de carga.

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js enviará **analyticsLogging: &quot;client_side&quot;** en las solicitudes de y devolverá una carga útil de Analytics para cada solicitud. [!DNL Target] Cuando se configura, el formato de la carga útil que se devuelve es el siguiente:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La carga útil se puede reenviar a Analytics mediante la API [de inserción](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)de datos.

Si no desea una configuración global y prefiere un método bajo demanda, puede utilizar la función at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) para conseguirlo al pasar **analyticsLogging: &quot;client_side&quot;**. The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

Por ejemplo:

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

Esta llamada invoca una respuesta desde la cual puede extraer la carga útil de Analytics.

La respuesta es la siguiente:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

La carga útil se puede reenviar a [!DNL Analytics] través de la API [de inserción](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)de datos.

## Paso 8: Validar la implementación {#step8}

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro `mboxMCSDID`[!DNL Target] en las llamadas de coinciden con el valor del parámetro `sdid`[!DNL Analytics] en la llamada de vista de página de 

Es especialmente importante confirmar esto en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

**Nota:** Es necesario que estos valores coincidan para que A4T funcione correctamente.

## Paso 9 (opcional): Eliminar el código de integración anterior

Recomendamos quitar la integración anterior para simplificar la implementación y que no resulte necesario resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

## Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]

