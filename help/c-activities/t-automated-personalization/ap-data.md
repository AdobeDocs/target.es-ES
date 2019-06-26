---
description: Adobe Target recopila automáticamente y utiliza diversos datos para crear sus algoritmos de personalización en las actividades de Personalización automatizada (AP) y Segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
keywords: environment data; session data; datos geográficos; datos geográficos; datos del dispositivo; datos móviles; attributes; atributos de perfil
seo-description: Adobe Target recopila automáticamente y utiliza diversos datos para crear sus algoritmos de personalización en las actividades de Personalización automatizada (AP) y Segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
seo-title: Recopilación de datos para algoritmos de personalización de Adobe Target
solution: Target
title: Recopilación de datos para los algoritmos de personalización de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# ![PREMIUM](/help/assets/premium.png) Recopilación de datos para los algoritmos de personalización de Target{#data-collection-for-the-target-personalization-algorithms}

Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).

Para obtener más información sobre los algoritmos de personalización de Target, consulte  [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Los datos de entrada establecidos se pueden aumentar en cualquier momento. Para obtener más información acerca de cómo cargar datos adicionales, consulte  [Carga de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos | Atributos de ejemplo |
| --- | --- | --- | --- |
| [Datos de dispositivos y dispositivos móviles](#device-mobile) | Dispositivo e información específica del móvil.<br>Consulte «Datos de dispositivo y dispositivos móviles». | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Mobile Device OS<br>Mobile Screen Size |
| [Datos ambientales](#env) | Información sobre el sistema operativo del visitante y cómo y cuándo el visitante accede a la actividad. | `Browser - / Operating System] - [Attribute Name]` | Navegador - Tipo |
| Segmento de Experience Cloud | Audiencias creadas en Audience Manager o Analytics y compartidas en Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Datos personalizados |
| [Datos geográficos](#geo) | Información sobre dónde se encuentra el visitante.<br>Consulte &quot;Datos geográficos&quot; a continuación. | `Geo - [geo attribute]` | Ciudad<br>País<br>Región/Estado<br>Código postal<br>Latitud<br>Longitud<br>Proveedor de servicios de internet u operador de telefonía móvil |
| Atributos de perfil | Los scripts o atributos de perfil cargados directamente en el perfil de Target a través de la API de actualización | `Custom - Visitor Profile - [attribute name]` | Datos personalizados |
| Parámetros de URL de referencia | En general, la URL de referencia es la URL que hace referencia a una página en particular que inició la llamada de mbox.<br>Tenga en cuenta que esta variable puede verse afectada por la actividad de los usuarios en su sitio, así como por la implementación técnica de este. | `Custom - [Referring URL Parameter] - [Parameter value]` | Datos personalizados |
| Segmentos de informes | Cualquier segmento configurado en la configuración de la actividad. | `Reporting Segment -[Segment Name]` | Datos personalizados |
| [Datos de sesión](#session) | Información sobre el comportamiento del visitante en la sesión al acceder a la actividad. | `Visitor Profile - [Attribute Name]` | Perfil del visitante - Inicio de la visita más reciente |
|  parámetros de URL  | Target inspecciona la URL para extraer los parámetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Datos personalizados |

Las secciones siguientes contienen información detallada sobre los distintos tipos de datos, incluyendo nombres de atributos, descripciones y valores de muestra.

## Device and Mobile data {#device-mobile}

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Móvil - Dispositivo - Marca | Marca del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Apple |
| Móvil - Dispositivo - ereader | Especifica si el dispositivo es un ereader. | 0 es False, 1 es verdadero |
| Móvil - Dispositivo - Consola de juegos | Especifica si el dispositivo es una consola de juego. | 0 es False, 1 es verdadero |
| Móvil - Dispositivo - Reproductor de medios | Especifica si el dispositivo es un reproductor multimedia. | 0 es False, 1 es verdadero |
| Móvil - Dispositivo - Teléfono móvil | Especifica si el dispositivo es móvil. | 0 es False, 1 es verdadero |
| Móvil - Dispositivo - Nombre de modelo | Nombre del modelo del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Iphone XS |
| Dispositivo - Cuadro de configuración superior | Especifica si el dispositivo es un cuadro superior. | 0 es False, 1 es verdadero |
| Móvil - Dispositivo - Tablet | Especifica si el dispositivo es una tableta. | 0 es False, 1 es verdadero |
| Móvil - Densidad de píxeles (ppp) | Densidad de píxeles del dispositivo móvil que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Mobile - OS - OSX (Android, Windows, etc.) | Especifica si el usuario ha utilizado un OSX (o Android, Windows, etc.) para acceder a la actividad. | 0 es False, 1 es verdadero |
| Móvil - Altura de la pantalla (px) | Altura de la pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Móvil - Ancho de la pantalla (px) | Ancho de pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |

## Environmental data {#env}

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Navegador - Día de la semana | El día de la semana en el que el visitante accedió a la actividad. | 0 a 6.<br>(0 es domingo) |
| Explorador - Hora del día | Hora del día en que el visitante accedió a la actividad. | 0 to 23<br>(0 is midnight) |
| Explorador - Hora de la semana | Hora de la semana en la que el visitante accedió a la actividad. | 0 to 168<br>(Sunday midnight is 0) |
| Navegador - Configuración de idioma | Idioma especificado en el explorador del visitante para acceder a la actividad. | English<br>German |
| Explorador - Altura de la pantalla (px) | Altura de la pantalla del explorador del dispositivo (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Explorador - Hora del día | Hora del día del explorador cuando el visitante accedió a la actividad. | 0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening) |
| Navegador - Zona horaria | Zona horaria del visitante al acceder a la actividad. | Pacific Time<br>Eastern Time<br>GMT |
| Navegador - Tipo | Tipo de explorador que el visitante utilizó al acceder a la actividad. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Explorador - Día de la semana/Fin de semana | Estado de trabajo cuando el visitante accedió a la actividad (fin de semana, horas laborables o día de la semana). | Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time |
| Explorador - Altura de ventana (px) | Altura de la ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Explorador - Ancho de ventana (px) | Ancho de ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Dispositivo - Altura de la pantalla | Altura de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Dispositivo - Ancho de la pantalla | Ancho de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Sistema operativo | Sistema operativo en el dispositivo del visitante utilizado para acceder a la actividad. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS |
| Sistema operativo - Versión | Versión del sistema operativo que el visitante utilizó para acceder a la actividad. | Windows 10<br>Mac OS 10 |
| Fuentes de tráfico - URL de página de aterrizaje referente | Primera página que vio el visitante al acceder al sitio. | `https://www.adobe.com/ecloud.html` |

## Geographical data {#geo}

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Geo - City | Ciudad desde la cual el visitante accedió a la actividad. | San Francisco |
| Geo - Country | País desde el cual el visitante accedió a la actividad. | Alemania |
| Geo - DMA | El área de mercadotecnia designada (DMA) desde la que el visitante accedió a la actividad. | Charlottesville |
| Geo - Latitud | Latitud desde la cual el visitante accedió a la actividad. | 47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Geo - Longitude | Longitud desde la cual el visitante accedió a la actividad. | -122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Geo - State/Region | Estado o región desde donde el visitante accedió a la actividad. | Utah<br>New South Wales |
| Geo - Código postal | Código postal desde el cual el visitante accedió a la actividad. | 84004 |
| Móvil: operador de telefonía móvil | Operador de telefonía móvil que el visitante utilizó al acceder a la actividad. | Vodafone<br>T-Mobile |
| Red - Velocidad de conexión | Velocidad de conexión de red del dispositivo cuando el visitante accedió a la actividad. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Red - Nombre de dominio | El nombre del dominio de red desde el cual el visitante accedió a la actividad. | `nnt.net` |
| Red - ISP | La red desde la cual el visitante accedió a la actividad. | nnt communications corporation |

## Session data {#session}

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Perfil del visitante - Valor de pedido de duración de actividad | Especifica la suma de todos los valores de pedidos en todas las visitas o sesiones a una actividad concreta. | Doble |
| Perfil del visitante: tiempo de duración de la actividad en el sitio | Especifica el tiempo total invertido en el sitio, excluido la sesión actual, y se actualiza cuando caduca la sesión. | Doble, milisegundos |
| Perfil del visitante: Vistas promedio de la página por visita durante la actividad | Especifica el número promedio de vistas de página por sesión, excluyendo la sesión actual. | Doble |
| Perfil del visitante - Tiempo promedio por visita | Especifica el tiempo promedio empleado por visita/sesión. Esto no incluye la sesión actual. | Doble, milisegundos |
| Perfil del visitante - Primera visita | Especifica el tiempo de la primera visita que el usuario interactuó con Target. | Doble, milisegundos |
| Perfil del visitante - Horas desde la última visita | Especifica las horas desde la última visita a esta actividad en particular. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Perfil del visitante: impresiones de ubicación/contenido | Especifica el número de impresiones de una combinación de contenido/ubicación en particular en una actividad concreta. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Perfil del visitante - Interacción con el último objetivo | Especifica el tiempo de la última interacción con Target. La interacción ocurre en cada solicitud de mbox porque la implementación actual de Target actualiza el perfil en cada solicitud. | Doble, milisegundos |
| Perfil del visitante: Páginas vistas antes de la actividad | Especifica el número total de vistas de página (impresiones), incluso la visita o sesión actual hasta que el visitante entra en la actividad. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Perfil del visitante: Vistas de página en la visita actual | Especifica el número de vistas de página en la visita o sesión actual hasta que el visitante entra en la actividad. Es más preciso el número de impresiones. Estas impresiones no son vistas reales de la página, sino que es el número de veces que la solicitud llegó a Target. Target no puede distinguir entre tiempos de espera ni otros motivos por los que el usuario no recibió ni visualizó el contenido. | Double (solo número positivo entero) |
| Perfil del visitante - Inicio de la visita actual | Especifica la hora en la que se inició la visita o sesión actual con Target. La visita con Target se puede iniciar sin entrar en una actividad. Todo lo que se requiere es una llamada a cualquier mbox. Un visitante podría tardar poco hasta entrar en la actividad y la instantánea. | Doble, milisegundos |
| Perfil del visitante - Inicio de la visita más reciente | Especifica el tiempo de la última visita o sesión con Target iniciada. Este atributo se actualiza cuando caduca la sesión.<br>Si ésta es la primera sesión del visitante, resultará en `LAST_SESSION_START = 0.` | Doble, milisegundos |
| Perfil del visitante: Tiempo desde la visita más reciente al entrar en la actividad por primera vez | Especifica la duración entre la sesión anterior y la hora en la que el usuario entra en la actividad y se realiza la instantánea. | Doble, milisegundos |
| Perfil del visitante - Tiempo en la visita antes de entrar en la actividad | Especifica la diferencia entre la última interacción con Target y la fecha en que comenzó la visita actual. Este atributo puede considerarse una duración de visita/sesión hasta que el usuario entre en la actividad y se realice la instantánea.<br>Los valores negativos se producen cuando la sesión empieza y el último tiempo de actualización se activa mediante la misma llamada de mbox. Los valores negativos deben considerarse 0 (cero). | Doble, milisegundos |
| Perfil del visitante - Visitas totales | Especifica el número total de visitas/sesiones. No incluye la visita o sesión actual. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Perfil del visitante - Número total de visitas a la actividad | Especifica el número de visitas a una actividad concreta. Si no hay ninguna visita anterior, devuelve 0 (cero). | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Perfil del visitante - Visitas totales a la actividad con conversión | Especifica el número de visitas/sesiones a una actividad concreta cuando había al menos una conversión durante la visita. | Doble |
| Perfil del visitante - Visitas a actividad sin conversión | Número de visitas/sesiones sin conversiones a una actividad en particular. Este valor se restablece en cero después de la conversión o -1 si la conversión no ha sucedido nunca. | Doble (solo número positivo entero) 1, 2, 3, etc. |
