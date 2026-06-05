---
keywords: reglas de inclusión;criterios de inclusión;Recommendations;creación de nuevos criterios;promoción;promociones;filtrado dinámico;dinámico;valores en blanco;ignorar regla de filtrado;filtro estático;filtrar por valor;coincidencia de atributos de entidad;coincidencia de atributos de perfil;coincidencia de parámetros;filtrado por valor;filtro estático
description: Aprenda a crear reglas de inclusión en  [!DNL Target] Recommendations para criterios y promociones.
title: ¿Cómo utilizo reglas de inclusión dinámicas y estáticas en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
TQID: https://experienceleague.adobe.com/PM9h863-uQWm3wrU7OVWfmnqQgyUGmF7QFpTUaAZuCQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2258
ht-degree: 14%

---

# Uso de reglas de inclusión dinámicas y estáticas

Cree reglas de inclusión para criterios y promociones en [!DNL Adobe Target] y agregue reglas de filtrado dinámicas o estáticas para lograr mejores resultados en las recomendaciones.

El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. En esta sección se tratan tanto los criterios y promociones como el uso de reglas de inclusión.

## Adición de reglas de filtrado a criterios y promociones {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Las secciones siguientes contienen más información:

### Agregar reglas de filtrado a los criterios

1. Mientras [crea criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) (**[!UICONTROL Recommendations] > [!UICONTROL Criterios] > [!UICONTROL Crear criterios] > [!UICONTROL Crear criterios]**), haga clic en **[!UICONTROL Agregar regla de filtrado]** en **[!UICONTROL Reglas de inclusión]**.

   ![Agregar regla de filtrado](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Haga clic en la lista desplegable **Filtro estático** en el cuadro &quot;Qué otras reglas debe obedecer la recomendación&quot; y, a continuación, elija la opción que desee en la lista desplegable [!UICONTROL Filtro estático].

   ![Lista desplegable de filtros estáticos](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

### Adición de reglas de filtrado a las promociones

1. Mientras [crea una promoción](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecciona **[!UICONTROL Promocionar por atributo]** y luego haz clic en **[!UICONTROL Agregar regla de filtrado]**.

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

En las secciones siguientes se enumeran los tipos de opciones de filtrado para [!UICONTROL Filtrado dinámico] y [!UICONTROL Filtrar por valor] tanto para criterios como para promociones:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y arrojan mejores resultados y participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en el parámetro de perfil de un usuario o en una llamada de mbox.

  Por ejemplo, puede crear una recomendación &quot;Criterios más populares&quot;. Del conjunto de recomendaciones devueltas, puede filtrar las recomendaciones (en tiempo real) con un atributo pasado cuando el usuario accede a una página donde se muestran las recomendaciones.

* Utilice reglas estáticas para limitar qué artículos se incluyen en la recomendación (en lugar de utilizar colecciones).

* Puede crear tantas reglas de inclusión dinámica como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

| Opción de filtrado dinámico | Detalles |
| --- | --- |
| [[!UICONTROL Coincidencia de atributos de entidad]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios hayan interactuado.<P>Use [!UICONTROL Coincidencia de atributos de entidad] cuando quiera mostrar recomendaciones que probablemente atraigan al visitante, como la marca favorita del visitante. |
| [[!UICONTROL Coincidencia de atributos de perfil]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor del perfil del usuario.<P>Use [!UICONTROL Coincidencia de atributos de perfil] cuando quiera mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita. |
| [[!UICONTROL Coincidencia de parámetros]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).<P>Use [!UICONTROL Coincidencia de parámetros] para recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones de dispositivo o ubicación geográfica. |

### Filtrar por valor

La siguiente opción está disponible para filtrar por valor:

| Filtrado por opción de valor | Detalles |
| --- | --- |
| [[!UICONTROL Filtro estático]](/help/main/c-recommendations/c-algorithms/static-value.md) | Introduzca manualmente uno o más valores estáticos para filtrar. |

## Operadores disponibles {#operators}

Los criterios y promociones dinámicos son mucho más potentes que los criterios y promociones estáticos y arrojan mejores resultados y participación.

Los siguientes ejemplos proporcionan ideas generales sobre cómo puede utilizar las promociones y exclusiones dinámicas en sus esfuerzos de marketing:

>[!NOTE]
>
>&quot;List&quot; requiere que tanto las entidades como los atributos de perfil se almacenen como matrices. Una lista separada por comas no funciona.

| Operador | Ejemplos |
| --- | --- |
| [!UICONTROL es igual a cualquiera de]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Con el operador &quot;es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos de:<ul><li>La misma marca</li><li>La misma categoría</li><li>La misma categoría Y de la marca de la casa</li><li>La misma tienda</li></ul> |
| [!UICONTROL no es igual a ninguno de]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Si utiliza el operador &quot;[!UICONTROL no es igual a ninguno de]&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos de:<ul><li>Una serie de TV diferente</li><li>Un género diferente</li><li>Una serie de productos diferente</li><li>Un ID de estilo diferente</li></ul> |
| [!UICONTROL es mayor o igual que cualquiera de]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Si usa el operador &quot;[!UICONTROL &quot; es mayor o igual que cualquiera de ], cuando un visitante está viendo un elemento en el sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Cuestan lo mismo o son más caros</li></ul> |
| [!UICONTROL  es menor o igual que cualquiera de ]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Si usa el operador &quot;[!UICONTROL &quot; es menor o igual que &quot;]&quot;, cuando un visitante esté viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Cuestan lo mismo o son menos caros</li><li>Excluir artículos que sean menos caros</li></ul> |
| [!UICONTROL contiene cualquiera de] (disponible con [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil], [!UICONTROL Coincidencia de parámetros] y [!UICONTROL Filtro estático]). | Con el operador &quot;[!UICONTROL contiene cualquiera de]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El título contiene la misma marca</li></ul> |
| [!UICONTROL no contiene ninguno]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Con el operador &quot;no contiene ninguno de&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El título no contiene palabrotas</li></ul> |
| [!UICONTROL comienza con cualquiera de]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Con el operador &quot;[!UICONTROL comienza con un de]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El nombre del producto comienza con iPhone</li></ul> |
| [!UICONTROL termina con cualquiera de]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil], [!UICONTROL coincidencia de parámetros] y [!UICONTROL filtro estático]). | Con el operador &quot;[!UICONTROL termina con un de]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El contenido termina con EN, que indica el idioma inglés</li></ul> |
| [!UICONTROL  está entre ]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Con el operador &quot;i[!UICONTROL s entre ]&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos que:<ul><li>Más caro</li><li>Menos costoso</li><li>Costo más o menos 30%</li><li>Episodios posteriores en la misma temporada</li><li>Libros anteriores de una serie</li></ul> |
| [!UICONTROL lista contiene un elemento en]<P>(Disponible con [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list contiene un elemento en]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos que:<ul><li>Disponible en la ubicación geográfica del visitante</li></ul>**Ejemplo**: desea recomendar elementos que solo están disponibles en el área geográfica de un visitante.<P>La regla de filtro puede tener el aspecto siguiente:<P>`availableGeographies list contains an item in user.currentGeography`<P>**Nota**: Al usar este operador, se espera una lista en el [lado derecho](#caveats) de la regla. |
| [!UICONTROL lista no contiene ningún elemento en]<P>(Disponible con [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo, una película, etc.), puede excluir otros elementos que:<ul><li>En la lista de los últimos diez elementos que el visitante ha visto</li></ul></ul>**Ejemplo**: no desea promocionar elementos que el visitante ha visto recientemente y en los que no ha mostrado interés.<P>La regla de filtrado puede tener este aspecto:<P>`id is not contained in list user.lastViewedItems`<P>**Nota**: Al usar este operador, se espera una lista en el [lado derecho](#caveats) de la regla. |
| [!UICONTROL lista contiene un elemento en]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list contiene un elemento en]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en el sitio web (como un evento deportivo o un concierto), puede promocionar otros elementos que:<ul><li>Asociado a uno de los equipos favoritos del visitante</li></ul>**Ejemplo**: desea recomendar juegos asociados con uno de los equipos favoritos del visitante.<P>La regla de filtrado puede tener este aspecto:<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL lista no contiene ningún elemento en]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de parámetros, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo, una película, etc.), puede excluir otros elementos que:<ul><li>Incluido en una lista de tipos prohibidos</li></ul>**Ejemplo**: desea excluir los artículos que están disponibles para visitantes adultos, como tabaco y alcohol.<P>La regla de filtrado puede tener este aspecto:<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL la lista contiene todos los elementos en]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en el sitio web (como una publicación o una fórmula de trabajo), puede promocionar otros elementos que:<ul><li>Incluir un conjunto de aptitudes</li><li>Incluir un conjunto de ingredientes necesarios</li></ul>**Ejemplo 1**: Supongamos que un visitante tiene un conjunto de aptitudes (Java, C++ y HTML). Los elementos del catálogo son trabajos con las aptitudes requeridas (Java y HTML). Debe asegurarse de que el perfil del visitante contiene todas las aptitudes necesarias antes de recomendar el trabajo al visitante.<P>La regla de filtrado puede tener este aspecto:<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Ejemplo 2**: Supongamos que un usuario tiene una lista de ingredientes de despensa. La receta tiene una lista de ingredientes necesarios. Debe asegurarse de que el perfil del visitante contenga todos los ingredientes necesarios antes de recomendar la fórmula al visitante.<P>La regla de filtrado puede tener este aspecto:<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL lista no contiene todos los elementos en]<P>(Disponible con [!UICONTROL coincidencia de atributos de entidad], [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros]). | Si utiliza el operador &quot;[!UICONTROL list no contiene todos los elementos en]&quot; en la coincidencia de atributos de entidad, cuando un visitante está viendo un elemento en el sitio web (como un evento deportivo o un concierto), puede promocionar otros elementos que:<ul><li>No incluya un conjunto de equipos</li></ul>**Ejemplo**: Supongamos que un evento deportivo incluye dos equipos. El perfil del visitante indica que este visitante no desea ver los juegos de estos equipos. Desea asegurarse de que no recomienda un juego si estos equipos están jugando.<P>La regla de filtrado puede tener este aspecto:<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |

## Administrar valores vacíos al filtrar por [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Puede elegir varias opciones para controlar los valores vacíos al filtrar por [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] para los criterios y promociones de salida.

Anteriormente, si un valor estaba en blanco no se devolvía ningún resultado. La lista desplegable “Si *x* está en blanco” le permite elegir la acción que se debe realizar si los criterios contienen valores en blanco, como se muestra en la siguiente ilustración:

![imagen empty_value](assets/empty_value.png)

Para seleccionar la acción que desee, pase el ratón sobre el icono del engranaje (![icon_gear_image](assets/icon_gear.png)) y, a continuación, elija la acción que desee:

| Acción | Disponible para | Detalles |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regla de filtrado] | [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] | Esta acción es la predeterminada para [!UICONTROL coincidencia de atributos de perfil] y [!UICONTROL coincidencia de parámetros].<P>Esta opción especifica que la regla se ignora. Por ejemplo, si hay tres reglas de filtrado y la tercera no pasa ningún valor, en vez de no devolver resultado alguno, puede simplemente ignorar la tercera regla con valores en blanco. |
| [!UICONTROL No mostrar ningún resultado para estos criterios]<P>(Solo criterios) | [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] | Esta acción es la predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<P>Esta acción es el modo en que [!DNL Target] gestiona los valores vacíos antes de la adición de esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL No promocionar ningún elemento<P>(Solo promociones)] | [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] | Esta acción es la predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<P>Esta acción es el modo en que [!DNL Target] gestiona los valores vacíos antes de la adición de esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL Usar un valor estático] | [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] | Si un valor está en blanco, puede optar por usar un valor estático. |

## Advertencias {#caveats}

>[!IMPORTANT]
>
>Es posible que no se puedan usar atributos de tipo de datos diferentes en los criterios dinámicos o promociones durante el tiempo de ejecución con los operadores “es igual que” y “no es igual que”. Use los valores de [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] y [!UICONTROL Environment] con prudencia en el lado derecho si el lado izquierdo tiene atributos predefinidos o personalizados.

![imagen left_right](assets/left_right.png)

La tabla siguiente contiene reglas eficaces y reglas que pueden no ser compatibles durante el tiempo de ejecución:

| Reglas compatibles | Reglas potencialmente incompatibles |
|--- |--- |
| value - está entre - 90 % and 110 % de Elemento actual - salesValue | salesValue - está entre - 90 % y 110% de Elemento actual - value |
| value - está entre - 90 % y 110 % de Elemento actual - value | clearancePrice - está entre - 90 % y 110 % de Elemento actual - margin |
| margin - está entre - 90 % y 110 % de Elemento actual - margin | storeInventory - es igual que - Elemento actual - inventory |
| inventory - es igual que - Elemento actual - inventory |  |
