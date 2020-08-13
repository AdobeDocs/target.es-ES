---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Los criterios de Adobe Target Recommendations son reglas que determinan qué productos recomendar en función de un conjunto predeterminado de comportamientos de visitante.
title: Criterios en Adobe Target Recommendations
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 74%

---


# ![PREMIUM](/help/assets/premium.png) Criterios{#criteria}

Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.

Los criterios determinan qué acción se obtendrá en cada recomendación. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Puede seleccionar un sector según los objetivos de la actividad de recomendación:

| Sector | Objetivo |
|--- |--- |
| Venta minorista/Comercio electrónico | Conversión que termina en compra |
| Generación de vanguardia/B2B/Servicios financieros | Conversión sin compra |
| Medios/Publicación | Participación |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

La clave de recomendación que seleccione determina el tipo de criterio. Existen varios tipos de criterios que se representan como tarjetas de criterio cuando configura una actividad de [!DNL Recommendations].

| Tipo de criterio | Claves |
|--- |--- |
| Actividad de la página actual | Recomiende artículos en función de lo que los usuarios hacen en la página actual. Por ejemplo, a los visitantes que ven un determinado artículo podría interesarles ver otros artículos de la misma categoría.<ul><li>Artículo actual</li><li>Categoría actual</li></ul> |
| Personalizado | Recomendar artículos según atributos personalizados.<ul><li>Atributo personalizado</li></ul>Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación.<br>Puede realizar el filtrado en tiempo real sobre su propia salida de criterios personalizados. Por ejemplo, puede limitar sus artículos recomendados solo a aquellos de la categoría o marca favorita de un visitante. Esto le da la capacidad de combinar cálculos sin conexión con filtrado en tiempo real.<br>Esta funcionalidad significa que puede usar Target para agregar una personalización además de sus recomendaciones calculadas sin conexión o listas personalizadas. Esto combina el poder de sus científicos e investigadores de datos con la entrega probada y comprobada de Adobe, el filtrado en tiempo de ejecución, las pruebas A/B, la orientación, los informes, las integraciones y más.<br>Con la adición de reglas de inclusión en Criterios personalizados, convierte las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses de los visitantes.<ul><li>Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.</li><li>Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.</li></ul>Los posibles casos de uso incluyen:<ul><li>Desea recomendar películas de una lista personalizada, pero solo si el visitante no las ha visto.</li><li>Desea ejecutar un algoritmo sin conexión y usar los resultados para potenciar sus recomendaciones, pero debe asegurarse de que los artículos agotados no sean recomendados.</li><li>Desea incluir solo los elementos que pertenecen a la categoría favorita de este visitante.</li></ul> |
| Comportamiento anterior | Recomiende artículos en función de cómo hayan respondido los visitantes a un artículo en el pasado. Por ejemplo, las personas que compraron una determinada marca son más propensas a comprar otro artículo de la misma marca.<ul><li>Último artículo comprado</li><li>Último artículo visitado</li><li>Artículo más visitado</li><li>Categoría favorita</li></ul> |
| Popularidad | Recomiende los artículos más populares, como los vídeos más populares de una categoría relacionada o los productos que se han visto con más frecuencia en su sitio.<ul><li>Popularidad</li></ul> |
| Artículos vistos recientemente | Recomiende los artículos que un visitante ha visto más recientemente, como los artículos que vio la última vez que estuvo en el sitio o los artículos más de moda en este momento.<br>El algoritmo de artículos vistos recientemente devuelve los resultados específicos de la actividad de un visitante dentro de un [entorno](/help/administrating-target/hosts.md). Si dos sitios pertenecen a entornos diferentes y un visitante cambia entre los dos, el algoritmo devuelve solamente los artículos vistos recientemente en el sitio apropiado.<br>Este tipo de criterios no está limitado por colecciones.<ul><li>Artículos vistos recientemente</li></ul>**Nota:** No puede usar los criterios de Artículos vistos recientemente para recomendaciones de copia de seguridad.<br>Los elementos/medios vistos recientemente se pueden filtrar para que solo se muestren los elementos con un atributo en particular.<ul><li>Los criterios visualizados recientemente se pueden configurar, como otros criterios en las recomendaciones.</li><li>Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.</li></ul>Los posibles casos de uso incluyen:<ul><li>Una empresa multinacional con múltiples negocios podría tener elementos de visualización de visitantes en múltiples propiedades digitales. En este caso, se pueden limitar los elementos vistos recientemente para que solo se muestren en relación con la propiedad respectiva en la que se visualizaron. Esto impide que los Elementos visualizados recientemente se muestren en el sitio de otra propiedad digital.</li></ul> |

## Uso de una clave de recomendación personalizada {#custom-key}

También puede basar las recomendaciones en el valor de un atributo de perfil personalizado.

>[!NOTE]
>
>Los parámetros de perfil personalizados se pueden pasar a Destinatario a través de JavaScript, API o integraciones. Para obtener más información sobre los atributos de perfil personalizados, consulte perfiles [de](/help/c-target/c-visitor-profile/visitor-profile.md)Visitante.

