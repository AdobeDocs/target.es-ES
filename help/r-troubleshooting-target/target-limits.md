---
keywords: límite de caracteres;parámetros de mbox;api de entrega por lotes;parámetros de perfil;límites;perfiles integrados;límite;máximo;restricción;carácter;práctica recomendada;id de pedido;total del pedido;id de terceros de mbox;categoría;id de categoría;solución de problemas
description: Visualización de una lista de límites de caracteres y de otro tipo (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de Adobe Target.
title: ¿Cuáles son los distintos límites de caracteres, tamaños y de otro tipo de Adobe Target?
feature: Resolución de problemas
mini-toc-levels: 3
exl-id: b318ab16-1382-4f3a-8764-064adf384d6b
source-git-commit: 2403f63a6b993818fdc845d17f1a0dde72be664d
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 91%

---

# Límites

Información sobre los límites de caracteres y de otro tipo (tamaño de oferta, audiencias, perfiles, valores, parámetros, etc.) que afectan a las actividades y otros elementos de [!DNL Adobe Target].

>[!NOTE]
>
>Los límites listados a continuación deben considerarse límites “duros” a menos que se especifique como “recomendado”.
>
>Cuando se aproximan o se exceden los límites designados como “recomendados”, el rendimiento puede ralentizarse. Si la interfaz tarda tiempo en cargarse también puede ser debido a una actividad muy compleja, como por ejemplo muchas audiencias, objetivos y experiencias en la misma actividad.
>
>Las actividades muy complejas se deben revisar con [!DNL Adobe] Consulting y deben probarse en un entorno limitado antes de su lanzamiento en producción.

## Actividades

### Nombres de actividades

* **Límite**: 250 caracteres.

### Número de actividades por cuenta

* **Límite recomendado**: 10 000 actividades activas.

* **Límite recomendado**: 10 000 acciones guardadas (y no finalizadas).

## Llamadas a API de Target

* **Límite**: 50 llamadas por minuto para las API de administración, creación de informes y actualización de perfiles en lote. Este límite no se aplica a las API de entrega y actualización de perfil único.

   Si realiza más de 50 llamadas de API por minuto, [!DNL Target] devuelve el mensaje de error Estado HTTP 503.

## Audiencias

### Nombres de audiencia

* **Límite**: 255 caracteres.

### Audiencias, reutilizables por cuenta

* **Límite recomendado**: 20,000 audiencias.

### Número de audiencias por mbox, métrica o experiencia

* **Límite**: 50 audiencias

## Parámetro categoryId

* **Límite**: 250 caracteres.

## Entrega de contenido {#content-delivery}

* **Límite**: 100 solicitudes de entrega de  [!DNL Target] contenido concurrentes por sesión de usuario.

   Si un cliente supera las 100 solicitudes de envío de contenido [!DNL Target] concurrentes para una sesión de usuario determinada, se bloquearán todas las solicitudes posteriores para esa sesión de usuario. Se consideran simultáneas dos o más solicitudes si todas se envían al servidor [!DNL Target] antes de recibir la respuesta de cualquiera de ellas. [!DNL Target] procesa las solicitudes simultáneas para la misma sesión secuencialmente.

* **Comportamiento** del error:

   * API de envío y Mbox por lotes v2:
      * Código de error: HTTP 420 demasiadas solicitudes
      * Mensaje de error: &quot;Demasiadas solicitudes con el mismo ID de sesión&quot;
   * API de mbox heredada:
      * Contenido predeterminado con el comentario &quot;Demasiadas solicitudes con el mismo ID de sesión&quot;
   * at.js:
      * Contenido predeterminado mostrado



## Atributos del cliente

### Nombres de atributos del cliente

* **Límite**: 250 caracteres mediante fuente o API.

### ID de alias de atributo de cliente

* **Límite** 50 caracteres.

### Atributos del cliente, carga

* **Tamaño de archivo máximo para cada carga con el método HTTP**: 100 MB.
* **Tamaño máximo de archivo para cada carga con el método FTP**: 4 GB
* **Número de atributos a los que puede suscribirse**: 5 para [!DNL Target Standard] y 200 para [!DNL Target Premium]

## Entidades

### Número de entidades

* El número máximo de entidades a las que se puede hacer referencia en un diseño, tanto codificadas como mediante bucles, es de 99.
* El límite recomendado para un mejor rendimiento es mantener el catálogo con menos de un millón de elementos por entorno y menos de diez millones de elementos en todos los entornos.
* El límite máximo es de diez millones de elementos por entorno y 100 millones de elementos en todos los entornos. Si tiene entre un millón y diez millones de elementos por entorno, el rendimiento de la IU de [!UICONTROL Búsqueda en catálogo] se ve afectado. [!DNL Target Recommendations], sin embargo, sigue produciendo y formulando recomendaciones.

### Atributos personalizados de entidad

* **Atributos de entidad personalizados**: 100.

* **Límite de caracteres**: La longitud máxima de caracteres depende del idioma.

   * 15 000 caracteres (un solo valor, uno y dos bytes)
   * 500 valores, 100 caracteres por valor (varios valores)

   La longitud máxima de los atributos personalizados de entidad de un solo valor es de 15 000 caracteres (para lenguajes con codificación UTF-8 de uno y dos bytes, como inglés y otros alfabetos latinos) o 10 000 caracteres (para lenguajes con codificación UTF-8 de 3 bytes como chino, japonés y coreano).

   Los atributos personalizados de entidad de varios valores no pueden contener más de 500 valores. Cada valor individual está limitado a 100 caracteres. El número total de caracteres en todos los valores debe cumplir las limitaciones de la longitud máxima de atributos personalizados de entidad de un solo valor (véase arriba).

### Parámetros de entityid

* **Límite**: 1000 caracteres.

## Excludedids {#excludedid}

* **Límite**: 5 KB para solicitudes POST. 2.083 caracteres menos la longitud de la URL para las solicitudes GET.

   Para las solicitudes GET, aunque el límite del back-end es 5 KB, debido al hecho de que Microsoft Internet Explorer limita la dirección URL a 2.083 caracteres, el límite realista es de 2.083 caracteres menos la longitud actual de la dirección URL.

## Experiencias

### Nombres de experiencias

* **Límite**: 50 caracteres.

### Experiencias por actividad

* **Límite**: 2000 experiencias por Segmentación de experiencias (XT), Prueba A/B, Prueba multivariada (MVT) y actividad de Segmentación automática.

   30 000 experiencias por actividad de Automated Personalization (AP).

### Modificaciones por experiencia

* **Límite**: 50 por experiencia en cualquier actividad

## mboxes regionales clásicos

### Valor de atributo de perfil In-mbox

* **Límite**: 256 caracteres.

   Los valores más largos que ese número se truncan.

### Nombres de perfiles In-mbox

* **Límite**: 128 caracteres.

### nombres de mbox

* **Límite**: 250 caracteres.

### Parámetros de mbox

* **Límite**: Los límites siguientes se aplican a los parámetros de mbox:

   Para llamadas de mbox estándar:

   * Parámetros de mbox: 500 parámetros por mbox.
   * Parámetros de perfil: 500 parámetros de perfil por mbox.
   * Otros parámetros (URL, URL de referencia, etc.): 50 por mbox para cada tipo de parámetro.

   Estos límites se aplican a menos que la solicitud se acorte debido a limitaciones del navegador.

   Si utiliza la API de envíos por lotes, el límite es de 50 mboxes por solicitud de lote.

   Si utiliza la [API de envío por lotes](https://developers.adobetarget.com/api/#server-side-batch-delivery) en el SDK de Mobile Services, el límite de 50 parámetros de mbox, 50 parámetros de perfil y 50 el resto de tipos de parámetros es una limitación de la propia API. No es posible enviar una solicitud que supere estos valores mediante la API de envío por lotes. Si una solicitud supera estos límites, la API devolverá el mensaje de error siguiente:

   &quot;El número de mboxParameters no puede superar los 50.&quot;

   Límites establecidos para extremos:

   **Lote de mbox v2**:

   * Parámetros de mbox 100
   * Longitud máxima del nombre del parámetro de mbox 128
   * El valor del parámetro de mbox no puede ser nulo
   * Valor del parámetro de mbox 5000
   * Parámetros de perfil: 50
   * Longitud máxima del nombre del parámetro de perfil 128
   * El valor del parámetro del perfil no puede ser nulo
   * Longitud máxima del valor del parámetro del perfil 256

   **Extremo de API de envíos**:

   * Parámetros de mbox 50
   * Longitud máxima del nombre del parámetro de mbox 128
   * El valor del parámetro de mbox no puede ser nulo
   * Valor del parámetro de mbox 5000
   * Parámetros de perfil: 50
   * Longitud máxima del nombre del parámetro de perfil 128
   * El valor del parámetro del perfil no puede ser nulo
   * Longitud máxima del valor del parámetro del perfil 256



### Direcciones URL de peticiones de mbox

* **Límite**: 2.083 caracteres.

   Este límite se debe a las restricciones de longitud de URL de Microsoft Internet Explorer.

### Parámetro mbox3rdPartyId

* **Límite**: 60 caracteres.

## Ofertas

### Nombres de ofertas

* **Límite**: 250 caracteres.

### Número de ofertas

* **Límite recomendado**: 50 000 ofertas totales.

### Tamaño de oferta {#offer-size}

A continuación se describen los límites de tamaño que se aplican a las ofertas:

* 1024 kB para ofertas HTML.
* 1024 KB (para cada experiencia) para ofertas visuales desde la interfaz de usuario.
* 1024 kB de la API.

   Si usa un mbox global, el límite es para todo el conjunto de contenidos devueltos de la página. La limitación del tamaño de la oferta mejora los tiempos de carga de la página. Si se supera el límite, aparece un mensaje como este:

   El contenido de la experiencia es demasiado grande para su entrega. Modifique la experiencia para afectar a menos código de página.

## Parámetro orderId

* **Límite recomendado**: 120 caracteres.

## Parámetro orderTotal

* **Límite recomendado**: 120 caracteres.

## Parámetro productPurchasedId

* **Límite**: 47 caracteres por valor separado por coma y 250 caracteres en total. El sistema puede truncar los valores individuales de más de 47 caracteres. Las longitudes totales de más de 250 caracteres pueden provocar el error 400.

## Scripts de perfil

* **Límite recomendado de scripts de perfil activos (los que están habilitados)**: 300

* **Límite recomendado de total de scripts de perfil por cuenta**: 2000

* **Recomendaciones de limitación de la complejidad de los scripts de perfiles**: Los scripts de perfiles pueden ejecutar un número limitado de instrucciones. Para obtener más información, consulte las [Prácticas recomendadas](/help/c-target/c-visitor-profile/profile-parameters.md#best) en *Atributos de perfil*.

## Propiedades

* **Límite recomendado**: 5000 propiedades.

## Informes de audiencias o segmentos

* **Límite**: 50 audiencias/segmentos por actividad.

## Cuadro de entrada de perfil de script en la IU de [!DNL Target]

* **Límite recomendado**: 2000 caracteres.

   Depende del tamaño de la cadena codificada, que puede ser mucho mayor que la cadena sin procesar. Si la cadena es demasiado larga, producirá un error antes de llegar a Adobe Target.

## Perfiles de scripts de comandos

### Nombres de perfiles de secuencia

* **Límite**: 50 caracteres.

### Valores de perfil de secuencia de comandos

* **Límite**: 2.048 caracteres.

   Por motivos de rendimiento, recomendamos un valor de retorno que no tenga más de 256 caracteres.

   Para un valor de retorno de cadena, si el tamaño del valor devuelto supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

   Para un valor de devolución de matriz, si el tamaño de los valores concatenados de la matriz supera los 2048 caracteres, el sistema desactiva la secuencia de comandos.

## Métricas de éxito

* **Límite**: 200 por actividad.

## Segmentación

### Condiciones de segmentación

* **Límite recomendado**: 1000 valores.

   Esto hace referencia al número de valores separados por líneas en el área de texto de determinación de objetivos. Por ejemplo, si se escriben 1000 códigos postales en un solo objetivo de código postal.

### Reglas de segmentación

* **Límite recomendado**: 2500 caracteres por valor de regla de direccionamiento.
* **Límite recomendado**: 30 000 valores únicos por audiencia en reglas de segmentación.
* **Límite recomendado**: 100 000 valores únicos de reglas de segmentación por actividad.
