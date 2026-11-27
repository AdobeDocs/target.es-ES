---
keywords: correo electrónico;ESP;proveedor de servicio de correo electrónico;rawbox;api de envío;plantilla de solo descarga;plantilla de correo electrónico;procesamiento por lotes;hora de creación del correo electrónico
description: Obtenga información sobre cómo integrar el correo electrónico con Adobe [!DNL Target Recommendations], incluido el uso de la API de entrega [!DNL Target], las plantillas rawbox y las plantillas de solo descarga.
title: ¿Cómo puedo integrar Recommendations con el correo electrónico?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 26%
---
# Integrar [!DNL Recommendations] con el correo electrónico {#integrate-recs-email}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información acerca de los métodos para integrar [!DNL Target Recommendations] con un proveedor de servicios de correo electrónico (ESP) para la personalización en tiempo de envío de recomendaciones en correos electrónicos.

>[!ENDSHADEBOX]

[!DNL Adobe Target] admite la personalización en tiempo de envío de recomendaciones en correos electrónicos. No se admite la personalización en tiempo abierto de recomendaciones.

Hay tres métodos disponibles para integrar [!DNL Target Recommendations] con un ESP. Las capacidades del ESP determinan qué método utilizar, y el administrador de cuentas o el consultor pueden ayudar a elegir la mejor opción.