Por ejemplo, supongamos que desea mostrar las películas recomendadas en función de la película que un usuario agregó más recientemente a la cola.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![Cuadro de diálogo Crear nuevo criterio](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

Por ejemplo, supongamos que desea mostrar los artículos más vendidos de la marca favorita de un usuario.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   Se muestra [!UICONTROL la] opción Agrupar por valor único de.

1. Seleccione el atributo de entidad que coincida con la clave que ha elegido. In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] ahora produce una lista &quot;Principales vendedores&quot; para cada marca y muestra al usuario la lista &quot;Principales vendedores&quot; correspondiente basada en el valor almacenado en el atributo de perfil de marca  favorita.

   ![Atributo Principales vendedores](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

[!DNL Target Recommendations] emplea sofisticados algoritmos que determinan si las acciones de un visitante cumplen los criterios establecidos en su actividad. La clave de recomendación determina las opciones de lógica de recomendaciones que se encuentran disponibles.

| Criterios | Descripción |
|--- |--- |
| Elementos/Medios con atributos similares | Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores.<br>**Nota:** Si selecciona Artículos/Medios con atributos similares, tendrá la opción de definir reglas de contenido similares. |
| Los usuarios que vieron esto, vieron aquello. | Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado. |
| Los usuarios que vieron esto, compraron aquello. | Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados. |
| Los usuarios que compraron esto, compraron aquello. | Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado. |
| Afinidad del sitio | Recomienda elementos según la certeza de una relación entre artículos. Puede configurar este criterio para determinar la cantidad de datos que se requiere antes de presentar una recomendación con el regulador Reglas de inclusión. Por ejemplo, si selecciona Muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.<br>Por ejemplo, si establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y son reemplazados por sus artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.<br>Es posible que algunos clientes con diferentes colecciones de productos y diversos comportamientos de sitio obtengan mejores resultados si establecen una afinidad de sitio débil. |
| Principales vendedores | Los artículos que están incluidos en los pedidos más completados. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido. |
| Más visitados | Los artículos o medios que se visitan con mayor frecuencia. |
| Elementos/Medios vistos recientemente | Artículos que el visitante ha visto recientemente. Cuando utilice este criterio, deberá actualizar el diseño de Target para controlar los casos en los que se mostrarían recomendaciones en blanco cuando no hubiera suficientes artículos vistos previamente para mostrar. |
| Recommendations basado en el usuario | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como &quot;Recomendado para usted&quot;.<br>Este criterio le permite entregar contenido y experiencias personalizadas a visitantes nuevos y reincidentes. La lista de las recomendaciones está ponderada en función de la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el usuario navega por el sitio.<br>Tanto las vistas como las compras se utilizan para determinar los artículos recomendados. La clave de recomendación especificada (por ejemplo, Elemento actual) se utiliza para aplicar cualquier filtros de regla de inclusión que seleccione. Por ejemplo, puede:<ul><li>Excluir elementos que no cumplen determinados criterios (productos sin existencias, artículos publicados hace más de 30 días, películas clasificadas como R, etc.)</li><li>Limitar los elementos incluidos a una sola categoría o a la categoría actual</li></ul> |

>[!NOTE]
>
>Si está ejecutando una recomendación y cambia su criterio, perderá los datos de informes.

También puede utilizar información adicional conocida acerca de un visitante para mejorar sus recomendaciones.

Todos los criterios de un día se ejecutan dos veces al día. Todos los criterios de una semana y un período mayor se ejecutan una vez al día. Los criterios de afinidad del sitio se ejecutan una vez al día. Los criterios de copia de seguridad se ejecutan dos veces al día.

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Para ver los detalles de los criterios de una tarjeta emergente, pase el cursor sobre una tarjeta y haga clic en el icono Información sin necesidad de abrir los criterios.

![Mantener el puntero encima de la tarjeta de criterios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Haga clic en la pestaña **[!UICONTROL Información del algoritmo]** para ver información general sobre los criterios seleccionados, como Nombre, Descripciones, Sector, Tipos de página, Clave de recomendación, Lógica de recomendación e ID del algoritmo.

![Pestaña Información del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Haga clic en la pestaña **[!UICONTROL Uso del algoritmo]** para ver una lista de actividades que hacen referencia a los criterios seleccionados. La tarjeta enumera las actividades activas e inactivas. Haga clic en las listas desplegables Actividades activas o Inactividades para ver la lista completa de actividades que hacen referencia a ese criterio. Puede hacer clic en el vínculo de la actividad para abrirla y modificarla.

![Ficha Uso del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La función Uso [!UICONTROL del] algoritmo solo se admite actualmente para actividades de Recommendations. Esta función no se admite actualmente en actividades de Prueba A/B y Segmentación de experiencias (XT) que incluyen [recomendaciones como oferta](/help/c-recommendations/recommendations-as-an-offer.md).
