---
keywords: rgpd;ue;unión europea;privacidad;faq;preguntas frecuentes;ley de privacidad del consumidor de california;ccpa;privacidad;protección de datos;exclusión;exclusión;gobierno;regulación
description: Obtenga información sobre  [!DNL Target]  y el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad.
title: ¿Cómo administra  [!DNL Target]  los reglamentos de protección de datos y privacidad?
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '2231'
ht-degree: 98%

---

# Reglamentos de protección de datos y privacidad

Información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad internacionales. Descubra cómo afectan estas regulaciones a su organización y [!DNL Adobe Target].

## Información general sobre el Reglamento General de Protección de Datos (RGPD)  {#topic_DE567ECB6C944695AEE5073889F1AEA9}

El 25 de mayo de 2018, entró en vigor el RGPD de la Unión Europea. Para obtener más información sobre qué significa esto para usted, consulte [RGPD y su empresa](https://business.adobe.com/es/privacy/general-data-protection-regulation.html).

Cuando [!DNL Adobe] proporciona software y servicios a una empresa, [!DNL Adobe] actúa como Procesador de datos de cualquier dato personal que procese y almacene en la provisión de dichos servicios. Como Procesador de datos, [!DNL Adobe] procesa los datos personales de acuerdo con los permisos e instrucciones que su empresa proporcione (y que pueden establecerse, por ejemplo, en el acuerdo entre su empresa y [!DNL Adobe]).

Como responsable del tratamiento de datos, usted determina los datos personales que [!DNL Adobe] trata y almacena en su nombre. Si usa soluciones de [!DNL Adobe Experience Cloud], [!DNL Adobe] podría alojar datos personales en su nombre según las soluciones que use y la información que decida enviar a su cuenta de [!DNL Adobe Experience Cloud]. Si desea ver una lista detallada de ejemplos, consulte [Privacidad de Adobe Experience Cloud](https://www.adobe.com/es/privacy/experience-cloud.html#collect).

[!DNL Adobe Experience Cloud] proporciona API preparadas para RGPD para Controladores de datos que les permite completar las tareas siguientes:

* Acceder a información del interesado almacenada dentro de [!DNL Target]
* Eliminar información del interesado almacenada dentro de [!DNL Target]

Para obtener más información, consulte:

* [Resumen de Privacy Service de Adobe](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es){target=-blank}
* [Guía de API de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es){target=_blank}
* [Información general sobre la IU de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=es){target=_blank}

## Información general sobre la Ley de privacidad del consumidor de California (CCPA)

La Ley de privacidad del consumidor de California (CCPA) segura a los consumidores californianos nuevos derechos relacionados con su información personal e impone responsabilidades de protección de datos a determinadas entidades que realizan negocios en California. La CCPA entró en vigor el 1 de enero de 2020.

La ley asegura varios derechos clave para los californianos, incluidos los derechos a:

* Solicitar información (acceso a datos)
* Excluirse de la venta de información personal (un derecho con una definición muy amplia para evitar que se comparta información con terceros)
* Eliminar información personal
* Saber que la información personal se está revelando o vendiendo

Si estuvo al tanto de la ley de privacidad de Europa (RGPD) del año pasado, algunos de estos derechos le resultarán familiares y podrá aprovechar gran parte del trabajo realizado.

>[!NOTE]
>
>El acceso a los datos y su eliminación, tal como se aplican a la CCPA, siguen el mismo proceso que para el RGPD.

## Inclusión de Adobe [!DNL Target] y [!DNL Adobe Experience Platform] {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] proporciona soporte de funcionalidad opcional a través de etiquetas en [!DNL Adobe Experience Platform] para ayudar a respaldar su estrategia de administración de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de [!DNL Target]. También hay una opción a través de [!DNL Adobe Experience Platform] para aprobar previamente la etiqueta de [!DNL Target]. Para activar Opt-in en la biblioteca at.js de [!DNL Target], debe utilizar `targetGlobalSettings` y agregar la configuración `optinEnabled=true`. En [!DNL Adobe ExperiencePlatform], tendrá que seleccionar “habilitar” en la lista desplegable de [!UICONTROL Inclusión del RGPD] en la vista de instalación de extensión. Consulte [Implementación [!DNL Target] using [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} para obtener más información.

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
>El uso de [!DNL Adobe Experience Platform] es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en [!DNL Adobe Experience Platform] para ocultar elementos seleccionados de su página antes de la activación de [!DNL Target] que son útiles para su estrategia de consentimiento.

Hay tres escenarios a considerar cuando se usa la inclusión:

1. **La etiqueta de [!DNL Target] se aprobó previamente mediante [!DNL Adobe Experience Platform] (o [!DNL Target] que el titular de los datos haya aprobado previamente):** La etiqueta de [!DNL Target] no se dispone para el consentimiento y funciona como se espera.
1. **La [!DNL Target] etiqueta de NO está aprobada previamente y `bodyHidingEnabled` es FALSE:** la [!DNL Target] etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Después de recibir el consentimiento, se llama a [!DNL Target], y el contenido personalizado está disponible para el sujeto de los datos (visitante). Debido a que solo el contenido predeterminado está disponible antes del consentimiento, es importante usar una estrategia adecuada, como una página de inicio que cubra cualquier parte de la página o contenido que pueda ser personalizado. Este proceso asegura que la experiencia se mantenga consistente para el sujeto de los datos (visitante).
1. **La [!DNL Target] etiqueta de NO está aprobada previamente y `bodyHidingEnabled` es TRUE:** la [!DNL Target] etiqueta de se activa solo después de que se haya obtenido el consentimiento del cliente. Antes de recopilar el consentimiento, solo está disponible el contenido predeterminado. Sin embargo, debido a que `bodyHidingEnabled` se establece como true, `bodyHiddenStyle` dicta qué contenido de la página está oculto hasta que se dispara la etiqueta de [!DNL Target] (o el sujeto de los datos rechaza la opción Opt-in, en cuyo caso se muestra el contenido predeterminado). De forma predeterminada, `bodyHiddenStyle` se establece en `body { opacity:0;}`, que oculta la etiqueta de cuerpo HTML. A continuación encontrará la configuración de página recomendada por Adobe para que todo el cuerpo de la página, excepto el cuadro de diálogo del administrador de consentimiento, se oculte al colocar el contenido de la página en un contenedor y el cuadro de diálogo del administrador de consentimiento en un contenedor separado. Estos ajustes configuran [!DNL Target] de modo que ocultan únicamente el contenedor de contenido de la página. Consulte [Resumen de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es).

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

### ¿Cuál es la política de [!DNL Adobe] para estas regulaciones? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] ya cumple o está implementando nuestras obligaciones como procesador de datos. Adobe tiene una base sólida de controles de privacidad y seguridad certificados y realizó mejoras de producto con antelación al plazo de mayo de 2018. Los clientes empresariales tienen la responsabilidad de implementar estas mejoras, como así también actualizar cualquier política y procedimiento necesarios.

### ¿Debe mi empresa, como responsable del tratamiento de datos, enviar una solicitud de RGPD o de CCPA para cada solución de [!DNL Adobe Experience Cloud] que utilice? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] ofrece una solución única para que los responsables de datos cumplan los requisitos del RGPD y de la CCPA. Los responsables del tratamiento de datos no necesitan ir directamente a cada una de las soluciones.

Todas las solicitudes de RGPD y CCPA entre soluciones de [!DNL Experience Cloud], incluido [!DNL Target], se realizan a través de una API [!DNL Adobe] central de denominada actualmente API del RGPD. La API completa la solicitud para el conjunto de soluciones de [!DNL Experience Cloud] del responsable de datos.

### ¿Qué información permite [!DNL Adobe] que nuestros clientes eliminen en respuesta a una solicitud del sujeto/usuario? {#section_4B51D00924EC4166B2442218B69214F0}

La información relacionada con un visitante individual dentro de [!DNL Target] está en el Perfil del visitante de [!DNL Target]. [!DNL Target] permite que los clientes eliminen todos los datos asociados con un ID en su perfil del visitante. Para ver ejemplos de los almacenes de datos de perfil de [!DNL Target], consulte [Perfil del visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Los datos agregados o anonimizados (por ejemplo, datos de informe) que no identifican a una persona en particular, o datos que no están relacionados con una persona específica (por ejemplo, datos de contenido) están fuera del alcance de una solicitud de eliminación de usuario.

[!DNL Target] De forma predeterminada, los perfiles del visitante de inactivos durante 90 días se eliminan sin necesidad de realizar acción alguna.

### ¿Qué ID se admiten para ayudar a los clientes a realizar una solicitud de eliminación y acceso de RGPD o de CCPA para [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] admite los siguientes tipos de ID para localizar un perfil de cliente:

| ID de usuario | Tipo de ID de espacio de nombres | ID de espacio de nombres | Definición |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID], conocido anteriormente como ID de visitante o Experience Cloud ID. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de TnT/ID de cookie(TNTID) | Estándar | 9 | [!DNL Target] Identificador de establecido como cookie en el navegador del visitante. Puede usar la API de JavaScript para ubicar este ID (consulte los detalles más abajo). |
| ID de terceros/ID de administración de la relación con los clientes. (THIRDPARTYID) | [!DNL Target]-Específico | N/A | Si proporciona a [!DNL Target] su administración de la relación con los clientes u otra información de identificador único para sus clientes. |

>[!NOTE]
>
>Aunque [!DNL Target] admite cookies de dominio cruzado de origen y de terceros, solo se recomiendan las cookies de origen de [!DNL Target] para RGPD y CCPA.

### ¿Cómo controla [!DNL Target] la gestión de consentimiento?  {#section_C86BF5EE4FAA47039659850E7594A6BA}

RGPD y CCPA no afectan al momento en el que se requiere consentimiento, sino que cambia el modo en que se consigue. La estrategia de consentimiento de cada cliente depende de su forma de recopilar y utilizar los datos, así como de su política de privacidad. La gestión de consentimiento no es compatible y no debería buscarse mediante [!DNL Target] para RGPD y CCPA.

[!DNL Adobe] no ofrece actualmente una solución de administración de consentimiento, pero hay diversas herramientas en desarrollo en el mercado para satisfacer algunos de los nuevos requisitos. Para obtener más información sobre herramientas de privacidad en general, incluidos los administradores de consentimiento, consulte el [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) disponible en el sitio web de la *International Association of Privacy Professionals (iapp)*.

[!DNL Target] proporciona soporte de funcionalidad de inclusión a través de [!DNL Adobe Experience Platform] para ayudar a su estrategia de administración de consentimiento. La funcionalidad de inclusión permite a los clientes controlar cómo y cuándo se inicia la etiqueta de [!DNL Target]. También hay una opción a través de [!DNL Adobe Experience Platform] para aprobar previamente la etiqueta de [!DNL Target]. El uso de [!DNL Adobe Experience Platform] es el enfoque recomendado para administrar inclusiones. Existe un control granular adicional en [!DNL Adobe Experience Platform] para ocultar elementos seleccionados de su página antes de la activación de [!DNL Target] que son útiles como parte de su estrategia de consentimiento.

Para obtener más información sobre el RGPD, la CCPA y [!DNL Adobe Experience Platform], consulte [la Biblioteca JavaScript de privacidad de Adobe y RGPD](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). Además, consulte la *inclusión de Adobe Target y Adobe Experience Platform* en la sección superior.

### ¿Envía `AdobePrivacy.js` información a la API del RGPD? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *no* envía esta información a la API. Debe hacerlo el cliente. Esta biblioteca proporciona únicamente los ID almacenados en el navegador para ese visitante concreto.

### ¿Qué elimina `removeIdentities`? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *elimina únicamente* esas identidades del navegador, y solo depende de si la [!DNL Adobe] solución de lo ha implementado.

Por ejemplo, [!DNL Target] elimina las cookies que almacenan sus ID, pero [!DNL Adobe Audience Manager] (AAM) no elimina el ID demdex, que se guarda en una cookie de terceros.

### ¿Qué información debe incluirse en una solicitud de RGPD o CCPA de [!DNL Target]? {#section_D29A4744AE6344E68AD7710B185FD6D0}

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

### ¿Qué tipos de respuesta puedo esperar de [!DNL Target] a través de la API del RGPD?  {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Estado de la solicitud | Mensaje de respuesta de [!DNL Target] | Situación |
|--- |--- |--- |
| Procesando | Procesando | [!DNL Target] ha recibido la solicitud de RGPD o de CCPA y la está procesando. |
| Completado | No aplicable: el contexto de la empresa no es aplicable | El ID de IMS de la solicitud de RGPD o de CCPA no está asignado a ningún cliente de [!DNL Target].<br>Algunas empresas tienen varios ID de IMS. Envíe el ID de IMS donde [!DNL Target] está aprovisionado. |
| Completado | No aplicable: no se encontró el contexto del usuario | El ID proporcionado en la solicitud de RGPD o de CCPA para el visitante o sujeto de datos específico no está presente en el almacén de perfiles de [!DNL Target].<br>Este resultado también devuelve si intenta enviar un tipo de ID de espacio de nombres no compatible con [!DNL Target] (consulte más atrás cuáles son los ID compatibles). |
| Error | Mensaje de error (los detalles dependen del tipo de error) | Error al recuperar o eliminar el perfil objeto de los datos solicitados.<br>Error al cargar en Azure la solicitud de acceso. |

### ¿Qué respuesta envía [!DNL Target] a la API de RGPD para una solicitud de acceso? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Las respuestas a solicitudes de datos de acceso contienen un resumen del perfil de [!DNL Target] para el visitante en cuestión. Esta devolución se envía a la API del RGPD de [!DNL Experience Cloud], que a su vez envía una respuesta a los Responsables de datos.

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
| namespace | También conocido como la fuente de datos. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?“ en este tema. |
| type | El tipo de ID para el cual solicitó acceso de datos del RGPD o de la CCPA. [!DNL Target] acepta varios tipos de ID, algunos de los cuales son estándares y algunos son específicos de [!DNL Target]. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?“ en este tema. |
| value | El ID de la fuente de datos/espacio de nombres. Consulte “¿Cuáles son los ID compatibles para ayudar a los clientes a realizar una solicitud de acceso y eliminación de RGPD o de CCPA para [!DNL Target]?“ para valores aceptados. |
| integration code | Los códigos de integración son nombres descriptivos para las fuentes de datos y ayudarle a seguir sus fuentes de datos con más facilidad que con los ID de fuentes de datos. |

Cuando se proporcionan varios valores para identificar perfiles, cada identificador válido tiene un archivo de perfil. Uno o varios de los archivos de perfil se envían al RGPD central de Azure Blob mediante la API central del RGPD, con el formato de una respuesta JSON de perfil de [!DNL Target]

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
| Sample_Parameter | El Responsable de datos carga o proporciona directamente gran cantidad de información en el perfil de [!DNL Target]. En este ejemplo, se cargó un parámetro en el perfil de [!DNL Target] con la API de actualización de perfil. Para obtener más información, consulte [Métodos para obtener datos en [!DNL Target]](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/). |
| user.ReturnTimeOfDay | Este campo estándar incluye la hora del día correspondiente a la visita de retorno más reciente de un usuario. |
| firstSessionStart | Este campo estándar incluye la hora del día en que comenzó la primera sesión del usuario. |
| user.sessionCountScript | El Responsable de datos carga o proporciona directamente gran cantidad de información en el perfil de [!DNL Target]. En este ejemplo, un script de perfil está incrementando el número de sesiones que este visitante realizó en el sitio del responsable del tratamiento de datos. Para obtener más información, consulte [Atributos de script de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Este ejemplo de código es una versión abreviada de un JSON de perfil de [!DNL Target] para ilustrarlo. Muchos de los campos del perfil de [!DNL Target] no son estándar. El resultado obtenido depende de la información que contenga ese perfil del visitante específico.

### ¿Admite [!DNL Target] la ocultación de la IP?  {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] admite la ocultación de la IP si se decide utilizar dicha ocultación como parte de la estrategia de implementación del RGPD o de la CCPA. Para obtener más información, consulte   [Privacidad](https://developer.adobe.com/target/before-implement/privacy/privacy/).

### ¿Debo hacer algo para evitar que mis datos se compartan o vendan a terceros?

[!DNL Target] no permite a los clientes compartir o vender datos directamente desde [!DNL Target] a terceros, por lo que no hay exclusión de la venta para [!DNL Target].
