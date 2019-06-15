---
description: Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
seo-description: Adobe Target recopila automáticamente y utiliza diversos datos para crear sus algoritmos de personalización en las actividades de Personalización automatizada (AP) y Segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
seo-title: Recopilación de datos para algoritmos de personalización de Adobe Target
solution: Target
title: Recopilación de datos para los algoritmos de personalización de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: tm+mt
source-git-commit: 1662c5e83a3712626536a659e5001cd537343883

---


# ![PREMIUM](/help/assets/premium.png) Recopilación de datos para los algoritmos de personalización de Target{#data-collection-for-the-target-personalization-algorithms}

Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).

Para obtener más información sobre los algoritmos de personalización de Target, consulte  [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

La tabla siguiente muestra los datos recopilados por Personalización automatizada de forma predeterminada, sin que el experto en marketing tenga que hacer nada. También se recoge la nomenclatura utilizada para indicar estos atributos en los [informes de Perspectivas de personalización](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Los datos de entrada establecidos se pueden aumentar en cualquier momento. Para obtener más información acerca de cómo cargar datos adicionales, consulte  [Carga de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos | Atributos de ejemplo |
| --- | --- | --- | --- |
| Parámetros de URL | Target inspecciona la URL para extraer los parámetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Datos personalizados |
| Parámetros de URL de referencia | En general, la URL de referencia es la URL que hace referencia a una página en particular que inició la llamada de mbox.<br>Tenga en cuenta que esta variable puede verse afectada por la actividad de los usuarios en su sitio, así como por la implementación técnica de este. | `Custom - [Referring URL Parameter] - [Parameter value]` | Datos personalizados |
| Datos de entorno y sesión | Información sobre cómo y cuándo accede el usuario a la actividad.<br>Consulte &quot;Datos ambientales y de sesión&quot; abajo. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Perfil de visitante: inicio de la visita más reciente<br>Perfil de visitante: visitas totales<br>Perfil de visitante: tiempo medio por visita<br>Explorador: zona horaria<br>Explorador: día de la semana<br>Explorador: configuración de idioma<br>Explorador: tipo<br>Sistema operativo: versión |
| Geográfico | Información sobre dónde se encuentra el visitante.<br>Consulte &quot;Datos geográficos&quot; a continuación. | `Geo - [geo attribute]` | Ciudad<br>País<br>Región/Estado<br>Código postal<br>Latitud<br>Longitud<br>Proveedor de servicios de internet u operador de telefonía móvil |
| Dispositivo y datos móviles | Dispositivo e información específica del móvil.<br>Consulte «Datos de dispositivo y dispositivos móviles». | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Tamaño de pantalla de dispositivo<br>móvil de dispositivo móvil |

Las secciones siguientes contienen información detallada sobre los distintos tipos de datos, incluyendo nombres de atributos, descripciones y valores de muestra.

>[!NOTE]
>
>Algunos de los valores de las tablas siguientes se redondean al entero o la hora más próximos.

## Datos ambientales y de sesión

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Navegador - Día de la semana | El día de la semana en el que el visitante accedió a la actividad. | 0 a 6.<br>(0 es domingo) |
| Explorador - Hora del día | Hora del día en que el visitante accedió a la actividad. | 0 a 23<br>(0 equivale a medianoche) |
| Explorador - Hora de la semana | Hora de la semana en la que el visitante accedió a la actividad. | 0 a 168<br>(el domingo, medianoche es 0) |
| Navegador - Configuración de idioma | Idioma especificado en el explorador del visitante para acceder a la actividad. | Inglés alemán<br> |
| Explorador - Altura de la pantalla (px) | Altura de la pantalla del explorador del dispositivo (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Explorador - Hora del día | Hora del día del explorador cuando el visitante accedió a la actividad. | 0, 6, 12, 18<br>(0 es la noche, 6 es mañana, 12 de la tarde, 18 es tarde) |
| Navegador - Zona horaria | Zona horaria del visitante al acceder a la actividad. | Pacífico timeeastern<br>timegmt<br> |
| Navegador - Tipo | Tipo de explorador que el visitante utilizó al acceder a la actividad. | Chromefirefoxinternet<br><br>explorersafariother<br><br> |
| Explorador - Día de la semana/Fin de semana | Estado de trabajo cuando el visitante accedió a la actividad (fin de semana, horas laborables o día de la semana). | Sábado y domingo es Week endendmonday<br>through Friday 0900 to 1800 es work timemonday<br>a través del viernes después de 1800 hasta que 0900 sea un día gratuito de la semana |
| Explorador - Altura de ventana (px) | Altura de la ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Explorador - Ancho de ventana (px) | Ancho de ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Dispositivo - Altura de la pantalla | Altura de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Dispositivo - Ancho de la pantalla | Ancho de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Móvil &gt; Densidad de píxeles (ppp) | Densidad de píxeles del dispositivo móvil que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Sistema operativo | Sistema operativo en el dispositivo del visitante utilizado para acceder a la actividad. | Mac oswindowslinuxsearch<br><br><br>botunknown<br>SO |
| Sistema operativo - Versión | Versión del sistema operativo que el visitante utilizó para acceder a la actividad. | Windows 10<br>Mac OS 10 |
| Fuentes de tráfico - URL de página de aterrizaje referente | Primera página que vio el visitante al acceder al sitio. | `https://www.adobe.com/ecloud.html` |

## Datos geográficos

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Geo - City | Ciudad desde la cual el visitante accedió a la actividad. | San Francisco |
| Geo - Country | País desde el cual el visitante accedió a la actividad. | Alemania |
| Geo - DMA | El área de mercadotecnia designada (DMA) desde la que el visitante accedió a la actividad. | Charlottesville |
| Geo - Latitud | Latitud desde la cual el visitante accedió a la actividad. | 47.269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) |
| Geo - Longitude | Longitud desde la cual el visitante accedió a la actividad. | -122.269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) |
| Geo - State/Region | Estado o región desde donde el visitante accedió a la actividad. | Utahnew<br>South Wales |
| Geo - Código postal | Código postal desde el cual el visitante accedió a la actividad. | 84004 |
| Móvil: operador de telefonía móvil | Operador de telefonía móvil que el visitante utilizó al acceder a la actividad. | Vodafonet<br>-Mobile |
| Red - Velocidad de conexión | Velocidad de conexión de red del dispositivo cuando el visitante accedió a la actividad. | Broadbandcabledslmobilewirelesssatellite<br><br><br><br><br> |
| Red - Nombre de dominio | El nombre del dominio de red desde el cual el visitante accedió a la actividad. | `nnt.net` |
| Red - ISP | La red desde la cual el visitante accedió a la actividad. | nnt communications corporation |

## Datos de dispositivos y dispositivos móviles

| Attribute name | Descripción de atributo | Valores de muestra |
| --- | --- | --- |
| Móvil - Dispositivo - Marca | Marca del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Apple |
| Móvil - Dispositivo - Nombre de modelo | Nombre del modelo del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Iphone XS |
| Mobile - OS - OSX | Especifica si el usuario utilizó un dispositivo OSX para acceder a la actividad. | 0 es False, 1 es verdadero |
| Móvil - Altura de la pantalla (px) | Altura de la pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |
| Móvil - Ancho de la pantalla (px) | Ancho de pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. |