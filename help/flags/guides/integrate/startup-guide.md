---
title: Guía de inicio
description: Siga estos pasos para integrar su aplicación con Banderas, desde solicitar acceso a crear su primera marca de características.
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 1%

---

# Guía de inicio {#startup-guide}

Siga estos pasos para integrar Flags en su aplicación.

## Paso 1: Solicitar acceso {#step-1-access}

Solicite acceso a la consola Banderas y únase a su equipo. Consulte [Solicitar acceso](../console/request-access.md) para obtener instrucciones paso a paso.

## Paso 2: Incorporar la aplicación {#step-2-onboard}

Después de obtener acceso, inicie sesión en la consola Indicadores y compruebe que la aplicación aparece en la lista de su equipo. Si no es así, pídale al administrador del equipo que lo añada. Consulte [Incorporar su aplicación](../applications/onboard-your-application.md).

Antes de la incorporación, prepare lo siguiente:

| Requisito | Detalles |
|---|---|
| **ID de aplicación** | Identificador de cliente único que se utiliza al llamar a las API de indicadores. Utilice el ID de cliente existente de la aplicación donde esté disponible. |
| **Clientes del lado del servidor** | Si se integra con un SDK del lado del servidor, necesita un ID de cliente de administración con los permisos adecuados. |
| **Clientes de escritorio** | Se puede utilizar un código de producto y una versión de producto en lugar de un ID de cliente. |

## Paso 3: Consiga sus credenciales {#step-3-credentials}

Las credenciales que necesita dependen de la ruta de integración:

* **Web y móvil (basado en etiquetas):** Use el **identificador de archivo de entorno** de su propiedad de etiquetas publicada. Consulte el paso 4a para saber cómo conseguirlo.
* **SDK del lado del servidor:** Solicite un **ID de cliente de token de servicio** y pida a la lista de permitidos de compatibilidad con indicadores que antes de poder realizar llamadas de API desde SDK.
* **Escritorio:** Se puede usar un código de producto y una versión de producto en lugar de un identificador de cliente.

## Paso 4: Integración con un SDK {#step-4-integrate}

Siga los [pasos de integración](integration-steps.md) para su tipo de aplicación. Elija la ruta que se ajuste a la pila:

* **Servicios web** → Java SDK o Node.js SDK
* **Aplicaciones web y móviles** → AEP Mobile SDK; consulte las guías de [Android](../sdk-releases/android/android-extension-integration-guide.md) y [iOS](../sdk-releases/ios/ios-extension-integration-guide.md)
* **Aplicaciones de escritorio** → SDK (próximamente)

## Paso 4a: Configurar la recopilación de datos y publicar la configuración {#step-4a-data-collection}

Si realiza la integración con un enfoque basado en etiquetas (web o móvil), configure la propiedad de etiquetas antes de inicializar SDK:

1. En [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection), abra su propiedad móvil o web.
1. Instale la extensión **Edge Network** y, a continuación, la extensión **Despliegue de experiencia** (en ese orden).
1. Seleccione su **flujo de datos** (debe incluir el conjunto de datos de Customer Journey Analytics) y su dominio Edge.
1. Publique la configuración mediante **Desarrollo → ensayo → producción**.
1. Copie el **id. de archivo de entorno** de la ficha **Entornos**; utilizará esto para inicializar SDK.

>[!IMPORTANT]
>
>En el entorno **staging**, agregue como prefijo el identificador del archivo de entorno `staging/`, es decir, use `staging/<environmentId>`. En **producción**, use directamente el ID del archivo de entorno.

## Paso 5: Crear y probar el primer indicador de funcionalidad {#step-5-feature-flag}

Una vez completada la integración, cree el primer indicador de funcionalidad en la consola y pruébelo:

* [Creación de la primera marca de funcionalidad](../feature-flags/create-your-first-feature-flag.md)

## Consulte también {#see-also}

* [Integración de indicadores en la aplicación](integrating-in-your-app.md)
* [Pasos de integración](integration-steps.md)
* [SDK](sdks.md)

<!-- -->
