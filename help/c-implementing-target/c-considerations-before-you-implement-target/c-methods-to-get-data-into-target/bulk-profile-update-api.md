---
keywords: implementar;implementación;configuración;configuración;actualización de perfiles en lote
description: Obtenga datos en [!DNL Target] mediante la API de actualización de perfiles en lote.
title: ¿Cómo puedo obtener datos en [!DNL Target] usando la API de actualización de perfiles en lote?
feature: Implementación
role: Developer
exl-id: 068658fc-7082-425a-87c1-dd0de03cdc71
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 79%

---

# API de actualización de perfiles en lote

Mediante API, envíe un archivo .csv a [!DNL Adobe Target] con actualizaciones de perfil del visitante para muchos visitantes. Cada perfil de visitante se puede actualizar con varios atributos de perfil en página con una llamada.

Esta opción es similar a Atributos del cliente con algunas diferencias:

* Los atributos de cliente utilizan una carga FTP, mientras que la API de actualización de perfiles en lote de Target utiliza una API HTTP POST.
* Los datos de atributos del cliente se pueden compartir con Analytics. La actualización de perfiles en lote solo se puede usar en Target.
* La compatibilidad de los atributos del cliente para crear un perfil para un usuario Target todavía no se ha constatado. La API de actualización de perfiles en lote solo actualiza los perfiles de Target existentes.
* Los atributos del cliente requieren el uso del Experience Cloud ID (ECID). La API de actualización de perfiles en lote requiere el ID de TNT o el `mbox3rdPartyId`.
* No se pueden enviar los siguientes caracteres en `mbox3rdPartyID`: signo más (+) y barra diagonal (/).

## Formato

El archivo .csv debe hacer referencia a cada visitante a través de su PCID de Target o mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite. Todos los atributos o valores del perfil se crean y actualizan a través de la API. En la documentación de la API encontrará detalles sobre el formato.

## Casos de uso de ejemplo

Su CRM u otro sistema interno almacena datos valiosos sobre sus visitantes que le interesa actualizar sistemáticamente en Target sin exponer los datos de perfil en la implementación de su página.

## Ventajas del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

## Advertencias

El tamaño del archivo en lote debe ser inferior a 50 MB. Además, el número total de filas no puede superar las 500 000 filas por carga.

No hay ningún límite en el número de filas que puede cargar en lotes consecutivos en un período de 24 horas. Sin embargo, el proceso de ingestión puede acelerarse durante el horario laboral para garantizar que otros procesos se ejecuten de forma eficaz.

Las [actualizaciones de llamadas en lote V2](https://developers.adobetarget.com/api/#updating-profiles) consecutivas   sin llamadas mbox intermedias para los mismos ID de terceros ignoran las propiedades actualizadas en la primera actualización de la llamada en lote.

## Ejemplos de código

Consulte [Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles).

### Enlaces a información relevante

[Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)
