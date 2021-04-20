---
keywords: implementar;implementación;configuración;configuración;parámetros de página
description: Obtenga datos en Target mediante parámetros de página.
title: ¿Cómo puedo obtener datos en Target mediante parámetros de página?
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: 8a12ef3581d3f99f21c0d6d50af0ac09e6aebd4c
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 45%

---

# Parámetros de página

Los parámetros de página (también llamados &quot;parámetros de mbox&quot;) son pares de nombre-valor que se pasan directamente a través del código de página y que no se almacenan en el perfil del visitante para su uso futuro.

Los parámetros de página son útiles para enviar datos de página a Target que no es necesario almacenar con el perfil del visitante para un uso de segmentación futuro. Estos valores, en cambio, se utilizan para describir la página o la acción realizada por el usuario en la página específica.

## Formato

Los parámetros de página se pasan a Target a través de una llamada de servidor como un par de nombre-valor de la cadena. Los nombres y valores del parámetro se pueden personalizar, aunque hay algunos “nombres reservados” para usos específicos.

### Ejemplos

* `page=productPage`

* `categoryId=homeLoans`

## Casos de uso de ejemplo

* **Páginas** de producto: Enviar información sobre el producto específico visualizado (este método es el funcionamiento de Recommendations)
* **Detalles** del pedido: Enviar ID de pedido, orderTotal, etc., para la recopilación de pedidos
* **Afinidad de la categoría**: envía información visualizada por categorías a Target para dar a conocer la afinidad del usuario con categorías concretas de sitios.
* **Datos de terceros**: envía información de fuentes de datos de terceros, como proveedores de segmentación por tiempo, datos de la cuenta (por ejemplo, DemandBase), datos demográficos (por ejemplo, Experian) y más.

## Ventajas del método

Los datos se envían a Target en tiempo real y se pueden utilizar en la misma llamada de servidor en la que ingresan los datos.

## Advertencias

* Se requiere la actualización del código de la página (directamente o a través de un sistema de administración de etiquetas).
* Si los datos deben utilizarse para la segmentación en una llamada posterior a una página o servidor, deben traducirse a un script de perfil.
* Las cadenas de consulta solo pueden contener caracteres según el [estándar Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Además de los caracteres mencionados en el sitio IETF, Target permite los siguientes caracteres en cadenas de consulta:

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   Todo lo demás debe tener codificación URL. El estándar especifica el siguiente formato ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), como se ilustra a continuación:

   ![](assets/ietf1.png)

   O, la lista completa para más simplicidad:

   ![](assets/ietf2.png)

## Ejemplos de código

targetPageParamsAll (sustituye los parámetros en todas las llamadas mbox de la página):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (sustituye los parámetros en el mbox global de la página):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parámetros en el código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## Enlaces a información relevante

Recommendations: [implementación según el tipo de página](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmación del pedido: [Rastrear conversiones](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Afinidad de la categoría: [afinidad de la categoría](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
