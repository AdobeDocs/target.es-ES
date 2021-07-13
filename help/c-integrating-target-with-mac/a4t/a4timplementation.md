---
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes;at.js;atjs;sdk web de adobe experience platform;sdk web de aep;sdk web de plataforma
description: Siga los pasos necesarios para implementar las soluciones de Analytics for [!DNL Target] (A4T) in your Adobe [!DNL Target] y Adobe Analytics.
title: ¿Cómo implemento Analytics para [!DNL Target] (A4T)?
feature: 'Analytics for Target (A4T) '
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 25%

---

# Implementación de Analytics for[!DNL Target]

Se requieren varios pasos a la hora de implementar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T). El proceso varía en función de si se implementa A4T con [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) o con at.js.

## ![Distintivo del SDK web de Adobe Experience Platform ](/help/assets/platform.png) Pasos de implementación para una implementación del SDK web de Adobe Experience Platform {#platform}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar el SDK web de Platform:

### Paso 1: Solicitar aprovisionamiento para [!DNL Analytics] y [!DNL Target]

Antes de implementar A4T, debe aprovisionarse para [!DNL Analytics] y [!DNL Target]. [Rellene este formulario para solicitar el aprovisionamiento](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Crear una configuración de Edge

Cree una configuración de Edge utilizando [!DNL Adobe Experience Platform Launch] la herramienta de configuración de Edge. Configure los [[!DNL Analytics] and [!DNL Target] ajustes de configuración de edge](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Paso 4: Instalación y configuración del SDK web de Platform

Para comenzar a enviar [!DNL Target] experiencias y aplicar [!DNL Analytics] para fines de seguimiento y análisis, [Instale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) y [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) el SDK web de la plataforma en las páginas del sitio.

### Paso 5: Habilitar las opciones para utilizar A4T

En la interfaz de usuario de [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, elija **[!UICONTROL Seleccionar por actividad]** o **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]

## ![Pasos de ](/help/assets/atjs.png) implementación de at.js para una implementación de at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar at.js:

### Paso 1: Solicitud de aprovisionamiento para Analytics y Target

Después de implementar [!DNL Analytics] como fuente de informes para [!DNL Target], debe aprovisionarse para [!DNL Analytics] y [!DNL Target]. [Rellene este formulario para solicitar el aprovisionamiento](http://www.adobe.com/go/audiences).

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de [!DNL Adobe Experience Cloud]. Implemente o migre a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementación del servicio de ID de Experience Cloud para Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) en la documentación *Servicio de ID de visitante de Experience Cloud* .

### Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Implemente o migre a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Información general sobre la implementación de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) en la *Guía de implementación de Analytics*.

Para realizar una migración, consulte [Migración a AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) en la *Guía de implementación de Analytics*.

### Paso 5: Descargar y actualizar at.js

Implemente o migre a la versión requerida de at.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

### Paso 6: Host at.js

Si ha implementado anteriormente at.js, puede reemplazar el archivo existente por la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

### Paso 7: Haga referencia a at.js en todas las páginas del sitio {#step7}

Incluya at.js debajo de VisitorAPI.js ; para ello, agregue la línea de código siguiente dentro de la etiqueta de todas las páginas:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js debe cargarse antes que at.js. Si va a actualizar un archivo at.js existente, asegúrese de comprobar el orden de carga.

La configuración predeterminada para la integración [!DNL Target] y [!DNL Analytics], desde una perspectiva de implementación, es utilizar el SDID que se pasa desde la página para unir automáticamente la solicitud [!DNL Target] y [!DNL Analytics] en el backend.

Puede controlar cómo y cuándo enviar los datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] con fines de informes. Si no desea aceptar la configuración predeterminada de que [!DNL Target] y [!DNL Analytics] vinculen automáticamente los datos de análisis mediante el SDID, establezca **analyticsLogging = client_side** mediante **window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js tiene **analyticsLogging: &quot;client_side&quot;** enviado dentro de las solicitudes [!DNL Target] y se devuelve una carga útil de Analytics para cada solicitud. Cuando se configura esta opción, el formato de la carga útil que se devuelve es el siguiente:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

La carga útil se puede reenviar a Analytics a través de la [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para las actividades de asignación automática y segmentación automática, también debe reenviar el sessionId. Para obtener más información, consulte [Informes de Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) en la guía *SDK para Adobe Target*.

Si no desea una configuración global y prefiere un método bajo demanda, utilice la función at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) pasando **analyticsLogging: &quot;client_side&quot;**. La carga útil de Analytics solo se devuelve para esta llamada y el back-end [!DNL Target] no reenvía la carga útil a [!DNL Analytics]. Al seguir este método, cada solicitud [!DNL Target] at.js devuelve la carga útil de forma predeterminada, pero solo cuando se desea y se especifica.

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

La carga útil se puede reenviar a [!DNL Analytics] a través de la [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Paso 8: Validar la implementación {#step8}

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro `mboxMCSDID`[!DNL Target] en las llamadas de coinciden con el valor del parámetro `sdid`[!DNL Analytics] en la llamada de vista de página de 

Es especialmente importante confirmar que estos valores coinciden en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

>[!NOTE]
>
>Es necesario que estos valores coincidan para que A4T funcione correctamente.

### Paso 9 (opcional): Eliminar el código de integración anterior

Adobe recomienda eliminar la integración anterior para simplificar la implementación y eliminar la necesidad de resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

### Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En [!DNL Target], haga clic en **[!UICONTROL Administración > Compositor de experiencias visuales]** y elija **[!UICONTROL Seleccionar por actividad]** o **[!UICONTROL Adobe Analytics]** para habilitar las opciones.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]


