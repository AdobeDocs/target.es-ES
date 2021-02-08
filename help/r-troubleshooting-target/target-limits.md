---
keywords: límite de caracteres;parámetros de mbox;api de envío por lotes;parámetros de perfil;límites;perfiles integrados;máximo;límite;restricción;carácter;mejor práctica;orderid;orderTotal;mbox3rdPartyID;categoría;categoryID;solución de problemas
description: Vista de una lista de límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.
title: Revisar una lista de límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.
feature: Troubleshooting
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 67%

---


# Límites

Información sobre los límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de [!DNL Adobe Target].

>[!NOTE]
>
>Los límites listados a continuación deben considerarse límites “duros” a menos que se especifique como “recomendado”.
>
>Cuando se aproximan o se exceden los límites designados como “recomendados”, el rendimiento puede ralentizarse. Si la interfaz tarda tiempo en cargarse también puede ser debido a una actividad muy compleja, como por ejemplo muchas audiencias, objetivos y experiencias en la misma actividad.
>
>Las actividades muy complejas deben revisarse con [!DNL Adobe] consultoría y probarse en un entorno limitado antes de ser liberadas a producción.

## Actividades

**Límite recomendado**: 10 000 actividades activas.

**Límite** recomendado: 10.000 actividades guardadas activas (y no finalizadas).

## Nombres de actividades

**Límite**: 250 caracteres.

## Nombres de audiencia

**Límite**: 255 caracteres.

## Audiencias

**Límite**: 50 audiencias por mbox, métrica o experiencia.

## Audiencias, reutilizables por cuenta

**Límite recomendado**: 20,000 audiencias.

## Parámetro categoryId

**Límite**: 128 caracteres.

## Nombres de atributos del cliente

**Límite**: 250 caracteres a través de la fuente o la API.

## ID de alias de atributo de cliente

**Límite** 50 caracteres.

## Atributos del cliente, carga

* **Tamaño máximo de archivo para cada carga mediante el método** HTTP: 100 MB.
* **tamaño máximo de archivo para cada carga mediante el método** FTP: 4 GB.
* **Número de atributos permitidos para la suscripción**: 5 para  [!DNL Target Standard] y 200 para  [!DNL Target Premium].

## Entidades

El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99.

## Atributos personalizados de entidad

Puede incluir hasta 100 atributos de entidad personalizados

**Límite**: La longitud máxima de caracteres depende del idioma.

* 15 000 caracteres (un solo valor, uno y dos bytes)
* 500 valores, 100 caracteres por valor (varios valores)

La longitud máxima de los atributos personalizados de entidad de un solo valor es de 15 000 caracteres (para lenguajes con codificación UTF-8 de uno y dos bytes, como inglés y otros alfabetos latinos) o 10 000 caracteres (para lenguajes con codificación UTF-8 de 3 bytes como chino, japonés y coreano).

Los atributos personalizados de entidad de varios valores no pueden contener más de 500 valores. Cada valor individual está limitado a 100 caracteres. El número total de caracteres en todos los valores debe cumplir las limitaciones de la longitud máxima de atributos personalizados de entidad de un solo valor (véase arriba).

## Parámetros de entityid

**Límite**: 1000 caracteres.

## Excludedids {#excludedid}

**Límite**: 5 KB para solicitudes POST. 2.083 caracteres menos la longitud de la URL para las solicitudes GET.

Para las solicitudes GET, aunque el límite del back-end es 5 KB, debido al hecho de que Microsoft Internet Explorer limita la dirección URL a 2.083 caracteres, el límite realista es de 2.083 caracteres menos la longitud actual de la dirección URL.

## Nombres de experiencias

**Límite**: 50 caracteres.

## Experiencias por actividad

**Límite**: 2000 experiencias por Segmentación de experiencias (XT), Prueba A/B, Prueba multivariada (MVT) y actividad de Segmentación automática.

30 000 experiencias por actividad de Automated Personalization (AP).

## Valor de atributo de perfil In-mbox

**Límite**: 256 caracteres.

Los valores más largos que ese número se truncan.

## Nombres de perfiles In-mbox

**Límite**: 128 caracteres.

## nombres de mbox

**Límite**: 250 caracteres.

## Parámetros de mbox

**Límite**: Los límites siguientes se aplican a los parámetros de mbox:

Para llamadas de mbox estándar:
* Parámetros de mbox: 500 parámetros por mbox.
* Parámetros de perfil: 500 parámetros de perfil por mbox.
* Otros parámetros (URL, URL de referencia, etc.): 50 por mbox para cada tipo de parámetro.

Estos límites se aplican a menos que la solicitud se acorte debido a limitaciones del navegador.

Si utiliza la API de Envío por lotes, el límite es de 50 mboxes por solicitud de lote.

