---
description: Información sobre la implementación de Adobe Target sin utilizar un administrador de etiquetas (Adobe Launch o Dynamic Tag Management).
keywords: confirmación de pedido;orderConfirmPage
seo-description: Información sobre la implementación de Adobe Target sin utilizar un administrador de etiquetas (Adobe Launch o Dynamic Tag Management).
seo-title: Implementación de Target sin un administrador de etiquetas
solution: Target
subtopic: Primeros pasos
title: Implementación de Target sin un administrador de etiquetas
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: a9779c434899e21af3167f2471cf57c76709a242

---


# Implementación de Target sin un administrador de etiquetas{#implement-target-without-a-tag-manager}

Información sobre la implementación de [!DNL Adobe Target] sin utilizar un administrador de etiquetas (Adobe Launch o Dynamic Tag Management).

## Implementación de Target sin un administrador de etiquetas {#topic_397FFA3D6918456BBE02A9FBE9537894}

Información sobre la implementación de Adobe Target sin utilizar un administrador de etiquetas (Adobe Launch o Dynamic Tag Management).

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) es el método preferido y actualizado para implementar Target y la biblioteca de at.js. La siguiente información no es aplicable cuando se utiliza Adobe Launch para implementar Target.

## Configuraciones de at.js {#concept_2FA0456607D04F82B0539C5BF5309812}

Información para definir varias configuraciones en la página Configuración de at.js.

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) es el método preferido y actualizado para implementar Target y la biblioteca de at.js. La siguiente información no es aplicable cuando se utiliza Adobe Launch para implementar Target.

>[!NOTE]
>
>En lugar de definir la configuración en la interfaz de usuario de Target Standard/Premium, puede anular la configuración de la biblioteca at.js o usar las API de REST. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

Para abrir la página [!UICONTROL Configuración]:

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]**.
1. Seleccione **[!UICONTROL at.js]** &gt; **[!UICONTROL Editar la configuración de at.js]**.

## Configuración de entrega de contenido {#section_118D290DFC444509AD8E4AE86C9D92C0}

Consulte con ClientCare antes de cambiar estas opciones de configuración. Son necesarias para la mayoría de las implementaciones.

| Configuración | Descripción |
|--- |--- |
| Crear automáticamente mbox global | Seleccione si quiere incrustar la llamada de mbox global en el archivo at.js para que se active automáticamente cada vez que se cargue la página.<br>Cambiar esta opción afecta a at.js y a mbox.js. |
| Nombre de mbox global | Seleccione un nombre para el mbox global. De forma predeterminada, este nombre es target-global-mbox.<br>Pueden utilizarse caracteres especiales, incluido el símbolo &amp;, en los nombres de mbox con at.js.<br>Cambiar esta opción afecta a at.js y a mbox.js. |

## Configuración avanzada {#section_33B697B77BA64A01B5939D7EC75231F2}

