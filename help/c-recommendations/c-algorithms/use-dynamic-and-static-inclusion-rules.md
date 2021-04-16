---
keywords: reglas de inclusión;criterios de inclusión;Recommendations;creación de nuevos criterios;promoción;promociones;filtrado dinámico;dinámico;valores en blanco;ignorar regla de filtrado;filtro estático;filtrar por valor;coincidencia de atributos de entidad;coincidencia de atributos de perfil;coincidencia de parámetros;filtrado por valor;filtro estático
description: Aprenda a crear reglas de inclusión en Adobe Target Recommendations para criterios y promociones. Para obtener mejores resultados, agregue reglas de filtrado más dinámicas o estáticas.
title: ¿Cómo utilizo las reglas de inclusión dinámicas y estáticas en Recommendations?
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
translation-type: tm+mt
source-git-commit: 43a7d3b3056a4404d18aa4a05a7a93d695900f73
workflow-type: tm+mt
source-wordcount: '2087'
ht-degree: 17%

---

# ![PREMIUM](/help/assets/premium.png) Uso de reglas de inclusión dinámicas y estáticas

Información sobre la creación de reglas de inclusión para criterios y promociones en [!DNL Adobe Target] y la adición de reglas de filtrado dinámicas o estáticas para obtener mejores resultados para sus recomendaciones.

El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Tanto los criterios como las promociones y el uso de reglas de inclusión se tratan en esta sección.

## Agregación de reglas de filtrado a los criterios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Mientras [crea criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), haga clic en **[!UICONTROL Agregar regla de filtrado]** en **[!UICONTROL Reglas de inclusión]**.

![](assets/inclusion_options_new.png)

Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

## Agregación de reglas de filtrado a las promociones    {#section_D59AFB62E2EE423086281CF5D18B1076}

Mientras [crea una promoción](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), seleccione **[!UICONTROL Promocionar por atributo]** y, a continuación, haga clic en **[!UICONTROL Agregar regla de filtrado]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

En las secciones siguientes se enumeran los tipos de opciones de filtrado para [!UICONTROL Filtrado dinámico] y [!UICONTROL Filtrar por valor] tanto para criterios como para promociones:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y ofrecen mejores resultados y una mayor participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en un parámetro de perfil de usuario o en una llamada de mbox.

   Por ejemplo, puede crear una recomendación &quot;Criterios más populares&quot;. Desde el conjunto de recomendaciones devueltas, puede filtrar cualquier recomendación (en tiempo real) con un atributo que se pase cuando el usuario acceda a una página en la que se muestran las recomendaciones.

* Utilice reglas estáticas para limitar qué artículos se incluyen en la recomendación (en lugar de usar colecciones).

* Puede crear tantas reglas de inclusión dinámicas como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

