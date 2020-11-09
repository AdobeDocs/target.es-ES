---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: Las actividades de Recommendations en Adobe Target muestran automáticamente productos o contenido que puede interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.
title: Adobe Target Recommendations
feature: recommendations general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 59%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations{#recommendations}

[!DNL Adobe Target Recommendations] Las actividades muestran automáticamente productos, servicios o contenido que pueda ser de interés para sus visitantes en función de la actividad previa del usuario, las preferencias u otros criterios. [!DNL Target Recommendations] ayuda a dirigir el visitante a elementos relevantes que de otra manera no conocerían. [!DNL Recommendations] le permite proporcionar a sus visitantes contenido relevante en el momento adecuado y en el lugar adecuado.

>[!NOTE]
>
>Las actividades de [!DNL Recommendations] están disponibles como parte de la [solución Target Premium](/help/c-intro/intro.md#premium). No están disponibles en [!DNL Target Standard] sin una licencia de [!DNL Target Premium].
>
>Si tiene [!DNL Recommendations Classic], para obtener más información acerca de las dos soluciones, consulte [Recommendations Classic comparado con Recommendations Activities en Target Premium](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5).

[!DNL Recommendations] le ayuda a optimizar y personalizar sugerencias en tiempo real en una variedad de canales, aplicaciones, páginas, mensajes de correo electrónico y otras opciones de entrega con el fin de aumentar la participación y la conversión, así como de reducir los esfuerzos de administración.

[!DNL Recommendations] ayuda a:

* Crear criterios (reglas) sofisticados para automatizar las recomendaciones
* Mostrar automáticamente las recomendaciones mediante algunos fragmentos de código JavaScript
* Probar y optimizar los criterios de recomendaciones y los diseños que se muestran en las recomendaciones
* Crear informes con los resultados de las actividades de Recommendations

La siguiente ilustración muestra recomendaciones en una página web:

![](assets/velocity_example.png)

Una recomendación determina cómo se sugiere un producto a un visitante, según las actividades de ese visitante en el sitio. Por ejemplo:

| Acción deseada | Recomendación |
|--- |--- |
| Anime a las personas que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. | Cree una recomendación que muestre artículos que a menudo se compran juntos, empleando el criterio “Otras personas que compraron esto también compraron aquello”. |
| Incremente el tiempo que pasan los visitantes en su sitio de contenido multimedia recomendando contenido multimedia parecido al que están viendo. | Cree una recomendación que sugiera otros vídeos, empleando el criterio “Otras personas que vieron esto también vieron aquello”. |
| Sugiera que los clientes que vieron información sobre planes de ahorro en su banco también lean información sobre cuentas de planes de pensiones. | Muestre otros productos que compraron otras personas después de ver un determinado producto, sin mostrar el primer producto en las recomendaciones, empleando el criterio “Otras personas que vieron esto también compraron”. |

Para obtener más información sobre estos y otros criterios de [!DNL Recommendations] consulte [Criterios](/help/c-recommendations/c-algorithms/algorithms.md).

## Términos

Antes de empezar a usar [!DNL Recommendations], es útil familiarizarse con algunos de los términos utilizados en esta sección. No se preocupe si todavía no entiende completamente estos términos, se familiarizará con ellos a medida que configure sus [!DNL Recommendations] actividades.

| Término | Definición |
| --- | --- |
| Actividad | Las actividades de [!DNL Target] permiten personalizar el contenido en audiencias específicas y probar diseños de página. [!DNL Recommendations] es solo uno de los muchos tipos de actividades disponibles en [!DNL Target]. Para obtener más información, consulte Tipos [de actividad de](/help/c-activities/target-activities-guide.md)Destinatario. |
| Entidades | Las entidades se refieren a los elementos que desea recomendar. Las entidades pueden ser cualquier cosa, como productos, contenido (artículos, presentaciones de diapositivas, imágenes, películas y programas de televisión), ofertas de empleo, restaurantes, etc. For more information, see [Entities](/help/c-recommendations/c-products/products.md). |
| Fuentes | Las fuentes se utilizan para importar entidades en [!DNL Recommendations]. Las entidades se pueden enviar con archivos CSV, el formato de fuente de Google Product Search y las clasificaciones de productos de Adobe Analytics. Para obtener más información, consulte [Fuentes](/help/c-recommendations/c-products/feeds.md). |
| Catálogo | Los catálogos hacen referencia a todo el conjunto de productos (entidades). El catálogo puede contener muchas colecciones, una forma de organizar los productos en bloques lógicos. |
| Colección | Las colecciones se refieren a un conjunto de elementos similares o relacionados, como una sola categoría de producto. Sin embargo, puede agrupar cualquier artículo en una categoría que tenga sentido para su negocio, como los productos de un determinado color o rango de precios, o los artículos que pueden resultar interesantes en una determinada área geográfica. For more information, see [Collections](/help/c-recommendations/c-products/collections.md). |
| Criterios | Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.<br>Algunos ejemplos de criterios son: <ul><li>Los usuarios que compraron esto, compraron aquello.</li><li>Los usuarios que vieron esto, vieron aquello.</li><li>Elementos con atributos similares.</li><li>Último artículo comprado</li><li>Categoría favorita</li></ul>  Para obtener más información, consulte [Criterios](/help/c-recommendations/c-algorithms/algorithms.md). |
| Diseños | Los diseños definen el aspecto de las recomendaciones en una [!DNL Recommendations] actividad, como una fila, una columna, una tabla o una cuadrícula. La ilustración de la parte superior de este artículo muestra un diseño de 4 x 1. For more information, see [Create a design](/help/c-recommendations/c-design-overview/create-design.md). |
| Ubicaciones | Las ubicaciones hacen referencia a un área de contenido específica de una página web, aplicación móvil o correo electrónico en la que se ejecuta una actividad con fines de personalización y optimización. |
| Audiencias | Las audiencias son grupos de participantes de actividad similares que verán una actividad de objetivo. Una audiencia es un grupo de personas con las mismas características, como un visitante nuevo, un visitante habitual o un visitante habitual de la zona oeste. La funcionalidad Audiencia le permite segmentar contenido y experiencias diferentes para optimizar el marketing web mostrando los mensajes adecuados para la persona adecuada y en el momento adecuado. Para obtener más información, consulte [Audiencias](/help/c-target/target.md). |
| Recommendations como oferta | Función que permite incluir recomendaciones dentro de actividades de Prueba A/B (incluidas Asignación automática y Destinatario automático) y Segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Vídeo de capacitación: Distintivo ![Información general de tipos de actividades](/help/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium]. Se habla sobre [!DNL Recommendations] a partir del minuto 7:20.

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Seminario web básico de Adobe Target: Introducción a Recommendations ![Insignia de tutorial](/help/assets/tutorial.png) {#intro-to-recs}

El seminario web *Introducción a Recommendations* incluye una exploración exhaustiva de cómo aprovechar el valor de [!DNL Adobe Target Recommendations]. Descubra cómo esta actividad [!DNL Target] muestra automáticamente los productos o el contenido que pueda interesar a sus clientes optimizando las sugerencias en tiempo real en función de las visitas anteriores. Además, sumérjase en la interfaz de usuario [!DNL Target] para obtener información general paso a paso sobre cómo generar una actividad [!DNL Recommendations].

[Introducción a Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)