| Configuración | Descripción |
|--- |--- |
| Código de cliente | El código de cliente es una secuencia de caracteres específica del cliente que a menudo se requiere al usar las API de Target.<br>No se pueden modificar estas opciones de configuración. |
| ID de organización de IMS | Este ID vincula la implementación con su cuenta de [!DNL Adobe Experience Cloud].<br>No se pueden modificar estas opciones de configuración. |
| Duración del perfil | Esta opción determina durante cuánto tiempo se almacenan los perfiles de los visitantes. De forma predeterminada, los perfiles se almacenan durante dos semanas. Esto se puede aumentar a 90 días.<br>Para modificar la opción Duración del perfil, póngase en contacto con [ClientCare](https://helpx.adobe.com/contact/enterprise-support.ec.html). |
| Dominio x | Determina si el navegador define cookies en su propio dominio (cookies individuales), en el dominio de Target o en ambos.<br>Cambiar esta opción afecta a at.js y a mbox.js. |
| Tiempo de espera | Si [!DNL Target] no responde con contenido dentro del periodo definido, se agota el tiempo de espera de la llamada del servidor y se muestra el contenido predeterminado. Se siguen realizando llamadas adicionales durante la sesión del visitante. El valor predeterminado es de 5 segundos.<br>Cambiar esta opción afecta a at.js y a mbox.js.<br>La biblioteca de at.js utiliza la configuración de tiempo de espera de `XMLHttpRequest`. El tiempo de espera empieza cuando una solicitud se activa y se detiene cuando Target obtiene una respuesta del servidor. Para obtener más información, consulte [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) en la red de desarrolladores de Mozilla.<br>Si el tiempo de espera especificado se agota antes de recibir una respuesta, se mostrará el contenido predeterminado y el visitante se podrá contar como un participante de la actividad, ya que la recopilación de datos se realizará a partir del límite de [!DNL Target]. Si la solicitud alcanza el límite de [!DNL Target], se contará al visitante.<br>Considere los siguientes puntos a la hora de configurar el tiempo de espera:<ul><li>Si el valor es demasiado bajo, los usuarios podrían ver el contenido predeterminado la mayor parte del tiempo, aunque se cuente al visitante como un participante de la actividad.</li><li>Si el valor es demasiado alto, los visitantes podrían ver áreas negras en la página web o páginas en blanco si oculta el cuerpo durante periodos muy largos.</li></ul>Para comprender mejor cómo funcionan los tiempos de respuesta de mbox, consulte la ficha Red en las herramientas para desarrolladores de su navegador. También puede utilizar herramientas de supervisión del rendimiento web de terceros, como Catchpoint.<br>**Nota:** Las características de [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) garantizan que [!DNL Target] no tenga que esperar a la respuesta de la API del visitante durante demasiado tiempo. Esta configuración y la configuración Tiempo de espera para at.js descrita no se afectan entre sí. |
| Compatibilidad con navegadores anteriores | **Nota:** La opción Compatibilidad con exploradores anteriores está disponible en la versión at.js 0.9.3 y anteriores. Esta opción se ha eliminado de la versión 0.9.4 de at.js. Para saber cuáles con los exploradores compatibles con at.js, consulte [Exploradores compatibles](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)<br>Los navegadores anteriores son navegadores más viejos que no admiten completamente CORS (Uso compartido de recursos de origen cruzado). Algunos de estos navegadores son: Internet Explorer antes de la versión 11 y Safari versión 6 y anteriores. Si está deshabilitada la Compatibilidad con navegadores anteriores, Target no entrega contenido ni cuenta los visitantes en informes en estos navegadores. Si esta opción está habilitada, se recomienda efectuar un control de calidad en todos los navegadores anteriores para garantizar una buena experiencia del cliente. |

## Configuración de código   {#section_D41C905D0F8149949F525C85F2CCFF7F}

| Configuración | Descripción |
|--- |--- |
| Encabezado de la biblioteca | Añada código de JavaScript personalizado para incluirlo en la parte superior de la biblioteca. |
| Pie de página de la biblioteca | Añada código de JavaScript personalizado para incluirlo en la parte inferior de la biblioteca. |

## Descargar at.js{#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instrucciones para descargar la biblioteca utilizando la interfaz de Target o la API de descarga.

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) es el método preferido y actualizado para implementar Target y la biblioteca de at.js. La siguiente información no es aplicable cuando se utiliza Adobe Launch para implementar Target.

>[!IMPORTANT]
>
>El equipo de Target mantiene solo dos versiones de [!DNL at.js]: la actual y la penúltima. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

## Descargar at.js desde la interfaz de Target {#section_1F5EE401C2314338910FC57F9592894E}

Para descargar [!DNL at.js] desde la interfaz de [!DNL Target]:

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]**.
1. Seleccione **[!UICONTROL at.js]**.
1. Haga clic en **[!UICONTROL Descargar at.js]**.

## Descargar at.js con la API de descarga de Target {#section_C0D9D2A9068144708D08526BA5CA10D0}

Para descargar [!DNL at.js] con la API

1. Obtenga el código de cliente.

   El código de cliente se encuentra disponible en la parte superior de la página **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]** &gt; **[!UICONTROL Editar la configuración de at.js]** en la página de la interfaz [!DNL Target].

1. Obtenga su número de administrador.

   Cargue esta dirección URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace `client code` with the client code from Step 1.

   El resultado de cargar esta dirección URL debería parecerse al siguiente ejemplo:

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   En este ejemplo, “6” es el número del administrador.

