---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
title: Implementación de Analytics for Target
feature: a4t implementation
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 50%

---


# Implementación de Analytics for Target{#analytics-for-target-implementation}

Se requieren varios pasos al implementar [!DNL Adobe Analytics] como fuente de sistema de informes para [!DNL Target] (A4T).

## Pasos de implementación {#section_73961BAD5BB4430A95E073DE5C026277}

Las siguientes secciones describen los pasos necesarios para implementar esta integración en el sitio.

## Paso 1: Solicitud de aprovisionamiento para Analytics y Destinatario

Después de implementar [!DNL Analytics] como fuente de sistema de informes para [!DNL Target], debe estar aprovisionado para [!DNL Analytics] y [!DNL Target]. [Rellene este formulario para solicitar el aprovisionamiento](http://www.adobe.com/go/audiences).

## Paso 2: Configurar los permisos de usuario

Los requisitos de cuenta de usuario deben cumplirse antes de poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de [!DNL Adobe Experience Cloud]. Debe implementar o migrar a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar el servicio de ID de Experience Cloud para Destinatario](https://experienceleague.adobe.com/docs/id-service/using/implementation-guides/setup-target.html) en la *documentación del servicio de ID de Visitante de Experience Cloud*.

## Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Debe implementar o migrar a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [información general sobre la implementación de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) en la *Guía de implementación de Analytics*.

Para ver una migración, consulte [Migración a AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) en la *Guía de implementación de Analytics*.

## Paso 5: Descargar y actualizar at.js

Debe implementar o migrar a la versión requerida de at.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Paso 6: Host de at.js

Si ya ha implementado at.js, puede reemplazar el archivo existente por la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

## Paso 7: Haga referencia a at.js en todas las páginas del sitio {#step7}

Incluya at.js debajo de VisitorAPI.js agregando la siguiente línea de código en la etiqueta de cada página:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Es esencial que VisitorAPI.js se cargue antes que at.js. Si está actualizando un archivo at.js o mbox.js existente, asegúrese de comprobar el orden de carga.

La manera en que la configuración predeterminada se configura para la integración [!DNL Target] y [!DNL Analytics] desde una perspectiva de implementación es utilizar automáticamente el SDID que se pasa desde la página para unir la solicitud [!DNL Target] y [!DNL Analytics] en el servidor.

Sin embargo, si desea obtener más control sobre cómo y cuándo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] con fines de sistema de informes, y no desea optar por la configuración predeterminada de [!DNL Target] y [!DNL Analytics] unir automáticamente los datos de análisis mediante el SDID, puede establecer **analyticsLogging = client_side** mediante **>window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js enviará **analyticsLogging: &quot;client_side&quot;** en las solicitudes de y devolverá una carga útil de Analytics para cada solicitud. [!DNL Target] Cuando se configura, el formato de la carga útil que se devuelve es el siguiente:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La carga útil se puede reenviar a Analytics mediante la [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Tenga en cuenta que, para las actividades [!UICONTROL Asignación automática] y [!UICONTROL Destinatario automático] también tendrá que reenviar el sessionId. Para obtener más información, consulte el sistema de informes [Analytics para Destinatario (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) en la guía *SDK para Adobe Target*.

Si no desea una configuración global y prefiere un método bajo demanda, puede utilizar la función at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) para conseguirlo al pasar **analyticsLogging: &quot;client_side&quot;**. La carga útil de Analytics se devolverá solo para esta llamada y el servidor [!DNL Target] no reenviará la carga útil a [!DNL Analytics]. Al seguir este método, cada solicitud de at.js [!DNL Target] no devolverá la carga útil de forma predeterminada, sino únicamente cuando se desee y se especifique.

Por ejemplo:

```javascript
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

```javascript
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

La carga útil se puede reenviar a [!DNL Analytics] mediante la [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Paso 8: Validar la implementación {#step8}

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro `mboxMCSDID`[!DNL Target] en las llamadas de coinciden con el valor del parámetro `sdid`[!DNL Analytics] en la llamada de vista de página de 

Es especialmente importante confirmar esto en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

**Nota:** Es necesario que estos valores coincidan para que A4T funcione correctamente.

## Paso 9 (opcional): Eliminar el código de integración anterior

Recomendamos quitar la integración anterior para simplificar la implementación y que no resulte necesario resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

## Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En [!DNL Target], haga clic en **[!UICONTROL Administración > Compositor de experiencias visuales]** y elija **[!UICONTROL Seleccionar por actividad]** o **[!UICONTROL Adobe Analytics]** para habilitar las opciones.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]

