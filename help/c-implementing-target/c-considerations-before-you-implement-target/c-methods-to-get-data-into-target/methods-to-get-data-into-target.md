---
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
description: Información sobre los distintos métodos que se pueden utilizar para introducir datos en Target, como el uso de parámetros de página, atributos de perfil en página, atributos de perfil en script, proveedores de datos, la API de actualización de perfiles en lote, la API de actualización de perfil único y los atributos del cliente.
title: Métodos para obtener los datos en Target
feature: implementation general
subtopic: Getting Started
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 96%

---


# Métodos para obtener los datos en Target{#methods-to-get-data-into-target}

Información sobre los distintos métodos que se pueden utilizar para introducir datos en Target, como el uso de parámetros de página, atributos de perfil en página, atributos de perfil en script, proveedores de datos, la API de actualización de perfiles en lote, la API de actualización de perfil único y los atributos del cliente.

## Parámetros de página (también denominados “parámetros de mbox”) {#section_5A297816173C4FE48DC4FE03860CB42B}

Los parámetros de página son pares de nombre-valor pasados directamente a través del código de página que no se almacenan en el perfil del visitante para un uso futuro.

Los parámetros de página son útiles para enviar a Target datos de página adicionales que no es necesario que se almacenen con el perfil del visitante para un uso de segmentación futuro. Estos valores, en cambio, se utilizan para describir la página o la acción realizada por el usuario en la página específica.

### Formato

Los parámetros de página se pasan a Target a través de una llamada de servidor como un par de nombre-valor de la cadena. Los nombres y valores del parámetro se pueden personalizar, aunque hay algunos “nombres reservados” para usos específicos.

Ejemplos:

* `page=productPage`

* `categoryId=homeLoans`

### Casos de uso de ejemplo

**Páginas de producto**: envía información sobre el producto específico visualizado (así es como funciona Recommendations).

**Detalles del pedido**: envía el ID de pedido, el total, etc. para la recopilación del pedido.

**Afinidad de la categoría**: envía información visualizada por categorías a Target para dar a conocer la afinidad del usuario con categorías concretas de sitios.

**Datos de terceros**: envía información de fuentes de datos de terceros, como proveedores de segmentación por tiempo, datos de la cuenta (por ejemplo, DemandBase), datos demográficos (por ejemplo, Experian) y más.

### Beneficios del método

Los datos se envían a Target en tiempo real y se pueden utilizar en la misma llamada de servidor en la que se integran los datos.

### Advertencias

* Se requiere la actualización del código de la página (directamente o a través de un sistema de administración de etiquetas).
* Si los datos se deben utilizar para segmentación en una página o llamada de servidor posterior, deben traducirse a un script de perfil.
* Las cadenas de consulta solo pueden contener caracteres según el [estándar Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Además de los mencionados en el sitio IETF, Target permite los siguientes caracteres en las cadenas de consulta:

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   Todo lo demás debe tener codificación URL. The standard specifies the following format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), as illustrated below:

   ![](assets/ietf1.png)

   O, la lista completa para más simplicidad:

   ![](assets/ietf2.png)

### Ejemplos de código

targetPageParamsAll (sustituye los parámetros en todas las llamadas mbox de la página):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (sustituye los parámetros en el mbox global de la página):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parámetros en el código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### Vínculos a información relevante

