---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Recommendations basado en claves utiliza el contexto de comportamiento de visitante para mostrar resultados relevantes en las actividades de Adobe Target Recommendations.
title: Basar la recomendación en una clave de recomendación
feature: criteria
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: 21c8e39669925e8fd26d7f64ea7dfe95f28795bf
workflow-type: tm+mt
source-wordcount: '2151'
ht-degree: 70%

---


# Basar la recomendación en una clave de recomendación

Recommendations based on keys use visitor behavior context to show relevant results in [!DNL Adobe Target] [!DNL Recommendations] activities.

Existen dos tipos de recomendaciones:

* **Popularidad:** enumera los elementos según los más visitados, los más vendidos y las métricas principales. La clave está vacía para los criterios de popularidad.
* **Basado en claves:** comprende el resto de los criterios. Recommendations ofrece un conjunto diverso de opciones con respecto al tipo de clave. Las opciones van desde “elemento actual” a “parámetros de perfil”, que le permiten establecer programáticamente la clave de los valores para recomendar. Puede probar varios criterios uno frente a otro basando cada criterio en una clave diferente.

Cada criterio está definido en su propia pestaña. El tráfico se divide equitativamente en las distintas pruebas de criterios. Es decir, si tiene dos criterios, el tráfico se divide a partes iguales entre ellos. Si tiene dos criterios y dos diseños, el tráfico se divide equitativamente entre las cuatro combinaciones. También puede especificar el porcentaje de los visitantes del sitio que ven el contenido predeterminado, para su comparación. En ese caso, el porcentaje de visitantes especificado ve el contenido predeterminado y el resto se divide entre las combinaciones de algoritmo y plantilla.

1. Create a new criteria, or select an existing criteria and click **[!UICONTROL Edit]**.
1. To change the recommendation key, select the new key from the [!UICONTROL Recommendation Key] drop-down list, then click **[!UICONTROL Save]** or **[!UICONTROL Update]**.

   Dado que lógicas diferentes dirigen a claves de recomendaciones diferentes, estas últimas se prestan a colocarse en diferentes tipos de páginas. Consulte las secciones siguientes para obtener más información sobre cada clave de recomendación.

## Claves de recomendación

Las siguientes claves de recomendación están disponibles en la lista desplegable Clave [!UICONTROL de] recomendación:

### Artículo actual

La recomendación está determinada por el artículo que el visitante está viendo en ese momento.

Las recomendaciones muestran otros artículos que pueden ser de interés para los visitantes interesados en el artículo especificado.

Si se selecciona está opción, el valor `entity.id` debe pasarse como parámetro en mbox de visualización.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

* Páginas con un solo elemento, como las páginas de productos.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Categoría actual

La recomendación está determinada por la categoría de producto que el visitante está viendo en ese momento.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

#### Lógica (criterio)

* Principales vendedores
* Más visitados

#### Ubicación en el sitio

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Atributo personalizado.  {#custom}

La recomendación viene determinada por un elemento almacenado en el perfil de un visitante, utilizando los atributos user.*x* o perfil.atributos *x*.

Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil.

#### Lógica (criterio)

* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Comportamiento general.]
* [!UICONTROL Más visitados]
* [!UICONTROL Principales vendedores]

Si la clave es un atributo de perfil personalizado y el tipo de algoritmo es el más visitado o el más vendido, aparece una nueva lista desplegable llamada “Agrupar por valor único de” que tiene una lista de atributos de entidades conocidas (excepto ID, categoría, margen, valor, inventario y entorno). Este campo es obligatorio.

#### Ubicación en el sitio

* Puede utilizarse en cualquier página.

#### Clave de recomendaciones personalizadas

Puede basar las recomendaciones en el valor de un atributo de perfil personalizado. Por ejemplo, supongamos que desea mostrar películas recomendadas basadas en la película que agregó un visitante recientemente a su cola.

