---
keywords: reglas de inclusión;criterios de inclusión;Recommendations;creación de nuevos criterios;promoción;promociones;filtrado dinámico;dinámico;valores en blanco;ignorar regla de filtrado;filtro estático;filtrar por valor;coincidencia de atributos de entidad;coincidencia de atributos de perfil;coincidencia de parámetros;filtrado por valor;filtro estático
description: Aprenda a crear reglas de inclusión en  [!DNL Target] Recommendations para criterios y promociones.
title: ¿Cómo utilizo reglas de inclusión dinámicas y estáticas en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 16%

---

# Uso de reglas de inclusión dinámicas y estáticas

Cree reglas de inclusión para criterios y promociones en [!DNL Adobe Target] y agregue reglas de filtrado dinámicas o estáticas para lograr mejores resultados en las recomendaciones.

El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. En esta sección se tratan tanto los criterios y promociones como el uso de reglas de inclusión.

## Adición de reglas de filtrado a criterios y promociones {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Las secciones siguientes contienen más información:

### Agregar reglas de filtrado a los criterios

1. Mientras [crea criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) (**[!UICONTROL Recommendations]> [!UICONTROL Criteria] > [!UICONTROL Create Criteria] >[!UICONTROL Create Criteria]**), haga clic en **[!UICONTROL Add Filtering Rule]** en **[!UICONTROL Inclusion Rules]**.

   ![Agregar regla de filtrado](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Haga clic en la lista desplegable **Filtro estático** en el cuadro &quot;Qué otras reglas debe obedecer la recomendación&quot; y, a continuación, elija la opción que desee en la lista desplegable [!UICONTROL Static Filter].

   ![Lista desplegable de filtros estáticos](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

### Adición de reglas de filtrado a las promociones

1. Mientras [crea una promoción](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), seleccione **[!UICONTROL Promote by Attribute]** y luego haga clic en **[!UICONTROL Add Filtering Rule]**.

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

Las secciones siguientes enumeran los tipos de opciones de filtrado para [!UICONTROL Dynamic Filtering] y [!UICONTROL Filter by Value], tanto para criterios como para promociones:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y arrojan mejores resultados y participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en el parámetro de perfil de un usuario o en una llamada de mbox.

  Por ejemplo, puede crear una recomendación &quot;Criterios más populares&quot;. Del conjunto de recomendaciones devueltas, puede filtrar las recomendaciones (en tiempo real) con un atributo pasado cuando el usuario accede a una página donde se muestran las recomendaciones.

* Utilice reglas estáticas para limitar qué artículos se incluyen en la recomendación (en lugar de utilizar colecciones).

* Puede crear tantas reglas de inclusión dinámica como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

| Opción de filtrado dinámico | Detalles |
| --- | --- |
| [[!UICONTROL Entity Attribute Matching]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios hayan interactuado.<P>Use [!UICONTROL Entity Attribute Matching] cuando quiera mostrar recomendaciones que probablemente atraigan al visitante, como la marca favorita del visitante. |
| [[!UICONTROL Profile Attribute Matching]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor del perfil del usuario.<P>Use [!UICONTROL Profile Attribute Matching] cuando quiera mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita. |
| [[!UICONTROL Parameter Matching]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).<P>Use [!UICONTROL Parameter Matching] para recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones de dispositivo o ubicación geográfica. |

### Filtrar por valor

La siguiente opción está disponible para filtrar por valor:

| Filtrado por opción de valor | Detalles |
| --- | --- |
| [[!UICONTROL Static Filter]](/help/main/c-recommendations/c-algorithms/static-value.md) | Introduzca manualmente uno o más valores estáticos para filtrar. |

## Operadores disponibles {#operators}

Los criterios y promociones dinámicos son mucho más potentes que los criterios y promociones estáticos y arrojan mejores resultados y participación.

Los siguientes ejemplos proporcionan ideas generales sobre cómo puede utilizar las promociones y exclusiones dinámicas en sus esfuerzos de marketing:

| Operador | Ejemplos |
| --- | --- |
| [!UICONTROL equals any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos de:<ul><li>La misma marca</li><li>La misma categoría</li><li>La misma categoría Y de la marca de la casa</li><li>La misma tienda</li></ul> |
| [!UICONTROL does not equal any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;[!UICONTROL does not equal any of]&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos de:<ul><li>Una serie de TV diferente</li><li>Un género diferente</li><li>Una serie de productos diferente</li><li>Un ID de estilo diferente</li></ul> |
| [!UICONTROL is greater than or equal to any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;[!UICONTROL is greater than or equal to any of]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Cuestan lo mismo o son más caros</li></ul> |
| [!UICONTROL is less than or equal to any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;[!UICONTROL is less than or equal to an of]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Cuestan lo mismo o son menos caros</li><li>Excluir artículos que sean menos caros</li></ul> |
| [!UICONTROL contains any of] (disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter]). | Con el operador &quot;[!UICONTROL contains any of]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El título contiene la misma marca</li></ul> |
| [!UICONTROL does not contain any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;no contiene ninguno de&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El título no contiene palabrotas</li></ul> |
| [!UICONTROL starts with any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;[!UICONTROL starts with an of]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El nombre del producto comienza con iPhone</li></ul> |
| [!UICONTROL ends with any of]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] y [!UICONTROL Static Filter].) | Con el operador &quot;[!UICONTROL ends with an of]&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El contenido termina con EN, que indica el idioma inglés</li></ul> |
| [!UICONTROL is between]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Con el operador &quot;i[!UICONTROL s between]&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos que:<ul><li>Más caro</li><li>Menos costoso</li><li>Costo más o menos 30%</li><li>Episodios posteriores en la misma temporada</li><li>Libros anteriores de una serie</li></ul> |
| [!UICONTROL list contains an item in]<P>(Disponible con [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Con el operador &quot;[!UICONTROL list contains an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede promocionar otros elementos que:<ul><li>Disponible en la ubicación geográfica del visitante</li></ul>**Ejemplo**: desea recomendar elementos que solo están disponibles en el área geográfica de un visitante.<P>La regla de filtro puede tener el aspecto siguiente:<P>`availableGeographies list contains an item in user.currentGeography`<P>**Nota**: Al usar este operador, se espera una lista en el [lado derecho](#caveats) de la regla. |
| [!UICONTROL list does not contain an item in]<P>(Disponible con [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede excluir otros elementos que:<ul><li>En la lista de los últimos diez elementos que el visitante ha visto</li></ul></ul>**Ejemplo**: no desea promocionar elementos que el visitante ha visto recientemente y en los que no ha mostrado interés.<P>La regla de filtrado puede tener este aspecto:<P>`id is not contained in list user.lastViewedItems`<P>**Nota**: Al usar este operador, se espera una lista en el [lado derecho](#caveats) de la regla. |
| [!UICONTROL list contains an item in]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Si utiliza el operador &quot;[!UICONTROL list contains an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un evento deportivo o un concierto), puede promocionar otros elementos que:<ul><li>Asociado a uno de los equipos favoritos del visitante</li></ul>**Ejemplo**: desea recomendar juegos asociados con uno de los equipos favoritos del visitante.<P>La regla de filtrado puede tener este aspecto:<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL list does not contain an item in]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de parámetros, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo, una película, etc.), puede excluir otros elementos que:<ul><li>Incluido en una lista de tipos prohibidos</li></ul>**Ejemplo**: desea excluir los artículos que están disponibles para visitantes adultos, como tabaco y alcohol.<P>La regla de filtrado puede tener este aspecto:<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL list contains all items in]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Si utiliza el operador &quot;[!UICONTROL list does not contain an item in]&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como una publicación o una fórmula de trabajo), puede promocionar otros elementos que:<ul><li>Incluir un conjunto de aptitudes</li><li>Incluir un conjunto de ingredientes necesarios</li></ul>**Ejemplo 1**: Supongamos que un visitante tiene un conjunto de aptitudes (Java, C++ y HTML). Los elementos del catálogo son trabajos con las aptitudes requeridas (Java y HTML). Debe asegurarse de que el perfil del visitante contiene todas las aptitudes necesarias antes de recomendar el trabajo al visitante.<P>La regla de filtrado puede tener este aspecto:<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Ejemplo 2**: Supongamos que un usuario tiene una lista de ingredientes de despensa. La receta tiene una lista de ingredientes necesarios. Debe asegurarse de que el perfil del visitante contenga todos los ingredientes necesarios antes de recomendar la fórmula al visitante.<P>La regla de filtrado puede tener este aspecto:<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |
| [!UICONTROL list does not contain all items in]<P>(Disponible con [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].) | Si utiliza el operador &quot;[!UICONTROL list does not contain all items in]&quot; en la coincidencia de atributos de entidad, cuando un visitante está viendo un elemento en el sitio web (como un evento deportivo o un concierto), puede promocionar otros elementos que:<ul><li>No incluya un conjunto de equipos</li></ul>**Ejemplo**: Supongamos que un evento deportivo incluye dos equipos. El perfil del visitante indica que este visitante no desea ver los juegos de estos equipos. Desea asegurarse de que no recomienda un juego si estos equipos están jugando.<P>La regla de filtrado puede tener este aspecto:<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Nota**: Al usar este operador, se espera una lista en [ambos lados](#caveats) de la regla. |

## Administrar valores vacíos al filtrar por [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Puede elegir varias opciones para controlar los valores vacíos al filtrar por [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] para los criterios de salida y las promociones.

Anteriormente, si un valor estaba en blanco no se devolvía ningún resultado. La lista desplegable “Si *x* está en blanco” le permite elegir la acción que se debe realizar si los criterios contienen valores en blanco, como se muestra en la siguiente ilustración:

![imagen empty_value](assets/empty_value.png)

Para seleccionar la acción que desee, pase el ratón sobre el icono del engranaje (![icon_gear_image](assets/icon_gear.png)) y, a continuación, elija la acción que desee:

| Acción | Disponible para | Detalles |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] | Esta acción es la predeterminada para [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching].<P>Esta opción especifica que la regla se ignora. Por ejemplo, si hay tres reglas de filtrado y la tercera no pasa ningún valor, en vez de no devolver resultado alguno, puede simplemente ignorar la tercera regla con valores en blanco. |
| [!UICONTROL Do not show any results for this criteria]<P>(Solo criterios) | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] | Esta acción es la predeterminada para [!UICONTROL Entity Attribute Matching].<P>Esta acción es el modo en que [!DNL Target] gestiona los valores vacíos antes de la adición de esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL No promocionar ningún elemento<P>(Solo promociones)] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] | Esta acción es la predeterminada para [!UICONTROL Entity Attribute Matching].<P>Esta acción es el modo en que [!DNL Target] gestiona los valores vacíos antes de la adición de esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] y [!UICONTROL Parameter Matching] | Si un valor está en blanco, puede optar por usar un valor estático. |

## Advertencias  {#caveats}

>[!IMPORTANT]
>
>Es posible que no se puedan usar atributos de tipo de datos diferentes en los criterios dinámicos o promociones durante el tiempo de ejecución con los operadores “es igual que” y “no es igual que”. Use los valores [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] y [!UICONTROL Environment] de forma acertada en el lado derecho si el lado izquierdo tiene atributos predefinidos o personalizados.

![imagen left_right](assets/left_right.png)

La tabla siguiente contiene reglas eficaces y reglas que pueden no ser compatibles durante el tiempo de ejecución:

| Reglas compatibles | Reglas potencialmente incompatibles |
|--- |--- |
| value - está entre - 90 % and 110 % de Elemento actual - salesValue | salesValue - está entre - 90 % y 110% de Elemento actual - value |
| value - está entre - 90 % y 110 % de Elemento actual - value | clearancePrice - está entre - 90 % y 110 % de Elemento actual - margin |
| margin - está entre - 90 % y 110 % de Elemento actual - margin | storeInventory - es igual que - Elemento actual - inventory |
| inventory - es igual que - Elemento actual - inventory |  |