Recommendations: [implementación según el tipo de página](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmación del pedido: [Rastrear conversiones](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Afinidad de la categoría: [afinidad de la categoría](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## Atributos de perfil en página (también denominados “atributos de perfil en mbox”){#section_57E1C161AA7B444689B40B6F459302B6}

Los atributos de perfil en página son pares de nombre-valor pasados directamente a través del código de página que se almacenan en el perfil del visitante para un uso futuro.

Los atributos de perfil en página permiten que los datos específicos del usuario se almacenen en el perfil de Target para una posterior segmentación.

### Formato

Los atributos de perfil en página pasan a Target a través de una llamada de servidor como un par de nombre-valor de cadena con el prefijo “perfil” antes del nombre del atributo.

Los nombres y valores del atributo se pueden personalizar, aunque hay algunos “nombres reservados” para usos específicos.

Ejemplos:

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### Casos de uso de ejemplo

**Información de inicio de sesión**: comparta con Target datos con información que no permita identificar personalmente a los usuarios en función del inicio de sesión del usuario. Puede tratarse, por ejemplo, del estado del abono, el historial de pedidos, etc.

**Información de la tienda**: hace el seguimiento de cuál es la ubicación de la tienda preferida de este usuario.

**Interacciones anteriores**: hace el seguimiento de las acciones realizadas anteriormente por el usuario en el sitio para proporcionar datos para una futura personalización.

### Beneficios del método

Los datos se envían a Target en tiempo real y se pueden utilizar en la misma llamada de servidor en la que se integran los datos.

### Advertencias

Se requieren actualizaciones del código de la página (directamente o a través de un sistema de administración de etiquetas).

Los atributos y los valores son visibles en las llamadas de servidor, para que el visitante pueda ver los valores. Si se comparte información como rangos de crédito u otra información potencialmente privada, esta no sería la mejor opción.

### Ejemplos de código

targetPageParamsAll (sustituye los atributos en todas las llamadas mbox de la página):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (sustituye los atributos en el mbox global de la página):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Atributos en el código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### Vínculos a información relevante

[Atributos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Perfil del visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## Atributos de perfil en script {#section_3E27B58C841448C38BDDCFE943984F8D}

Los atributos de perfil en script son pares de nombre-valor definidos en la solución de Target. El valor se determina a partir de la ejecución de un fragmento JavaScript en el servidor de Target por llamada de servidor.

Los usuarios escriben pequeños fragmentos de código que se ejecutan mediante una llamada de mbox y antes de que el visitante se evalúe por audiencia y abono a la actividad.

### Formato

Los atributos de perfil en script se crean en la sección Audiencias de Target. Cualquier nombre de atributo es válido y el valor es el resultado de una función JavaScript escrita por el usuario de Target. Al nombre de atributo se le añade automáticamente el prefijo “user. &quot; en Target para distinguirlo de los atributos del perfil en página.

El fragmento de código se escribe en lenguaje Rhino JS y puede hacer referencia a tokens y a otros valores.

### Casos de uso de ejemplo

**Abandono del carrito**: cuando el visitante llega hasta el carrito de compra, el script de perfil se establece en 1. Si el visitante hace una conversión, se restablece en 0. Si el valor es igual a 1, el visitante tiene un artículo en el carrito.

**Recuento de visitas**: en cada nueva visita el recuento aumenta 1 punto para hacer el seguimiento de la frecuencia con la que un visitante regresa al sitio.

### Beneficios del método

No requiere actualizaciones de código.

Se ejecuta antes de la toma de decisiones de audiencia y abono a la actividad, por lo que estos atributos de script de perfil pueden afectar al abono en una sola llamada de servidor.

Puede ser muy potente. Se pueden ejecutar hasta 2000 instrucciones por script.

### Advertencias

Se requieren conocimientos de JavaScript.

La orden de ejecución de los scripts de perfil no está garantizada, por lo que no pueden depender los unos en los otros.

La depuración puede ser difícil.

### Ejemplos de código

Los scripts de perfil son bastante flexibles:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Vínculos a información relevante

[Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## Proveedores de datos {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

Proveedores de datos es una funcionalidad que permite pasar fácilmente datos de terceros a Target.

Nota: Proveedores de datos requiere at.js 1.3 o posterior.

### Formato

La configuración `window.targetGlobalSettings.dataProviders` es una matriz de proveedores de datos.

Para obtener más información sobre la estructura de cada proveedor de datos, consulte [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Casos de uso de ejemplo

Recabar datos de terceros, por ejemplo, un servicio meteorológico, un DMP o incluso su propio servicio web. Puede usar estos datos para crear audiencias, dirigir contenido y enriquecer el perfil del visitante.

### Beneficios del método

Esta configuración permite a los clientes recopilar información de proveedores de datos de terceros, como Demandbase, BlueKai y servicios personalizados, y pasar los datos a Target como parámetros de mbox en la solicitud global de mbox.

Admite la recopilación de datos de múltiples proveedores a través de solicitudes de desincronización y sincronización.

El uso de este enfoque facilita la administración del parpadeo del contenido predeterminado de la página, al tiempo que incluye tiempos de espera independientes para cada proveedor para limitar el impacto en el rendimiento de la página.

### Advertencias

Si los proveedores de datos agregados a `window.targetGlobalSettings.dataProviders` son asincrónicos, se ejecutarán en paralelo. La solicitud de API del visitante se ejecutará en paralelo con las funciones agregadas a `window.targetGlobalSettings.dataProviders` para permitir un tiempo de espera mínimo.

at.js no intentará almacenar en caché los datos. Si el proveedor de datos obtiene datos solo una vez, el proveedor de datos debe asegurarse de que los datos estén en caché y, cuando se invoque la función del proveedor, sirva los datos de caché para la segunda invocación.

### Ejemplos de código

Se pueden encontrar varios ejemplos en [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Vínculos a información relevante

Documentación: [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### Vídeos de formación:

* [Uso de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementación de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## API de actualización de perfiles en lote {#section_92AB4820A5624C669D9A1F1B6220D4FA}

A través de la API, envíe un archivo .csv a Target que incluya actualizaciones de perfil de visitantes para muchos visitantes. Cada perfil de visitante se puede actualizar con varios atributos de perfil en página con una llamada.

Esta opción es muy similar a los atributos de cliente con algunas diferencias:

* Los atributos de cliente utilizan una carga FTP, mientras que la API de actualización de perfiles en lote de Target utiliza una API HTTP POST.
* Los datos de atributos del cliente se pueden compartir con Analytics. La actualización de perfiles en lote solo se puede usar en Target.
* La compatibilidad de los atributos del cliente para crear un perfil para un usuario Target todavía no se ha constatado. La API de actualización de perfiles en lote solo actualiza los perfiles de Target existentes.
* Los atributos del cliente requieren el uso del Experience Cloud ID (ECID). La API de actualización de perfiles en lote requiere el ID de TNT o el `mbox3rdPartyId`.
* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

### Formato

El archivo .csv debe hacer referencia a cada visitante a través de su PCID de Target o mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite. Todos los atributos o valores del perfil se crean y actualizan a través de la API. En la documentación de la API encontrará detalles sobre el formato.

### Casos de uso de ejemplo

Su CRM u otro sistema interno almacena datos valiosos sobre sus visitantes que le interesa actualizar sistemáticamente en Target sin exponer los datos de perfil en la implementación de su página.

### Beneficios del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

### Advertencias

El tamaño del archivo en lote debe ser inferior a 50 MB. Además, el número total de filas no puede superar las 500 000 filas por carga.

No hay ningún límite en el número de filas que puede cargar en lotes consecutivos en un período de 24 horas. Sin embargo, el proceso de ingestión puede acelerarse durante el horario laboral para garantizar que otros procesos se ejecuten de forma eficaz.

Las [actualizaciones de llamadas en lote V2](https://developers.adobetarget.com/api/#updating-profiles) consecutivas   sin llamadas mbox intermedias para los mismos ID de terceros ignoran las propiedades actualizadas en la primera actualización de la llamada en lote.

### Ejemplos de código

Consulte [Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles).

### Vínculos a información relevante

[Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)

## API de actualización de perfil único {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Funciona de forma casi idéntica a la API de actualización de perfiles en lote, con la diferencia de que solo se actualiza el perfil de un visitante a partir de la llamada de la API y no del archivo .csv.

### Formato

El visitante se debe identificar a través del valor mboxPC de Target o del valor mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite.

### Casos de uso de ejemplo

Quiere actualizar Target en tiempo real cuando un visitante realiza alguna acción que no sea en Internet, como contactar con un centro telefónico de atención al cliente, financiar un crédito, usar una tarjeta de fidelidad en una tienda, ir a un quiosco, etc.

### Beneficios del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

### Advertencias

Límite de 1 000 000 (1 millón) de llamadas a la API por período de 24 horas

Solo se actualiza el perfil. No se puede crear un perfil para un usuario potencial que Target todavía tiene que ver.

### Ejemplos de código

Se admiten GET y POST.  `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Vínculos a información relevante

[Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)

## Atributos del cliente {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target.

Los clientes de Target Standard pueden utilizar 5 atributos; los clientes de Target Premium pueden utilizar 200 atributos.

### Formato

Se carga un archivo .csv con Experience Cloud IDs (ECID) y pares de atributos nombre-valor a través de FTP o manualmente en la IU de Experience Cloud.

### Casos de uso de ejemplo

Su CRM u otros sistemas internos almacenan información valiosa que le interesa compartir con Adobe Experience Cloud, incluidos Target y Analytics.

### Beneficios del método

Al cargar datos del cliente se crea una entrada de perfil para cada visitante en Target, aunque Target todavía no haya visto el visitante.

Los mismos datos están disponibles automáticamente en Target y Analytics.

FTP puede ser un método de implementación más sencillo que la API.

### Advertencias

Los clientes de Target Standard pueden utilizar 5 atributos; los clientes de Target Premium pueden utilizar 200 atributos.

Los valores solo se pueden actualizar a través de Atributos del cliente, no en la página.

Se requiere la implementación del Experience Cloud ID (ECID).

### Ejemplos de código

Details can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

### Vínculos a información relevante

[Creación de un origen de atributos del cliente y carga del archivo de datos](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).