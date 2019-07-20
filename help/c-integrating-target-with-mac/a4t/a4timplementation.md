---
description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes
seo-description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
seo-title: Implementación de Analytics for Target
solution: Target
title: Implementación de Analytics for Target
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Implementación de Analytics for Target{#analytics-for-target-implementation}

Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).

## Pasos de la implementación {#section_73961BAD5BB4430A95E073DE5C026277}

En la tabla siguiente se describen los pasos necesarios para implementar esta integración en un sitio.

## Paso 1: Solicitar el aprovisionamiento para Analytics y Target

Después de implementar Analytics como fuente de informes para Target, debe aprovisionar para Analytics y Target. [Rellene este formulario para solicitar el aprovisionamiento](http://www.adobe.com/go/audiences).

## Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear en Adobe Target una actividad basada en Adobe Analytics. Consulte  [Requisitos de permisos de usuario](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de Experience Cloud. Debe implementar o migrar a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementación del servicio de Experience Cloud ID para Target](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html) en la documentación del servicio ID de visitante de Experience Cloud.

## Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Debe implementar o migrar a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Implementación de JavaScript para Analytics](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

Para realizar una migración, consulte [Migración a AppMeasurement para JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs_migrate).

## Paso 5: Descargar y actualizar at.js o mbox.js

Debe implementar o migrar a la versión requerida de at.js o mbox.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Paso 6: Host at.js o mbox.js

Si ha implementado anteriormente at.js o mbox.js, puede reemplazar el archivo existente con la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

## Paso 7: Agregar la referencia de at.js o mbox.js a todas las páginas del sitio {#step7}

Incluya at. js o mbox. js debajo de visitorapi. js agregando la línea de código siguiente en la etiqueta de cada página:

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

Es esencial que visitorapi. js se cargue antes que at. js o mbox. js. Si está actualizando un archivo at. js o mbox. js existente, asegúrese de verificar el orden de carga.

La configuración predeterminada que se configura para la integración de Target y Analytics desde una perspectiva de implementación es utilizar el SDID que se pasa desde la página para unir la solicitud de Target y Analytics en forma conjunta en el back-backend automáticamente.

However, if you want more control on how and when to send analytics data related to Target to Analytics for reporting purposes, and you do not want to opt-in to the default settings of having Target and Analytics automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Nota: las versiones anteriores a 2.1 no admiten este método.

Por ejemplo:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

This set up has a global effect, which means that every call made by at.js will have **analyticsLogging: "client_side"** sent within the Target requests and an analytics payload will be returned for every request. Cuando se configura, el formato de la carga útil que se devuelve es el siguiente:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

If a global setting is not desired and a more on-demand approach is preferable, then you can use the at.js function [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) to achieve this by passing in **analyticsLogging: "client_side"**. La carga útil de Analytics solo se devolverá para esta llamada y el back-backend de Target no reenviará la carga útil a Analytics. Al llevar a cabo este enfoque, cada solicitud de at. js de Target no devolverá la carga útil de forma predeterminada, sino solo si se desea y se especifica.

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

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Paso 8: Validar la implementación {#step8}

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro mboxMCSDID en las llamadas de Target coinciden con el valor del parámetro sdid en la llamada de vista de página de Analytics.

Es especialmente importante confirmar esto en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

**Nota:** Es necesario que estos valores coincidan para que A4T funcione correctamente.

## Paso 9 (opcional): Eliminar el código de integración anterior

Recomendamos quitar la integración anterior para simplificar la implementación y que no resulte necesario resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

## Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En Target, haga clic en [!UICONTROL Configuración &gt; Preferencias] y elija [!UICONTROL Seleccionar por actividad] o [!UICONTROL Adobe Analytics] para habilitar las opciones.

* La opción Seleccionar por actividad permite elegir entre Target y Analytics a la hora de crear cada actividad.
* La opción Adobe Analytics establece Analytics como fuente de informes para todas las actividades que cree.

