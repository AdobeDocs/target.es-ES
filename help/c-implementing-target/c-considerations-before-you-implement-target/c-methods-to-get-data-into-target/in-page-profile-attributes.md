---
keywords: implementar;implementación;configuración;configuración;parámetro de página
description: Obtenga datos en [!DNL Target] mediante atributos de perfil en página.
title: ¿Cómo puedo obtener datos en  [!DNL Target] mediante el uso de atributos de perfil en la página?
feature: Implementación
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 56%

---

# Atributos de perfil en página

Los atributos de perfil en página en [!DNL Adobe Target] (también denominados &quot;atributos de perfil en mbox&quot;) son pares de nombre-valor pasados directamente a través del código de página que se almacenan en el perfil del visitante para uso futuro.

Los atributos de perfil en página permiten que los datos específicos del usuario se almacenen en el perfil de Target para una posterior segmentación.

## Formato

Los atributos de perfil en página pasan a Target a través de una llamada de servidor como un par de nombre-valor de cadena con el prefijo “perfil” antes del nombre del atributo.

Los nombres y valores del atributo se pueden personalizar, aunque hay algunos “nombres reservados” para usos específicos.

### Ejemplos

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## Casos de uso de ejemplo

* **Información de inicio de sesión**: comparta con Target datos con información que no permita identificar personalmente a los usuarios en función del inicio de sesión del usuario. Estos datos pueden ser el estado de pertenencia, el historial de pedidos o más.
* **Información de la tienda**: hace el seguimiento de cuál es la ubicación de la tienda preferida de este usuario.
* **Interacciones anteriores**: hace el seguimiento de las acciones realizadas anteriormente por el usuario en el sitio para proporcionar datos para una futura personalización.

## Ventajas del método

Los datos se envían a Target en tiempo real y se pueden utilizar en la misma llamada de servidor en la que entran los datos.

## Advertencias

Se requieren actualizaciones del código de la página (directamente o a través de un sistema de administración de etiquetas).

Los atributos y los valores son visibles en las llamadas de servidor, para que el visitante pueda ver los valores. Si se comparte información como rangos de crédito u otra información potencialmente privada, este método puede no ser el mejor.

## Ejemplos de código

targetPageParamsAll (sustituye los atributos en todas las llamadas mbox de la página):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (sustituye los atributos en el mbox global de la página):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Atributos en el código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## Enlaces a información relevante

[Atributos de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Perfil del visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
