---
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes;at.js;atjs;sdk web de adobe experience platform;sdk web de aep;sdk web de platform
description: Siga los pasos necesarios para implementar Analytics para [!DNL Target] (A4T) en su Adobe [!DNL Target] y soluciones de Adobe Analytics.
title: ¿Cómo puedo implementar Analytics para? [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 17%

---

# Analytics para [!DNL Target] implementación

Se requieren varios pasos al implementar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T). El proceso varía en función de si implementa A4T con la variable [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) o con at.js.

## ![Distintivo del SDK web de Adobe Experience Platform](/help/main/assets/platform.png) Pasos de implementación de un SDK web de Adobe Experience Platform {#platform}

En las secciones siguientes se describen los pasos necesarios para implementar esta integración en el sitio si tiene pensado utilizar el SDK web de Platform:

### Paso 1: Solicitar aprovisionamiento para [!DNL Analytics] y [!DNL Target]

Antes de implementar A4T, debe estar aprovisionado para [!DNL Analytics] y [!DNL Target]. [Utilice este formulario para solicitar el aprovisionamiento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] in [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Crear una configuración de Edge

Creación de una configuración de Edge con [!DNL Adobe Experience Platform] uso de la herramienta de configuración edge. Configure las variables [Creación y configuración de flujos de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

### Paso 4: Instalación y configuración del SDK web de Platform

Para empezar a enviar [!DNL Target] experiencias y para aplicar [!DNL Analytics] para fines de seguimiento y análisis, [Instalar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) y [configurar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) el SDK web de Platform en las páginas del sitio.

### Paso 5: Habilitar las opciones para usar A4T

En el [!DNL Target] IU, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** y, a continuación, elija **[!UICONTROL Select per activity]** o **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** permite elegir entre [!DNL Target] y [!DNL Analytics] al crear cada actividad.
* **[!UICONTROL Adobe Analytics]** conjuntos [!DNL Analytics] como fuente de informes para todas las actividades que cree.

## ![Distintivo de at.js](/help/main/assets/atjs.png) Pasos de implementación para una implementación de at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar at.js:

### Paso 1: Solicitar el aprovisionamiento para Analytics y Target

Después de la implementación [!DNL Analytics] como fuente de informes para [!DNL Target], debe estar aprovisionado para [!DNL Analytics] y [!DNL Target]. [Utilice este formulario para solicitar el aprovisionamiento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear un [!DNL Analytics]actividad basada en en en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a los usuarios en [!DNL Adobe Experience Cloud] soluciones. Implemente o migre a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementación del servicio de ID de Experience Cloud para Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) en el *Servicio de ID de visitante de Experience Cloud* documentación.

### Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Implemente o migre a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Información general sobre la implementación de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) en el *Guía de implementación de Analytics*.

Para ver una migración, consulte [Migración a AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) en el *Guía de implementación de Analytics*.

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

La configuración predeterminada para [!DNL Target] y [!DNL Analytics] La integración de, desde una perspectiva de implementación, es utilizar el SDID que se pasa desde la página para unir el [!DNL Target] y [!DNL Analytics] solicitar juntos en el backend automáticamente.

Puede controlar cómo y cuándo enviar datos de análisis relacionados con [!DNL Target] hasta [!DNL Analytics] para fines de informes. Si no desea adherirse a la configuración predeterminada de tener [!DNL Target] y [!DNL Analytics] unir automáticamente los datos de Analytics mediante el SDID, establecido **analyticsLogging = client_side** mediante **window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js tiene **analyticsLogging: &quot;client_side&quot;** enviado dentro de [!DNL Target] y se devuelve una carga útil de analytics por cada solicitud. Cuando se configura esta opción, el formato de la carga útil que se devuelve es el siguiente:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La carga útil se puede reenviar a Analytics a través de la variable [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para las actividades de Asignación automática y Segmentación automática, también debe reenviar el sessionId. Para obtener más información, consulte [Creación de informes en Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} en el *SDK para Adobe Target* guía.

Si no desea una configuración global y prefiere un método bajo demanda, utilice la función at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} al pasar **analyticsLogging: &quot;client_side&quot;**. La carga útil de Analytics solo se devuelve para esta llamada y el [!DNL Target] backend no reenvía la carga útil a [!DNL Analytics]. Al llevar a cabo este enfoque, cada at.js [!DNL Target] La solicitud de devuelve la carga útil de forma predeterminada, pero solo cuando se desea y se especifica.

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

La carga útil se puede reenviar a [!DNL Analytics] a través de [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Paso 8: Validar la implementación {#step8}

Cargue las páginas después de actualizar las bibliotecas JavaScript para confirmar que la variable `mboxMCSDID` valores de parámetro en [!DNL Target] las llamadas coinciden con `sdid` valor de parámetro en [!DNL Analytics] llamada de vista de página.

SPA Es especialmente importante confirmar que estos valores coinciden en Aplicaciones de una sola página () en las que el orden de las llamadas no siempre es predecible.

>[!NOTE]
>
>Se requiere la coincidencia de estos valores para que A4T funcione correctamente.

### Paso 9 (opcional): Eliminar el código de integración anterior

Adobe recomienda eliminar la integración anterior para simplificar la implementación y eliminar la necesidad de resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

### Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

Entrada [!DNL Target], haga clic en **[!UICONTROL Administration > Reporting]** y elija **[!UICONTROL Select per activity]** o **[!UICONTROL Adobe Analytics]** para activar las opciones.

* **[!UICONTROL Select per activity]** permite elegir entre [!DNL Target] y [!DNL Analytics] al crear cada actividad.
* **[!UICONTROL Adobe Analytics]** conjuntos [!DNL Analytics] como fuente de informes para todas las actividades que cree.


