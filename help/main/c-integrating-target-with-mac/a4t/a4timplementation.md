---
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes;at.js;atjs;sdk web de adobe experience platform;sdk web de aep;sdk web de platform
description: Siga los pasos necesarios para implementar Analytics for [!DNL Target] (A4T) en sus soluciones de Adobe [!DNL Target]  y Adobe Analytics.
title: ¿Cómo implemento Analytics para  [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 17%

---

# Implementación de Analytics for [!DNL Target]

Se requieren varios pasos al implementar [!DNL Adobe Analytics] como origen de informes para [!DNL Adobe Target] (A4T). El proceso varía en función de si implementa A4T con [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) o con at.js.

## ![Distintivo de Adobe Experience Platform Web SDK](/help/main/assets/platform.png) Pasos de implementación para una implementación de Adobe Experience Platform Web SDK {#platform}

En las secciones siguientes se describen los pasos necesarios para implementar esta integración en el sitio si tiene pensado utilizar Platform Web SDK:

### Paso 1: Solicitar aprovisionamiento para [!DNL Analytics] y [!DNL Target]

Antes de implementar A4T, debe estar aprovisionado para [!DNL Analytics] y [!DNL Target]. [Use este formulario para solicitar el aprovisionamiento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Crear una configuración de Edge

Cree una configuración de Edge con [!DNL Adobe Experience Platform] mediante la herramienta de configuración de Edge. Configure [Crear y configurar flujos de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

### Paso 4: Instalación y configuración de Platform Web SDK

Para empezar a entregar experiencias de [!DNL Target] y aplicar [!DNL Analytics] con fines de seguimiento y análisis, [instale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) y [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) Platform Web SDK en las páginas del sitio.

### Paso 5: Habilitar las opciones para usar A4T

En la interfaz de usuario de [!DNL Target], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** y, a continuación, elija **[!UICONTROL Select per activity]** o **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** le permite elegir entre [!DNL Target] y [!DNL Analytics] al crear cada actividad.
* **[!UICONTROL Adobe Analytics]** establece [!DNL Analytics] como el origen de informes para todas las actividades que cree.

## ![distintivo de at.js](/help/main/assets/atjs.png) Pasos de implementación para una implementación de at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar at.js:

### Paso 1: Solicitar el aprovisionamiento para Analytics y Target

Después de implementar [!DNL Analytics] como el origen de informes de [!DNL Target], debe aprovisionarse para [!DNL Analytics] y [!DNL Target]. [Use este formulario para solicitar el aprovisionamiento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante le permite identificar usuarios en [!DNL Adobe Experience Cloud] soluciones. Implementar o migrar a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar el servicio Experience Cloud ID para Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) en la documentación de *Servicio Experience Cloud ID de visitante*.

### Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Implemente o migre a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Descripción general de la implementación de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) en la *Guía de implementación de Analytics*.

Para realizar una migración, consulte [Migración a AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) en la *Guía de implementación de Analytics*.

### Paso 5: Descargar y actualizar at.js

Implemente o migre a la versión requerida de at.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Paso 6: Host at.js

Si ha implementado anteriormente at.js, puede reemplazar el archivo existente con la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

### Paso 7: Agregar la referencia de at.js a todas las páginas del sitio {#step7}

Incluya at.js debajo de VisitorAPI.js agregando la siguiente línea de código en la etiqueta de cada página:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js debe cargarse antes que at.js. Si está actualizando un archivo at.js existente, asegúrese de comprobar el orden de carga.

La configuración predeterminada para la integración de [!DNL Target] y [!DNL Analytics], desde una perspectiva de implementación, es utilizar el SDID que se pasa desde la página para unir automáticamente la solicitud de [!DNL Target] y [!DNL Analytics] en el servidor.

Puede controlar cómo y cuándo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] con fines de creación de informes. Si no desea adherirse a la configuración predeterminada de que [!DNL Target] y [!DNL Analytics] vinculen automáticamente los datos de análisis mediante el SDID, establezca **analyticsLogging = client_side** mediante **window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js tiene **analyticsLogging: &quot;client_side&quot;** enviado dentro de las [!DNL Target] solicitudes y se devuelve una carga útil de Analytics para cada solicitud. Cuando se configura esta opción, el formato de la carga útil que se devuelve es el siguiente:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La carga útil se puede reenviar a Analytics a través de la [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para las actividades de Asignación automática y Segmentación automática, también debe reenviar el sessionId. Para obtener más información, consulte [Informes de Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} en la guía de *SDK de Adobe Target*.

Si no desea una configuración global y prefiere un método bajo demanda, use la función at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} pasando **analyticsLogging: &quot;client_side&quot;**. La carga útil de Analytics solo se devuelve para esta llamada y el backend [!DNL Target] no reenvía la carga útil a [!DNL Analytics]. Al llevar a cabo este enfoque, cada solicitud at.js [!DNL Target] devuelve la carga útil de forma predeterminada, pero solo cuando se desea y se especifica.

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

### Paso 8: Validar la implementación {#step8}

Cargue las páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro `mboxMCSDID` en las llamadas [!DNL Target] coinciden con el valor del parámetro `sdid` en la llamada de vista de página [!DNL Analytics].

Es especialmente importante confirmar que estos valores coinciden en aplicaciones de una sola página (SPA) en las que el orden de las llamadas no siempre es predecible.

>[!NOTE]
>
>Se requiere la coincidencia de estos valores para que A4T funcione correctamente.

### Paso 9 (opcional): Eliminar el código de integración anterior

Adobe recomienda quitar la integración anterior para simplificar la implementación y evitar la necesidad de resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, incluido `mboxLoadSCPlugin`.

### Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En [!DNL Target], haga clic en **[!UICONTROL Administration > Reporting]** y elija **[!UICONTROL Select per activity]** o **[!UICONTROL Adobe Analytics]** para habilitar las opciones.

* **[!UICONTROL Select per activity]** le permite elegir entre [!DNL Target] y [!DNL Analytics] al crear cada actividad.
* **[!UICONTROL Adobe Analytics]** establece [!DNL Analytics] como el origen de informes para todas las actividades que cree.


