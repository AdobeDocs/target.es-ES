---
description: Información sobre conceptos clave que le ayudarán a comprender las características y capacidades de Adobe Target.
keywords: Información general y referencia;actividad
seo-description: Información sobre conceptos clave que le ayudarán a comprender las características y capacidades de Adobe Target.
seo-title: Conceptos clave de Target
solution: Target
subtopic: Primeros pasos
title: Conceptos clave de Target
topic: Standard
uuid: c62ac156-b4cf-494c-979f-33f889abd118
translation-type: tm+mt
source-git-commit: b1dd50db873cb9a7cdca976366171ddf0c02d156

---


# Conceptos clave de Target{#target-key-concepts}

Información sobre conceptos clave que le ayudarán a comprender las características y capacidades de Adobe Target.

## Actividades y pruebas {#section_BEA0A0C51A8847579B566060206DE7E8}

Una actividad determina las experiencias que puede recibir un visitante del sitio.

Por ejemplo, podría diseñar una actividad que pruebe dos páginas de aterrizaje diferentes: una que destaque información sobre calzado de verano para señora y otra que destaque ropa de verano más general. La actividad determina las condiciones que controlan cuándo aparece cada una de estas páginas de aterrizaje y las métricas que determinan qué página tiene mayor éxito. La actividad está configurada para comenzar y finalizar cuando se cumplan unas condiciones específicas como, por ejemplo, entre fechas concretas o que comience cuando se apruebe la actividad y finalice cuando se desactive.

Al diseñar una actividad, debería planificarla con mucho cuidado. Determine cuándo comenzará la actividad y la duración que tendrá. A continuación, enumere las ofertas y asigne una audiencia segmentada a cada una de ellas.

Target incluye varios tipos de actividades. En la tabla siguiente se proporciona una descripción general de cada tipo de actividad con vínculos para ayudarle a obtener más información. Para ayudarle a elegir mejor el mejor tipo de actividad, también hemos creado la Guía de actividades [de Adobe Target](/help/c-activities/target-activities-guide.md).

