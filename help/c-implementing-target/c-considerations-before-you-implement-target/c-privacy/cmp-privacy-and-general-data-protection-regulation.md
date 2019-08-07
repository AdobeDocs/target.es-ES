---
description: Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea y la Ley de privacidad del consumidor de California (CCPA) y cómo estos reglamentos afectan a su organización y Adobe Target.
keywords: gdpr; eu; unión europea; privacy; faq; preguntas más frecuentes; california consumer privacy act; ccpa
seo-description: Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea y la Ley de privacidad del consumidor de California (CCPA) y cómo estos reglamentos afectan a su organización y Adobe Target.
seo-title: Reglamento general de protección de datos (RGPD), Ley de privacidad del consumidor de California (CCPA) y Adobe Target
solution: Target
title: Normativas de privacidad y protección de datos
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 222fb66f58ea5bcecabfaa2ab966ad9a686dc9ef

---


# Normativas de privacidad y protección de datos {#privacy-and-general-data-protection-regulation-gdpr}

Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea y la Ley de privacidad del consumidor de California (CCPA) y cómo estos reglamentos afectan a su organización y [!DNL Adobe Target].

## Descripción general del Reglamento General de Protección de Datos (RGPD) {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Información sobre la ayuda que Adobe le brinda para estar preparado respecto al Reglamento General de Protección de Datos (RGPD) de la Unión Europea.

### Información general del RGPD {#section_8C99434A431B4494998B01B869E7EA5D}