Si utiliza la [API de envío por lotes](https://developers.adobetarget.com/api/#server-side-batch-delivery) en el SDK de Mobile Services, el límite de 50 parámetros de mbox, 50 parámetros de perfil y 50 el resto de tipos de parámetros es una limitación de la propia API. No es posible enviar una solicitud que supere estos valores mediante la API de envío por lotes. Si una solicitud contiene más de estos límites, la API devolverá el siguiente mensaje de error:

&quot;El número de mboxParameters no puede superar los 50.&quot;

Límites establecidos para los extremos:

Lote mbox v2:
* Parámetros de mbox 100
* Longitud máxima del nombre del parámetro de mbox 128
* El valor del parámetro mbox no puede ser nulo
* Valor del parámetro de mbox 5000
* Parámetros de perfil 50
* Longitud máxima del nombre del parámetro de perfil 128
* El valor del parámetro de perfil no puede ser nulo
* Longitud máxima del valor del parámetro de perfil 256

Extremo de API de envío
* Parámetros de mbox 50
* Longitud máxima del nombre del parámetro de mbox 128
* El valor del parámetro mbox no puede ser nulo
* Valor del parámetro de mbox 5000
* Parámetros de perfil 50
* Longitud máxima del nombre del parámetro de perfil 128
* El valor del parámetro de perfil no puede ser nulo
* Longitud máxima del valor del parámetro de perfil 256

## Direcciones URL de peticiones de mbox

**Límite**: 2.083 caracteres.

Este límite se debe a las restricciones de longitud de URL de Microsoft Internet Explorer.

## Parámetro mbox3rdPartyId

**Límite**: 60 caracteres.

## Nombres de ofertas

**Límite**: 250 caracteres.

## Tamaño de oferta

**Límite**: Los límites de tamaño siguientes se aplican a las ofertas:

* 256 kB para ofertas HTML.
* 64 kB para ofertas visuales de la interfaz de usuario.
* 512 kB de la API.

Si usa un mbox global, el límite es para todo el conjunto de contenidos devueltos de la página. La limitación del tamaño de la oferta mejora los tiempos de carga de la página. Si se supera el límite, aparece un mensaje como este:

El contenido de la experiencia es demasiado grande para su entrega. Modifique la experiencia para afectar a menos código de página.

## Ofertas

**Límite recomendado**: 50 000 ofertas totales.

## Parámetro orderId

**Límite recomendado**: 120 caracteres.

## Parámetro orderTotal

**Límite recomendado**: 120 caracteres.

## Parámetro productPurchasedId

**Límite**: 47 caracteres por valor separado por coma y 250 caracteres en total. El sistema puede truncar los valores individuales superiores a 47 caracteres. Las longitudes totales superiores a 250 caracteres pueden resultar en un error de 400.

## Scripts de perfil

**Límite recomendado de secuencias de comandos** de perfil activas: 300

**Límite recomendado del total de secuencias de comandos de perfil por cuenta**: 2.000

**Recommendations para limitar la complejidad** del script de perfil: Las secuencias de comandos de perfil pueden ejecutar un número limitado de instrucciones. Para obtener más información, consulte [Prácticas recomendadas](/help/c-target/c-visitor-profile/profile-parameters.md#best) en *Atributos de Perfil*.

## Propiedades

**Límite recomendado**: 5000 propiedades.

## Informes de audiencias o segmentos

**Límite**: 50 audiencias/segmentos por actividad.

## Cuadro de entrada de perfil de script en la interfaz de usuario de Target

**Límite recomendado**: 2000 caracteres.

Depende del tamaño de la cadena codificada, que puede ser mucho mayor que la cadena sin procesar. Si la cadena es demasiado larga, producirá un error antes de llegar a Adobe Target.

## Nombres de perfiles de secuencia

**Límite**: 50 caracteres.

## Valores de perfil de secuencia de comandos

**Límite**: 2.048 caracteres.

Por motivos de rendimiento, recomendamos un valor de retorno que no tenga más de 256 caracteres.

Para un valor de retorno de cadena, si el tamaño del valor devuelto supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

Para un valor de devolución de matriz, si el tamaño de los valores concatenados de la matriz supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

## Métricas de éxito

**Límite**: 200 por actividad.

## Condiciones de segmentación

**Límite recomendado**: 1000 valores.

Esto hace referencia al número de valores separados por líneas en el área de texto de determinación de objetivos. Por ejemplo, si se escriben 1000 códigos postales en un solo objetivo de código postal.

## Reglas de segmentación

**Límite** recomendado: 2.500 caracteres por valor de regla de objetivo.

**Límite recomendado**: 30 000 valores únicos por audiencia en reglas de segmentación.

**Límite recomendado**: 100 000 valores únicos de reglas de segmentación por actividad.