| Tipo de actividad | Descripción |
|--- |--- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Una prueba A/B compara dos o más versiones del contenido de su sitio web para comprobar cuál mejora más las conversiones durante un periodo previamente establecido.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de actividades de prueba A/B](/help/c-recommendations/recommendations-as-an-offer.md). Esta funcionalidad requiere que tenga una licencia [de Target Premium](/help/c-intro/intro.md#premium). |
| [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Asignación automática identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de actividades de asignación automática](/help/c-recommendations/recommendations-as-an-offer.md). Esta funcionalidad requiere que tenga una funcionalidad de testa requiere que tenga una licencia [de Target Premium](/help/c-intro/intro.md#premium). |
| [Auto-targettarget](/help/c-activities/auto-target-to-optimize.md)<br>![Premium](/help/assets/premium.png) | La segmentación automática utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función de su perfil de cliente y del comportamiento de visitantes anteriores con perfiles similares, todo ello con el fin de personalizar el contenido y dirigir las conversiones.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de actividades de segmentación automática](/help/c-recommendations/recommendations-as-an-offer.md). Esta funcionalidad requiere que disponga de esta funcionalidad para que tenga una licencia [de Target Premium](/help/c-intro/intro.md#premium). |
| [Uso de datos de Analytics](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A 4 T) | Puede configurar una actividad para que use [!DNL Adobe Analytics] como fuente de informes. Para este tipo de actividad es necesario que vincule su cuenta de [!DNL Adobe Experience Cloud] con [!DNL Analytics] y [!DNL Target]. |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | La prueba multivariable (MVT) compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica, además de identificar qué elemento tiene el mayor impacto en el éxito de la actividad. |
| [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) | Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de actividades de Segmentación de experiencias](/help/c-recommendations/recommendations-as-an-offer.md). Esta funcionalidad requiere que tenga una licencia [de Target Premium](/help/c-intro/intro.md#premium). |
| [Personalización automatizada PersonalizationTarget](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Premium](/help/assets/premium.png) | La personalización automatizada (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante en función de su perfil de cliente, con el fin de personalizar el contenido y dirigir las conversiones. |
| [Recomendaciones starget](/help/c-recommendations/recommendations.md)<br>![Premium](/help/assets/premium.png) | Una recomendación determina el modo en que se sugiere un producto a un usuario del sitio web según las actividades que este realice en el sitio.<br>Por ejemplo, puede que quiera animar a los usuarios que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. Podría crear una recomendación que muestre artículos que a menudo se compran juntos, empleando el algoritmo “Otras personas que compraron esto también compraron aquello”. O puede que quiera animar a los visitantes a pasar más tiempo en su sitio multimedia mediante la recomendación de un vídeo similar al que están viendo, empleando el algoritmo “Otras personas que han visto esto también vieron aquello”.<br>**Nota:** Ahora puede incluir recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Consulte [Recomendaciones como oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Ubicaciones {#section_F18FBF1ED23340ED9F39C51971A4E874}

Una ubicación es básicamente una página de su sitio web. También puede hacer referencia a un lugar en una aplicación móvil, un correo electrónico o cualquier otro lugar donde ejecute una optimización.

Las ubicaciones son esenciales para las actividades y las experiencias. Puede decidir si las ubicaciones realizan una, ambas o ninguna de estas acciones:

* Mostrar e intercambiar contenido para los visitantes.
* Registrar el comportamiento de los visitantes.

En [!DNL Target Standard], una ubicación puede ser cualquier elemento de una página siempre que la página contenga una sola línea de código que active [!DNL Target] en la sección `<head>` de cada página que desee rastrear. Esta línea de código llama a las bibliotecas de JavaScript necesarias para recopilar información y ofrecer experiencias segmentadas para los visitantes de su sitio.

Consulte [Conocimiento sobre las bibliotecas JavaScript de Target](../c-implementing-target/c-considerations-before-you-implement-target/target-implement.md#concept_60B748DE4293488F917E8F1FA4C7E9EB) para obtener más información sobre las diferencias entre la implementación de la ubicación en [!DNL Target Standard] y la implementación de mbox en [!DNL Target Classic].

Las ubicaciones se combinan con audiencias para proporcionar un número casi inagotable de opciones de segmentación de información a sus clientes. Por ejemplo, si un visitante nunca ha estado antes en el sitio, puede mostrar un cupón de descuento para nuevos clientes. Del mismo modo, puede cambiarse la página para que muestre ofertas que estén más optimizadas para clientes que vuelven a visitar el sitio.

También puede usar las ubicaciones para realizar el seguimiento del progreso de un visitante a través del sitio web o rastrear si el visitante completa una métrica de éxito específica como, por ejemplo, añadir un artículo al carro de compras o realizar una compra.

## Experiencias y diseños de página {#section_B806FB752EC1470784755C1EB3D4AC70}

Una experiencia, a veces denominada fórmula, define el contenido que se muestra en su página, así como otros elementos de página, como los vínculos.

Una experiencia determina qué oferta se muestra en un lugar determinado cuando se cumplen las condiciones específicas de segmentación. Por ejemplo, la experiencia determina que, cuando un visitante vuelve a visitar el sitio web, aparecerá una oferta de envío en dos días en la parte superior de la página. La experiencia determina también que, cuando un visitante visita el sitio web por primera vez, aparece un 10 % de descuento en la misma ubicación.

Una experiencia está compuesta por ofertas, recursos de imagen y cualquier otro elemento HTML (como vínculos) que aparezca en la página para ayudar a dirigir al visitante al resultado que desea. [!DNL Target] combina ubicaciones, ofertas y experiencias para determinar qué contenido aparece en el sitio durante una prueba determinada.

Una experiencia también puede ser un diseño de página distinto. Por ejemplo, es posible que una experiencia tenga un conjunto de vínculos en la parte superior de la página, mientras que otra experiencia tenga vínculos diferentes o los mismos vínculos ordenados de manera distinta. Puede interesarle probar si una imagen proporciona más alza que otra, o si hay más probabilidades de que los visitantes hagan clic en un anuncio cerca de la parte superior de la página o en otra ubicación distinta.

[!DNL Target] optimiza las experiencias de cada uno de los visitantes en los puntos de contacto digitales y prueba las distintas experiencias para determinar cuál tendrá más éxito. Si planifica meticulosamente la segmentación de las experiencias, tendrá la garantía de que los visitantes del sitio verán las ofertas más relevantes en las ubicaciones adecuadas de la página, lo que mejorará las probabilidades de que la visita tenga el resultado que desea.

## Ofertas {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

Una oferta es el contenido que se muestra en las páginas web durante las campañas o las actividades.

Cuando realiza una prueba de sus páginas web, se mide el éxito de cada experiencia con diferentes ofertas en sus ubicaciones.

Una oferta puede contener distintos tipos de contenido, incluido:

* Imagen
* Texto
* HTML
* Vínculo
* Botón

Por ejemplo, una página web con dos ofertas podría mostrar cualquiera de las dos, en función de si el visitante ya ha estado en el sitio antes.

Una *experiencia* determina el contenido que se muestra cuando se cumplen unas condiciones determinadas.

## Audiencias{#section_3F32DA46BDF947878DD79DBB97040D01}

Optimice el contenido segmentado de su sitio para los participantes de la actividad que cumplan determinados criterios.

Las audiencias definen el segmento de su actividad y se emplean siempre que la segmentación esté disponible.

Las audiencias de [!DNL Target] conforman un conjunto definido de criterios de visitantes. Se pueden segmentar las ofertas para determinadas audiencias (o segmentos). Solo los visitantes que pertenezcan a esa audiencia verán la experiencia que esté segmentada para ellos.

Por ejemplo, puede segmentar una actividad para una audiencia formada por visitantes que usan un determinado navegador o sistema operativo.

O puede segmentar la actividad para los visitantes que procedan de una zona geográfica concreta o para los usuarios que accedan a la página desde un determinado motor de búsqueda.

Las audiencias se pueden guardar para reutilizarlas en varias actividades o pueden crearse para una campaña específica.

| Tipo de audiencia | Descripción |
|--- |--- |
| Audiencias reutilizables | Pueden seleccionarse audiencias reutilizables para cualquier prueba. Si cambia una de estas audiencias, se cambia para todas las actividades que la usen. |
| Segmentos personalizados | Los segmentos personalizados (también conocidos como segmentos específicos de campaña) son lo que se utilizan en una campaña de Target Classic. Se crean como parte de la campaña y no se pueden reutilizar en otras campañas. |
| Audiencias compartidas | Las audiencias se pueden compartir entre las distintas soluciones de [!DNL Adobe Experience Cloud]. Para ver algunos ejemplos, consulte [Audiencias de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html). |

Si desea obtener información sobre el modo en que el perfil del visitante realiza el seguimiento de la información sobre los visitantes de su página, consulte.[Perfiles de visitantes](../c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1).

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Uso de audiencias en Adobe Target (6:21)

En este vídeo se describe cómo usar las audiencias en [!DNL Target Standard/Premium].

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)