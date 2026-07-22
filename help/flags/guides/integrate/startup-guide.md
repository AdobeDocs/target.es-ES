---
title: Guía de inicio
description: Siga estos pasos para integrar su aplicación con Banderas, desde solicitar acceso a crear su primera marca de características.
badge: label="Beta" type="Informative"
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 339de89fff7bb14eb8146d42482b30c86feeedef
workflow-type: tm+mt
source-wordcount: '397'
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

## Paso 3: Obtención del ID de archivo de entorno {#step-3-credentials}

El ID del archivo de entorno que necesita depende de la ruta de integración:

* **Web y móvil (basado en etiquetas):** Use el **identificador de archivo de entorno** de su propiedad de etiquetas publicada. Consulte el paso 4a para saber cómo conseguirlo.

## Paso 4: Integración con un SDK {#step-4-integrate}

Siga la guía de integración para su tipo de aplicación. Elija la ruta que se ajuste a la pila:

* **Aplicaciones web y móviles**: consulte las guías de [Android](../sdk-releases/android/android-extension-integration-guide.md), [iOS](../sdk-releases/ios/ios-extension-integration-guide.md) y [Web](../sdk-releases/web/web-extension-integration-guide.md) en la sección de la guía de integración

## Paso 4a: Configurar la recopilación de datos y publicar la configuración {#step-4a-data-collection}

Si realiza la integración con un enfoque basado en etiquetas (web o móvil), configure la propiedad de etiquetas antes de inicializar SDK:

1. En [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection), cree una [propiedad de etiquetas](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start) si todavía no la tiene, o use una propiedad de etiquetas existente.
1. Abra la propiedad de etiquetas móviles o web y vaya a [Extensiones](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/extensions/overview).
1. Instale y configure la extensión **Edge Network**. Luego instale la extensión **Flags**.
1. Seleccione la **secuencia de datos** (debe incluir el conjunto de datos de Customer Journey Analytics) y configure el dominio de Edge.
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
* [SDK](sdks.md)

<!-- -->
