---
keywords: rgpd;ue;unión europea;privacidad;faq;preguntas frecuentes;ley de privacidad del consumidor de california;ccpa;privacidad;protección de datos;exclusión;exclusión;gobierno;regulación
description: Obtenga información sobre [!DNL Target] y el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad.
title: How [!DNL Target] ¿Gestionar las normas de privacidad y protección de datos?
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '2209'
ht-degree: 57%

---

# Reglamentos de protección de datos y privacidad

Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad internacionales. Descubra cómo afectan estas regulaciones a su organización y [!DNL Adobe Target].

## Información general sobre el Reglamento General de Protección de Datos (RGPD)  {#topic_DE567ECB6C944695AEE5073889F1AEA9}

El 25 de mayo de 2018, entró en vigor el RGPD de la Unión Europea. Para obtener más información sobre qué significa esta regulación para usted, consulte [RGPD y su empresa](https://business.adobe.com/privacy/general-data-protection-regulation.html).

Cuando [!DNL Adobe] proporciona software y servicios a una empresa, [!DNL Adobe] actúa como Procesador de datos de cualquier dato personal que procese y almacene en la provisión de dichos servicios. Como Procesador de datos, [!DNL Adobe] procesa los datos personales de acuerdo con los permisos e instrucciones que su empresa proporcione (y que pueden establecerse, por ejemplo, en el acuerdo entre su empresa y [!DNL Adobe]).

Como responsable del tratamiento de datos, usted determina los datos personales que [!DNL Adobe] trata y almacena en su nombre. Si usa soluciones de [!DNL Adobe Experience Cloud], [!DNL Adobe] podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de [!DNL Adobe Experience Cloud]. Si desea ver una lista detallada de ejemplos, consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud.html#collect).

[!DNL Adobe Experience Cloud] proporciona API preparadas para RGPD para controladores de datos que les permiten completar las siguientes tareas:

* Acceder a información del interesado almacenada dentro de [!DNL Target]
* Eliminar información del interesado almacenada dentro de [!DNL Target]

Para obtener más información, consulte:

* [Resumen del Privacy Service de Adobe](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Guía de API del Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Información general sobre la IU de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## Información general sobre la Ley de privacidad del consumidor de California (CCPA)

La Ley de privacidad del consumidor de California (CCPA) segura a los consumidores californianos nuevos derechos relacionados con su información personal e impone responsabilidades de protección de datos a determinadas entidades que realizan negocios en California. La CCPA entró en vigor el 1 de enero de 2020.

La ley asegura varios derechos clave para los californianos, incluidos los derechos a:

* Solicitar información (acceso a datos)
* Exclusión de la venta de información personal (derecho definido en términos generales a no compartir información con terceros)
* Eliminar información personal
* Saber que la información personal se está revelando o vendiendo

Si estuvo ocupado preparándose para la ley de privacidad de Europa (RGPD) del año pasado, algunos de estos derechos pueden resultarle familiares y gran parte del trabajo que ha hecho puede ser reutilizado.

>[!NOTE]
>
>El acceso a los datos y su eliminación, tal como se aplican a la CCPA, siguen el mismo proceso que para el RGPD.

## Adobe [!DNL Target] y [!DNL Adobe Experience Platform] inclusión {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] proporciona compatibilidad con la funcionalidad de inclusión mediante etiquetas en [!DNL Adobe Experience Platform] para ayudar a respaldar su estrategia de administración de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de [!DNL Target]. También hay una opción a través de [!DNL Adobe Experience Platform] para aprobar previamente la etiqueta de [!DNL Target]. Para activar Opt-in en la biblioteca at.js de [!DNL Target], debe utilizar `targetGlobalSettings` y agregar la configuración `optinEnabled=true`. En [!DNL Adobe ExperiencePlatform], seleccione &quot;habilitar&quot; en el [!UICONTROL Inclusión en el RGPD] lista desplegable en la vista de instalación de la extensión. Consulte [Implementación [!DNL Target] using [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obtener más información.

El siguiente fragmento de código muestra cómo habilitar la configuración `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>La funcionalidad Opt-in es compatible con la versión 1.7.0 de at.js y con at.js 2.1.0 o posteriores. Opt-in no es compatible con la versión 2.0.0 y 2.0.1 de at.js.
>
>El uso de [!DNL Adobe Experience Platform] es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en [!DNL Adobe Experience Platform] para ocultar elementos seleccionados de su página antes de [!DNL Target] activación que son útiles para usar como parte de su estrategia de consentimiento.

Hay tres escenarios a considerar cuando se usa la inclusión:

1. **La etiqueta de [!DNL Target] se aprobó previamente mediante [!DNL Adobe Experience Platform] (o [!DNL Target] que el titular de los datos haya aprobado previamente):** La etiqueta de [!DNL Target] no se dispone para el consentimiento y funciona como se espera.
1. **[!DNL Target]La etiqueta de NO está aprobada previamente y `bodyHidingEnabled` es FALSO:** la etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. [!DNL Target] Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Después de recibir el consentimiento, se llama a [!DNL Target], y el contenido personalizado está disponible para el sujeto de los datos (visitante). Dado que solo el contenido predeterminado está disponible antes del consentimiento, es importante utilizar una estrategia adecuada, como una página de inicio que cubra cualquier parte de la página o el contenido que se pueda personalizar. Este proceso garantiza que la experiencia sea coherente para el interesado (visitante).
1. **[!DNL Target]La etiqueta de NO está aprobada previamente y `bodyHidingEnabled` es VERDADERO:** la etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. [!DNL Target] Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Sin embargo, debido a que `bodyHidingEnabled` se establece como verdadero, `bodyHiddenStyle` dicta qué contenido de la página está oculto hasta que se dispara la etiqueta de [!DNL Target] (o el sujeto de los datos rechaza la opción Opt-in, en cuyo caso se muestra el contenido predeterminado). De forma predeterminada, `bodyHiddenStyle` está configurado como `body { opacity:0;}`, que oculta la etiqueta de cuerpo del HTML. La configuración de página recomendada de Adobe se muestra a continuación para que todo el cuerpo de la página, excepto el cuadro de diálogo del administrador de consentimiento, se oculte al colocar el contenido de la página en un contenedor y el cuadro de diálogo del administrador de consentimiento en un contenedor separado. Estos ajustes configuran [!DNL Target] de modo que ocultan únicamente el contenedor de contenido de la página. Consulte la [Información general del Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).

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

## Preguntas frecuentes sobre legislación de protección de datos y privacidad {#concept_41F88DE95D2943178BEC382736B5C038}

Preguntas frecuentes sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de privacidad del consumidor de California (CCPA) y otros requisitos de privacidad internacionales específicos de [!DNL Target].

### ¿Qué es el [!DNL Adobe] ¿política para estas regulaciones? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] ya cumple o está implementando sus obligaciones como procesador de datos. Adobe tiene una base sólida de controles de privacidad y seguridad certificados por diseño y realizó mejoras del producto antes de la fecha límite de mayo de 2018. Los clientes empresariales tienen la responsabilidad de implementar estas mejoras y actualizar cualquier política y procedimiento necesarios.

### ¿Debe mi empresa, como responsable del tratamiento de datos, enviar una solicitud de RGPD o de CCPA a cada [!DNL Adobe Experience Cloud] solución que utiliza? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] proporciona una manera central de ayudar a los responsables del tratamiento de datos a cumplir con los requisitos del RGPD y de la CCPA. Los controladores de datos no necesitan ir directamente a cada solución.

Todas las solicitudes de RGPD y CCPA entre [!DNL Experience Cloud] soluciones, incluidas [!DNL Target], a través de un [!DNL Adobe] , actualmente denominada API del RGPD. A continuación, la API completa la solicitud en el [!DNL Experience Cloud] grupo de soluciones.

### Qué información hace [!DNL Adobe] ¿permite que los clientes eliminen en respuesta a una solicitud del interesado/usuario? {#section_4B51D00924EC4166B2442218B69214F0}

La información relacionada con un visitante individual dentro de [!DNL Target] está en el Perfil del visitante de [!DNL Target]. [!DNL Target] permite a los clientes eliminar todos los datos asociados con un ID en su perfil del visitante. Para ver ejemplos de los almacenes de datos de perfil de [!DNL Target], consulte [Perfil del visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Los datos agregados o anonimizados (por ejemplo, datos de informe) que no identifican a una persona en particular, o datos que no están relacionados con una persona específica (por ejemplo, datos de contenido) están fuera del alcance de una solicitud de eliminación de usuario.

[!DNL Target]De forma predeterminada, los perfiles del visitante de inactivos durante 90 días se eliminan sin necesidad de realizar acción alguna.

### ¿Qué ID se admiten para ayudar a los clientes a realizar una solicitud de eliminación y acceso de RGPD o de CCPA para [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] admite los siguientes tipos de ID para localizar un perfil de cliente:

| ID de usuario | Tipo de ID de espacio de nombres | ID de espacio de nombres | Definición |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID], anteriormente conocido como ID de visitante o ID de Experience Cloud. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de TnT/ID de cookie(TNTID) | Estándar | 9 | [!DNL Target]Identificador de establecido como cookie en el navegador del visitante. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de terceros/ID de administración de la relación con los clientes.  (THIRDPARTYID) | [!DNL Target]-Específico | N/A | Si proporciona [!DNL Target] con su CRM u otra información de identificador único para sus clientes. |

>[!NOTE]
>
>Aunque [!DNL Target] admite cookies de dominio cruzado de origen y de terceros, solo se recomiendan las cookies de origen de [!DNL Target] para RGPD y CCPA.

### ¿Cómo controla [!DNL Target] la gestión de consentimiento?  {#section_C86BF5EE4FAA47039659850E7594A6BA}

El RGPD y la CCPA no cambian cuándo debe obtener el consentimiento, sino cómo obtenerlo. La estrategia de consentimiento de cada cliente depende de sus prácticas de recopilación y uso de datos y de su política de privacidad. La gestión de consentimiento no es compatible y no debería buscarse mediante [!DNL Target] para RGPD y CCPA.

[!DNL Adobe] no ofrece actualmente una solución de administración de consentimiento, pero hay diversas herramientas en desarrollo en el mercado para satisfacer algunos de los nuevos requisitos. Para obtener más información sobre las herramientas de privacidad en general, incluidos los administradores de consentimiento, consulte la [Informe de proveedor técnico de privacidad de 2017](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) en el *Asociación Internacional de Profesionales de la Privacidad (iaap)* sitio web.

[!DNL Target] proporciona compatibilidad con la funcionalidad de inclusión a través de [!DNL Adobe Experience Platform] para respaldar su estrategia de gestión del consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de [!DNL Target]. También hay una opción a través de [!DNL Adobe Experience Platform] para aprobar previamente la etiqueta de [!DNL Target]. El uso de [!DNL Adobe Experience Platform] es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en [!DNL Adobe Experience Platform] para ocultar elementos seleccionados de su página antes del [!DNL Target] la activación que puede resultar útil como parte de su estrategia de consentimiento.

Para obtener más información sobre el RGPD, la CCPA y [!DNL Adobe Experience Platform], consulte [El RGPD y la biblioteca JavaScript de privacidad de Adobe](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). Consulte también la *Inclusión de Adobe Target y Adobe Experience Platform* sección anterior.

### ¿Envía `AdobePrivacy.js` información a la API del RGPD? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *no* envía esta información a la API. Debe hacerlo el cliente. Esta biblioteca proporciona únicamente los ID almacenados en el navegador para ese visitante concreto.

### Qué hace `removeIdentities` remove? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *elimina únicamente* esas identidades del navegador, y solo depende de si la [!DNL Adobe] solución de lo ha implementado.

Por ejemplo, [!DNL Target] elimina las cookies que almacenan sus ID, pero [!DNL Adobe Audience Manager] (AAM) no elimina el ID demdex, que se guarda en una cookie de terceros.

### Qué información debe incluirse en una [!DNL Target] ¿Solicitud de RGPD o de CCPA? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Además de los requisitos del Servicio de privacidad central, un mensaje de RGPD o de CCPA válido para [!DNL Target] contiene lo siguiente:

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

### Qué tipos de respuestas puedo esperar de [!DNL Target] a través de la API RGPD? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Estado de la solicitud | [!DNL Target] Mensaje de respuesta | Situación |
|--- |--- |--- |
| Procesando | Procesando | [!DNL Target] ha recibido la solicitud de RGPD o de CCPA y la está procesando. |
| Completado | No aplicable: el contexto de la empresa no es aplicable | El ID de IMS de la solicitud de RGPD o de CCPA no está asignado a ninguna [!DNL Target] cliente.<br>Algunas empresas tienen varios ID de IMS. Enviar el ID de IMS donde [!DNL Target] está aprovisionado. |
| Completado | No aplicable: no se encontró el contexto del usuario | El ID proporcionado en la solicitud de RGPD o de CCPA para el visitante o sujeto de datos específico no está presente en la variable [!DNL Target] almacén de perfiles.<br>Este resultado también devuelve si intenta enviar un tipo de ID de espacio de nombres que no sea compatible con [!DNL Target] (consulte más arriba cuáles son los ID compatibles). |
| Error | Mensaje de error (los detalles dependen del tipo de error) | Error al recuperar o eliminar el perfil objeto de los datos solicitados.<br>Error al cargar en Azure la solicitud de acceso. |

### Qué respuesta hace [!DNL Target] enviar a la API RGPD para una solicitud de acceso? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Las respuestas a solicitudes de datos de acceso contienen un resumen del perfil de [!DNL Target] para el visitante en cuestión. Esta devolución se envía a la variable [!DNL Experience Cloud] La API del RGPD, que a su vez envía una respuesta a los responsables del tratamiento de datos.

Una respuesta de API de acceso para [!DNL Target] de muestra tendrá un aspecto similar a la siguiente:

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
| jobId | Indica el ID del trabajo del RGPD o de la CCPA a partir de la API del RGPD central. |
| imsOrgID | Proporciona un identificador único para su empresa. |
| namespace | También conocido como la fuente de datos. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?&quot; en este tema. |
| type | El tipo de ID para el cual solicitó acceso de datos del RGPD o de la CCPA. [!DNL Target] acepta varios tipos de ID, algunos de los cuales son estándar y algunos son específicos de [!DNL Target]. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?&quot; en este tema. |
| value | El ID de la fuente de datos/espacio de nombres. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?&quot; para valores aceptados. |
| integration code | Los códigos de integración son nombres descriptivos para las fuentes de datos y ayudarle a seguir sus fuentes de datos con más facilidad que con los ID de fuentes de datos. |

Cuando se proporcionan varios valores para identificar perfiles, cada identificador válido tiene un archivo de perfil. Se envían uno o más archivos de perfil al RGPD central de Azure Blob a través de la API central del RGPD, con el formato de [!DNL Target] Respuesta JSON de perfil.

Un JSON de perfil de [!DNL Target] de muestra podría parecerse al siguiente ejemplo:

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
| Sample_Parameter | El Responsable de datos carga o proporciona directamente gran cantidad de información en el perfil de [!DNL Target]. En este ejemplo, se cargó un parámetro en el perfil de [!DNL Target] con la API de actualización de perfil. Para obtener más información, consulte [Métodos para obtener datos en [!DNL Target]](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo estándar incluye la hora del día correspondiente a la visita de retorno más reciente de un usuario. |
| firstSessionStart | Este campo estándar incluye la hora del día en que comenzó la primera sesión del usuario. |
| user.sessionCountScript | El Responsable de datos carga o proporciona directamente gran cantidad de información en el perfil de [!DNL Target]. En este ejemplo, un script de perfil está incrementando el número de sesiones que este visitante realizó en el sitio del responsable del tratamiento de datos. Para obtener más información, consulte [Atributos de script de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Este ejemplo de código es una versión abreviada de un [!DNL Target] JSON de perfil para ilustrarlo. Muchos de los campos del perfil de [!DNL Target] no son estándar. El resultado obtenido depende de la información que contenga ese perfil del visitante específico.

### Does [!DNL Target] ¿admite la confusión de IP? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] admite la ocultación de la IP si se decide utilizar dicha ocultación como parte de la estrategia de implementación del RGPD o de la CCPA. Para obtener más información, consulte  [Privacidad](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).

### ¿Debo hacer algo para evitar que mis datos se compartan o vendan a terceros?

[!DNL Target] no permite a los clientes compartir o vender datos directamente desde [!DNL Target] a terceros, por lo que no hay exclusión de la venta para [!DNL Target].
