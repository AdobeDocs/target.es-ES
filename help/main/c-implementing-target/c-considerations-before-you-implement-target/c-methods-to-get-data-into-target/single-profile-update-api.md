---
keywords: implementar;implementación;configuración;configuración;actualización de perfil único
description: Obtener datos en [!DNL Target] uso de la API de actualización de perfil único.
title: ¿Cómo puedo obtener datos en [!DNL Target] ¿Usar la API de actualización de perfil único?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 44%

---

# API de actualización de perfil único

Casi idéntico a la API de actualización de perfiles en lote, pero un perfil de visitante se actualiza a la vez, en línea en la llamada de API en lugar de con un archivo .csv.

## Formato

El visitante se debe identificar a través del valor mboxPC de Target o del valor mboxThirdPartyId. El Experience Cloud ID (ECID) no se admite.

## Casos de uso de ejemplo

Desea actualizar Target en tiempo real cuando un visitante realiza alguna acción sin conexión. Las acciones pueden incluir llegar a un centro de llamadas, financiar un préstamo, usar una tarjeta de fidelidad en una tienda, acceder a un quiosco, etc.

## Ventajas del método

No hay ningún límite en la cantidad de atributos del perfil.

Los atributos de perfil enviados a través del sitio se pueden actualizar a través de la API y viceversa.

## Advertencias

Límite de 1 000 000 (1 millón) de llamadas a la API por período de 24 horas

Solo se actualiza el perfil. No se puede crear un perfil para un usuario potencial que Target todavía tiene que ver.

## Ejemplos de código

Se admiten GET y POST.  `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [Actualización de perfiles](https://developers.adobetarget.com/api/#updating-profiles)

