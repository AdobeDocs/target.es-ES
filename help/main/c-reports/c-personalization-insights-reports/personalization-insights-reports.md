---
keywords: Segmentación;informes de AP;informes de personalización automatizada;segmentación automática;informe de segmentación automática;informes de segmentación automática;personalización;perspectivas;segmentos automatizados;faq;preguntas más frecuentes;atributos importantes
description: 'Aprenda a utilizar los informes especializados para las actividades de Automated Personalization (AP) y Segmentación automática (AT): Segmentos automatizados y Atributos importantes.'
title: ¿Cómo utilizo los informes de Personalization Insights?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] informes

Hay disponibles dos informes especializados para los usuarios de las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT): los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes].

## Consideraciones

Tenga en cuenta lo siguiente al usar [!UICONTROL Personalization Insights] informes:

* Las actividades de AP y AT están disponibles como parte de la [[!DNL Target Premium] solución](/help/main/c-intro/intro.md#premium). No se incluyen en [!DNL Target Standard] sin una licencia [!DNL Target Premium].

* Los informes de [!UICONTROL Personalization Insights] solo están disponibles para actividades AP y AT configuradas de la siguiente manera:

   * Informes de [!DNL Target] > [!UICONTROL Conversion]

     Por ejemplo:

     ![Informes de Target > Conversión](/help/main/c-reports/assets/conversion.png)

   * Informes de [!DNL Analytics] > [!DNL Conversion]

     Por ejemplo:

     ![Informes analíticos > Conversión](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * Informes de [!DNL Analytics] > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     Por ejemplo:

     ![Usar una métrica de Analytics > Maximizar tasa de conversión de visitas](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* Tampoco se admiten las actividades en las que el objetivo de optimización se cambió a la conversión de ingresos después de que la actividad ya estaba activa.

* Los informes de [!UICONTROL Personalization Insights] solo están disponibles si se ha seleccionado [!UICONTROL Primary Goal] en la lista desplegable [!UICONTROL Report Metric].

* Los informes de [!UICONTROL Personalization Insights] solo se admiten en el [entorno predeterminado](/help/main/administrating-target/hosts.md).

* Los informes de [!UICONTROL Personalization Insights] se generan solamente para las actividades que están en estado [!UICONTROL Live] y que se han activado y recibido tráfico durante al menos 15 días.

## Información general de informes de Personalization Insights {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

El objetivo de los informes de [!UICONTROL Personalization Insights] es proporcionar más información sobre cómo los modelos de personalización de [!UICONTROL Target] detrás de las actividades AP y AT personalizan el tráfico de visitantes. El [algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) es la base de los modelos de personalización [!DNL Target].

Dado que el objetivo de los informes de [!UICONTROL Personalization Insights] es comprender cómo decidieron los modelos de personalización de [!DNL Target] enviar el contenido a los visitantes, los informes de [!UICONTROL Personalization Insights] solo reflejan un subsegmento de todo el tráfico servido por su actividad de AP o AT. Específicamente, los dos informes reflejan todo el tráfico que utilizó el modelo de personalización. En otras palabras, los informes de [!UICONTROL Personalization Insights] no consideran el tráfico de control ni el tráfico servido por el modelo ganador general.

Hay disponibles dos informes de [!UICONTROL Personalization Insights]:

| Informe | Detalles |
|--- |--- |
| [!UICONTROL Automated Segments] | Los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de [!DNL Target] respondieron a las ofertas y experiencias de la actividad. |
| [!UICONTROL Important Attributes] | En las distintas actividades, distintos atributos son más o menos importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa. |

## Interpretación de atributos en Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Existen dos tipos de atributos representados en [!UICONTROL Personalization Insights] informes que se utilizan en sus modelos de AP o Segmentación automática:

* **Atributos recopilados automáticamente por Target:** [!DNL Target] utiliza un conjunto de datos base para crear sus algoritmos de personalización en actividades AP y AT que se reflejan en Personalization Insights. Consulte [Recopilación de datos para algoritmos Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para ver los tipos de datos, atributos de ejemplo y su convención de nomenclatura [!UICONTROL Personalization Insights]. Tenga en cuenta que, aunque estos atributos se tienen en cuenta, los modelos de una actividad concreta podrían no utilizarlos todos en el modelo final.
* **Atributos pasados a Target:** Consulte [Carga de datos para los algoritmos de Personalization de Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] proporciona muchas maneras de pasar datos adicionales a [!DNL Target] para enriquecer el conjunto de datos base utilizado para crear sus algoritmos de personalización en las actividades AP y AT:

| Tipo de datos | Descripción | Nomenclatura de los tipos de datos |
|--- |--- |--- |
| Atributos de perfil, incluidos los scripts de perfil, API de actualización de perfil y atributos de perfil en página | La información que haya decidido incluir en el perfil de usuario de Target.<br>Esta información podría provenir de los scripts de perfil, de la información cargada mediante la API de actualización de perfil o de los parámetros de perfil de mbox con el prefijo “perfil”. | `Custom - Profile - [parameter name]` |
| Parámetros de página (también denominados &quot;parámetros de mbox&quot;) | Pares de nombre/valor que se pasan directamente mediante código de página y que no se almacenan en el perfil del visitante para su uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos del cliente | Los atributos del cliente le permiten cargar datos de perfil del visitante a través del FTP a Experience Cloud. Una vez cargados, podrá sacar el máximo partido de los datos en Adobe Analytics y Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Audiencias compartidas (Adobe Audience Manager o Adobe Analytics) | Audiencias creadas a través de Adobe Audience Manager o Adobe Analytics y compartidas con Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Audiencias compartidas (Adobe Experience Platform/CDP en tiempo real) | Audiencias creadas mediante Adobe Experience Platform/Real-time CDP y compartidas con Target mediante Destinos. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Atributos compartidos (Adobe Experience Platform/CDP en tiempo real) | Atributos creados mediante Adobe Experience Platform/Real-time CDP y compartidos con Target mediante Destinos. Esta función se encuentra actualmente en Beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Audiencias/segmentos de informes de actividad | Audiencias definidas en su actividad de AP o Segmentación automática durante la configuración en &quot;Objetivos y métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Preguntas frecuentes

Lista de las preguntas más frecuentes sobre los informes [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] [!UICONTROL Insights].

### ¿Durante cuánto tiempo persisten los datos de los modelos [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target]?

Los modelos [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] se han entrenado en los últimos 45 días del comportamiento del usuario (perfiles de usuario, eventos de impresión y eventos de conversión) para la actividad.

Los modelos [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] conservan el comportamiento del usuario, los registros de formación y los datos de decisión de modelos durante 90 días para producir [!UICONTROL Insights] informes. Después de 90 días, los registros de formación y las decisiones de modelo se descartan. Los modelos [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] también conservan los datos agregados de impresión y conversión a nivel de oferta/experiencia para la creación de informes durante dos años. Estos datos son solo datos de nivel agregado y no contienen datos de perfil de nivel individual.

## Vídeo de formación: Uso de los informes de Personalization Insights ![Distintivo de tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obtener más información, consulte [Uso de los informes de Personalization Insights en Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs de Adobe

* Parte 1: [Sacar el misterio de la magia del Personalization impulsado por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Un vistazo detrás de la cortina de IA para Personalization en Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — la solución al problema de la caja negra del Personalization impulsado por IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