1. Seleccione su atributo de perfil personalizado en la lista **[!UICONTROL desplegable Clave]** de recomendación (por ejemplo, «Última visualización agregada a la lista de observación»).
1. A continuación, seleccione la lógica **[!UICONTROL de recomendación]** (por ejemplo, &quot;Personas que vieron esto, Vieron aquello&quot;).

   ![Crear nuevo cuadro de diálogo de criterios](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si el atributo de perfil personalizado no coincide directamente con un ID de entidad único, es necesario explicar cómo [!DNL Recommendations] desea que se produzca la coincidencia en una entidad. Por ejemplo, supongamos que desea mostrar los artículos más vendidos de la marca favorita de un visitante.

1. Seleccione su atributo de perfil personalizado en **[!UICONTROL la lista desplegable Clave]** de recomendación (por ejemplo, «Marca favorita»).

1. A continuación, seleccione **[!UICONTROL la lógica]** de recomendación que desee utilizar con esta clave (por ejemplo, &quot;Principales vendedores&quot;).

   Se muestra [!UICONTROL la] opción Agrupar por valor único de.

1. Seleccione el atributo de entidad que coincida con la clave que ha elegido. En este caso, «Marca favorita» coincide con `entity.brand`.

   [!DNL Recommendations] ahora genera una lista «Principales vendedores» para cada marca y muestra al visitante la lista «Principales vendedores» adecuada en función del valor almacenado en el atributo de perfil de Marca favorita del visitante.

   ![Crear nuevo cuadro de diálogo de criterios 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Último artículo comprado

La recomendación está determinada por el último artículo que compró cada visitante único. La captura se realiza de forma automática, por lo tanto no es necesario pasar valores a la página.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

### Último artículo visitado

La recomendación está determinada por el último artículo que vio cada visitante único. La captura se realiza de forma automática, por lo tanto no es necesario pasar valores a la página.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

### Artículo más visitado

La recomendación está definida por el artículo que se vio con mayor frecuencia, usando el mismo método utilizado en la categoría de favoritos.

Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de producto
* 5 puntos por cada visualización subsiguiente
* Al final de la sesión, se dividen todos los valores por 2

Por ejemplo, si ve surfboardA y luego surfboardB en una misma sesión, el resultado es A: 10, B: 5. Cuando la sesión finalice, tendrá A: 5, B: 2,5. Si ve los mismos artículos en la sesión siguiente, los valores cambian a A: 15 B: 7,5.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Categoría favorita

La recomendación está determinada por la categoría que recibió la mayor cantidad de actividad, usando el mismo método empleado con el “artículo más visitado”, excepto que se clasifican las categorías en lugar de los productos.

Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de categoría
* 5 puntos por cada visualización subsiguiente

Las categorías visitadas por primera vez reciben 10 puntos. Por las siguientes visitas a la misma categoría, se conceden 5 puntos. Con cada visita, la puntuación de las categorías antiguas que se vieron con anterioridad se reduce 1 punto.

Por ejemplo, si ve categoría A y luego categoría B en una sesión, el resultado es A: 9, B: 10. Si ve los mismos elementos en la próxima sesión, los valores serán A: 20 B: 9.

#### Lógica (criterio)

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Popularidad

La recomendación está determinada por la popularidad de los artículos del sitio. La popularidad incluye a los principales vendedores y a los más visitados según los datos del mbox, y si usa Adobe Analytics, todas las métricas disponibles en el informe de productos. Los elementos se clasifican según la lógica de recomendación seleccionada.

#### Lógica (criterio)

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]
* Métricas de informe de productos (si utiliza Adobe Analytics)

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Artículos vistos recientemente.  {#recently-viewed}

Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño.

Los criterios de Elementos visualizados recientemente ahora devuelven resultados específicos de un [entorno](/help/administrating-target/hosts.md) determinado. Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

>[!NOTE]
>
>Elementos vistos recientemente respeta tanto la configuración global de Exclusiones como la configuración de Colección seleccionada para la Actividad. Si un elemento queda excluido por una Exclusión global o no está contenido en la Colección seleccionada, no se mostrará; por lo tanto, al utilizar los criterios de Artículos vistos recientemente, se suele utilizar la opción «Todas las colecciones».

## Lógica de recomendación

La siguiente lógica de recomendación (criterios) está disponible en la lista desplegable [!UICONTROL de la lógica] de recomendación:

### Elementos con atributos similares

La similitud de contenido compara palabras clave de los atributos de los artículos y realiza recomendaciones basándose en la cantidad de palabras clave que los artículos tienen en común. Las recomendaciones que se basan en la similitud de contenido no requieren información anterior para ofrecer buenos resultados.

El uso de la similitud de contenido para generar recomendaciones resulta especialmente eficaz para los nuevos artículos, que probablemente no se muestren en las recomendaciones con Personas que vieron esto, vieron aquello y otras lógicas basadas en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Para obtener más información, consulte [Similitud](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)de contenido.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Más visitados

Muestra los artículos más vistos del sitio.

Esta lógica le permite mostrar recomendaciones basadas en los artículos más vistos del sitio para aumentar las conversiones de otros artículos. Por ejemplo: un sitio de medios podría mostrar recomendaciones en su página de inicio para los vídeos más populares a fin de animar a los visitantes a ver vídeos adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Categoría actual
* Atributo personalizado. 
* Categoría favorita
* Popularidad

### Los usuarios que compraron esto, compraron aquello.

Muestra los artículos que otros visitantes también compraron y compraron el artículo seleccionado.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra los artículos que otros compradores también compraron. Por ejemplo, si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales comprados por otros visitantes, como corbatas, zapatos de vestir y corbatas. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones de compra adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, compraron aquello.

Muestra otros artículos comprados por visitantes que vieron el artículo seleccionado.

Esta lógica le permite aumentar las oportunidades de venta cruzada al mostrar una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes vieron el artículo comprado. Por ejemplo, si el visitante está viendo un poste de pesca, la recomendación podría mostrar elementos adicionales que otros visitantes estén viendo el artículo comprado, como las cajas de abordaje, los alcantarillados y los lúpulos de pesca. A medida que los visitantes navegan por el sitio, usted les proporciona recomendaciones de compra adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, vieron aquello.

Muestra elementos que otros visitantes también vieron y vieron que vieron el elemento seleccionado.

Esta lógica le permite crear oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que vista bicicletas de carretera en su sitio también pueden mirar cascos para bicicletas, kits para ciclismo, cerraduras, etc. Puede crear una recomendación utilizando esta lógica que sugiera otros productos.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Afinidad del sitio

Muestra artículos que utilizan un algoritmo propietario de Adobe para recomendar otros artículos según criterios, como vistas de páginas de productos, compras y actividades del carro de compras (adición o eliminación de artículos, visualización del carro de compras, etc.)

Por ejemplo: un minorista en línea puede recomendar elementos en los que un visitante ha mostrado interés durante sesiones anteriores en visitas posteriores. La actividad de cada sesión de visitante se captura para calcular una puntuación de afinidad basada en un modelo de actualización y frecuencia. A medida que este visitante regresa a su sitio, la afinidad del sitio se utiliza para mostrar las recomendaciones en base a acciones anteriores en el sitio.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Principales vendedores

Muestra los artículos más vendidos del sitio en base a las conversiones de visitantes.

Esta lógica le permite crear recomendaciones para artículos populares en el sitio para aumentar la conversión. Esta lógica es especialmente adecuada para los visitantes nuevos del sitio.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Categoría favorita
* Popularidad
