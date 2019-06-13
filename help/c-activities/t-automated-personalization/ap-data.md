---
description: Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
seo-description: Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).
seo-title: Recopilación de datos para los algoritmos de personalización de Target
solution: Target
title: Recopilación de datos para los algoritmos de personalización de Target
title-outputclass: Premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: Premium
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Recopilación de datos para los algoritmos de personalización de Target{#data-collection-for-the-target-personalization-algorithms}

Target recopila y utiliza automáticamente una variedad de datos para crear sus algoritmos de personalización en las actividades de personalización automatizada (AP) y segmentación automática (AT). Cuando un visitante introduce una actividad AP o AT, se pasa una instantánea de información a un conjunto de “registros de formación” (los datos de visitantes que aprenderán los algoritmos de personalización).

Para obtener más información sobre los algoritmos de personalización de Target, consulte  [Algoritmo de bosque aleatorio](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

La tabla siguiente muestra los datos recopilados por Personalización automatizada de forma predeterminada, sin que el experto en marketing tenga que hacer nada. También se recoge la nomenclatura utilizada para indicar estos atributos en los [informes de Perspectivas de personalización](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). Los datos de entrada establecidos se pueden aumentar en cualquier momento. Para obtener más información acerca de cómo cargar datos adicionales, consulte  [Carga de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos | Atributos de ejemplo |
|--- |--- |--- |--- |
| Parámetros de URL | Target inspecciona la URL para extraer los parámetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Datos personalizados |
| Parámetros de URL de referencia | En general, la URL de referencia es la URL que hace referencia a una página en particular que inició la llamada de mbox.<br>Tenga en cuenta que esta variable puede verse afectada por la actividad de los usuarios en su sitio, así como por la implementación técnica de este. | `Custom - [Referring URL Parameter] - [Parameter value]` | Datos personalizados |
| Datos de entorno y sesión | Información sobre cómo y cuándo accede el usuario a la actividad. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Perfil de visitante: inicio de la visita más reciente<br>Perfil de visitante: visitas totales<br>Perfil de visitante: tiempo medio por visita<br>Explorador: zona horaria<br>Explorador: día de la semana<br>Explorador: configuración de idioma<br>Explorador: tipo<br>Sistema operativo: versión |
| Geografía | Información sobre dónde se encuentra el visitante. | `Geo - [geo attribute]` | Ciudad<br>País<br>Región/Estado<br>Código postal<br>Latitud<br>Longitud<br>Proveedor de servicios de internet u operador de telefonía móvil |
| Dispositivo y datos móviles | Dispositivo e información específica del móvil. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Sistema operativo del dispositivo móvil<br>Tamaño de la pantalla del dispositivo móvil |

