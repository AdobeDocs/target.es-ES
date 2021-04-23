---
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo;clave de recomendación;clave personalizada;sector vertical;comercio;electrónico;generación de posibles clientes;b2b;servicios financieros;medios;publicación
description: Aprenda a utilizar los criterios en Adobe [!DNL Target] Recommendations. Los criterios son reglas que determinan qué contenido se debe recomendar en función de un conjunto predeterminado de comportamientos del visitante.
title: ¿Cómo utilizo los criterios en [!DNL Target] Recommendations?
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 52%

---

# ![PREMIUM](/help/assets/premium.png) Criterios

Los criterios de [!DNL Adobe Target] son reglas que determinan qué productos o contenido se recomiendan en función de un conjunto predeterminado de comportamientos del visitante. Los criterios se pueden basar en tendencias populares, los comportamientos actuales y pasados de un visitante o productos y contenido similares. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

En las secciones siguientes se explica más sobre las claves de criterios y la lógica de recomendación que puede usar para cada clave. Haga clic en los vínculos para obtener información más detallada.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Mientras crea un criterio, selecciona un sector en función de los objetivos de su actividad de recomendaciones.

| Sector | Objetivo |
|--- |--- |
| Venta minorista/Comercio electrónico | Conversión que termina en compra |
| Generación de vanguardia/B2B/Servicios financieros | Conversión sin compra |
| Medios/Publicación | Participación |

Otras opciones de criterios cambian según el sector que seleccione. Puede establecer el sector predeterminado en la página **[!UICONTROL Recommendations > Configuración]** o especificar el sector para cada criterio.

## Clave de recomendación {#section_885B3BB1B43048A88A8926F6B76FC482}

La clave de recomendación que seleccione determina el tipo de criterio. Existen varios tipos de criterios que se representan como tarjetas de criterio cuando configura una actividad de [!DNL Recommendations].

![Página Criterios](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

En la tabla siguiente se explican los distintos tipos de criterios y las claves que los acompañan. Haga clic en los vínculos para obtener información más detallada sobre cada clave.

| Tipo de criterio | Claves |
|--- |--- |
| Actividad de la página actual | Recomiende artículos en función de lo que los usuarios hacen en la página actual. Por ejemplo, a los visitantes que ven un determinado artículo podría interesarles ver otros artículos de la misma categoría.<ul><li>[Artículo actual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Categoría actual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personalizado | Recomendar artículos según atributos personalizados.<ul><li>[Atributo personalizado. ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación. |
| Comportamiento anterior | Recomiende artículos en función de cómo hayan respondido los visitantes a un artículo en el pasado. Por ejemplo, las personas que compraron una determinada marca son más propensas a comprar otro artículo de la misma marca.<ul><li>[Último artículo comprado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Último artículo visitado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Artículo más visitado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Categoría favorita](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularidad | Recomiende los artículos más populares, como los vídeos más populares de una categoría relacionada o los productos que se han visto con más frecuencia en su sitio.<ul><li>[Popularidad](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Artículos vistos recientemente. ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Recomiende los artículos que un visitante haya visto más recientemente, como los artículos que vio la última vez que visitó su sitio o los artículos que son más de moda en este momento. |

## Uso de una clave de recomendación personalizada {#custom-key}

También puede basar las recomendaciones en el valor de un atributo de perfil personalizado.

>[!NOTE]
>
>Los parámetros de perfil personalizados se pueden pasar a Target a través de JavaScript, API o integraciones. Para obtener más información sobre los atributos de perfil personalizados, consulte [Perfiles de visitante](/help/c-target/c-visitor-profile/visitor-profile.md).

Por ejemplo, supongamos que desea mostrar películas recomendadas basadas en la película que agregó un usuario más recientemente a la cola.

1. Seleccione su atributo de perfil personalizado en la lista desplegable [!UICONTROL Clave de recomendación] (por ejemplo, [!UICONTROL Última visualización agregada a la lista de observación]).

1. Seleccione su [!UICONTROL Lógica de recomendación] (por ejemplo, [!UICONTROL Personas que vieron esto, Vieron aquello]).

   ![Cuadro de diálogo Crear nuevo criterio](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

Si el atributo de perfil personalizado no coincide directamente con un ID de entidad único, es necesario explicar a [!DNL Recommendations] cómo desea que se produzca la coincidencia en una entidad.

Por ejemplo, supongamos que desea mostrar los artículos más vendidos de la marca favorita de un usuario.

1. Seleccione su atributo de perfil personalizado en la lista desplegable [!UICONTROL Clave de recomendación] (por ejemplo, [!UICONTROL Marca favorita]).

1. Seleccione la [!UICONTROL Lógica de recomendación] que desee utilizar con esta clave (por ejemplo, [!UICONTROL Principales vendedores]).

   Se muestra [!UICONTROL la] opción Agrupar por valor único de.

1. Seleccione el atributo de entidad que coincida con la clave que ha elegido. En este caso, [!UICONTROL Marca favorita] coincide con `entity.brand`.

   [!DNL Recommendations] ahora genera una lista &quot;Principales vendedores&quot; para cada marca y muestra al usuario la lista &quot;Principales vendedores&quot; adecuada en función del valor almacenado en el atributo  [!UICONTROL Favorite ] Brandprofile.

   ![Atributo Principales vendedores](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criterios/algoritmos {#criteria-algorithms}

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
| [Recommendations basado en usuarios](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recomienda artículos en función del historial de navegación, visualización y compra de cada visitante. Estos artículos generalmente se denominan &quot;Recomendado para ti&quot;. |

>[!NOTE]
>
>Si está ejecutando una recomendación y cambia su criterio, perderá los datos de informes.

También puede utilizar información adicional conocida acerca de un visitante para mejorar sus recomendaciones.

Todos los criterios de un día se ejecutan dos veces al día. Todos los criterios de una semana y un período mayor se ejecutan una vez al día. Los criterios de afinidad del sitio se ejecutan una vez al día. Los criterios de copia de seguridad se ejecutan dos veces al día.

## Visualización de la información de criterios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Para ver los detalles de los criterios de una tarjeta emergente, pase el cursor sobre una tarjeta y haga clic en el icono Información sin necesidad de abrir los criterios.

![Mantener el puntero encima de la tarjeta de criterios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Haga clic en la pestaña **[!UICONTROL Información del algoritmo]** para ver información general sobre los criterios seleccionados, como Nombre, Descripciones, Sector, Tipos de página, Clave de recomendación, Lógica de recomendación e ID del algoritmo.

![Pestaña Información del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Haga clic en la pestaña **[!UICONTROL Uso del algoritmo]** para ver una lista de actividades que hacen referencia a los criterios seleccionados. La tarjeta enumera las actividades activas, inactivas y de borrador. Haga clic en las listas desplegables Actividades activas/Actividades inactivas/Actividades de borrador para ver la lista completa de actividades que hacen referencia a ese criterio. Puede hacer clic en el vínculo de la actividad para abrirla y modificarla.

![Pestaña Uso del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>Actualmente, la función [!UICONTROL Uso del algoritmo] solo es compatible con las actividades de Recommendations. Actualmente, esta función no es compatible con las actividades Prueba A/B, Asignación automática, Segmentación automática y Segmentación de experiencias (XT) que incluyen [recomendaciones como oferta](/help/c-recommendations/recommendations-as-an-offer.md).