El 25 de mayo de 2018, el RGPD de la Unión Europea entró en vigor. Para obtener más información sobre qué significa esto para usted, consulte [RGPD y su empresa](https://www.adobe.com/privacy/general-data-protection-regulation.html).

Cuando proporciona software y servicios a una empresa, Adobe actúa como procesador de datos de cualquier dato personal que procese y almacene como parte de la provisión de dichos servicios. Como procesador de datos, Adobe procesa los datos personales de acuerdo con los permisos e instrucciones que su empresa proporcione (y que pueden establecerse, por ejemplo, en el acuerdo entre su empresa y Adobe).

Como responsable del tratamiento de datos, determinará qué datos personales Adobe trata y almacena en su nombre. Si usa soluciones de Adobe Experience Cloud, Adobe podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de Adobe Experience Cloud. Si desea ver una lista detallada de ejemplos, consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

Adobe Experience Cloud proporcionará API listas para el RGPD a los responsables del tratamiento de datos, que les permitirán realizar las siguientes tareas, antes de la fecha de entrada en vigencia de la normativa RGPD:

* Acceder a información del interesado almacenada dentro de Target
* Eliminar información del interesado almacenada dentro de Target

### El sitio web de la API del Reglamento General de Protección de Datos de Adobe  {#section_51B8FA3CBE234E9592BDA7083B5CE4CD}

Para obtener más información, consulte:

* [Sitio web de la API del Reglamento General de Protección de Datos de Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentación del RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Información general sobre la Ley de privacidad del consumidor de California (CCPA)

La Ley de privacidad del consumidor de California (CCPA) entró en vigor el 1 de enero de 2020. Por diseño, la ley proporciona al programador de California un margen para realizar ajustes y aclarar los detalles, lo que significa que puede tener muchas preguntas. Si tiene alguna duda, no es la única persona que trabaja a través de las incertidumbres de la ley e intenta comprender y desarrollar un enfoque para satisfacer los requisitos legales, operativos y técnicos.

CCPA proporciona a los consumidores de California nuevos derechos relacionados con su información personal e impone responsabilidades de protección de datos en determinadas entidades que realizan negocios en California. En un nivel alto, la ley otorga a California varios derechos clave, incluidos los derechos para: (1) información de solicitud (acceso a los datos), (2) desactivar la venta de información personal (un derecho muy amplio a dejar de compartir información con terceros), (3) tener la información personal eliminada y (4) ser informada de que la información personal se está divulgando o vendiendo.

Si estuviera ocupado para la ley de privacidad de Europa (RGPD) del año pasado, algunos de estos derechos podrían estar familiarizados y gran parte del trabajo que ha realizado podría ser rediseñado.

## Inclusión de Adobe Target y Adobe Launch {#section_6F7B53F5E40C4425934627B653E831B0}

Target proporciona soporte de funcionalidad opcional a través de Adobe Launch para ayudar a respaldar su estrategia de gestión de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de Target. También hay una opción a través de Adobe Launch para aprobar previamente la etiqueta de Target. Para activar la opción Opt-In en Target at.js, debe utilizar `targetGlobalSettings` y agregar la configuración `optinEnabled=true`. En Launch tendrá que seleccionar “habilitar” en la lista desplegable Opt-In del RGPD de la vista de instalación de Target Launch Extension. Consulte la [documentación de Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obtener más detalles.

El siguiente fragmento de código muestra cómo habilitar la configuración `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>La funcionalidad de inclusión es compatible con la versión 1.7.0 de at. js y con at. js 2.1.0 o posterior. La inclusión no es compatible con la versión 2.0.0 y 2.0.1 de at. js.
>
>El uso de Adobe Launch es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en Adobe Launch para ocultar elementos seleccionados de su página antes de la activación de Target que son útiles para aprovechar como parte de su estrategia de consentimiento.

Hay tres escenarios a considerar cuando se usa la inclusión:

1. **La etiqueta de Target se aprobó previamente mediante Adobe Launch (o el titular de los datos previamente aprobado):** La etiqueta de Target no se mantiene para el consentimiento y funciona como se espera.
1. **La etiqueta de Target NO está aprobada previamente y`bodyHidingEnabled`es FALSO:** la etiqueta de Target se activa solo después de que se haya obtenido el consentimiento del cliente. Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Después de recibir el consentimiento, se llama a Target y el contenido personalizado está disponible para el sujeto de los datos (visitante). Debido a que solo el contenido predeterminado está disponible antes del consentimiento, es importante aprovechar una estrategia adecuada, como una página de inicio que cubra cualquier parte de la página o contenido que pueda ser personalizado. Esto asegura que la experiencia se mantenga consistente para el sujeto de los datos (visitante).
1. **La etiqueta de Target NO está aprobada previamente y`bodyHidingEnabled`es VERDADERO:** la etiqueta de Target se activa solo después de que se haya obtenido el consentimiento del cliente. Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Sin embargo, debido a que `bodyHidingEnabled` se establece en verdadero, `bodyHiddenStyle` dicta qué contenido de la página está oculto hasta que se dispara la etiqueta de Target (o el sujeto de los datos rechaza la opción de inclusión, en cuyo caso se muestre el contenido por defecto). De forma predeterminada, `bodyHiddenStyle` se establece en `body { opacity:0;`}, que oculta la etiqueta de cuerpo HTML. La configuración de nuestra página recomendada se encuentra a continuación para que todo el cuerpo de la página, excepto el cuadro de diálogo del administrador de consentimiento, se oculte al colocar el contenido de la página en un contenedor y el cuadro de diálogo del administrador de consentimiento en un contenedor separado. Estos ajustes configuran Target de modo que ocultan solo el contenedor de contenido de la página. Consulte la [documentación de Adobe Launch para obtener más información sobre cómo configurar estos ajustes](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html).

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

## Preguntas frecuentes sobre reglas de protección de datos y privacidad {#concept_41F88DE95D2943178BEC382736B5C038}

Preguntas más frecuentes sobre el Reglamento General de Protección de Datos (RGPD) y la Ley de Privacidad del Consumidor de California (CCPA) específicas de Adobe Target.

### ¿Qué es la política de Adobe para estas regulaciones? {#section_A6849628D6524C80A6E16946DC5D25A9}

Adobe ya cumple o está implementando nuestras obligaciones como procesador de datos. Tenemos una base sólida de controles de privacidad y seguridad certificados e intencionales y seguiremos realizando mejoras de producto con antelación al plazo de mayo de 2018. Los clientes empresariales tendrán la responsabilidad de implementar estas mejoras, como así también actualizar cualquier política y procedimiento necesarios.

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each Adobe Experience Cloud solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, Adobe proporciona un método central para ayudar a los controladores de datos a cumplir con los requisitos del RGPD y CCPA. Los responsables del tratamiento de datos no necesitan ir directamente a cada una de las soluciones.

Todas las solicitudes GDPR y CCPA de las soluciones de Experience Cloud, incluido Target, se realizarán a través de una API central de Adobe, denominada actualmente API de RGPD. A continuación, la API completará la solicitud para el conjunto de soluciones de Experience Cloud del responsable del tratamiento de datos.

### ¿Qué información Adobe permitirá que nuestros clientes eliminen en respuesta a una solicitud del interesado/usuario?  {#section_4B51D00924EC4166B2442218B69214F0}

La información relacionada con un visitante individual dentro de Target está contenida dentro del perfil del visitante de Target. Adobe Target permitirá que los clientes eliminen todos los datos asociados con un ID en su perfil del visitante. Para ver ejemplos de los datos de perfil que Adobe Target almacena, consulte  [Perfil del visitante](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Los datos agregados o anonimizados (por ejemplo, datos de informe) que no identifican a una persona en particular, o datos que no están relacionados con una persona específica (por ejemplo, datos de contenido) están fuera del alcance de una solicitud de eliminación de usuario.

De forma predeterminada, los perfiles del visitante de Target inactivos durante 90 días se eliminan sin necesidad de realizar acción alguna.

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

Target admite los siguientes tipos de ID para localizar un perfil de cliente:

| ID de usuario | Tipo de ID de espacio de nombres | ID de espacio de nombres | Definición |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID, conocido anteriormente como ID de visitante o Marketing Cloud ID. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de TnT/ID de cookie(TNTID) | Standard | 9 | Identificador de Target establecido como cookie en el navegador del visitante. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de terceros/ID de administración de la relación con los clientes  (THIRDPARTYID) | Específico de Target | N/A | Si proporciona a Target su administración de la relación con los clientes u otra información de identificador único para sus clientes. |

>[!NOTE]
>
>Aunque Adobe Target admite cookies de origen y de terceros de terceros, solo se recomiendan cookies de Adobe Target de origen para RGPD y CCPA.

### ¿Cómo gestiona Adobe Target la administración de consentimiento?{#section_C86BF5EE4FAA47039659850E7594A6BA}

El RGPD y CCPA no cambian cuando necesita obtener el consentimiento, sino cómo lo obtiene. La estrategia de consentimiento de cada cliente depende de su forma de recopilar y utilizar los datos, así como de su política de privacidad. La administración de consentimiento no es compatible con Target para GDPR ni CCPA.

Adobe no ofrece actualmente una solución de administración de consentimiento, pero hay diversas herramientas en desarrollo en el mercado para satisfacer algunos de los nuevos requisitos. Para obtener más información sobre herramientas de privacidad en general, incluidos los administradores de consentimiento, consulte el [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) disponible en el sitio web de la International Association of Privacy Professionals (iaap).

Adobe Target proporciona soporte de funcionalidad de inclusión a través de Adobe Launch para ayudar a respaldar su estrategia de gestión de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de Adobe Target. También hay una opción a través de Adobe Launch para aprobar previamente la etiqueta de Adobe Target. El uso de Adobe Launch es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en Adobe Launch para ocultar elementos seleccionados de su página antes de la activación de Adobe Target que son útiles para aprovechar como parte de su estrategia de consentimiento.

For more information on GDPR, CCPA and Adobe Launch, see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Además, consulte la sección “Inclusión de Adobe Target y Adobe Launch” anterior.

### ¿Envía AdobePrivacy.js información a la API del RGPD?{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *no* envía esta información a la API. Debe hacerlo el cliente. Esta biblioteca proporciona únicamente los ID almacenados en el navegador para ese visitante concreto.

### ¿Qué elimina removeIdentities?{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *elimina únicamente* esas identidades del navegador, y solo depende de si la solución de Adobe lo ha implementado.

Por ejemplo, Target elimina las cookies que almacenan sus ID, pero Adobe Audience Manager (AAM) no elimina el ID demdex, que se guarda en una cookie de terceros.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Además de los requisitos de Servicio de privacidad central, un mensaje GDPR o CCPA válido para Target contiene:

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

### ¿Qué tipos de respuesta puedo esperar de Target a través de la API del RGPD?  {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Estado de la solicitud | Mensaje de respuesta de Target | Situación |
|--- |--- |--- |
| Procesando | Procesando | Target recibió la solicitud GDPR o CCPA y está procesando. |
| Completado | No aplicable: el contexto de la empresa no es aplicable | El ID IMS de la solicitud RDPD o CCPA no está asignado a ningún cliente de Target.<br>Tenga en cuenta que algunas empresas cuentan con varios ID de IMS. Debe enviar el ID de IMS en el que Target está aprovisionado. |
| Completado | No aplicable: no se encontró el contexto del usuario | El ID proporcionado en la solicitud RDPD o CCPA para el visitante o asunto de datos específico no está presente en el almacén de perfiles de Target.<br>Tenga en cuenta que este resultado también devuelve si intenta enviar un tipo de ID de espacio de nombres no compatible con Target (consulte más atrás cuáles son los ID compatibles). |
| Error | Mensaje de error (los detalles dependen del tipo de error) | Error al recuperar o eliminar el perfil objeto de los datos solicitados.<br>Error al cargar en Azure la solicitud de acceso. |

### ¿Qué respuesta Target envía a la API de RGPD para una solicitud de acceso?{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Las respuestas a solicitudes de datos de acceso contienen un resumen del perfil de Target para el visitante en cuestión. Tenga en cuenta que esta devolución se envía a la API del RGPD de Experience Cloud, que a su vez envía una respuesta a los responsables del tratamiento de datos.

Una respuesta de API de acceso para Target de muestra tendrá un aspecto similar al siguiente:

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
| jobId | Indica el ID de trabajo RDPD o CCPA de la API central GDPR. |
| imsOrgID | Proporciona un identificador único para su empresa. |
| namespace | También conocido como la fuente de datos. Consulte «¿Qué ID se admiten para ayudar a los clientes a completar un acceso al RGPD o CCPA y una solicitud de eliminación para Target?» en este tema. |
| type | El tipo de ID para el cual solicitó el acceso a los datos del RGPD o CCPA. Target acepta varios tipos de ID, algunos de los cuales son estándares y algunos son específicos de Target. Consulte «¿Qué ID se admiten para ayudar a los clientes a completar un acceso al RGPD o CCPA y una solicitud de eliminación para Target?» en este tema. |
| value | El ID de la fuente de datos/espacio de nombres. Consulte «¿Qué ID se admiten para ayudar a los clientes a completar un acceso al RGPD o CCPA y una solicitud de eliminación para Target?» para valores aceptados. |
| integration code | Los códigos de integración son nombres descriptivos para las fuentes de datos y ayudarle a seguir sus fuentes de datos con más facilidad que con los ID de fuentes de datos. |

Cuando se proporcionan varios valores para identificar perfiles, cada identificador válido tiene un archivo de perfil. Los archivos de perfil se envían RGPD central de Azure Blob mediante la API central del RGPD, con el formato de una respuesta JSON de perfil de Target.

Un JSON de perfil de Target podría tener un aspecto similar al siguiente ejemplo:

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
| Sample_Parameter | El responsable del tratamiento de datos carga o proporciona directamente gran cantidad de información en el perfil de Target. En este ejemplo, se cargó un parámetro en el perfil de Target con la API de actualización de perfil. Para obtener más información, consulte [Métodos para obtener los datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo estándar incluye la hora del día correspondiente a la visita de retorno más reciente de un usuario. |
| firstSessionStart | Este campo estándar incluye la hora del día en que comenzó la primera sesión del usuario. |
| user.sessionCountScript | El responsable del tratamiento de datos carga o proporciona directamente gran cantidad de información en el perfil de Target. En este ejemplo, un script de perfil está incrementando el número de sesiones que este visitante realizó en el sitio del responsable del tratamiento de datos. Para obtener más información, consulte [Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Esta es una versión abreviada del JSON de un perfil de Target con fines ilustrativos. Muchos de los campos del perfil de Target no son estándares. El resultado obtenido depende de la información que contenga ese perfil del visitante específico.

## ¿Admite Target la ocultación de la IP?  {#section_428907B0CD9842D9B245B38C66A53C6A}

Target admite la confusión de IP en Target si decide usarla como parte de su estrategia de implementación GDPR o CCPA. For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
