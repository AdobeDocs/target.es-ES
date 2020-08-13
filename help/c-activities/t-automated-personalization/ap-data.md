---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
description: Adobe Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
title: Recopilación de datos para los algoritmos de personalización de Adobe Target
feature: ap
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1755'
ht-degree: 97%

---


# ![PREMIUM](/help/assets/premium.png) Recopilación de datos para los algoritmos de personalización de Target{#data-collection-for-the-target-personalization-algorithms}

 Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).

Para obtener más información sobre los algoritmos de personalización de Target, consulte  [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

La tabla siguiente muestra los datos recopilados por Automated Personalization y Segmentación automática de forma predeterminada, sin que el experto en marketing tenga que hacer nada. También se recoge la nomenclatura utilizada para indicar estos atributos en los [Informes de perspectivas de personalización](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Los datos de entrada establecidos se pueden aumentar en cualquier momento. Para obtener más información acerca de cómo cargar datos adicionales, consulte  [Carga de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos | Atributos de ejemplo |
| --- | --- | --- | --- |
| [Datos de dispositivos y móviles](#device-mobile) | Dispositivo e información específica del móvil.<br>Consulte “Datos de dispositivos y móviles”. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | SO de dispositivo móvil<br>Tamaño de pantalla de dispositivo |
| [Datos ambientales](#env) | Información sobre el sistema operativo del visitante y cómo y cuándo el visitante accede a la actividad. | `Browser - / Operating System] - [Attribute Name]` | Browser - Type |
| Segmento de Experience Cloud | Audiencias creadas en Audience Manager o Analytics y compartidas en Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Datos personalizados |
| [Datos geográficos](#geo) | Información sobre dónde se encuentra el visitante.<br>Consulte “Datos geográficos” a continuación. | `Geo - [geo attribute]` | Ciudad<br>País<br>Región/Estado<br>Código postal<br>Latitud<br>Longitud<br>Proveedor de servicios de internet u operador de telefonía móvil |
| Atributos de perfil | Los scripts o atributos de perfil cargados directamente en el perfil de Target a través de la API de actualización | `Custom - Visitor Profile - [attribute name]` | Datos personalizados |
| Parámetros de URL de referencia | En general, la dirección URL de referencia es la dirección URL que hace referencia a una página concreta que inició la llamada de Destinatario.<br>Tenga en cuenta que esta variable puede verse afectada por la actividad de los usuarios en su sitio, así como por la implementación técnica de este. | `Custom - [Referring URL Parameter] - [Parameter value]` | Datos personalizados |
| Segmentos de informes | Cualquier segmento configurado en la configuración de la actividad. | `Reporting Segment -[Segment Name]` | Datos personalizados |
| [Datos de sesión](#session) | Información sobre el comportamiento del visitante en la sesión al acceder a la actividad. | `Visitor Profile - [Attribute Name]` | Visitor Profile - Start of Most Recent Visit |
| parámetros de URL. | Target inspecciona la URL para extraer los parámetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Datos personalizados |

Las secciones siguientes contienen información detallada sobre los distintos tipos de datos, incluidos nombres de atributos, descripciones y valores de muestra.

## Datos de dispositivos y móviles {#device-mobile}

| Nombre de atributo | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Mobile - Device - Brand | Marca del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Apple |
| Mobile - Device - eReader | Especifica si el dispositivo es un eReader. | 0 es Falso, 1 es Verdadero |
| Mobile - Device - Game Console | Especifica si el dispositivo es una videoconsola. | 0 es Falso, 1 es Verdadero |
| Mobile - Device - Media Player | Especifica si el dispositivo es un reproductor multimedia. | 0 es Falso, 1 es Verdadero |
| Mobile - Device - Mobile Phone | Especifica si el dispositivo es un teléfono móvil. | 0 es Falso, 1 es Verdadero |
| Mobile - Device - Model Name | El nombre del modelo del dispositivo móvil que el visitante utilizó para acceder a la actividad. | iPhone XS |
| Device - Set-Top Box | Especifica si el dispositivo es un cuadro de configuración superior. | 0 es Falso, 1 es Verdadero |
| Mobile - Device - Tablet | Especifica si el dispositivo es una tablet. | 0 es Falso, 1 es Verdadero |
| Mobile - Pixel Density (ppi) | Densidad de píxeles del dispositivo móvil que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Móvil - OS - OSX (Android, Windows, etc.) | Especifica si el usuario ha utilizado un OSX (o Android, Windows, etc.) para acceder a la actividad. | 0 es Falso, 1 es Verdadero |
| Mobile - Screen Height (px) | Altura de la pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Mobile - Screen Width (px) | Ancho de pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |

## Datos ambientales {#env}

| Nombre de atributo | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Browser - Day of Week | El día de la semana en el que el visitante accedió a la actividad. | De 0 a 6.<br>(0 es domingo) |
| Browser - Hour of Day | Hora del día en que el visitante accedió a la actividad. | 0 a 23<br>(0 equivale a medianoche) |
| Browser - Hour of Week | Hora de la semana en la que el visitante accedió a la actividad. | 0 a 168<br>(el domingo a medianoche es 0) |
| Browser - Language Setting | El idioma especificado en el explorador del visitante utilizado para acceder a la actividad. | English<br>German |
| Browser - Screen Height (px) | Altura de la pantalla del explorador del dispositivo (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Browser - Time of Day | Hora del día del explorador cuando el visitante accedió a la actividad. | 0, 6, 12, 18<br>(0 es la noche, 6 es mañana,<br>12 es mediodía, 18 es tarde) |
| Browser - Timezone | Zona horaria del visitante al acceder a la actividad. | Pacific Time<br>Eastern Time<br>GMT |
| Browser - Type | Tipo de explorador que el visitante utilizó al acceder a la actividad. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Browser - Weekday/Weekend | Estado de trabajo cuando el visitante accedió a la actividad (fin de semana, jornada laboral o tiempo libre entre semana). | Sábado y domingo es fin de semana<br>De lunes a viernes de 09:00 a 18:00 es jornada laboral<br>De lunes a viernes después de 18:00 hasta 09:00 es tiempo libre entre semana |
| Browser - Window Height (px) | Altura de la ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Browser - Window Width (px) | Ancho de ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Device - Screen Height | Altura de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Device - Screen Width | Ancho de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Sistema operativo | Sistema operativo en el dispositivo del visitante utilizado para acceder a la actividad. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>OS Unknown |
| Operating System - Version | Versión del sistema operativo que el visitante utilizó para acceder a la actividad. | Windows 10<br>Mac OS 10 |
| Traffic Sources - Referring Landing Page URL | Primera página que vio el visitante al acceder al sitio. | `https://www.adobe.com/ecloud.html` |

## Datos geográficos {#geo}

| Nombre de atributo | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Geo - City | Ciudad desde la que el visitante accedió a la actividad. | San Francisco |
| Geo - Country | País desde el que el visitante accedió a la actividad. | Alemania |
| Geo - DMA | El área designada de marketing (DMA) desde la que el visitante accedió a la actividad. | Charlottesville |
| Geo - Latitude | Latitud desde la cual el visitante accedió a la actividad. | 47 269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) |
| Geo - Longitude | Longitud desde la cual el visitante accedió a la actividad. | -122 269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) |
| Geo - State/Region | Estado o región desde donde el visitante accedió a la actividad. | Utah<br>New South Wales |
| Geo - Zip Code | Código postal desde el cual el visitante accedió a la actividad. | 84004 |
| Mobile - Carrier | Operador de telefonía móvil que el visitante utilizó al acceder a la actividad. | Vodafone<br>T-Mobile |
| Network - Connection Speed | Velocidad de conexión de red del dispositivo cuando el visitante accedió a la actividad. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Network - Domain Name | El nombre del dominio de red desde el cual el visitante accedió a la actividad. | `nnt.net` |
| Network - ISP | La red desde la cual el visitante accedió a la actividad. | nnt communications corporation |

## Datos de sesión {#session}

| Nombre de atributo | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Especifica la suma de todos los valores de pedidos en todas las visitas o sesiones a una actividad concreta. | Doble |
| Visitor Profile - Activity Lifetime Time on Site | Especifica el tiempo total invertido en el sitio, excluida la sesión actual, y se actualiza cuando caduca la sesión. | Doble, milisegundos |
| Visitor Profile -Average Page Views per Visit during Activity | Especifica el número promedio de vistas de página por sesión, excluida la sesión actual. | Doble |
| Visitor Profile - Average Time per Visit | Especifica el tiempo promedio empleado por visita/sesión. Esto no incluye la sesión actual. | Doble, milisegundos |
| Visitor Profile - First Visit | Especifica la hora de la primera visita en la que el usuario interactuó con Target. | Doble, milisegundos |
| Visitor Profile - Hours since Last Visit | Especifica las horas desde la última visita a esta actividad en particular. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Visitor Profile - Impressions of Location/Content | Especifica el número de impresiones de una combinación de contenido/ubicación en particular en una actividad concreta. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Visitor Profile - Last Target Interaction | Especifica la hora de la última interacción con Target. Interaction happens on every [!DNL Target] request because the current implementation of [!DNL Target] updates the profile on each request. | Doble, milisegundos |
| Visitor Profile - Pages Seen Before Activity | Especifica el número total de vistas de página (impresiones), incluida la visita o sesión actual hasta que el visitante entra en la actividad. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Visitor Profile - Page Views in Current Visit | Especifica el número de vistas de página en la visita o sesión actual hasta que el visitante entra en la actividad. En concreto, el número de impresiones. Estas impresiones no son vistas reales de la página, sino el número de veces que la solicitud llegó a Target. Target no puede distinguir entre tiempos de espera u otros motivos por los que el usuario no recibió o visualizó el contenido. | Doble (solo número positivo entero) |
| Visitor Profile - Start of Current Visit | Especifica la hora en la que se inició la visita o sesión actual de Target. La visita con Target se puede iniciar sin entrar en una actividad. All that is required is a call to any [!DNL Target] request. Un visitante podría tardar un poco hasta entrar en la actividad y registrar el acceso. | Doble, milisegundos |
| Visitor Profile - Start of Most Recent Visit | Especifica la hora en la que se inició la última visita o sesión de Target. Este atributo se actualiza cuando caduca la sesión.<br>Si esta es la primera sesión del visitante, resultará en `LAST_SESSION_START = 0.` | Doble, milisegundos |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Especifica la duración entre la sesión anterior y la hora en la que el usuario entra en la actividad y se registra el acceso. | Doble, milisegundos |
| Visitor Profile - Time in Visit Before Enter Activity | Especifica la diferencia entre la última interacción con Target y la fecha en la que comenzó la visita actual. Este atributo puede considerarse una duración de visita/sesión hasta que el usuario entre en la actividad y se registre el acceso.<br>[!DNL Target]Los valores negativos se producen cuando la sesión empieza, y la última hora de actualización se activa mediante la misma llamada de Los valores negativos deben considerarse como 0 (cero). | Doble, milisegundos |
| Perfil del visitante - Visitas totales | Especifica el número total de visitas/sesiones. No incluye la visita o sesión actual. | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity | Especifica el número de visitas a una actividad concreta. Si no hay ninguna visita anterior, devuelve 0 (cero). | Doble (solo número positivo entero) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity with Conversion | Especifica el número de visitas/sesiones a una actividad concreta cuando hay al menos una conversión durante la visita. | Doble |
| Visitor Profile - Visits to Activity with No Conversion | Número de visitas/sesiones sin conversiones a una actividad en particular. Este valor se restablece en cero después de la conversión o -1 si la conversión no ha sucedido nunca. | Doble (solo número positivo entero) 1, 2, 3, etc. |