1. Descargar [!DNL at.js].

   Cargue esta dirección URL con la siguiente estructura:

   ```
   https://admin<varname>admin number</varname>>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code </varname>version=<version number>
   ```

   * Replace `admin number` with your admin number.
   * Replace `client code` with the client code from Step 1.
   * Replace `version number` with the desired at.js version number (for example, 2.2).
   >[!IMPORTANT]
   >
   >El equipo de Target mantiene solo dos versiones de [!DNL at.js]: la actual y la penúltima. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

   Al cargar esta dirección URL, se inicia la descarga del archivo [!DNL at.js] personalizado.

## Implementación de at.js {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js debe implementarse en el elemento `<head>` de cada página de su sitio web.

Una implementación típica de Target que no utiliza un administrador de etiquetas como [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) o [Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) tiene este aspecto:

```
<!doctype html> 
<html> 
 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head> 
 
<body> 
    The default content of the page 
</body> 
 
</html>
```

Tenga en cuenta las siguientes notas importantes:

* Se debe utilizar el tipo de documento HTML5 (por ejemplo, `<!doctype html>`). Los tipos de documentos no admitidos o anteriores pueden hacer que Target no pueda realizar una solicitud.
* Conexión previa y Recuperación previa son opciones que pueden ayudar a que sus páginas web se carguen más rápido. Si usa estas configuraciones, asegúrese de reemplazar `<client code>` con su propio código de cliente, que puede obtener desde la página **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]** &gt; **[!UICONTROL Editar configuración de at.js]**.
* Si tiene una capa de datos es óptimo definir la mayor cantidad posible en el `<head>` de sus páginas antes de que se cargue at.js. Esta ubicación proporciona la máxima capacidad para aprovechar esta información en Target para personalización.
* Las funciones especiales de Target, como `targetPageParams()`, `targetPageParamsAll()`, proveedores de datos y `targetGlobalSettings()` deben definirse después de la capa de datos y antes de que at.js cargue. Alternativamente, se podrían guardar en la sección [!UICONTROL Encabezado de biblioteca] de la página [!UICONTROL Editar configuración de at.js] y guardarse como parte de la propia biblioteca de at.js. Para obtener más información sobre estas funciones, consulte   [Funciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* Si usa las bibliotecas de ayuda de JavaScript, como jQuery, inclúyalas antes de Target para poder aprovechar su sintaxis y sus métodos al crear experiencias de Target.
* Incluya at.js en el `<head>` de sus páginas.

## Seguimiento de conversiones {#task_E85D2F64FEB84201A594F2288FABF053}

El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.

<!-- 

ov/t_create_orderconfirm-page-mbox-atjs.xml

 -->

>[!NOTE]
>
>Si los usuarios realizan compras en su sitio web, le recomendamos que implemente un mbox de confirmación de pedido aunque use los informes de Analytics para Target (A4T).

1. En la página de detalles del pedido, inserte el script de mbox siguiendo el modelo que aparece a continuación.
1. Reemplace las PALABRAS EN MAYÚSCULAS por valores dinámicos o estáticos del catálogo.

   >[!NOTE]
   >
   >Utilice la delimitación por comas para separar varios ID de producto.

   **Consejo:** También puede pasar información de pedidos a cualquier mbox (no necesita llamarse `orderConfirmPage`). De igual modo, es posible pasar información de pedido a varios mbox dentro de la misma campaña.

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

El mbox de confirmación de pedido utiliza los siguientes parámetros:

| Parámetro | Descripción |
|--- |--- |
| orderId | Valor único para identificar un pedido de recuento de conversión.<br>El `orderId` debe ser único. Los pedidos duplicados se ignoran en los informes. |
| orderTotal | Valor monetario de la compra.<br>No pase el símbolo de moneda. Use un punto (no una coma) para indicar valores decimales. |
| productPurchasedId (opcional) | Lista de ID de productos comprados en el pedido, separados por comas.<br>Estos ID de productos se muestran en el informe de auditoría para admitir un análisis de informe adicional. |