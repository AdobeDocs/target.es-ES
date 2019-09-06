---
description: 'Los usuarios de las actividades de Personalización automatizada (AP) y Segmentación automática (AT) disponen de dos informes especializados: los informes Segmentación automática y Atributos importantes.'
keywords: Segmentación;informes de AP;informes de personalización automatizada;segmentación automática;informe de segmentación automática;informes de segmentación automática;personalización;perspectivas;segmentos automatizados;faq;preguntas más frecuentes;atributos importantes
seo-description: 'Los usuarios de las actividades de Personalización automatizada (AP) y Segmentación automática (AT) disponen de dos informes especializados: los informes Segmentación automática y Atributos importantes.'
seo-title: Informes de Perspectivas de personalización
solution: Target
title: Informes de Perspectivas de personalización
title-outputclass: premium
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
badge: premium
translation-type: tm+mt
source-git-commit: c0d0ae6bcd401777169e74b93a4fb18f1a9b24dc

---


# ![PREMIUM](/help/assets/premium.png) Informes de Perspectivas de personalización{#personalization-insights-reports}

Los usuarios de las actividades de Personalización automatizada (AP) y Segmentación automática (AT) disponen de dos informes especializados: los informes Segmentos automatizados y Atributos importantes.

>[!NOTE]
>
>Las actividades de AP y AT están disponibles como parte de la solución [!DNL Target Premium]. No se incluyen en [!DNL Target Standard] sin una licencia [!DNL Target Premium].
>
>Los informes de Perspectivas de personalización están disponibles solo para actividades de AP y AT que utilizan un objetivo de optimización de conversión. Tampoco se admiten las actividades en las que el objetivo de optimización se cambió a la conversión de ingresos después de que la actividad ya estaba activa.
>
>Los informes de perspectivas de personalización solo son compatibles con el [entorno predeterminado](../../administrating-target/hosts.md).
>
>Los informes de perspectivas de personalización se generan solamente para actividades que están en estado Activo y que se han activado y recibido durante al menos 15 días.

## Descripción general de los informes de Perspectivas de personalización {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

El objetivo de los informes de [!UICONTROL Perspectivas de personalización] es proporcionar más información sobre cómo los modelos de personalización de Target que hay tras las actividades de AP y AT personalizan el tráfico de visitantes. El [algoritmo de bosque aleatorio](/help/c-activities/t-automated-personalization/algo-random-forest.md) es la base de los modelos de personalización de Target.

Como el objetivo de los informes de Perspectivas de personalización es comprender cómo han decidido los modelos de personalización de Target enviar el contenido a los visitantes, los informes de Perspectivas de personalización solo reflejan un subsegmento de todo el tráfico servido por su actividad de AP o AT. Específicamente, los dos informes reflejan todo el tráfico que utilizó el modelo de personalización. En otras palabras, los informes de Perspectivas de personalización no tienen en cuenta ni el tráfico de control ni el tráfico servido por el modelo ganador general.

Hay dos informes de Perspectivas de Personalización disponibles:

| Informe | Detalles |
|--- |--- |
| Segmentos automatizados | Los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad. |
| Atributos importantes | En las distintas actividades, distintos atributos son más o menos importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa. |

## Interpretación de atributos en Perspectivas de personalización {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

En los informes de [!UICONTROL Perspectivas de personalización] se representan dos tipos de atributos que se utilizan en los modelos de AP y Segmentación automática:

* **Atributos recopilados automáticamente por Target:** Target utiliza un conjunto de datos base para crear sus algoritmos de personalización en actividades de AP y AT que se reflejan en Perspectivas de personalización. Consulte [Recopilación de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) para los tipos de datos, atributos de ejemplo y la convención de nomenclatura de [!UICONTROL Perspectivas de personalización]. Tenga en cuenta que, aunque estos atributos se toman en consideración, los modelos de una actividad concreta podrían no utilizarlos todos en el modelo final.
* **Atributos pasados a Target:** consulte  [Carga de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

Target le ofrece muchas maneras de incluir datos adicionales con los que enriquecer el conjunto de datos base utilizado para crear sus algoritmos de personalización en actividades de AP y AT:

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos |
|--- |--- |--- |
| Atributos de perfil, incluidos los scripts de perfil, API de actualización de perfil y atributos de perfil en página | La información que haya decidido incluir en el perfil de usuario de Target.<br>Esta información podría provenir de los scripts de perfil, de la información cargada mediante la API de actualización de perfil o de los parámetros de perfil de mbox con el prefijo “perfil”. | `Custom - Profile - [parameter name]` |
| Parámetros de página (también denominados “parámetros de mbox”) | Pares de nombre/valor que se pasan directamente mediante código de página y que no se almacenan en el perfil del visitante para su uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos del cliente | Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiencias compartidas (Adobe Audience Manager o Adobe Analytics) | Audiencias creadas a través de Adobe Audience Manager o Adobe Analytics y compartidas con Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiencias/segmentos de informes de actividad | Audiencias definidas en su actividad de AP o Segmentación automática durante la configuración en “Objetivos y métricas”. | `Custom - Reporting Segment - [segment name]` |

## Vídeo de formación: Uso de los informes de Perspectivas de personalización

>[!VIDEO](https://video.tv.adobe.com/v/25601/?captions=spa)

Para obtener más información, consulte [Uso de los informes de perspectivas de personalización en Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).
