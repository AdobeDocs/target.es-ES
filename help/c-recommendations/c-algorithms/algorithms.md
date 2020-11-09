---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Los criterios de Adobe Target son reglas que determinan qué productos o contenido recomendar en función de un conjunto predeterminado de comportamientos de visitante.
title: Criterios en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 53%

---


# ![PREMIUM](/help/assets/premium.png) Criterios

Criteria in [!DNL Adobe Target] are rules that determine which products or content to recommend based on a predetermined set of visitor behaviors. Los criterios se pueden basar en tendencias populares, los comportamientos actuales y pasados de un visitante o productos y contenido similares. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

Las siguientes secciones explican más sobre las claves de criterios y la lógica de recomendación que puede utilizar para cada clave. Haga clic en los vínculos para obtener información más detallada.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Al crear un criterio, se selecciona un sector en función de los objetivos de la actividad de recomendaciones.

| Sector | Objetivo |
|--- |--- |
| Venta minorista/Comercio electrónico | Conversión que termina en compra |
| Generación de vanguardia/B2B/Servicios financieros | Conversión sin compra |
| Medios/Publicación | Participación |

Otras opciones de criterios cambian en función del sector que seleccione. Puede definir la industria predeterminada en la página **[!UICONTROL Recommendations > Configuración]** o especificar la industria vertical para cada criterio.

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

La clave de recomendación que seleccione determina el tipo de criterio. Existen varios tipos de criterios que se representan como tarjetas de criterio cuando configura una actividad de [!DNL Recommendations].

![Página Criterios](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

En la tabla siguiente se explican los distintos tipos de criterios y las claves que los acompañan. Haga clic en los vínculos para obtener información más detallada sobre cada clave.

| Tipo de criterio | Claves |
|--- |--- |
| Actividad de la página actual | Recomiende artículos en función de lo que los usuarios hacen en la página actual. Por ejemplo, a los visitantes que ven un determinado artículo podría interesarles ver otros artículos de la misma categoría.<ul><li>[Artículo actual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Categoría actual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personalizado | Recomendar artículos según atributos personalizados.<ul><li>[Atributo personalizado. ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación. |
| Comportamiento anterior | Recomiende artículos en función de cómo hayan respondido los visitantes a un artículo en el pasado. Por ejemplo, las personas que compraron una determinada marca son más propensas a comprar otro artículo de la misma marca.<ul><li>[Último artículo comprado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Último artículo visitado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Artículo más visitado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Categoría favorita](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularidad | Recomiende los artículos más populares, como los vídeos más populares de una categoría relacionada o los productos que se han visto con más frecuencia en su sitio.<ul><li>[Popularidad](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Artículos vistos recientemente. ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Recomiende los artículos que un visitante ha visto más recientemente, como los artículos que vio un visitante la última vez que visitó el sitio o los artículos que son más de moda en este momento. |

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
| [Elementos/Medios con atributos similares](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores. |
| [Los usuarios que vieron esto, vieron aquello.](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado. |
| [Los usuarios que vieron esto, compraron aquello.](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. |
| [Los usuarios que compraron esto, compraron aquello.](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado. |
| [Afinidad del sitio](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | Recomienda elementos según la certeza de una relación entre artículos. |
| [Principales vendedores](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | Los artículos que están incluidos en los pedidos más completados. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido. |
| [Más visitados](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | Los artículos o medios que se visitan con mayor frecuencia. |
| [Recommendations basado en el usuario](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como &quot;Recomendado para usted&quot;. |

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

Haga clic en la pestaña **[!UICONTROL Uso del algoritmo]** para ver una lista de actividades que hacen referencia a los criterios seleccionados. La tarjeta lista actividades activas, inactivas y de borrador. Haga clic en las listas desplegables Actividades activas/Actividades inactivas/Borradores de Actividades para vista de toda la lista de actividades que hacen referencia a esos criterios. Puede hacer clic en el vínculo de la actividad para abrirla y modificarla.

![Ficha Uso del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>La función Uso [!UICONTROL del] algoritmo solo se admite actualmente para actividades de Recommendations. Esta función no se admite actualmente en actividades de Prueba A/B, Asignación automática, Destinatario automático y Segmentación de experiencias (XT) que incluyen [recomendaciones como oferta](/help/c-recommendations/recommendations-as-an-offer.md).
