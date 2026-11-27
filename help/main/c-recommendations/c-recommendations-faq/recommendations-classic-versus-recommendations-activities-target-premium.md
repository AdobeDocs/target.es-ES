---
keywords: Recommendations;algoritmos de Recommendations;actividad de Recommendations;Recommendations Classic
description: Revise la información para comprender las diferencias entre las actividades heredadas de Recommendations Classic y las de Recommendations en [!DNL Target] Premium.
title: ¿Cuál es la diferencia entre Recommendations Classic y Recommendations en [!DNL Target] Premium?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
TQID: 'https://experienceleague.adobe.com/EoTkyY0kOwRKT52WIwOuTCoUziIJOnNtTo6llsTNpsM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%
---
# Comparación entre Recommendations Classic y actividades de Recommendations en [!DNL Target] Premium {#classic-versus-activities}

>[!BEGINSHADEBOX]

**En esta página:** Descubra en qué se diferencia [!DNL Recommendations Classic] de [!DNL Recommendations] actividades en [!DNL Target Premium], para elegir entre ellas.

>[!ENDSHADEBOX]

>[!NOTE]
>
>Las actividades de [!DNL Recommendations] están disponibles como parte de la solución [!DNL Target Premium]. No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].

En el producto clásico de [!DNL Recommendations], las recomendaciones se mostraban al crear un mbox de recopilación de datos en una página y, después, al añadir un mbox de visualización en una ubicación de página específica. La actividad [!DNL Recommendations] en [!DNL Target Premium] recopila información sobre el visitante y crea las recomendaciones en cualquier parte de la página, sin un mbox para cada ubicación donde se recomienden productos o contenido. Una referencia de JavaScript en el encabezado de la página habilita las recomendaciones en cualquier parte de la página. Esta referencia pasa claves, como `entity.id` y `entity.categoryId`, al mbox global [!DNL Target].

[!DNL Recommendations Classic] aparece con su propia tarjeta en la interfaz de usuario de [!DNL Experience Cloud]. Dentro del flujo de trabajo de [!DNL Recommendations] hay disponible una actividad de [!DNL Target Premium].

Los usuarios de [!DNL Recommendations Classic] pueden seguir utilizando sus mboxes de [!DNL Recommendations] en [!DNL Target Recommendations]. Los enfoques classic y [!DNL Target] también se pueden combinar conservando los mboxes y usando el código JavaScript en el encabezado para activar la funcionalidad [!DNL Recommendations] para los demás elementos de la página. Sin embargo, para obtener la funcionalidad completa de [!DNL Target], es posible que [!DNL Recommendations Classic] usuarios prefieran eliminar el mbox antiguo y depender solamente de [!DNL Target Recommendations].

La actividad [!DNL Recommendations] en [!DNL Target] mejora con respecto a [!DNL Recommendations Classic] en las siguientes áreas principales.

## Recomendaciones como oferta {#recs-as-offer}

Las recomendaciones se pueden incluir dentro de la [!UICONTROL prueba A/B] (incluidas las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]) y [!UICONTROL Segmentación de experiencias] (XT). Esto permite, entre otras capacidades, probar y segmentar contenido de recomendaciones y no recomendaciones dentro de la misma actividad. Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

## Criterios {#criteria-comparison}

[!DNL Target Recommendations] incluye una biblioteca de criterios con conjuntos empaquetados previamente de reglas y configuraciones. En [!DNL Recommendations Classic], cada recomendación se creó manualmente rellenando un formulario y eligiendo entre una gran lista de reglas. Cuando se crea una actividad [!DNL Recommendations], se elige un conjunto de criterios preconfigurados. Se pueden crear recomendaciones personalizadas, pero la biblioteca de criterios contiene muchas de las configuraciones más comunes, prediseñadas para simplificar el proceso y utilizar un lenguaje que la gente entienda. Los criterios preempaquetados se pueden utilizar tal cual, o bien copiarse y editarse para adaptarlos a necesidades específicas.

![Diapositiva que muestra una tarjeta de criterios, de venta ascendente, con el idioma que entienden las personas, las reglas y la lógica, y la configuración etiquetada](assets/overview_criteria.png)

Los criterios están preconfigurados y ordenados por sectores, tipos de página e implementación. Por ejemplo, los criterios que se aplican al vertical minorista se pueden encontrar para usarlos en una página de productos, que muestre productos de una categoría en particular (definida por el parámetro `entity.categoryID`).

Para obtener más información sobre el uso y la creación de criterios, consulte [Criterios](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Flujo de trabajo {#workflow-comparison}

El flujo de trabajo [!DNL Recommendations] se ha simplificado. En lugar de formularios complicados, un flujo de trabajo visual le guiará por los siguientes pasos:

1. Seleccionar el criterio.
1. Seleccione un [diseño](/help/main/c-recommendations/c-design-overview/create-design.md#create-design) preconfigurado.
1. Obtener una vista previa de las recomendaciones resultantes.

## Vista previa {#visual-preview}

Las recomendaciones se pueden previsualizar una vez configuradas y se pueden realizar los cambios necesarios, sin crear las recomendaciones en la página y luego probarlas. Las vistas previas están disponibles desde [!DNL Target].

## Segmentación {#targeting-comparison}

[!DNL Recommendations Classic] tenía seis opciones de segmentación. [!DNL Recommendations] actividades usan el rango completo de [!DNL Target] opciones de segmentación. Una audiencia se define usando [!DNL Target] u otras [!DNL Adobe Experience Cloud] audiencias (como [!DNL Audience Manager] y [!DNL Analytics]). A continuación, se selecciona el porcentaje de participantes en la actividad que ven cada diseño y el porcentaje que ve el control.

![Diagrama de flujo con la audiencia de Todos los visitantes, los criterios de mejora de ventas, tres diseños con un 30% de tráfico cada uno y el grupo de control Sin recomendación](assets/overview_targeting.png)

## Creación de informes {#reporting-comparison}

En [!DNL Target], [!DNL Recommendations] proporciona informes mejorados que aprovechan las capacidades de [!DNL Target] y [!DNL Experience Cloud]. En lugar de mostrar solamente el alza que [!DNL Recommendations] proporciona comparada con los resultados sin ellos, los informes muestran información completa sobre la actividad [!DNL Recommendations].

