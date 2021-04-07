---
keywords: implementar;implementación;configuración;configuración;proveedores de datos
description: Obtenga datos en Target mediante proveedores de datos.
title: ¿Cómo puedo obtener datos en Target mediante proveedores de datos?
feature: Implementación
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 66%

---

# Proveedores de datos

Los proveedores de datos son una capacidad que le permite pasar fácilmente datos de terceros a [!DNL Adobe Target].

Nota: Los proveedores de datos requieren at.js 1.3 o posterior.

## Formato

La configuración `window.targetGlobalSettings.dataProviders` es una matriz de proveedores de datos.

Para obtener más información sobre la estructura de cada proveedor de datos, consulte [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Casos de uso de ejemplo

Recabar datos de terceros, por ejemplo, un servicio meteorológico, un DMP o incluso su propio servicio web. Puede usar estos datos para crear audiencias, dirigir contenido y enriquecer el perfil del visitante.

## Ventajas del método

Esta configuración permite a los clientes recopilar información de proveedores de datos de terceros, como Demandbase, BlueKai y servicios personalizados, y pasar los datos a Target como parámetros de mbox en la solicitud global de mbox.

Admite la recopilación de datos de múltiples proveedores a través de solicitudes de desincronización y sincronización.

El uso de este enfoque facilita la administración del parpadeo del contenido predeterminado de la página, al tiempo que incluye tiempos de espera independientes para cada proveedor para limitar el impacto en el rendimiento de la página.

## Advertencias

Si los proveedores de datos agregados a `window.targetGlobalSettings.dataProviders` son asincrónicos, se ejecutan en paralelo. La solicitud de API de visitante se ejecuta en paralelo con las funciones agregadas a `window.targetGlobalSettings.dataProviders` para permitir un tiempo de espera mínimo.

at.js no intenta almacenar en caché los datos. Si el proveedor de datos obtiene datos solo una vez, el proveedor de datos debe asegurarse de que los datos estén en caché y, cuando se invoque la función del proveedor, sirva los datos de caché para la segunda invocación.

## Ejemplos de código

Se pueden encontrar varios ejemplos en [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Enlaces a información relevante

Documentación: [Proveedores de datos](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## Vídeos de formación:

* [Uso de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementación de Proveedores de datos en Adobe Target](https://helpx.adobe.com/es/target/kt/using/dataProviders-atjs-technical-video-implement.html)