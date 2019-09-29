---
description: Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos internacionales de privacidad, y cómo estas regulaciones afectan a su organización y a Adobe Target.
keywords: gdpr;eu;unión europea;privacidad;faq;preguntas más frecuentes;california ley de privacidad del consumidor;ccpa;privacidad;protección de datos;exclusión;desactivación;gobierno;regulación
seo-description: Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos internacionales de privacidad, y cómo estas regulaciones afectan a su organización y a Adobe Target.
seo-title: Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos internacionales de privacidad, y cómo estas regulaciones afectan a su organización y a Adobe Target.
solution: Target
title: Normas de privacidad y protección de datos
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# Normas de privacidad y protección de datos {#privacy-and-general-data-protection-regulation-gdpr}

Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos internacionales de privacidad, y cómo estas regulaciones afectan a su organización y a Adobe Target.

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

El 25 de mayo de 2018 entró en vigor el RGPD de la Unión Europea. Para obtener más información sobre qué significa esto para usted, consulte [RGPD y su empresa](https://www.adobe.com/privacy/general-data-protection-regulation.html).

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. Si desea ver una lista detallada de ejemplos, consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

[!DNL Adobe Experience Cloud] proporcione API listas para el RGPD para los controladores de datos que les permitan completar las siguientes tareas:

* Acceder a información del interesado almacenada dentro de [!DNL Target]
* Eliminar información del interesado almacenada dentro de [!DNL Target]

Para obtener más información, consulte:

* [Sitio web de la API del Reglamento General de Protección de Datos de Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentación del RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Información general sobre la Ley de privacidad del consumidor de California (CCPA)

La Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés) otorga a los consumidores de California nuevos derechos con respecto a su información personal e impone responsabilidades de protección de datos a ciertas entidades que realizan negocios en California. La CCPA entrará en vigor el 1 de enero de 2020.

A un alto nivel, la ley otorga a los californianos varios derechos fundamentales, entre ellos los siguientes:

* Solicitar información (acceso a datos)
* Exclusión de la venta de información personal (un derecho muy amplio de no compartir información con terceros)
* Se eliminó la información personal
* Esté informado de que la información personal se está divulgando o vendiendo

Si el año pasado estuvieras ocupado preparándote para la ley europea de privacidad (RGPD), algunos de estos derechos podrían ser familiares y gran parte del trabajo que has hecho podría ser redirigido.

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] proporciona soporte de funcionalidad de inclusión mediante [!DNL Launch] ayuda para apoyar su estrategia de administración de consentimiento. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. Consulte la [documentación de Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obtener más detalles.

El siguiente fragmento de código muestra cómo habilitar la configuración `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>La funcionalidad de inclusión se admite en la versión 1.7.0 de at.js y en at.js 2.1.0 o posterior. La inclusión no se admite en las versiones 2.0.0 y 2.0.1 de at.js.
>
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide selected elements of your page prior to [!DNL Target] firing that are helpful to leverage as part of your consent strategy.

Hay tres escenarios a considerar cuando se usa la inclusión:

1. **[!DNL Target]La[!DNL Launch]etiqueta se aprueba previamente mediante[!DNL Target](o el asunto de datos aprobado anteriormente**): La [!DNL Target] etiqueta no se mantiene para el consentimiento y funciona según lo esperado.
1. **[!DNL Target]La etiqueta de NO está aprobada previamente y`bodyHidingEnabled`es FALSO:** la etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. [!DNL Target] Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). Debido a que solo el contenido predeterminado está disponible antes del consentimiento, es importante aprovechar una estrategia adecuada, como una página de inicio que cubra cualquier parte de la página o contenido que pueda ser personalizado. Esto asegura que la experiencia se mantenga consistente para el sujeto de los datos (visitante).
1. **[!DNL Target]La etiqueta de NO está aprobada previamente y`bodyHidingEnabled`es VERDADERO:** la etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. [!DNL Target] Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Sin embargo, debido a que `bodyHidingEnabled` se establece en verdadero, `bodyHiddenStyle` dicta qué contenido de la página está oculto hasta que se dispara la etiqueta de  (o el sujeto de los datos rechaza la opción de inclusión, en cuyo caso se muestre el contenido por defecto). [!DNL Target] De forma predeterminada, `bodyHiddenStyle` se establece en `body { opacity:0;`}, que oculta la etiqueta de cuerpo HTML. La configuración de nuestra página recomendada se encuentra a continuación para que todo el cuerpo de la página, excepto el cuadro de diálogo del administrador de consentimiento, se oculte al colocar el contenido de la página en un contenedor y el cuadro de diálogo del administrador de consentimiento en un contenedor separado. This setup configures [!DNL Target] so that it hides the page content container only. Consulte la [documentación de Launch para obtener más información sobre cómo configurar estos ajustes](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html).

   La configuración de página recomendada para el escenario 3 es:

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   Suponiendo el `bodyHiddenStyle` de:

   ```
   #pageContent { opacity:0;}
   ```

## Preguntas más frecuentes sobre las normas de privacidad y protección de datos {#concept_41F88DE95D2943178BEC382736B5C038}

Preguntas más frecuentes sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos internacionales de privacidad específicos de Target.

### ¿Cuál es la política de Adobe para estas regulaciones? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] ya cumple o está implementando nuestras obligaciones como procesador de datos. Tenemos una sólida base de controles de seguridad y privacidad certificados por diseño y hemos realizado mejoras de productos antes de la fecha límite de mayo de 2018. Los clientes empresariales tendrán la responsabilidad de implementar estas mejoras, como así también actualizar cualquier política y procedimiento necesarios.

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. Los responsables del tratamiento de datos no necesitan ir directamente a cada una de las soluciones.

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], will be made through a central Adobe API, currently called the GDPR API. The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target] permitirá que los clientes eliminen todos los datos asociados con un ID en su perfil del visitante. Para obtener ejemplos de los [!DNL Target] almacenes de datos de perfil, consulte Perfil [del](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)visitante.

Los datos agregados o anonimizados (por ejemplo, datos de informe) que no identifican a una persona en particular, o datos que no están relacionados con una persona específica (por ejemplo, datos de contenido) están fuera del alcance de una solicitud de eliminación de usuario.

[!DNL Target]De forma predeterminada, los perfiles del visitante de inactivos durante 90 días se eliminan sin necesidad de realizar acción alguna.

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] admite los siguientes tipos de ID para localizar un perfil de cliente:

| ID de usuario | Tipo de ID de espacio de nombres | ID de espacio de nombres | Definición |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID, conocido anteriormente como ID de visitante o Marketing Cloud ID. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de TnT/ID de cookie(TNTID) | Standard | 9 | Identificador de Target establecido como cookie en el navegador del visitante. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de terceros/ID de administración de la relación con los clientes. (THIRDPARTYID) | Específico de Target | N/A | Si proporciona a Target su administración de la relación con los clientes u otra información de identificador único para sus clientes. |

>[!NOTE]
>
>Although [!DNL Target] supports both first-party and third-party cross-domain cookies, first-party [!DNL Target] cookies only are recommended for GDPR and CCPA.

### How does [!DNL Target] handle consent management? {#section_C86BF5EE4FAA47039659850E7594A6BA}

El RGPD y la CCPA no cambian cuando necesitas obtener el consentimiento, sino cómo lo consigues. La estrategia de consentimiento de cada cliente depende de su forma de recopilar y utilizar los datos, así como de su política de privacidad. Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe] no ofrece actualmente una solución de administración de consentimiento, pero hay diversas herramientas en desarrollo en el mercado para satisfacer algunos de los nuevos requisitos. For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] proporciona soporte de funcionalidad de inclusión mediante [!DNL Launch] el fin de proporcionar soporte para su estrategia de administración de consentimiento. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### ¿Envía AdobePrivacy.js información a la API del RGPD?{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *no* envía esta información a la API. Debe hacerlo el cliente. Esta biblioteca proporciona únicamente los ID almacenados en el navegador para ese visitante concreto.

### ¿Qué elimina removeIdentities?{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *elimina únicamente*[!DNL Adobe] esas identidades del navegador, y solo depende de si la solución de lo ha implementado.

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### ¿Qué tipos de respuesta puedo esperar de Target a través de la API del RGPD? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Estado de la solicitud | Mensaje de respuesta de Target | Situación |
|--- |--- |--- |
| Procesando | Procesando | Target received the GDPR or CCPA request and is processing. |
| Completado | No aplicable: el contexto de la empresa no es aplicable | El ID de IMS de la solicitud de RGPD o CCPA no está asignado a ningún cliente de Target.<br>Tenga en cuenta que algunas empresas cuentan con varios ID de IMS. Debe enviar el ID de IMS en el que Target está aprovisionado. |
| Completado | No aplicable: no se encontró el contexto del usuario | El ID proporcionado en la solicitud GDPR o CCPA para el visitante o el sujeto de datos específicos no está presente en el almacén de perfiles de Target.<br>Tenga en cuenta que este resultado también devuelve si intenta enviar un tipo de ID de espacio de nombres no compatible con Target (consulte más atrás cuáles son los ID compatibles). |
| Error | Mensaje de error (los detalles dependen del tipo de error) | Error al recuperar o eliminar el perfil objeto de los datos solicitados.<br>Error al cargar en Azure la solicitud de acceso. |

### ¿Qué respuesta Target envía a la API de RGPD para una solicitud de acceso?{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| Campo | Descripción |
|--- |--- |
| jobId | Indicates the GDPR or CCPA job ID from the Central GDPR API. |
| imsOrgID | Proporciona un identificador único para su empresa. |
| namespace | También conocido como la fuente de datos. See "What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target?" en este tema. |
| type | The type of ID for which you requested the GDPR or CCPA data access. Target acepta varios tipos de ID, algunos de los cuales son estándares y algunos son específicos de Target. See "What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target?" en este tema. |
| value | El ID de la fuente de datos/espacio de nombres. See "What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target?" para valores aceptados. |
| integration code | Los códigos de integración son nombres descriptivos para las fuentes de datos y ayudarle a seguir sus fuentes de datos con más facilidad que con los ID de fuentes de datos. |

Cuando se proporcionan varios valores para identificar perfiles, cada identificador válido tiene un archivo de perfil. The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

A sample [!DNL Target] Profile JSON could look like the following example:

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

La siguiente tabla contiene descripción de los campos JSON de perfil ilustrativos:

| Campo | Descripción |
|--- |--- |
| Sample_Parameter | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. Para obtener más información, consulte [Métodos para obtener datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo estándar incluye la hora del día correspondiente a la visita de retorno más reciente de un usuario. |
| firstSessionStart | Este campo estándar incluye la hora del día en que comenzó la primera sesión del usuario. |
| user.sessionCountScript | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. En este ejemplo, un script de perfil está incrementando el número de sesiones que este visitante realizó en el sitio del responsable del tratamiento de datos. Para obtener más información, consulte [Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. Many of the fields of the [!DNL Target] profile are not standard. El resultado obtenido depende de la información que contenga ese perfil del visitante específico.

### ¿Admite Target la ocultación de la IP? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] admite la confusión de IP si elige usarla como parte de su estrategia de implementación GDPR o CCPA. Para obtener más información, consulte [Privacidad](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
