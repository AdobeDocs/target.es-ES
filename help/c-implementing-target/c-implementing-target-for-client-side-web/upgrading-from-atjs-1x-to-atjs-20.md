---
description: Actualización desde at. js 1. x a at. js 2. x
keywords: versiones de at.js;versiones de at.js;aplicación de una sola página;spa
seo-description: Información detallada sobre la actualización de Adobe Target at.js 1.x a at.js versión 2.0.0
seo-title: 'Actualización de Adobe Target at.js versión 1.x a at.js versión 2.0.0 '
solution: Target
subtopic: Primeros pasos
title: Actualización desde at. js 1. x a at. js 2. x
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 6d3d8468dc65fc350dcf7d669039fae79015455d

---


# Actualización desde at. js 1. x a at. js 2. x {#upgrading-from-atjs-1x-to-atjs-200}

La versión más reciente de at. js proporciona [!DNL Adobe Target] conjuntos de funciones enriquecidos que equipan su negocio para ejecutar personalización en tecnologías de lado de cliente de próxima generación. Esta nueva versión se centra en actualizar at.js para tener interacciones armoniosas con aplicaciones de una sola página (SPA).

Estos son algunos beneficios de utilizar at. js 2. x que no están disponibles en versiones anteriores:

* La capacidad de almacenar en caché todas las ofertas al cargar la página para reducir el número de llamadas al servidor a una sola llamada.
* Importante mejora de las experiencias de los usuarios finales en su sitio porque las ofertas se muestran inmediatamente a través de la caché sin ningún tiempo de retraso que introducen las llamadas tradicionales al servidor.
* Una sencilla línea de código y configuración de desarrollador único para permitir que sus especialistas en marketing creen y ejecuten actividades A/B y XT a través del VEC en sus SPA.

## Diagramas del sistema at. js 2. x

