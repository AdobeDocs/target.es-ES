---
keywords: Segmentación;informes de AP;informes de personalización automatizada;segmentación automática;informe de segmentación automática;informes de segmentación automática;personalización;perspectivas;segmentos automatizados;faq;preguntas más frecuentes;atributos importantes
description: 'Aprenda a utilizar los informes especializados para las actividades de Automated Personalization (AP) y Segmentación automática (AT): Segmentos automatizados y Atributos importantes.'
title: ¿Cómo utilizo los informes de Perspectivas de personalización?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 46%

---

# Informes de Perspectivas de personalización

Los usuarios de las actividades de [!UICONTROL Personalización automatizada] (AP) y Segmentación automática (AT) disponen de dos informes especializados: los informes [!UICONTROL Segmentos automatizados] y Atributos importantes.

>[!NOTE]
>
>Tenga en cuenta lo siguiente al utilizar los informes de Perspectivas de personalización:
>
>* Las actividades de AP y AT están disponibles como parte de la solución [!DNL Target Premium]. No se incluyen en [!DNL Target Standard] sin una licencia [!DNL Target Premium].
>
>* [!UICONTROL Los informes de Perspectivas de personalización están disponibles solo para actividades de AP y AT que utilizan un objetivo de optimización de conversión. ] Tampoco se admiten las actividades en las que el objetivo de optimización se cambió a la conversión de ingresos después de que la actividad ya estaba activa.
>
>* [!UICONTROL Perspectivas de personalización] Los informes de solo están disponibles si la variable [!UICONTROL Objetivo principal] se selecciona en el [!UICONTROL Métrica de informes] lista desplegable.
>
>* Los informes de perspectivas de personalización solo son compatibles con el [entorno predeterminado](/help/main/administrating-target/hosts.md).
>
>* [!UICONTROL Perspectivas de personalización] los informes solo se generan para las actividades que se encuentran en la variable [!UICONTROL Activo] estado y se han activado y recibido tráfico durante al menos 15 días.


## Descripción general de los informes de Perspectivas de personalización {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

El objetivo de los informes de [!UICONTROL Perspectivas de personalización] es proporcionar más información sobre cómo los modelos de personalización de Target que hay tras las actividades de AP y AT personalizan el tráfico de visitantes.  El [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) es la base del [!DNL Target] modelos de personalización.

Porque el objetivo del [!UICONTROL Perspectivas de personalización] es comprender cómo se usa la función [!DNL Target] modelos de personalización decidieron enviar a qué visitante qué parte o partes del contenido, la variable [!UICONTROL Perspectivas de personalización] Los informes de solo reflejan un subsegmento de todo el tráfico servido por su actividad de AP o AT. Específicamente, los dos informes reflejan todo el tráfico que utilizó el modelo de personalización. En otras palabras, los informes de [!UICONTROL Perspectivas de personalización] no tienen en cuenta ni el tráfico de control ni el tráfico servido por el modelo ganador general.

Dos [!UICONTROL Perspectivas de personalización] hay informes disponibles:

| Informe | Detalles |
|--- |--- |
| [!UICONTROL Segmentos automatizados] | Los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra los distintos segmentos automatizados definidos por la variable [!DNL Target] los modelos de personalización respondieron a las ofertas y experiencias de la actividad. |
| [!UICONTROL Atributos importantes] | En las distintas actividades, distintos atributos son más o menos importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa. |

## Interpretación de atributos en Perspectivas de personalización {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

En los informes de [!UICONTROL Perspectivas de personalización] se representan dos tipos de atributos que se utilizan en los modelos de AP y Segmentación automática:

* **Atributos recopilados automáticamente por :**[!DNL Target] Target utiliza un conjunto de datos base para crear sus algoritmos de personalización en actividades de AP y AT que se reflejan en Perspectivas de personalización. Consulte [Recopilación de datos para los algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para tipos de datos, atributos de ejemplo y sus [!UICONTROL Perspectivas de personalización] convención de nomenclatura. Tenga en cuenta que, aunque estos atributos se tienen en cuenta, los modelos de una actividad concreta podrían no utilizarlos todos en el modelo final.
* **Atributos pasados a Target:** Consulte [Carga de datos para los algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] proporciona muchas maneras de pasar datos adicionales a [!DNL Target] para enriquecer el conjunto de datos base utilizado para crear sus algoritmos de personalización en las actividades AP y AT:

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos |
|--- |--- |--- |
| Atributos de perfil, incluidos los scripts de perfil, API de actualización de perfil y atributos de perfil en página | La información que haya decidido incluir en el perfil de usuario de Target.<br>Esta información podría provenir de los scripts de perfil, de la información cargada mediante la API de actualización de perfil o de los parámetros de perfil de mbox con el prefijo “perfil”. | `Custom - Profile - [parameter name]` |
| Parámetros de página (también denominados &quot;parámetros de mbox&quot;) | Pares de nombre/valor que se pasan directamente mediante código de página y que no se almacenan en el perfil del visitante para su uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos del cliente | Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiencias compartidas (Adobe Audience Manager o Adobe Analytics) | Audiencias creadas a través de Adobe Audience Manager o Adobe Analytics y compartidas con Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiencias compartidas (Adobe Experience Platform/CDP en tiempo real) | Audiencias creadas mediante Adobe Experience Platform/Real-time CDP y compartidas con Target mediante Destinos. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Atributos compartidos (Adobe Experience Platform/CDP en tiempo real) | Atributos creados mediante Adobe Experience Platform/Real-time CDP y compartidos con Target mediante Destinos. Esta función está actualmente en versión beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Audiencias/segmentos de informes de actividad | Audiencias definidas en su actividad de AP o Segmentación automática durante la configuración en &quot;Objetivos y métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Preguntas frecuentes

Lista de las preguntas más frecuentes sobre [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] [!UICONTROL Insights] informes.

### ¿Durante cuánto tiempo persisten los datos de los modelos de [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática]?

[!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] Los modelos de reciben formación sobre los últimos 45 días de comportamiento del usuario (perfiles de usuario, eventos de impresión y eventos de conversión) para la actividad.

[!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] Los modelos de conservan el comportamiento del usuario, los registros de formación y los datos de decisión del modelo durante 90 días para producir [!UICONTROL Insights] informes. Después de 90 días, los registros de formación y las decisiones de modelo se descartan. [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] Los modelos de también conservan los datos agregados de impresiones y conversiones de nivel de oferta/experiencia a efectos de la creación de informes durante dos años. Estos datos son solo datos de nivel agregado y no contienen datos de perfil de nivel individual.

## Vídeo de formación: Uso de los informes de Perspectivas de personalización ![Distintivo de tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obtener más información, consulte [Uso de los informes de Perspectivas de personalización en Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe Blogs

* Parte 1: [Sacar el misterio de la magia de la personalización impulsada por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Un vistazo tras la cortina de la IA para la personalización en Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX: la solución al problema de la caja negra de la personalización impulsada por IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
