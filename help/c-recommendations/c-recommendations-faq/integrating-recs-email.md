---
keywords: correo electrónico;ESP;proveedor de servicio de correo electrónico;rawbox;api de envío;plantilla de solo descarga;plantilla de correo electrónico;procesamiento por lotes;hora de creación del correo electrónico
description: Aprenda a integrar el correo electrónico con la API de entrega de Adobe  [!DNL Target Recommendations], including using the [!DNL Target] , las plantillas de rawbox y las plantillas de solo descarga.
title: ¿Cómo integrar Recommendations con el correo electrónico?
feature: Recomendaciones
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
translation-type: ht
source-git-commit: f29701f5357e86b694acdf3a48fa7eace8d382cb
workflow-type: ht
source-wordcount: '1524'
ht-degree: 100%

---

# ![PREMIUM](/help/assets/premium.png) Integrar Recommendations con el correo electrónico 

Información acerca del modo de integrar el correo electrónico con [!UICONTROL Recommendations].

Las funcionalidades del proveedor de servicios de correo electrónico determinan el método que se debe utilizar. Su administrador de cuentas o asesor puede ayudarle a elegir la opción más adecuada para usted.

>[!IMPORTANT]
>
>Las siguientes directrices de capacidad se aplican a las opciones de API de envío y la plantilla de correo electrónico rawbox que se describen a continuación (opciones 1 y 2):
>
>* Las solicitudes deben estar limitadas a una tasa menor de 1000 solicitudes por segundo o 25 veces el tráfico diario máximo
>* Tráfico de rampa en pasos de 200 solicitudes por segundo cada minuto

> 
>
Póngase en contacto con su administrador de cuentas si desea usar límites de tasa más altos.

## Opción 1: Usar la API de envío {#section_9F00D271BABA4B7390B461F4C44EC319}

La API de envío es una solicitud POST que funciona con la hora de creación de correo electrónico. Esta opción es el método preferido para la hora de creación de correo electrónico.

La mayoría de los clientes de correo electrónico no aceptan solicitudes POST; por tanto, no se recomienda esta API para los casos de uso de hora de apertura. Algunos clientes de correo electrónico, como Gmail o Outlook, podrían guardar el contenido en caché o bloquear la imagen y exigir al destinatario que permita activamente que se muestre la imagen.

No se puede devolver contenido predeterminado mediante la API de envío.

El siguiente código es un ejemplo de solicitud de envío mediante API:

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

El elemento `clientcode` es su código de cliente de [!DNL Target]

>[!NOTE]
>
>Asegúrese de proporcionar un valor único para `sessionId` y uno para `tntId` o `thirdPartyId` para cada destinatario de correo electrónico (por ejemplo, para cada llamada de API). Si no proporciona valores únicos en estos campos, la respuesta de la API puede ralentizarse o dar error debido al gran número de eventos generados dentro de un solo perfil.