Los siguientes diagramas le ayudan a comprender el flujo de trabajo de at. js 2. x con vistas y cómo esto mejora la integración de SPA. Para obtener una mejor introducción a los conceptos utilizados en at. js 2. x, consulte [Implementación de aplicación de una sola página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Flujo de Target con at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| La llamada | Detalles |
| --- | --- |
| 1 | La llamada devuelve el [!DNL Experience Cloud ID] si el usuario se autentica, y otra llamada sincroniza el ID del cliente. |
| 2 | La biblioteca de at.js carga de forma sincronizada y oculta el cuerpo del documento.at.js <br> también se puede cargar de manera asíncrona con una opción de fragmento de ocultamiento previo implementado en la página. |
| 3 | Se solicita una carga de página que incluye todos los parámetros configurados (MCID, SDID y el ID del cliente). |
| 4 | Se ejecutan los scripts de perfiles y se incluyen en el Almacenamiento de perfiles. El Almacenamiento solicita audiencias de la Biblioteca de audiencias que cumplan los requisitos (por ejemplo, audiencias compartidas de Adobe Analytics, Gestión de público, etc.).<br>Se envían los atributos del cliente al Almacenamiento de perfiles en un procesamiento de lotes. |
| 5 | Según los parámetros de la solicitud de la URL y los datos de perfil, [!DNL Target] decide qué actividades y experiencias vuelven al visitante para la página actual y las vistas futuras. |
| 6 | El contenido dirigido se devuelve a la página, incluyendo, de manera opcional, los valores de perfil para una personalización adicional.<br>El contenido dirigido se muestra en la página actual lo más rápido posible y sin parpadeo del contenido predeterminado.<br>Contenido dirigido para vistas que se muestran como resultado de acciones del usuario en una SPA almacenada en caché en el explorador, de modo que se pueda aplicar instantáneamente sin una llamada al servidor adicional cuando se activan las vistas `triggerView()`. |
| 7 | Se envían los datos de Analytics a los servidores de recopilación de datos. |
| 8 | Se comparan los datos de Target con los datos de Analytics mediante el SDID y se procesan en el almacén de informes de Analytics.<br>Por lo tanto, los datos de Analytics se pueden visualizar tanto en Analytics como en Target mediante los informes de Analytics for Target (A4T). |

Ahora, independientemente de que se implemente `triggerView()` en la SPA, las vistas y acciones se recuperan de la caché y se muestran al usuario sin una llamada al servidor. `triggerView()` también realiza una solicitud de notificaciones al back-end [!DNL Target] para aumentar y registrar los recuentos de impresión.

![Flujo de Target de at. js 2. x activgerview](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| La llamada | Detalles |
| --- | --- |
| 1 | En la SPA, se llama a `triggerView()` para procesar la vista y aplicar acciones para modificar los elementos visuales. |
| 2 | El contenido dirigido para la vista se lee desde la caché. |
| 3 | El contenido dirigido se muestra lo más rápido posible y sin parpadeo del contenido predeterminado. |
| 4 | La solicitud de notificación se envía al Almacenamiento de perfiles de [!DNL Target] para contar al visitante en la actividad e incrementar las métricas. |
| 5 | Los datos de Analytics se envían a los servidores de recopilación de datos. |
| 6 | Se comparan los datos de Target con los datos de Analytics mediante el SDID y se procesan en el almacén de informes de Analytics. Por lo tanto, los datos de Analytics se pueden visualizar tanto en Analytics como en Target mediante los informes de A4T. |

## Implementar at. js 2. x {#deploy-atjs-200}

1. Implemente at. js 2. x [mediante](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) la extensión Adobe Launch.

   >[!NOTE]
   >
   > La implementación de at. js con Adobe Launch es el método preferido.

   O

   Descargue manualmente at. js 2. x mediante la interfaz de usuario de Target e impleméntelo usando [el método de su elección](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## Funciones obsoletas de at.js

Existen varias funciones que se han quedado obsoletas en at. js 2. x.

>[!IMPORTANT]
>
>Si se siguen utilizando estas funciones en desuso en el sitio cuando se implementa at. js 2. x, verá advertencias de consola. El método recomendado al actualizar es probar la implementación de at. js 2. x en un entorno de ensayo y asegurarse de avanzar por cada advertencia que se haya registrado en la consola y traducir las funciones obsoletas a nuevas funciones introducidas en at. js 2. x.

Puede encontrar las funciones obsoletas y sus equivalentes a continuación. Para ver una lista completa de las funciones, consulte [Funciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>at. js 2. x ya no oculta automáticamente `mboxDefault` los elementos marcados. Por lo tanto, los clientes tendrán que ajustar manualmente la lógica de ocultación previa en el sitio o a través de un administrador de etiquetas.

### mboxCreate(mbox,params)

**Descripción**:

Ejecuta una solicitud y aplica la oferta al DIV más cercano con el nombre de clase `mboxDefault`.

**Ejemplo:**

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**Equivalente de at. js 2. x**

`getOffer()` y `applyOffer()` son una alternativa a `mboxCreate(mbox, params)`.

**Ejemplo:**

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() y mboxUpdate()

**Descripción**:

Crea una asignación interna entre un elemento y un nombre de mbox, pero no ejecuta la solicitud. Se utiliza junto con `mboxUpdate()`, que ejecuta la solicitud y aplica la oferta al elemento identificado por ID de nodo en `mboxDefine()`. También se puede usar para actualizar un mbox iniciado por `mboxCreate`.

**Ejemplo:**

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**Equivalente de at. js 2. x**:

Una alternativa a `mboxDefine()` y `mboxUpdate` es `getOffer()` y `applyOffer()`, con la opción de selector utilizada en `applyOffer()`. Este método permite asignar la oferta a un elemento mediante cualquier selector de CSS, no solo a uno con un ID.

**Ejemplo:**

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**Descripción**:

Ofrece una forma estándar de registrar una extensión determinada.

Esto ya no se admite y no debe usarse.

## Resumen de las funciones de at.js obsoletas, nuevas y admitidas en 2.0

| Método | Compatible? | nueva? | Obsoleto?<br>(Se muestra el contenido predeterminado) |
| --- | --- | --- | --- |
| `getOffer()` | Sí |  |  |
| `getOffers()` |  | Sí |  |
| `applyOffer()` | Sí |  |  |
| `applyOffers()` |  | Sí |  |
| `triggerView()` |  | Sí |  |
| `trackEvent()` | Sí |  |  |
| `mboxCreate()` |  |  | Sí |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | Sí |
| `targetGlobalSettings()` | Sí |  |  |
| `Data Providers` | Sí |  |  |
| `targetPageParams()` | Sí |  |  |
| `targetPageParamsAll()` | Sí |  |  |
| `registerExtension()` |  |  | Sí |
| `At.js Custom Events` | Sí |  |  |

## Limitaciones y llamadas

Tenga en cuenta las siguientes limitaciones y llamadas:

**Seguimiento de conversiones**

Los clientes que utilizan `mboxCreate()` para el seguimiento de conversiones deben utilizar `trackEvent()` o `getOffer()`.

**Entrega de ofertas**

Los clientes que no reemplacen `mboxCreate()` por `getOffer()` o `applyOffer()` se arriesgan a que no se entreguen las ofertas.

**Puede usar at. js 2. x en algunas páginas mientras at. js 1.*x*o mbox.js se encuentran en otras páginas?**

Sí, el perfil del visitante se conserva en todas las páginas que utilizan distintas versiones y bibliotecas. El formato de la cookie es el mismo.

**Adobe Experience Cloud Debugger no es totalmente compatible con at. js 2. x**

[!DNL Adobe Experience Cloud Debugger][!UICONROL Las funciones de ficha] Resumen y [!UICONTROL Deshabilitar y las herramientas de registro] de consola son compatibles, pero las solicitudes de red y mboxtrace no son compatibles con at. js 2. x.

Esto se debe a que en at. js 2. x se envía una carga útil JSON en lugar de pares clave-valor. Para inspeccionar solicitudes [!DNL Target], filtre la pestaña [!UICONTROL Red] de las herramientas para desarrolladores del explorador a “entrega”, “`tt.omtrdc.net`” o su código de cliente. Los datos de seguimiento se pueden seguir inspeccionando utilizando el parámetro de cadena de consulta y el token de autorización. Para obtener más información, consulte [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md).

**Nuevo uso de API en at. js 2. x**

at. js 2. x usa una nueva API, que llamamos la API de envío. Para depurar si at.js llama al servidor [!DNL Target] Edge correctamente, puede filtrar la pestaña Red de las herramientas para desarrolladores del explorador en “entrega”, “`tt.omtrdc.net`” o código de cliente. También notará que [!DNL Target] envía una carga útil JSON en lugar de pares clave-valor.

**Mbox Global de Target ya no se utiliza**.

En at. js 2. x, ya no ve «`target-global-mbox`» visiblemente en las llamadas de red. En su lugar, hemos sustituido la sintaxis “`target-global-mbox`” por “`execute > pageLoad`” en la carga útil JSON enviado por los servidores [!DNL Target] como se ve a continuación:

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

fundamentalmente, el concepto de mbox global se introdujo para hacer saber a [!DNL Target] si se recuperarán las ofertas y el contenido durante la carga de página. Esto lo hemos hecho más explícito en la versión más reciente.

**¿Sigue siendo relevante el nombre de mbox global en at.js?**

Los clientes pueden especificar un nombre de mbox global mediante [!UICONTROL Target &gt; Configuración &gt; Implementación &gt; Editar la configuración de at.js]. Este ajuste lo utilizan los servidores [!DNL Target] Edge para traducir Ejecutar &gt; pageLoad al nombre de mbox global que aparece en la interfaz de usuario [!DNL Target]. Esto permite a los clientes seguir utilizando API del lado del servidor, el compositor basado en formularios, los comandos de perfil y crear audiencias utilizando el nombre de mbox global. Le recomendamos encarecidamente que verifique que se haya configurado el mismo nombre de mbox global en la página [!UICONTROL Configuración &gt; Preferencias], en caso de que tenga páginas con at.js 1.*x* o mbox.js como se muestra en las ilustraciones siguientes.

![Modificación del diálogo at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

y

![mbox global personalizado](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**¿Es necesario activar la configuración de mbox global de forma automática para at. js 2. x?**

En la mayoría de los casos, sí. Esta configuración indica a. js 2. x que active una solicitud a los servidores [!DNL Target] Edge al cargar la página. Este ajuste debería estar activado ya que mbox global se traduce para Ejecutar &gt; pageLoad, y si desea activar una solicitud al cargar la página.

**¿Seguirán funcionando las actividades existentes de VEC, aunque el nombre de mbox global de Target no se especifique desde at. js 2. x?**

Sí, porque Ejecutar &gt; pageLoad se trata en el backend [!DNL Target] como `target-global-mbox`.

**Si mis actividades basadas en formularios están dirigidas a`target-global-mbox`, ¿seguirán funcionando esas actividades?**

Sí, porque Ejecutar &gt; pageLoad se trata en los servidores [!DNL Target] Edge como `target-global-mbox`.

**Configuración admitida y no admitida en at. js 2. x**

| Configuración | Compatible? |
| --- | --- |
| Dominio x | No |
| Creación automática de mbox global | Sí |
| Nombre de mbox global | Sí |

*No* se admite el **seguimiento entre dominios**

El seguimiento entre dominios permite ver sesiones en dos sitios relacionados, pero con distintos dominios, como una sola sesión. Puede crear una actividad de [!DNL Target] que abarque `siteA.com` y `siteB.com`, y que el visitante permanezca en la misma experiencia cuando se compartan dominios. Esta funcionalidad se vincula al comportamiento de cookies de origen y de terceros de Target.

En [!DNL Target], la cookie de terceros se almacena en `[CLIENTCODE].tt.omtrdc.net` y la cookie de origen en `clientdomain.com`. La primera solicitud devuelve encabezados de respuesta HTTP que intentan establecer cookies de terceros denominadas `mboxSession` y `mboxPC`, mientras se devuelve una solicitud de redirección con un parámetro adicional (`mboxXDomainCheck=true`). Si el navegador acepta cookies de terceros, la solicitud de redirección incluye dichas cookies y la oferta se devuelve. Este flujo de trabajo es posible porque utilizamos el método HTTP GET.

Sin embargo, en at. js 2. x, HTTP GET ya no se usa y en su lugar utilizamos HTTP POST. HTTP POST se utiliza a través de at.js para enviar cargas JSON a servidores Edge [!DNL Target]. Esto significa que la solicitud de redirección para comprobar si un explorador admite cookies de terceros se interrumpe. Esto se debe a que las solicitudes HTTP GET son transacciones idempotentes mientras que HTTP POST no es idempotente ni se debe repetir arbitrariamente. Por lo tanto, ya no se admite el seguimiento entre dominios en at. js 2. x.

**Se admite Crear automáticamente un mbox global**

Esta configuración indica a. js 2. x que active una solicitud a los servidores [!DNL Target] Edge durante la carga de página. Dado que el mbox global se traduce en ejecutar &gt; pageLoad, y este es interpretado por los servidores Edge de [!DNL Target], los clientes deben habilitarlo si desean activar una solicitud durante la carga de página.

**Se admite el nombre de mbox global**

Los clientes pueden especificar un nombre de mbox global mediante [!UICONTROL Target &gt; Configuración &gt; Implementación &gt; Editar la configuración de at.js]. Este ajuste lo utilizan los servidores Edge [!DNL Target] para representar ejecutar &gt; pageLoad en el nombre de mbox global introducido. Esto permite a los clientes seguir utilizando las API del servidor, el compositor basado en formularios, scripts de perfil y crear audiencias dirigidas al mbox global.

**¿Los eventos personalizados de at.js se aplican a`triggerView()`, o es solo para`applyOffer()`o`applyOffers()`?**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Sí, los eventos personalizados de at.js también son aplicables en `triggerView()`.

**Indica que cuando llama a`triggerView()`con`{“page” : “true”}`, envía una notificación al back-end de[!DNL Target]y aumenta la impresión. ¿También provoca que se ejecuten los scripts de perfil?**

Cuando se realiza una llamada de recuperación previa al back-end de [!DNL Target], se ejecutan los scripts de perfil. A partir de ahí, los datos de perfil afectados se cifran y se devuelven al cliente. Después de la invocación de `triggerView()` con `{"page": "true"}`, se envía una notificación junto con los datos de perfil cifrados. Es entonces cuando el back-end de [!DNL Target] descifra los datos de perfil y los almacena en las bases de datos.

**¿Es necesario agregar el código de ocultamiento previo antes de llamar a`triggerView()`para administrar el parpadeo?**

No, no es necesario agregar el código de ocultamiento previo antes de llamar a `triggerView()`. at. js 2. x administra la lógica de ocultamiento previo y parpadeo antes de que se muestre y se aplique la vista.

## Compatibilidad de at.js

Las tablas siguientes explican la compatibilidad de at.js 2.0.0 con diferentes tipos de actividades, integraciones, características y funciones de at.js.

### Tipos de actividades {#types}

| Tipo | Compatible? |
| --- | --- |
| Prueba A/B | Sí |
| Asignación automática | Sí |
| Segmentación automática | Sí |
| Segmentación de experiencias | Sí |
| Prueba multivariable | Sí |
| Personalización automatizada | Sí |
| Las actividades de | Sí |

>[!NOTE]
>
>Las actividades de segmentación automática se admiten a través de at. js 2. x y el VEC cuando se aplican todas las modificaciones al `Page Load Event`. Cuando se agregan modificaciones a vistas específicas, solo se admiten las actividades Prueba A/B, Asignar automáticamente y Segmentación de experiencias (XT).

### Integraciones {#integrations}

| Tipo | Compatible? |
| --- | --- |
| Analytics for Target (A4T) | Sí |
| Audiencias | Sí |
| Atributos del cliente | Sí |
| Fragmentos de experiencia de AEM | Sí |
| Extensión Adobe Launch | [Sí](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| Depurador | Sí |
| Auditor | Las reglas todavía no se han actualizado para at. js 2. x |
| Administrador dinámico de etiquetas (DTM) | Sí |
| Inclusión | No. La compatibilidad con el [RGPD](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) se admite en [la versión 2.1.0 de at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| Personalización mejorada AEM con tecnología de Adobe Target | No |

### Funciones

| Función | Compatible? |
| --- | --- |
| Dominio x | No |
| Propiedades/Espacios de trabajo | Sí |
| Vínculos de control de calidad | Sí |
| Compositor de experiencias basadas en formularios | Sí |
| Compositor de experiencias visuales (VEC) | Sí |
| Código personalizado | Sí |
| Tokens de respuesta | [Sí](#response-tokens) |
| Seguimiento de clics | Sí |
| Entrega de varias actividades | Sí |
| targetGlobalSettings | Sí (pero no x-dominio) |
| Métodos de at.js | Se admiten todas las opciones excepto <br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br> que muestran el contenido predeterminado. |

### Parámetros de cadena de consulta

| Parámetro | Compatible? |
| --- | --- |
| `?mboxDisable` | Sí |
| `?mboxDisable` | Sí |
| `?mboxTrace` | Sí |
| `?mboxSession` | No |
| `?mboxOverride.browserIp` | No |

## Tokens de respuesta {#response-tokens}

at.js 2.*x*, igual que at. js 1.*x*, utiliza el evento personalizado `at-request-succeeded` para los tokens de respuesta. Para obtener ejemplos de código con el evento `at-request-succeeded` personalizado, consulte [Tokens de respuesta](/help/administrating-target/response-tokens.md).

## Parámetros de at. js 1. x en la asignación de carga útil at. js 2. x {#payload-mapping}

Esta sección describe las asignaciones entre at. js 1.*x* y at. js 2. x.

Antes de profundizar en la asignación de parámetros, los puntos finales que utilizan las versiones de la biblioteca han cambiado:

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at. js 2. x - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

Otra diferencia importante es que:

* at.js 1.*x* : El código de cliente forma parte de la ruta
* at. js 2. x: El código de cliente se envía como parámetro de cadena de consulta, como:
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

Las siguientes secciones enumeran cada at. js 1.*x* parameter, its description, and the corresponding 2.0.0 JSON payload (, si corresponde):

### at_ property

(at.js 1.*x* parameter)

Se utiliza para [permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

(at.js 1.*x* parameter)

Altura de la ventana del explorador del visitante.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

(at.js 1.*x* parameter)

Ancho de la ventana del explorador del visitante.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### Browsertimeoffset

(at.js 1.*x* parameter)

Desplazamiento de zona horaria.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### Screenheight

(at.js 1.*x* parameter)

Altura de la pantalla del visitante.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### Screenwidth

(at.js 1.*x* parameter)

Ancho de la pantalla del visitante.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

(at.js 1.*x* parameter)

Profundidad de color de la pantalla del visitante.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

(at.js 1.*x* parameter)

Dominio de la página en la que se ejecuta la biblioteca de Target.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1.*x* parameter)

Las capacidades del procesador WEB GL del navegador. El mecanismo de detección de dispositivos lo utiliza para determinar si el dispositivo del visitante es un escritorio, iphone, dispositivo Android, etc.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### Mboxurl

(at.js 1.*x* parameter)

La dirección URL de la página.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### Mboxreferrer

(at.js 1.*x* parameter)

El referente de la página.

Carga útil JSON de at. js 2. x:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox (el nombre) es igual a mbox global

(at.js 1.*x* parameter)

La API de envío ya no tiene un concepto de mbox global. En la carga útil JSON debe utilizar `execute > pageLoad`.

Carga útil JSON de at. js 2. x:

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox (el nombre) *no* es igual al mbox global

(at.js 1.*x* parameter)

Para utilizar un nombre de mbox, páselo a `execute > mboxes`. Un mbox requiere un índice y un nombre.

Carga útil JSON de at. js 2. x:

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### Mboxid

(at.js 1.*x* parameter)

Ya no se utiliza.

### Mboxcount

(at.js 1.*x* parameter)

Ya no se utiliza.

### Mboxrid

(at.js 1.*x* parameter)

Solicitar ID utilizados por los sistemas descendentes para ayudar a depurar.

Carga útil JSON de at. js 2. x:

```
{
  "requestId": "2412234442342"
  ....
}
```

### Mboxtime

(at.js 1.*x* parameter)

Ya no se utiliza.

### mboxSession

(at.js 1.*x* parameter)

El ID de sesión se envía como parámetro de cadena de consulta (`sessionId`) al extremo de la API de envío.

### mboxPC

(at.js 1.*x* parameter)

El ID de TNT se pasa a `id > tntId`.

Carga útil JSON de at. js 2. x:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* parameter)

Se pasa el ID de visitante de Marketing Cloud a `id > marketingCloudVisitorId`.

Carga útil JSON de at. js 2. x:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst. aaaa. id y vst. aaaa. authstate

(at.js 1.*x* parameters)

Los ID de cliente se deben pasar a `id > customerIds`.

Carga útil JSON de at. js 2. x:

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1.*x* parameter)

ID de terceros de cliente utilizado para vincular distintos ID de Target.

Carga útil JSON de at. js 2. x:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### Mboxmcsdid

(at.js 1.*x* parameter)

SDID, también conocido como ID de datos suplementarios. Debe pasar `experienceCloud > analytics > supplementalDataId`a.

Carga útil JSON de at. js 2. x:

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst. trk

(at.js 1.*x* parameter)

Servidor de seguimiento de Analytics. Debe pasar `experienceCloud > analytics > trackingServer`a.

Carga útil JSON de at. js 2. x:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst. trks

(at.js 1.*x* parameter)

Servidor de seguimiento de Analytics seguro. Debe pasar `experienceCloud > analytics > trackingServerSecure`a.

Carga útil JSON de at. js 2. x:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1.*x* parameter)

Sugerencia de ubicación de Audience Manager. Debe pasar `experienceCloud > audienceManager > locationHint`a.

Carga útil JSON de at. js 2. x:

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1.*x* parameter)

Blob de Audience Manager. Debe pasar `experienceCloud > audienceManager > blob`a.

Carga útil JSON de at. js 2. x:

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### Mboxversion

(at.js 1.*x* parameter)

La versión se envía como parámetro de cadena de consulta a través del parámetro version.

## Vídeo de capacitación: Diagrama de arquitectura at. js 2. x

at. js 2. x mejora la compatibilidad de Adobe Target con los SPA e integra con otras soluciones de Experience Cloud. Este vídeo explica cómo se vincula todo.

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=spa)

Consulte [Explicación de cómo funciona at. js 2. x](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) para obtener más información.