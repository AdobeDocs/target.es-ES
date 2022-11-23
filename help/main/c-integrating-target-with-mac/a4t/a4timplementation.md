---
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes;at.js;atjs;sdk web de adobe experience platform;sdk web de aep;sdk web de plataforma
description: Siga los pasos necesarios para implementar Analytics para [!DNL Target] (A4T) en el Adobe [!DNL Target] y soluciones de Adobe Analytics.
title: ¿Cómo implemento Analytics para [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 231cf7972b7343e02245d12ea9380df8d4b125da
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 24%

---

# Implementación de Analytics for [!DNL Target]

Se requieren varios pasos al implementar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T). El proceso varía en función de si se implementa A4T con la variable [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) o con at.js.

## ![Distintivo del SDK web de Adobe Experience Platform](/help/main/assets/platform.png) Pasos de implementación para una implementación del SDK web de Adobe Experience Platform {#platform}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar el SDK web de Platform:

### Paso 1: Solicitar aprovisionamiento para [!DNL Analytics] y [!DNL Target]

Antes de implementar A4T, debe aprovisionarse para [!DNL Analytics] y [!DNL Target]. [Rellene este formulario para solicitar el aprovisionamiento](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una actividad basada en [!DNL Analytics] en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Crear una configuración de Edge

Crear una configuración de Edge usando [!DNL Adobe Experience Platform] con la herramienta de configuración de edge. Configure las variables [[!DNL Analytics] and [!DNL Target] configuración de edge](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Paso 4: Instalación y configuración del SDK web de Platform

Para empezar a entregar [!DNL Target] experiencias y aplicar [!DNL Analytics] con fines de seguimiento y análisis, [Instalar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) y [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) el SDK web de Platform en las páginas del sitio.

### Paso 5: Habilitar las opciones para utilizar A4T

En el [!DNL Target] IU, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]**, elija **[!UICONTROL Seleccionar por actividad]** o **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]

## ![Distintivo de at.js](/help/main/assets/atjs.png) Pasos de implementación para una implementación de at.js{#section_73961BAD5BB4430A95E073DE5C026277}

Las secciones siguientes describen los pasos necesarios para implementar esta integración en su sitio si planea utilizar at.js:

### Paso 1: Solicitud de aprovisionamiento para Analytics y Target

Después de la implementación [!DNL Analytics] como fuente de informes para [!DNL Target], debe estar aprovisionado para [!DNL Analytics] y [!DNL Target]. [Utilice este formulario para solicitar el aprovisionamiento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear una [!DNL Analytics]actividad basada en [!DNL Target]. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de [!DNL Adobe Experience Cloud]. Implemente o migre a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementación del servicio de ID de Experience Cloud para Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) en el *Servicio de ID de visitante Experience Cloud* documentación.

### Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Implemente o migre a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Información general sobre la implementación de JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) en el *Guía de implementación de Analytics*.

Para ver una migración, consulte [Migración a AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) en el *Guía de implementación de Analytics*.

### Paso 5: Descargar y actualizar at.js

Implemente o migre a la versión requerida de at.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Paso 6: Host at.js

Si ha implementado anteriormente at.js, puede reemplazar el archivo existente por la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

### Paso 7: Haga referencia a at.js en todas las páginas del sitio {#step7}

Incluya at.js debajo de VisitorAPI.js ; para ello, agregue la línea de código siguiente dentro de la etiqueta de todas las páginas:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js debe cargarse antes que at.js. Si va a actualizar un archivo at.js existente, asegúrese de comprobar el orden de carga.

La configuración predeterminada para [!DNL Target] y [!DNL Analytics] , desde una perspectiva de implementación, es utilizar el SDID que se pasa desde la página para unir [!DNL Target] y [!DNL Analytics] solicite conjuntamente en el backend automáticamente.

Puede controlar cómo y cuándo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] a efectos de la elaboración de informes. Si no desea utilizar la configuración predeterminada de [!DNL Target] y [!DNL Analytics] vincular automáticamente los datos de análisis mediante el SDID, establezca **analyticsLogging = client_side** via **window.targetGlobalSettings**. Nota: Las versiones anteriores a 2.1 no son compatibles con este método.

Por ejemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Esta configuración tiene un efecto global, lo que significa que cada llamada realizada por at.js tiene **analyticsLogging: &quot;client_side&quot;** enviado dentro de la variable [!DNL Target] se devuelven solicitudes y una carga útil de analytics para cada solicitud. Cuando se configura esta opción, el formato de la carga útil que se devuelve es el siguiente:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A continuación, la carga útil se puede reenviar a Analytics mediante el complemento [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para las actividades de asignación automática y segmentación automática, también debe reenviar el sessionId. Para obtener más información, consulte [Creación de informes en Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} en la sección *SDK para Adobe Target* guía.

Si no desea una configuración global y prefiere un método bajo demanda, utilice la función at.js [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank} pasando **analyticsLogging: &quot;client_side&quot;**. La carga útil de Analytics solo se devuelve para esta llamada y la variable [!DNL Target] backend no reenvía la carga útil a [!DNL Analytics]. Al seguir este enfoque, cada at.js [!DNL Target] de forma predeterminada, devuelve la carga útil, pero solo cuando se desea y se especifica.

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

La carga útil se puede reenviar a [!DNL Analytics] a través de la variable [API de inserción de datos](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Paso 8: Validar la implementación {#step8}

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro `mboxMCSDID`[!DNL Target] en las llamadas de coinciden con el valor del parámetro `sdid`[!DNL Analytics] en la llamada de vista de página de 

Es especialmente importante confirmar que estos valores coinciden en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

>[!NOTE]
>
>Es necesario que estos valores coincidan para que A4T funcione correctamente.

### Paso 9 (opcional): Eliminar el código de integración anterior

Adobe recomienda eliminar la integración anterior para simplificar la implementación y eliminar la necesidad de resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

### Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En [!DNL Target], haga clic en **[!UICONTROL Administración > Informes]** y elija **[!UICONTROL Seleccionar por actividad]** o **[!UICONTROL Adobe Analytics]** para activar las opciones.

* **[!UICONTROL La opción Seleccionar por actividad permite elegir entre y a la hora de crear cada actividad.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL La opción Adobe establece Analytics como fuente de informes para todas las actividades que cree.]**[!DNL Analytics]