Consulte la [documentación de la API de envío](https://developers.adobetarget.com/api/#server-side-delivery) para obtener más información.

## Opción 2: usar una plantilla de correo electrónico de rawbox {#section_C0D48A42BCCE45D6A68852F722C7C352}

Un rawbox es parecido a una solicitud de mbox, pero para entornos que no son de web, como los proveedores de servicios de correo electrónico (ESP). Dado que no tiene [!DNL mbox.js] o [!DNL at.js] para utilizarlos en las solicitudes rawbox, debe crear las solicitudes manualmente. Los siguientes ejemplos explican cómo trabajar con las solicitudes rawbox en correos electrónicos.

>[!NOTE]
>
>Cuando utilice rawbox y [!DNL Target], consulte el aviso de seguridad importante que encontrará en [Creación de listas de hosts con autorización para enviar llamadas de mbox a [!DNL Target]](/help/administrating-target/hosts.md#allowlist).

Este método permite rastrear el rendimiento de las recomendaciones en los mensajes de correo electrónico, probarlos de manera normal con una recomendación y continuar el rastreo en el sitio.

Configure una actividad de [!DNL Recommendations] en [!DNL Target] utilizando la opción del [compositor de experiencias basado en formularios](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E). Para la ubicación, seleccione el nombre del mbox que quiera utilizar en la solicitud rawbox proveniente del ESP. Seleccione un diseño con el aspecto que desee para su correo electrónico. A la hora de crear un correo electrónico, el ESP hace una llamada a los servidores de [!DNL Target] para cada rawbox de los mensajes de correo electrónicos que se generan. Su ESP debe tener algún modo de incluir el HTML devuelto en el correo electrónico cuando este se envía.

El sistema de correo electrónico que utilice debe poder solventar los siguientes problemas:

### Se recibe una respuesta, pero no hay ninguna recomendación

* En este caso, la respuesta será la que esté establecida como valor del parámetro `mboxDefault`. Consulte la explicación sobre este parámetro más abajo.
* El proveedor de correo electrónico debe tener un bloqueo HTML predeterminado de recomendaciones para utilizarlo en este caso.

### El servidor de [!DNL Target] agota el tiempo de espera y vuelve sin datos

* En este caso, el servidor de [!DNL Target] devolverá el siguiente contenido:

   `//ERROR: application server timeout`

* La aplicación de correo electrónico debe buscar ese texto y poder gestionar el error. El proveedor de correo electrónico tiene varias opciones para solventar este problema:

   * Intente realizar otra llamada del servidor inmediatamente (recomendado, tal vez con un contador de intentos).
   * Envíe ese correo electrónico en concreto y continúe con el siguiente.
   * Ponga en cola ese correo electrónico en concreto y vuelva ejecutar los correos electrónicos erróneos como un lote al final de la primera ejecución.

### URL de solicitud de ejemplo

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Parámetros necesarios: {#reqparams}

>[!NOTE]
>
>Para utilizar [!DNL Recommendations] en correos electrónicos, la llamada de rawbox debe incluir el `entity.id`, `entity.categoryId` o ambos, según el tipo de criterios de recomendación. La llamada de ejemplo anterior incluye ambos.

| Parámetro | Valor | Descripción | Información general |
|--- |--- |--- |--- |
| `client_code` | *client_code* | El código del cliente utilizado en Recommendations. Su asesor de Adobe puede facilitarle este valor. |  |
| `mbox` | *mboxName* | El nombre de mbox que se utiliza para la segmentación. | Misma validación que la de todas las llamadas de mbox.<br>Límite de 250 caracteres.<br>No puede contener ninguno de los siguientes caracteres: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | disabled | Evita que la respuesta establezca una cookie en entornos que no son de web. |  |
| `entity.id`<br>(Necesario para determinados tipos de criterio: visualización/visualización, visualización/compra, compra/compra) | *entity_id* | El productId en el que se basa la recomendación, como un producto que se ha dejado en el carro, o en una compra anterior.<br>Si el criterio lo requiere, la llamada de rawbox debe incluir el `entity.id`. |  |
| `entity.event.detailsOnly` | true | Si se pasa el `entity.id`, se recomienda pasar también este parámetro para evitar que la solicitud incremente el número de visualizaciones escrutadas de la página para un elemento y para no distorsionar los algoritmos de productos basados en visualizaciones. |  |
| `entity.categoryId`<br>(Necesario para determinados tipos de criterio: más vistos por categoría y más vendidos por categoría) | *category_id* | La categoría en la que se basa la recomendación, como los más vendidos en una categoría.<br>Si el criterio lo requiere, la llamada de rawbox debe incluir el `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Si el parámetro `mboxNoRedirect` no está presente, `mboxDefault` debe ser una URL absoluta que devuelva el contenido predeterminado si no hay recomendaciones disponibles. Esta URL puede ser una imagen u otro contenido estático.<br>Si el parámetro `mboxNoRedirect` está presente, `mboxDefault` puede ser cualquier texto que indique que no hay recomendaciones, por ejemplo `no_content`.<br>El proveedor de correo electrónico necesita procesar el caso en el que se devuelve este valor e insertar el HTML predeterminado en el correo electrónico. <br> **Práctica recomendada de seguridad**: Tenga en cuenta que si el dominio que se usa en la URL `mboxDefault` no está incluido en la lista de permitidos, se expone a una posible vulnerabilidad de redireccionamiento abierto. Para evitar el uso no autorizado de vínculos de redirector o `mboxDefault` de terceros, Adobe le recomienda utilizar “hosts autorizados” en la lista de permitidos de los dominios de URL de redireccionamiento predeterminados. Target usa hosts para la lista de permitidos de dominios a los que desea permitir redirecciones. Para obtener más información, consulte [Creación de listas de permitidos que especifiquen hosts con autorización para enviar llamadas de mbox a  [!DNL Target]](/help/administrating-target/hosts.md#allowlist) en *Hosts*. |  |
| `mboxHost` | *mbox_host* | Este es el dominio que se añade al entorno predeterminado (grupo de host) al activar la llamada. |  |
| `mboxPC` | Vacío | (Necesario para recomendaciones que utilizan el perfil de un visitante).<br>Si no se proporcionó el valor “thirdPartyId”, se genera un nuevo tntId que se devuelve como parte de la respuesta. En caso contrario, permanece vacío.<br>**Nota**: Asegúrese de proporcionar un valor exclusivo de `mboxSession` y `mboxPC` para cada destinatario del correo electrónico (es decir, para cada llamada a la API). Si no proporciona valores únicos en estos campos, la respuesta de la API puede ralentizarse o dar error debido al gran número de eventos generados dentro de un solo perfil. | 1 &lt; Longitud &lt; 128<br>No puede contener más de un “.” (punto).<br>El único punto permitido es el del sufijo de ubicación del perfil. |

### Parámetros opcionales

| Parámetro | Valor | Descripción | Información general |
|--- |--- |--- |--- |
| `mboxPC`<br>(Opcional) | *mboxPCId* | Id de visitante de Target Utilice este valor si desea rastrear el recorrido completo de un usuario hasta su sitio en varias visitas o cuando utiliza un parámetro de perfil de usuario.<br>Este valor debe ser el PCID de [!DNL Adobe Target] real del usuario, que se exportaría desde el sitio web a su CRM. El proveedor de correo electrónico recuperaría este ID desde su CRM o desde el Data Warehouse, y lo usaría para el valor de este parámetro.<br>El valor `mboxPC` solo es útil para rastrear el comportamiento de visitantes en el sitio en varias visitas para métricas que rastrean si una recomendación es parte de una actividad A/B.<br>**Nota**: Asegúrese de proporcionar un valor exclusivo de `mboxSession` y `mboxPC` para cada destinatario del correo electrónico (es decir, para cada llamada a la API). Si no proporciona valores únicos en estos campos, la respuesta de la API puede ralentizarse o dar error debido al gran número de eventos generados dentro de un solo perfil. | 1 &lt; Longitud &lt; 128<br>No puede contener más de un “.” (punto).<br>El único punto permitido es el del sufijo de ubicación del perfil. |
| `mboxNoRedirect`<br>(Opcional) | 1 | El llamador se redirige de forma predeterminada cuando no se encuentra contenido disponible. Utilícelo para desactivar el comportamiento predeterminado. |  |
| `mbox3rdPartyId` | *xxx* | Utilice esta opción si tiene su propio ID de visitante personalizado para el direccionamiento de perfiles. |  |

### Posibles respuestas del servidor de [!DNL Target]

| Respuesta | Descripción |
|--- |--- |
| //ERROR: | Generado por el equilibrador de carga cuando no puede devolver contenido. |
| Correcto | El parámetro `mboxNoRedirect` se establece en “true” y el servidor no devuelve ninguna recomendación (es decir, no hay coincidencia con el mbox o el caché del servidor no se ha iniciado). |
| bad request | Falta el parámetro `mbox`.<ul><li>No se ha especificado el parámetro `mboxDefault` o el `mboxNoRedirect`.</li><li>Se ha especificado el parámetro de solicitud `mboxTrace` pero no el parámetro `mboxNoRedirect`.</li><li>No se ha especificado el parámetro `mboxTarget` cuando los nombres de mbox terminan con el sufijo `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | No se ha especificado `mboxDefault` cuando no existe coincidencia con la solicitud y el parámetro `mboxNoRedirect` no se ha especificado. |
| `Invalid mbox name:= MBOX_NAME` | Indica que el parámetro `mbox` contiene caracteres no válidos. |
| `Mbox name [MBOX_NAME] is too long` | Indica que el parámetro `mbox` sobrepasa los 250 caracteres. |

## Opción 3: usar la plantilla de solo descarga {#section_518C279AF0094BE780F4EA40A832A164}

Configure una recomendación como de costumbre pero elija **descargar solamente** en la sección de presentación en lugar de una combinación de plantilla y mbox. Luego en ESP, indíquele al ESP qué ID de recomendación creó. El ESP accede a los datos de la recomendación a través de la API. Estos datos muestran los artículos que deben recomendarse para un artículo clave o una categoría en particular, como los artículos abandonados en el carro de compras. A continuación, el ESP almacena estos datos, los conecta con su propio aspecto y presentación, muestra la información sobre cada artículo y la envía en los mensajes de correo electrónico.

Con esta opción, el servidor de Recommendations no puede rastrear directamente el rendimiento de una recomendación o dividir el tráfico en múltiples combinaciones de algoritmo y plantilla. Además, las recomendaciones no están asociadas a un perfil del visitante.

Para obtener más información sobre la API de descarga, consulte [API heredadas > Descargar](/help/assets/adobe-recommendations-classic.pdf).