| Método | Detalles |
| --- | --- |
| [Método 1: [!DNL Adobe Target Delivery API]](#delivery-api) (preferido) | Use [!DNL Adobe Target Delivery API] para realizar solicitudes de recomendaciones por cliente y por correo electrónico. |
| [Método 2: [!DNL Adobe Rawbox API]](#rawbox) | Use [!DNL Adobe Target Rawbox API] para realizar solicitudes de recomendaciones por cliente y por correo electrónico. |
| [Método 3: [!DNL Recommendations Download API]](#download-api) | Use [!DNL Recommendations Download API] para solicitar recomendaciones masivas para una lista de productos o categorías en formato CSV. |

Los métodos 1 y 2 requieren que el ESP realice llamadas a una API externa por cliente y por correo electrónico, y que espere a que se devuelva el contenido. No todos los ESP admiten estos métodos, por lo que se debe contactar con el ESP para determinar si es compatible con este patrón de integración.

El método 3 requiere que el ESP adjunte una lista de recomendaciones por ID de producto o ID de categoría a la lista de correos electrónicos. Esta unión se puede basar en un atributo como el último producto visualizado, el último producto comprado o la categoría más visualizada del cliente. El ESP debe tener acceso a estos datos en su perfil de cliente para realizar la unión, por lo que se debe contactar con el ESP para determinar si tiene acceso a estos datos y si es compatible con este patrón de integración.

>[!IMPORTANT]
>
>Las siguientes directrices de capacidad se aplican a los métodos de API de entrega y de plantilla de correo electrónico rawbox (métodos 1 y 2):
>
>* Las solicitudes deben estar limitadas a una tasa menor de 1000 solicitudes por segundo o 25 veces el tráfico diario máximo.
>* El tráfico debe aumentarse en pasos de 200 solicitudes por segundo cada minuto.
>
>Para usar límites de tasa más altos, comuníquese con el administrador de cuentas.

## Método 1: usar la API de entrega (preferido) {#delivery-api}

La API de envío es una petición POST que funciona con el correo electrónico en tiempo de compilación. Esta opción es el método preferido para la hora de creación de correo electrónico.

La mayoría de los clientes de correo electrónico no permiten solicitudes POST, por lo que no se recomienda esta API para casos de uso de hora de apertura. Algunos clientes de correo electrónico, como Gmail o Outlook, pueden almacenar el contenido en caché o bloquear la imagen y exigir al destinatario que permita activamente que se muestre la imagen.

No se puede devolver el contenido predeterminado con la API de envío.

El siguiente código es una solicitud de entrega de API de ejemplo, donde `clientcode` es el código de cliente [!DNL Target]:

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

>[!NOTE]
>
>Proporcione un valor único para `sessionId` y uno para `tntId` o `thirdPartyId` para cada destinatario de correo electrónico (para cada llamada de API). Sin valores únicos en estos campos, la respuesta de la API puede ralentizarse o dar error debido al gran número de eventos generados dentro de un solo perfil.

Para obtener más información, consulte la [documentación de la API de entrega](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=es){target=_blank}.

## Método 2: usar una plantilla de correo electrónico de rawbox {#rawbox}

Un rawbox es similar a una solicitud de mbox, pero para entornos que no son de web, como los proveedores de servicios de correo electrónico (ESP). [!DNL Adobe Experience Platform Web SDK] y [!DNL at.js] no están disponibles para las solicitudes rawbox, por lo que las solicitudes deben crearse manualmente. Los siguientes ejemplos explican cómo trabajar con las solicitudes rawbox en correos electrónicos.

Este método permite rastrear el rendimiento de las recomendaciones en los correos electrónicos, probarlos de manera normal con una recomendación y continuar el seguimiento en el sitio.

>[!NOTE]
>
>Cuando utilice rawbox y [!DNL Target], consulte el aviso de seguridad importante que encontrará en [Creación de listas de hosts con autorización para enviar llamadas de mbox a [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

1. Configure una actividad [!DNL Recommendations] en [!DNL Target], con la opción [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

1. Para la ubicación, seleccione el nombre del mbox que se utiliza en la solicitud rawbox procedente de ESP.

1. Seleccione un diseño con el aspecto que desee para el correo electrónico.

A la hora de crear un correo electrónico, el ESP hace una llamada a los servidores de [!DNL Target] para cada rawbox de los mensajes de correo electrónicos que se generan. El ESP debe tener alguna forma de incluir el HTML devuelto en el correo electrónico cuando se envía.

El sistema de correo electrónico debe ser capaz de gestionar los siguientes casos.

### Se recibe una respuesta, pero no hay ninguna recomendación

* La respuesta es el valor establecido en el parámetro `mboxDefault`. Consulte la descripción de este parámetro en la tabla de parámetros obligatorios.
* El proveedor de correo electrónico debe tener un bloqueo HTML predeterminado de recomendaciones para utilizarlo en este caso.

### El servidor de [!DNL Target] agota el tiempo de espera y vuelve sin datos

* El servidor [!DNL Target] devuelve el siguiente contenido:

  `//ERROR: application server timeout`

* La aplicación del correo electrónico debe buscar ese texto y poder gestionar el error. El proveedor de correo electrónico tiene varias opciones para solventar este problema:

  * Intente realizar otra llamada del servidor inmediatamente (recomendado, tal vez con un contador de intentos).
  * Descarte ese correo electrónico en particular y continúe con el siguiente.
  * Ponga en cola ese correo electrónico en particular y vuelva a ejecutar los correos electrónicos erróneos como un lote al final de la primera ejecución.

### URL de solicitud de ejemplo

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Parámetros necesarios {#reqparams}

>[!NOTE]
>
>Para usar [!DNL Recommendations] en el correo electrónico, la llamada de rawbox debe incluir `entity.id`, `entity.categoryId` o ambos, según el tipo de criterios de recomendación. La llamada de ejemplo anterior incluye ambos.

| Parámetro | Valor | Descripción | Información general |
|--- |--- |--- |--- |
| `client_code` | *client_code* | El código de cliente usado en [!DNL Recommendations]. El consultor de Adobe puede proporcionar este valor. |  |
| `mbox` | *mboxName* | El nombre de mbox que se utiliza para la segmentación. | La misma validación que para todas las llamadas de mbox.<br>Límite de 250 caracteres.<br>No puede contener ninguno de los siguientes caracteres: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | disabled | Evita que la respuesta establezca una cookie en entornos que no son de web. |  |
| `entity.id`<br>(Necesario para determinados tipos de criterio: visualización/visualización, visualización/compra, compra/compra) | *entity_id* | Id de producto en el que se basa la recomendación, como un producto abandonado en el carro de compras o una compra anterior.<br>Si el criterio lo requiere, la llamada de rawbox debe incluir el `entity.id`. |  |
| `entity.event.detailsOnly` | true | Si se pasa `entity.id`, se recomienda pasar este parámetro para evitar que la solicitud incremente el número de visualizaciones escrutadas de la página para un elemento y para no distorsionar los algoritmos basados en visualizaciones de productos. |  |
| `entity.categoryId`<br>(Necesario para determinados tipos de criterio: más vistos por categoría y más vendidos por categoría) | *category_id* | Categoría en la que se basa la recomendación, como los principales vendedores de una categoría.<br>Si el criterio lo requiere, la llamada de rawbox debe incluir el `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Si el parámetro `mboxNoRedirect` no está presente, `mboxDefault` debe ser una URL absoluta que devuelva el contenido predeterminado si no hay recomendaciones disponibles. Esta URL puede ser una imagen u otro contenido estático.<br>Si el parámetro `mboxNoRedirect` está presente, `mboxDefault` puede ser cualquier texto que indique que no hay recomendaciones, por ejemplo `no_content`.<br>El proveedor de correo electrónico debe controlar el caso en el que se devuelve este valor e insertar HTML predeterminado en el correo electrónico.<br>Consulte las prácticas recomendadas de seguridad debajo de las tablas. |  |
| `mboxHost` | *mbox_host* | Este es el dominio que se añade al entorno predeterminado (grupo de hosts) cuando se activa la llamada. |  |
| `mboxPC` | Vacío | (Necesario para recomendaciones que utilizan el perfil de un visitante.)<br>Si no se proporcionó el valor &quot;thirdPartyId&quot;, se genera un nuevo tntId que se devuelve como parte de la respuesta. De lo contrario, el valor permanece vacío.<br>Vea la nota sobre valores únicos debajo de las tablas. | 1 &lt; Longitud &lt; 128<br>No puede contener más de un “.” (punto).<br>El único punto permitido es el del sufijo de ubicación del perfil. |

### Parámetros opcionales

| Parámetro | Valor | Descripción | Información general |
|--- |--- |--- |--- |
| `mboxPC`<br>(Opcional) | *mboxPCId* | Identificador de visitante [!DNL Target]. Utilice este valor para rastrear a un usuario con un círculo completo de vuelta al sitio en varias visitas o cuando utilice un parámetro de perfil de usuario.<br>Este valor debe ser el PCID de [!DNL Adobe Target] real del usuario, que se exporta desde el sitio web al CRM. El proveedor de correo electrónico recupera este ID desde CRM o desde el almacén de datos y lo utiliza como valor de este parámetro.<br>El valor `mboxPC` también es útil para rastrear el comportamiento de visitantes en el sitio en varias visitas para el seguimiento de métricas, cuando una recomendación es parte de una actividad A/B.<br>Vea la nota sobre valores únicos debajo de las tablas. | 1 &lt; Longitud &lt; 128<br>No puede contener más de un “.” (punto).<br>El único punto permitido es el del sufijo de ubicación del perfil. |
| `mboxNoRedirect`<br>(Opcional) | 1 | El llamador se redirige de forma predeterminada cuando no se encuentra contenido disponible. Utilice este parámetro para desactivar el comportamiento predeterminado. |  |
| `mbox3rdPartyId` | *xxx* | Utilice esta opción para especificar un ID de visitante personalizado para la segmentación de perfiles. |  |

Para `mboxSession` y `mboxPC`, proporcione un valor único para cada destinatario de correo electrónico (para cada llamada de API). Sin valores únicos en estos campos, la respuesta de la API puede ralentizarse o dar error debido al gran número de eventos generados dentro de un solo perfil.

Como práctica recomendada de seguridad para `mboxDefault`, use hosts autorizados para la lista de permitidos de los dominios de URL de redireccionamiento predeterminados. Si el dominio utilizado en la dirección URL `mboxDefault` no está incluido en la lista de permitidos, puede exponerse el riesgo de una vulnerabilidad de redirección abierta. Los hosts autorizados evitan el uso no autorizado de vínculos de redirector o `mboxDefault` por parte de terceros. [!DNL Target] usa hosts para realizar listas de permitidos en los dominios a los que se permiten redirecciones. Para obtener más información, consulte el aviso de seguridad al principio de esta sección.

### Posibles respuestas del servidor de [!DNL Target]

| Respuesta | Descripción |
|--- |--- |
| //ERROR: | Generado por el equilibrador de carga cuando no puede devolver contenido. |
| Éxito | El parámetro `mboxNoRedirect` está establecido en &quot;true&quot; y el servidor no devuelve ninguna recomendación (no hay coincidencia con el mbox o la caché del servidor no está inicializada). |
| bad request | Falta el parámetro `mbox`.<ul><li>No se ha especificado el parámetro `mboxDefault` o el `mboxNoRedirect`.</li><li>El parámetro de solicitud `mboxTrace` se ha especificado, pero `mboxNoRedirect` no.</li><li>No se especificó el parámetro `mboxTarget` cuando los nombres de mbox terminan con el sufijo `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` no se especifica cuando no existe ninguna coincidencia con la solicitud y el parámetro `mboxNoRedirect` no se ha especificado. |
| `Invalid mbox name:= MBOX_NAME` | El parámetro `mbox` contiene caracteres no válidos. |
| `Mbox name [MBOX_NAME] is too long` | El parámetro `mbox` tiene más de 250 caracteres. |

## Método 3: usar la API de descarga de Recommendations {#download-api}

Configure una recomendación como de costumbre pero elija **descargar solamente** en la sección de presentación en lugar de una combinación de plantilla y mbox. A continuación, proporcione al ESP el ID de la recomendación que se creó. El ESP accede a los datos de recomendación a través de la API. Estos datos muestran los artículos que deben recomendarse para un artículo clave o una categoría en particular, como los artículos abandonados en el carro de compras. El ESP almacena estos datos, los conecta con su propia apariencia, muestra información sobre cada elemento y los envía por correo electrónico.

Con esta opción, el servidor de Recommendations no puede rastrear directamente el rendimiento de una recomendación o dividir el tráfico en varias combinaciones de algoritmo y plantilla. Además, las recomendaciones no están asociadas a un perfil del visitante.

Para obtener más información sobre la API de descarga, consulte [API heredadas > Descargar](/help/main/assets/adobe-recommendations-classic.pdf).
