---
keywords: implementar target;implementación;implementar at.js;administrador de etiquetas;decisiones en el dispositivo;en la toma de decisiones del dispositivo
description: Obtenga información sobre cómo especificar la configuración (detalles de la cuenta, métodos de implementación, etc.) para implementar la biblioteca Adobe [!DNL Target] at.js sin utilizar un administrador de etiquetas.
title: ¿Puedo implementar [!DNL Target] sin un Administrador de etiquetas?
feature: Implementación del lado del servidor
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '1687'
ht-degree: 53%

---

# Implementar [!DNL Target] sin un administrador de etiquetas

Información sobre la implementación de [!DNL Adobe Target] sin utilizar un administrador de etiquetas ([!DNL Adobe Experience Platform Launch]).

>[!NOTE]
>
>[Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) Launch es el método preferido para implementar Target y la biblioteca de at.js. La siguiente información no es aplicable cuando se utiliza el Platform launch de Adobe para implementar Target.

Para acceder a la página [!UICONTROL Implementación], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.

Puede especificar la siguiente configuración en esta página:

* Detalles de la cuenta
* Métodos de implementación
* API de perfil
* Herramientas de depuración
* Privacidad

>[!NOTE]
>
>En lugar de definir la configuración en la interfaz de usuario de Target Standard/Premium, puede anular la configuración de la biblioteca at.js o usar las API de REST. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Detalles de la cuenta

Puede ver los siguientes detalles de la cuenta. Estos ajustes no se pueden cambiar.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Código de cliente] | El código de cliente es una secuencia de caracteres específica del cliente que a menudo se requiere al usar las API de Target. |
| [!UICONTROL ID de organización de IMS] | Este ID vincula la implementación con su cuenta de [!DNL Adobe Experience Cloud]. |
| [!UICONTROL Toma de decisiones en el dispositivo] | Para activar la toma de decisiones en el dispositivo, deslice el conmutador a la posición &quot;activado&quot;.<br>La toma de decisiones en el dispositivo le permite almacenar en caché las campañas A/B y de Segmentación de experiencias (XT) en el servidor y realizar decisiones en la memoria con una latencia cercana a cero. Para obtener más información, consulte [Introducción a la toma de decisiones en el dispositivo](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) en la guía *Adobe Target SDK*. |
| [!UICONTROL Incluya en el artefacto todas las actividades cualificadas para la toma de decisiones en el dispositivo.] | (Condicional) Esta opción se muestra si habilita la toma de decisiones en el dispositivo.<br>Deslice la opción a la posición &quot;activada&quot; si desea que todas las actividades de Target activas que cumplen los requisitos para la toma de decisiones en el dispositivo se incluyan automáticamente en el artefacto.<br>Si deja esta opción desactivada, debe volver a crear y activar cualquier actividad de toma de decisiones en el dispositivo para que se incluya en el artefacto de reglas generadas. |

## Métodos de implementación

Se pueden configurar las siguientes opciones en el panel Métodos de implementación:

### Configuración global

>[!NOTE]
>
>Esta configuración se aplica a todas las bibliotecas [!DNL Target] .js. Después de realizar cambios en la sección Métodos de implementación , debe descargar la biblioteca y actualizarla en la implementación.

