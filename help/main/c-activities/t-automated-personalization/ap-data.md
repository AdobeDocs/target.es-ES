---
keywords: datos de entorno;datos de sesión;datos geográficos;datos geográficos;datos de dispositivo;datos móviles;atributos;atributos de perfil;algoritmos de personalización;algoritmos de aprendizaje automático;algoritmos de aprendizaje automático
description: Descubra qué datos [!DNL Adobe Target] recopila y utiliza para crear sus algoritmos de aprendizaje automático de.
title: ¿Qué datos se recopilan para crear algoritmos de aprendizaje automático?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '2024'
ht-degree: 56%

---

# Datos utilizados por los algoritmos de aprendizaje automático de [!DNL Target]

[!DNL Adobe Target] recopila y utiliza automáticamente varios datos para crear sus algoritmos de personalización en [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] Actividades de (AT). Cuando un visitante introduce un [!UICONTROL Automated Personalization] o [!UICONTROL Segmentación automática] actividad, se pasa una instantánea de información a un conjunto de &quot;registros de formación&quot; (los datos de visitante que aprenden los algoritmos de personalización).

Para obtener más información sobre [!DNL Target] algoritmos de personalización, consulte [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Predeterminado [!DNL Target] categorías de atributos

La siguiente tabla muestra los datos recopilados por [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] actividades de forma predeterminada, sin ninguna configuración de [!DNL Target] u otros [!DNL Adobe] soluciones. La tabla también incluye la convención de nomenclatura utilizada para indicar estos atributos en [Informes de Perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Los datos de entrada establecidos se pueden aumentar en cualquier momento. Para obtener más información acerca de cómo cargar datos adicionales, consulte  [Carga de datos para [!DNL Target] algoritmos de personalización](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Categoría de datos | Prefijo del sistema | Descripción | Nombre para mostrar en [!UICONTROL Insights] informes |
| --- | --- | --- | --- |
| Parámetros de entorno | ENV | Información sobre el entorno de un usuario, incluido el sistema operativo, el explorador y la hora del día/día de la semana. | Explorador - [Nombre de atributo]<br>Sistema operativo - [Valor] |
| Geografía | GEO | Información sobre la ubicación geográfica de un usuario, obtenida mediante la búsqueda de IP. | Geo - [atributo geográfico] |
| Dispositivo móvil | MOB | Información acerca del dispositivo móvil de un usuario. | Dispositivo - [atributo de dispositivo]<br>Móvil - [atributo móvil] |
| [!DNL Target] segmentos de informes | SEG | Segmentos de informes configurados en [!DNL Target] informes. | Segmento de informes -[Nombre del segmento] |
| Comportamiento de sesión | SES | Información sobre el comportamiento del usuario, como el número de páginas vistas. | Perfil del visitante - [Nombre de atributo] |

## Personalizado [!DNL Target] categorías de atributos

La siguiente tabla muestra los datos proporcionados por el cliente y recopilados por [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] actividades. Estos datos se recopilan únicamente si se proporcionan. Los nombres de atributos específicos y los valores de muestra son específicos de la configuración del sistema.

| Categoría de datos | Prefijo del sistema | Descripción | Nombre para mostrar en [!UICONTROL Insights] informes |
| --- | --- | --- | --- |
| Parámetros de página | CAJA | Parámetros de página personalizados (&quot;parámetros de mbox&quot;) pasados en la llamada a [!DNL Target]. | Personalizado: parámetro de mbox [nombre del parámetro] |
| [!DNL Target] perfil | PRO | Los atributos de perfil personalizados se cargan directamente en [!DNL Target] perfil mediante API o parámetro de página y [!DNL Target] scripts de perfil. | Personalizado - Perfil del visitante - [nombre de atributo] |
| Atributos del cliente | CRS | Atributos del cliente cargados en [!DNL Target] perfil a través de [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personalizado - Perfil del visitante - [nombre de atributo] |
| parámetros de URL. | Dirección URL | URL y cualquier parámetro de URL para la página visualizada actualmente. | Personalizado: parámetro de URL [Parámetro URL] |
| Dirección URL de referencia | REF | URL de referencia y cualquier parámetro de URL para la URL de referencia. | Personalizado - [Parámetro de URL referente] - [Valor de parámetro] |
| [!DNL Adobe Experience Cloud] audiencias compartidas | AAM | Todas las audiencias compartidas con [!DNL Target] de otros [!DNL Adobe Experience Cloud] soluciones (por ejemplo, [!DNL Adobe Audience Manager] y [!DNL Adobe Analytics], a través de [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personalizado - Audiencia de Experience Cloud - [Nombre de audiencia] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | Audiencias de CDP en tiempo real de Platform compartidas con [!DNL Target] mediante [!UICONTROL Destinos]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] atributos | AEP | Atributos CDP en tiempo real de Platform compartidos con [!DNL Target] mediante [!UICONTROL Destinos]. |  |

## Bloqueo de funciones de [!DNL Target] algoritmos de aprendizaje automático

Las funciones se pueden bloquear desde [!DNL Target] algoritmos de aprendizaje automático, lo que impide su uso en cualquier [!UICONTROL Automated Personalization] o [!UICONTROL Segmentación automática] modelo o actividad.

Para obtener más información, consulte [Información general sobre la API de modelos (Inclusión en la lista de bloqueados)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} en el *[!DNL Adobe Target]Guía para desarrolladores*.

## Datos de dispositivos y móviles {#device-mobile}

| Nombre de atributo | Descripción de atributo | Valores de muestra | Nombre del sistema |
| --- | --- | --- | --- |
| Mobile - Device - Brand | Marca del dispositivo móvil que el visitante utilizó para acceder a la actividad. | Apple | MOB_targeting.mobile.vendor |
| Mobile - Device - eReader | Especifica si el dispositivo es un eReader. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.ereader |
| Mobile - Device - Game Console | Especifica si el dispositivo es una videoconsola. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | Especifica si el dispositivo es un reproductor multimedia. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | Especifica si el dispositivo es un teléfono móvil. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | El nombre del modelo del dispositivo móvil que el visitante utilizó para acceder a la actividad. | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | Especifica si el dispositivo es un cuadro de configuración superior. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | Especifica si el dispositivo es una tablet. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | Densidad de píxeles del dispositivo móvil que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. | MOB_targeting.mobile.displayPpi |
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows], etc.) | Especifica si el usuario ha utilizado un OSX (o [!DNL Android], [!DNL Windows], etc.) para acceder a la actividad. | 0 es Falso, 1 es Verdadero | MOB_targeting.mobile.os[SO]<br>Por ejemplo, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | Altura de la pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | Ancho de pantalla del dispositivo móvil (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Datos ambientales {#env}

| Nombre de atributo | Descripción de atributo | Valores de muestra | Nombre del sistema |
| --- | --- | --- | -- |
| Browser - Day of Week | El día de la semana en el que el visitante accedió a la actividad. | 0 – 6.<br>(0 es domingo) | ENV_DayOfWeek |
| Browser - Hour of Day | Hora del día en que el visitante accedió a la actividad. | 0 - 23<br>(0 es medianoche) | ENV_UserHour |
| Browser - Hour of Week | Hora de la semana en la que el visitante accedió a la actividad. | 0 - 168<br>(El domingo a medianoche es 0) | ENV_WeekHour |
| Browser - Language Setting | El idioma especificado en el explorador del visitante utilizado para acceder a la actividad. | English<br>German | ENV_Language |
| Browser - Time of Day | Hora del día del explorador cuando el visitante accedió a la actividad. | 0, 6, 12, 18<br>(0 es la noche, 6 es mañana,<br>12 es mediodía, 18 es tarde) | ENV_LocalTimePeriod |
| Browser - Timezone | Zona horaria del visitante al acceder a la actividad. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | Tipo de explorador que el visitante utilizó al acceder a la actividad. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Otro: | ENV_Browser |
| Browser - Weekday/Weekend | Estado de trabajo cuando el visitante accedió a la actividad (fin de semana, jornada laboral o tiempo libre entre semana). | Sábado y domingo son fin de semana<br>De lunes a viernes de 09:00 a 18:00 es jornada laboral<br>De lunes a viernes después de las 18:00 hasta las 09:00 es tiempo libre entre semana | ENV_UserHourType |
| Browser - Window Height (px) | Altura de la ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc., | ENV_BrowserHeight |
| Browser - Window Width (px) | Ancho de ventana del explorador (en píxeles) que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc., | ENV_BrowserWidth |
| Device - Screen Height (px) | Altura de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc., | ENV_ScreenHeight |
| Device - Screen Width (px) | Ancho de pantalla del dispositivo que el visitante utilizó para acceder a la actividad. | 1, 2, 3, etc., | ENV_ScreenWidth |
| Sistema operativo | Sistema operativo en el dispositivo del visitante utilizado para acceder a la actividad. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Buscar bots<br>SO desconocido | ENV_OperatingSystem |
| Operating System - Version | Versión del sistema operativo que el visitante utilizó para acceder a la actividad. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | Primera página que vio el visitante al acceder al sitio. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Datos geográficos {#geo}

| Nombre de atributo | Descripción de atributo | Valores de muestra | Nombre del sistema |
| --- | --- | --- | --- |
| Geo - City | Ciudad desde la que el visitante accedió a la actividad. | San Francisco | Geo_City |
| Geo - Country | País desde el que el visitante accedió a la actividad. | Alemania | País_geográfico |
| Geo - DMA | El área designada de marketing (DMA) desde la que el visitante accedió a la actividad. | Charlottesville | Geo_DMA |
| Geo - Latitude | Latitud desde la cual el visitante accedió a la actividad. | 47,269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) | GEO_Latitude |
| Geo - Longitude | Longitud desde la cual el visitante accedió a la actividad. | -122,269<br>Redondeado a 3 decimales (precisión de 100 metros aproximadamente) | GEO_Longitude |
| Geo - State/Region | Estado o región desde donde el visitante accedió a la actividad. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - Zip Code | Código postal desde el cual el visitante accedió a la actividad. | 84004 | GEO_ZipCode |
| Mobile - Carrier | Operador de telefonía móvil que el visitante utilizó al acceder a la actividad. | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| Network - Connection Speed | Velocidad de conexión de red del dispositivo cuando el visitante accedió a la actividad. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite | GEO_ConnectionSpeed |
| Network - Domain Name | El nombre del dominio de red desde el cual el visitante accedió a la actividad. | `nnt.net` | GEO_DomainName |
| Network - ISP | La red desde la cual el visitante accedió a la actividad. | nnt communications corporation | GEO_IspName |

## Datos de sesión {#session}

| Nombre de atributo | Descripción de atributo | Valores de muestra | Nombre del sistema |
| --- | --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Especifica la suma de todos los valores de pedidos en todas las visitas o sesiones a una actividad concreta. | Doble | SES_CUMULATIVE_ORDER_VALUE |
| Visitor Profile - Activity Lifetime Time on Site | Especifica el tiempo total invertido en el sitio, excluida la sesión actual, y se actualiza cuando caduca la sesión. | Doble, milisegundos | SES_TOTAL_TIME |
| Visitor Profile -Average Page Views per Visit during Activity | Especifica el número promedio de vistas de página por sesión, excluida la sesión actual. | Doble | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | Especifica el tiempo promedio empleado por visita/sesión. Esto no incluye la sesión actual. | Doble, milisegundos | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | Especifica la hora de la primera visita en la que el usuario interactuó con [!DNL Target]. | Doble, milisegundos | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Especifica las horas desde la última visita a esta actividad en particular. | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Especifica el número de impresiones de una combinación de contenido/ubicación en particular en una actividad concreta. | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Perfil del visitante - Último [!DNL Target] Interacción | Especifica la hora de la última interacción con [!DNL Target]. La interacción se produce en cada [!DNL Target] solicitud porque la implementación actual de [!DNL Target] actualiza el perfil en cada solicitud. | Doble, milisegundos | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Especifica el número total de vistas de página (impresiones), incluida la visita o sesión actual hasta que el visitante entra en la actividad. | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Especifica el número de vistas de página en la visita o sesión actual hasta que el visitante entra en la actividad. En concreto, el número de impresiones. Estas impresiones no son vistas reales de la página, sino el número de veces que la solicitud llegó a [!DNL Target]. [!DNL Target] no puede distinguir entre tiempos de espera u otros motivos por los que el usuario no recibió o visualizó el contenido. | Doble (solo número positivo entero) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Especifica la hora en la que se produce la visita o sesión actual con [!DNL Target] iniciado. La visita con [!DNL Target] se puede iniciar sin entrar en una actividad. Todo lo que se requiere es una llamada a cualquier [!DNL Target] solicitud. Un visitante puede tardar un poco hasta entrar en la actividad y registrar el acceso. | Doble, milisegundos | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Especifica la hora de la última visita o sesión con [!DNL Target] iniciado. Este atributo se actualiza cuando caduca la sesión.<br>Si esta es la primera sesión del visitante, resulta en `LAST_SESSION_START = 0.` | Doble, milisegundos | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Especifica la duración entre la sesión anterior y la hora en la que el usuario entra en la actividad y se registra el acceso. | Doble, milisegundos | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Especifica la diferencia entre la última interacción con [!DNL Target] y cuando comenzó la visita actual. Este atributo puede considerarse una duración de visita/sesión hasta que el usuario entre en la actividad y se registre el acceso.<br>Los valores negativos se producen cuando la sesión comienza y la última hora de actualización se activan de la misma forma [!DNL Target] llamada. Los valores negativos deben considerarse como 0 (cero). | Doble, milisegundos | SES_SESSION_TIME |
| Perfil del visitante - Visitas totales | Especifica el número total de visitas/sesiones. No incluye la visita o sesión actual. | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Especifica el número de visitas a una actividad concreta. Si no hay ninguna visita anterior, devuelve 0 (cero). | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Especifica el número de visitas/sesiones a una actividad concreta cuando hay al menos una conversión durante la visita. | Doble | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Número de visitas/sesiones sin conversiones a una actividad en particular. Este valor se restablece en cero después de la conversión o -1 si la conversión no ha sucedido nunca. | Doble (solo número positivo entero) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