| Opción de filtrado dinámico | Detalles |
| --- | --- |
| [Coincidencia de atributos de entidad](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios han interactuado.<br>Utilice la  [!UICONTROL Coincidencia de atributos de ] entidad cuando desee mostrar recomendaciones que puedan atraer al visitante, como la marca favorita del visitante. |
| [Coincidencia de atributos de perfil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor del perfil del usuario.<br>Utilice  [!UICONTROL Coincidencia de atributos de ] perfil cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como el tamaño o la marca favorita. |
| [Coincidencia de parámetros](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).<br>Utilice  [!UICONTROL Coincidencia de ] parámetros para recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones de dispositivo o ubicación geográfica. |

### Filtrar por valor

La siguiente opción está disponible para filtrar por valor:

| Filtrado por valor, opción | Detalles |
| --- | --- |
| [Filtro estático](/help/c-recommendations/c-algorithms/static-value.md) | Introduzca manualmente uno o varios valores estáticos para filtrar. |

## Operadores disponibles {#operators}

Los criterios y promociones dinámicos son mucho más potentes que los estáticos y ofrecen mejores resultados y una mayor participación.

En los ejemplos siguientes se proporcionan ideas generales sobre cómo usar las promociones y exclusiones dinámicas en los esfuerzos de marketing:

| Operador | Ejemplos |
| --- | --- |
| Es igual a<br>(Disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Con el operador &quot;es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos de:<ul><li>La misma marca</li><li>La misma categoría</li><li>La misma categoría Y de la marca propia</li><li>La misma tienda</li></ul> |
| Does Not Equal<br>(Disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Con el operador &quot;no es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos de:<ul><li>Una serie de televisión diferente</li><li>Un género diferente</li><li>Una serie de productos diferente</li><li>Un ID de estilo diferente</li></ul> |
| No contiene subcadena<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Usando el operador &quot;no contiene subcadena&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El título no contiene una palabra grosera</li></ul> |
| Comienza con<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Con el operador &quot;comienza con&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El nombre del producto comienza con iPhone</li></ul> |
| Finaliza con<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Usando el operador &quot;termina con&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>El contenido termina con EN, que indica el idioma inglés</li></ul> |
| Is Bueno que o igual a<br>(Disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Usando el operador &quot;es bueno o igual que&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Coste igual o son más caros</li></ul> |
| Is Less Thor Equal To<br>(Disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil, coincidencia de parámetros y filtro estático). | Con el operador &quot;es menor o igual que&quot;, cuando un visitante está viendo un elemento en su sitio web (como un producto), puede promocionar otros elementos que:<ul><li>Coste igual o son menos costosos</li><li>Excluir artículos menos costosos</li></ul> |
| Está entre<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros). | Usando el operador &quot;está entre&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos que:<ul><li>Más caro</li><li>Menos caro</li><li>Costo más o menos 30%</li><li>Episodios posteriores en la misma temporada</li><li>Libros anteriores de una serie</li></ul> |
| Está contenido en la lista<br>(disponible con coincidencia de atributos de perfil y coincidencia de parámetros). | Utilizando el operador &quot;está contenido en la lista&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo o una película), puede promocionar otros elementos que:<ul><li>Disponible en la geografía del visitante</li></ul>**Ejemplo**: Desea recomendar solo los elementos que están disponibles en el área geográfica de un visitante.<br>Su regla de filtro puede tener el siguiente aspecto: <br>`availableGeographies list contains an item in user.currentGeography`<br>**Nota**: Al utilizar este operador, se espera una lista en el lado  [derecho ](#caveats) de la regla. |
| No está contenido en la lista<br>(disponible con coincidencia de atributos de perfil y coincidencia de parámetros). | Utilizando el operador &quot;no está contenido en la lista&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo o una película), puede excluir otros elementos que:<ul><li>En la lista de los últimos diez elementos que el visitante ha visto</li></ul></ul>**Ejemplo**: No desea promocionar artículos que el visitante haya visto recientemente y en los que no haya mostrado interés.<br>La regla de filtrado puede tener el siguiente aspecto: <br>`id is not contained in list user.lastViewedItems`<br>**Nota**: Al utilizar este operador, se espera una lista en el lado  [derecho ](#caveats) de la regla. |
| La lista contiene un elemento en<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros). | Usando el operador &quot;lista contiene un elemento en&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un evento deportivo o un concierto), puede promocionar otros elementos que:<ul><li>Asociado a uno de los equipos favoritos del visitante</li></ul>**Ejemplo**: Desea recomendar juegos asociados a uno de los equipos favoritos del visitante.<br>La regla de filtrado puede tener el siguiente aspecto: <br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Nota**: Al utilizar este operador, se espera una lista en  [ambos ](#caveats) lados de la regla. |
| La lista no contiene ningún elemento en<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros). | Usando el operador &quot;lista no contiene un elemento en&quot; en la coincidencia de atributos de parámetros, cuando un visitante está viendo un elemento en su sitio web (como un producto, un artículo, una película, etc.), puede excluir otros elementos que:<ul><li>Incluido en una lista de tipos prohibidos</li></ul>**Ejemplo**: Desea excluir los artículos disponibles para los visitantes que son adultos, como el tabaco y el alcohol.<br>La regla de filtrado puede tener el siguiente aspecto: <br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Nota**: Al utilizar este operador, se espera una lista en  [ambos ](#caveats) lados de la regla. |
| La lista contiene todos los elementos de<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros). | Usando el operador &quot;lista contiene todos los elementos en&quot; en la coincidencia de atributos de perfil, cuando un visitante está viendo un elemento en su sitio web (como un anuncio de trabajo o una fórmula), puede promocionar otros elementos que:<ul><li>Incluir un conjunto de habilidades</li><li>Incluir un conjunto de ingredientes necesarios</li></ul>**Ejemplo 1**: Supongamos que un visitante tiene un conjunto de habilidades (Java, C++ y HTML). Los artículos del catálogo son trabajos con las habilidades necesarias (Java y HTML). Antes de recomendar el trabajo al visitante, debe asegurarse de que el perfil del visitante contenga todas las habilidades necesarias.<br>La regla de filtrado puede tener el siguiente aspecto: <br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Ejemplo 2**: Supongamos que un usuario tiene una lista de ingredientes de la despensa. La receta tiene una lista de ingredientes necesarios. Antes de recomendar la fórmula al visitante, debe asegurarse de que el perfil del visitante contenga todos los ingredientes necesarios.<br>La regla de filtrado puede tener el siguiente aspecto: <br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Nota**: Al utilizar este operador, se espera una lista en  [ambos ](#caveats) lados de la regla. |
| La lista no contiene todos los elementos en<br>(disponible con coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros). | Usando el operador &quot;lista no contiene todos los elementos en&quot; en la coincidencia de atributos de entidad, cuando un visitante está viendo un elemento en su sitio web (como evento deportivo o concierto), puede promocionar otros elementos que:<ul><li>No incluir un conjunto de equipos</li></ul>**Ejemplo**: Supongamos que un evento deportivo incluye dos equipos: los Astros de Houston y los cerveceros Milwaukee. El perfil del visitante indica que este visitante no desea ver los juegos de estos equipos. Desea asegurarse de que no recomienda un juego si estos equipos están jugando.<br>La regla de filtrado puede tener el siguiente aspecto: <br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Nota**: Al utilizar este operador, se espera una lista en  [ambos ](#caveats) lados de la regla. |

## Gestión de valores vacíos al filtrar por coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Puede elegir varias opciones para gestionar valores vacíos al filtrar por [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] para criterios de salida y promociones.

Anteriormente, si un valor estaba en blanco no se devolvía ningún resultado. La lista desplegable “Si *x* está en blanco” le permite elegir la acción que se debe realizar si los criterios contienen valores en blanco, como se muestra en la siguiente ilustración:

![](assets/empty_value.png)

Para seleccionar la acción deseada, pase el ratón sobre el icono del engranaje (![](assets/icon_gear.png)) y, a continuación, elija la acción deseada:

| Acción | Disponible para | Detalles |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regla de filtrado] | [!UICONTROL Coincidencia de atributos de perfil ] y coincidencia  [!UICONTROL de parámetros] | Esta acción es la predeterminada para [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros].<br>Esta opción especifica que la regla se ignora. Por ejemplo, si hay tres reglas de filtrado y la tercera no pasa ningún valor, en vez de no devolver resultado alguno, puede simplemente ignorar la tercera regla con valores en blanco. |
| [!UICONTROL No mostrar ningún resultado para estos criterios]<br> (solo criterios) | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Esta acción es la predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<br>Esta acción es el  [!DNL Target] modo en que se gestionan los valores vacíos antes de añadir esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL No promocionar ningún elemento<br> (solo promociones)] | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Esta acción es la predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<br>Esta acción es el  [!DNL Target] modo en que se gestionan los valores vacíos antes de añadir esta opción: no se muestran resultados para este criterio. |
| [!UICONTROL Uso de un valor estático] | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Si un valor está en blanco, puede optar por usar un valor estático. |

## Advertencias {#caveats}

>[!IMPORTANT]
>
>Es posible que no se puedan usar atributos de tipo de datos diferentes en los criterios dinámicos o promociones durante el tiempo de ejecución con los operadores “es igual que” y “no es igual que”. Utilice los valores [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] y [!UICONTROL Environment] sabiamente en el lado derecho si el lado izquierdo tiene atributos predefinidos o personalizados.

![](assets/left_right.png)

La tabla siguiente contiene reglas eficaces y reglas que pueden no ser compatibles durante el tiempo de ejecución:

| Reglas compatibles | Reglas potencialmente incompatibles |
|--- |--- |
| value - está entre - 90 % and 110 % de Elemento actual - salesValue | salesValue - está entre - 90 % y 110% de Elemento actual - value |
| value - está entre - 90 % y 110 % de Elemento actual - value | clearancePrice - está entre - 90 % y 110 % de Elemento actual - margin |
| margin - está entre - 90 % y 110 % de Elemento actual - margin | storeInventory - es igual que - Elemento actual - inventory |
| inventory - es igual que - Elemento actual - inventory |  |