| Configuración | Descripción |
| --- | --- |
| Carga de página habilitada (Crear automáticamente mbox global) | Seleccione si quiere incrustar la llamada de mbox global en el archivo at.js para que se active automáticamente cada vez que se cargue la página. |
| Mbox global | Seleccione un nombre para el mbox global. De forma predeterminada, este nombre es target-global-mbox.<br>Pueden utilizarse caracteres especiales, incluido el símbolo &amp;, en los nombres de mbox con at.js. |
| Tiempo de espera (segundos) | Si [!DNL Target] no responde con contenido dentro del periodo definido, se agota el tiempo de espera de la llamada del servidor y se muestra el contenido predeterminado. Se siguen realizando llamadas adicionales durante la sesión del visitante. El valor predeterminado es de 5 segundos.<br>La biblioteca de at.js utiliza la configuración de tiempo de espera de `XMLHttpRequest`. El tiempo de espera empieza cuando una solicitud se activa y se detiene cuando [!DNL Target] obtiene una respuesta del servidor. Para obtener más información, consulte [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) en la red de desarrolladores de Mozilla.<br>Si el tiempo de espera especificado se agota antes de recibir una respuesta, se mostrará el contenido predeterminado y el visitante se podrá contar como un participante de la actividad, ya que la recopilación de datos se realizará a partir del límite de [!DNL Target]. Si la solicitud alcanza el límite de [!DNL Target], se contará al visitante.<br>Considere los siguientes puntos a la hora de configurar el tiempo de espera:<ul><li>Si el valor es demasiado bajo, los usuarios podrían ver el contenido predeterminado la mayor parte del tiempo, aunque se cuente al visitante como un participante de la actividad.</li><li>Si el valor es demasiado alto, los visitantes podrían ver áreas negras en la página web o páginas en blanco si oculta el cuerpo durante periodos muy largos.</li></ul>Para comprender mejor cómo funcionan los tiempos de respuesta de mbox, consulte la ficha Red en las herramientas para desarrolladores de su navegador. También puede utilizar herramientas de supervisión del rendimiento web de terceros, como Catchpoint.<br>**Nota:** Las características de [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) garantizan que [!DNL Target] no tenga que esperar a la respuesta de la API del visitante durante demasiado tiempo. Esta configuración y la configuración Tiempo de espera para at.js descrita no se afectan entre sí. |
| Duración del perfil | Esta opción determina durante cuánto tiempo se almacenan los perfiles de los visitantes. De forma predeterminada, los perfiles se almacenan durante dos semanas. Esta configuración se puede aumentar hasta 90 días.<br>Para modificar la opción Duración del perfil, póngase en contacto con [ClientCare](https://helpx.adobe.com/es/contact/enterprise-support.ec.html). |

### Método de implementación principal

>[!IMPORTANT]
>
>El equipo de Target es compatible con at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que está ejecutando una versión compatible.

Para descargar la versión de at.js deseada, haga clic en el botón **[!UICONTROL Download]** correspondiente.

Para editar la configuración de at.js, haga clic en **[!UICONTROL Editar]** junto a la versión de at.js que desee.

>[!IMPORTANT]
>
>Antes de cambiar esta configuración predeterminada, consulte con [Client Care](/help/cmp-resources-and-contact-information.md) para que no afecte a su implementación actual.

Además de la configuración explicada anteriormente, también están disponibles las siguientes configuraciones específicas de at.js :

| Configuración | Descripción |
|--- |--- |
| Encabezado de biblioteca personalizado | Añada código de JavaScript personalizado para incluirlo en la parte superior de la biblioteca. |
| Pie de página de biblioteca personalizado | Añada código de JavaScript personalizado para incluirlo en la parte inferior de la biblioteca. |

### API de perfil

Habilite o deshabilite la autenticación para actualizaciones en lote mediante API y genere un token de autenticación de perfil.

Para obtener más información, consulte [Configuración de la API del perfil](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### Herramientas de depuración

Genere un token de autorización para utilizar herramientas de depuración [!DNL Target] avanzadas. Haga clic en **[!UICONTROL Generar nuevo token de autenticación]**.

![Generar nuevo token de autenticación](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### Privacidad

Esta configuración le permite utilizar [!DNL Target] de conformidad con las leyes aplicables sobre privacidad de datos.

Elija la configuración que desee en la lista desplegable Proteger dirección IP del visitante :

* Confusión de último octeto
* Confusión de IP completa
* Ninguna

Para obtener más información, consulte  [Privacidad](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).

>[!NOTE]
>
>La opción Compatibilidad con navegadores anteriores estaba disponible en la versión 0.9.3 (y anteriores) de at.js . Esta opción se ha eliminado de la versión 0.9.4 de at.js. Para saber cuáles con los exploradores compatibles con at.js, consulte [Exploradores compatibles](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)<br>Los navegadores anteriores son navegadores más viejos que no admiten completamente CORS (Uso compartido de recursos de origen cruzado). Algunos de estos navegadores son: Internet Explorer antes de la versión 11 y Safari versión 6 y anteriores. Si se deshabilitaba la compatibilidad con navegadores anteriores, Target no ofrecía contenido ni contaba los visitantes en los informes de estos navegadores. Si esta opción está habilitada, se recomienda realizar un control de calidad en los exploradores más antiguos para garantizar una buena experiencia del cliente.

## Descargar at.js{#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instrucciones para descargar la biblioteca mediante la interfaz [!DNL Target] o la API de descarga.

>[!NOTE]
>
>* [Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) Launch es el método preferido para implementar Target y la biblioteca de at.js. La siguiente información no es aplicable cuando se utiliza el Platform launch de Adobe para implementar Target.
   >
   >
* El equipo de Target es compatible con at.js 1.*x* y at.js 2.*x*. Actualice a la actualización más reciente de cualquiera de las versiones principales de at.js para asegurarse de que está ejecutando una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).


### Descargar at.js mediante la interfaz [!DNL Target] {#section_1F5EE401C2314338910FC57F9592894E}

Para descargar [!DNL at.js] desde la interfaz de [!DNL Target]:

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.
1. En la sección [!UICONTROL Implementation methods] , haga clic en el botón **[!UICONTROL Download]** situado junto a la versión de at.js que desee.

### Descargar at.js con la [!DNL Target] API de descarga {#section_C0D9D2A9068144708D08526BA5CA10D0}

Para descargar [!DNL at.js] con la API

1. Obtenga el código de cliente.

   El código de cliente se encuentra disponible en la parte superior de la página **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** de la interfaz [!DNL Target].

1. Obtenga su número de administrador.

   Cargue esta dirección URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Sustituya `client code` por el código de cliente del paso 1.

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
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Sustituya `admin number` por su número de administrador.
   * Sustituya `client code` por el código de cliente del paso 1.
   * Sustituya `version number` por el número de versión de at.js deseado (por ejemplo, 2.2).

   >[!IMPORTANT]
   >
   >El equipo de Target mantiene solo dos versiones de [!DNL at.js]: la actual y la penúltima. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

   Al cargar esta dirección URL, se inicia la descarga del archivo [!DNL at.js] personalizado.

## Implementación de at.js {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js debe implementarse en el elemento `<head>` de cada página de su sitio web.

Una implementación típica de Target que no utiliza un administrador de etiquetas como [Adobe Platform launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) tiene este aspecto:

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
* Conexión previa y Recuperación previa son opciones que pueden ayudar a que sus páginas web se carguen más rápido. Si utiliza estas configuraciones, asegúrese de reemplazar `<client code>` por su propio código de cliente, que puede obtener desde la página **[!UICONTROL Administración]** > **[!UICONTROL Implementación].
* Si tiene una capa de datos es óptimo definir la mayor cantidad posible en el `<head>` de sus páginas antes de que se cargue at.js. Esta ubicación proporciona la máxima capacidad para utilizar esta información en Target para personalización.
* Las funciones especiales de Target, como `targetPageParams()`, `targetPageParamsAll()`, proveedores de datos y `targetGlobalSettings()` deben definirse después de la capa de datos y antes de que at.js cargue. Alternativamente, estas funciones se podrían guardar en la sección [!UICONTROL Encabezado de biblioteca] de la página [!UICONTROL Editar configuración de at.js] y guardarse como parte de la propia biblioteca de at.js. Para obtener más información sobre estas funciones, consulte   [Funciones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* Si utiliza bibliotecas de ayuda de JavaScript, como jQuery, inclúyalas antes de Target para poder usar su sintaxis y métodos al crear experiencias de Target.
* Incluya at.js en el `<head>` de sus páginas.

## Seguimiento de conversiones {#task_E85D2F64FEB84201A594F2288FABF053}

El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.

>[!NOTE]
>
>Si los usuarios realizan compras en el sitio web, Adobe recomienda implementar un mbox de confirmación de pedido aunque use Analytics para Target (A4T) para los informes.

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
