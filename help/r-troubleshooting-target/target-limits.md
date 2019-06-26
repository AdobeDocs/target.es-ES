---
description: Información sobre los límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.
keywords: límite de caracteres;parámetros de mbox;api de entrega por lotes;parámetros de perfil;límites;perfiles integrados;límite;máximo;restricción;carácter;práctica recomendada;id de pedido;total del pedido;id de terceros de mbox;categoría;id de categoría
seo-description: Información sobre los límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.
seo-title: Límites
solution: Target
title: Límites
topic: Standard
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Límites{#limits}

Información sobre los límites de caracteres y otros límites (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.

A continuación se indican los límites recomendados. Al aproximarse o superar estos límites, pueden producirse problemas de rendimiento. Si la interfaz tarda tiempo en cargarse también puede ser debido a una actividad muy compleja, como por ejemplo muchas audiencias, objetivos y experiencias en la misma actividad.

Las actividades muy complejas deben ser revisadas por los asesores de Adobe y probadas en un entorno limitado antes de su lanzamiento en producción.

## Nombres de actividades

**Límite**: 250 caracteres.

## Nombres de audiencia

**Límite**: 256 caracteres.

Los valores más largos de 256 caracteres se truncan.

## Parámetro categoryId

**Límite**: 250 caracteres.

## Nombres de atributos del cliente

**Límite**: 128 caracteres.

## ID de alias de atributo de cliente

**Límite de** 50 caracteres.

## Atributos personalizados de entidad

**Límite**: La longitud máxima depende del idioma.

* 15 000 caracteres (un solo valor, idiomas de uno y dos bytes)
* 500 valores, 100 caracteres por valor (varios valores)

La longitud máxima de los atributos personalizados de entidad de un solo valor es de 15 000 caracteres (para idiomas con codificación UTF-8 de uno y dos bytes, como inglés y otros alfabetos latinos) o 10 000 caracteres (para lenguajes con codificación UTF-8 de tres bytes, como chino, japonés y coreano).

Los atributos personalizados de entidad de varios valores no pueden contener más de 500 valores. Cada valor individual está limitado a 100 caracteres. El número total de caracteres en todos los valores debe cumplir las limitaciones de la longitud máxima de atributos de entidad personalizados de un solo valor (véase arriba).

## Parámetros de entityID

**Límite**: 1000 caracteres.

## excludedIds {#excludedid}

**Límite**: 5 kB para solicitudes POST. 2083 caracteres menos la longitud de la URL para las solicitudes GET.

Para las solicitudes GET, aunque el límite del back-end es 5 kB, debido al hecho de que Microsoft Internet Explorer limita la dirección URL a 2083 caracteres, el límite realista es de 2083 caracteres menos la longitud actual de la dirección URL.

## Nombres de experiencias

**Límite**: 20 caracteres.

## Valor de atributo de perfil In-mbox

**Límite**: 256 caracteres.

Los valores más largos que ese número se truncan.

## Perfiles In-mbox en una petición de mbox

**Límite**: 50 perfiles.

Se ignorarán todos los perfiles por encima de 50.

## Nombres de perfiles In-mbox

**Límite**: 128 caracteres.

## Nombres de mbox

**Límite**: 250 caracteres.

## Parámetros de mbox

**Límite**: Los límites siguientes se aplican a los parámetros de mbox:

* Parámetros de mbox: 500 parámetros por mbox.
* Parámetros de perfil: 500 parámetros.
* parámetros de perfil por mbox:
* Otros parámetros (URL, URL de referencia, etc.): 50 por mbox para cada tipo de parámetro.

Para los parámetros que se registran en la base de datos de Target, los límites anteriores son para solicitudes de mbox estándar. Estos límites se aplican a menos que la solicitud se acorte debido a limitaciones del navegador.

Si utiliza la [API de envío por lotes](https://developers.adobetarget.com/api/#server-side-batch-delivery) en el SDK de Mobile Services, el límite de 50 parámetros de mbox, 50 parámetros de perfil y 50 el resto de tipos de parámetros es una limitación de la propia API. No es posible enviar una solicitud que supere estos valores mediante la API de envío por lotes. Si una solicitud supera estos valores, la API devolverá el siguiente mensaje de error: “El número de parámetros de mbox no puede superar los 100”.

## Direcciones URL de peticiones de mbox

**Límite**: 2083 caracteres.

Este límite se debe a las restricciones de longitud de dirección URL de Microsoft Internet Explorer.

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

## Parámetro orderId

**Límite**: 120 caracteres.

Límite recomendado.

## Parámetro orderTotal

**Límite**: 120 caracteres.

Límite recomendado.

## Parámetro productPurchasedId

**Límite**: 47 caracteres por valor separado por coma.

El sistema truncará lo que supere este límite.

## Cuenta/Audiencias reutilizables

**Límite**: 75 audiencias.

Límite recomendado. Se producen errores de tiempo de espera de JavaScript en la interfaz si tiene demasiados.

## Cuadro de entrada de perfil de script en la interfaz de usuario de Target

**Límite**: 2000 caracteres.

Límite recomendado. Depende del tamaño de la cadena codificada, que puede ser mucho mayor que la cadena sin procesar. Si la cadena es demasiado larga, producirá un error antes de llegar a Adobe Target.

## Nombres de perfiles de secuencia

**Límite**: 50 caracteres.

## Valores de perfil de secuencia

**Límite**: 2048 caracteres.

Por motivos de rendimiento, recomendamos un valor de retorno que no tenga más de 256 caracteres.

Para un valor de retorno de cadena, si el tamaño del valor devuelto supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

Para un valor de devolución de matriz, si el tamaño de los valores concatenados de la matriz supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

## Condiciones de segmentación

**Límite**: 1000 valores.

Límite recomendado. Esto hace referencia al número de valores separados por líneas en el área de texto de determinación de objetivos. Por ejemplo, si se escriben 1000 códigos postales en un solo objetivo de código postal.