---
keywords: clave de recomendación;lógica de recomendación;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;artículo más visto;artículo más visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visitado;más visto;favorito;recientemente visto
description: Obtenga información sobre cómo utilizar las recomendaciones basadas en claves que utilizan el contexto de comportamiento de visitante para mostrar resultados relevantes en las actividades de Adobe Target Recommendations.
title: ¿Cómo baso la recomendación en una clave de recomendación?
feature: Recommendations
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '2932'
ht-degree: 67%

---


# Basar la recomendación en una clave de recomendación

Recommendations basado en claves utiliza el contexto de comportamiento de visitante para mostrar resultados relevantes en actividades [!DNL Adobe Target] [!DNL Recommendations].

Existen dos tipos de recomendaciones:

* **Popularidad:** enumera los elementos según los más visitados, los más vendidos y las métricas principales. La clave está vacía para los criterios de popularidad.
* **Basado en claves:** comprende el resto de los criterios. Recommendations ofrece un conjunto diverso de opciones con respecto al tipo de clave. Las opciones van desde “elemento actual” a “parámetros de perfil”, que le permiten establecer programáticamente la clave de los valores para recomendar. Puede probar varios criterios uno frente a otro basando cada criterio en una clave diferente.

Cada criterio está definido en su propia pestaña. El tráfico se divide equitativamente en las distintas pruebas de criterios. Es decir, si tiene dos criterios, el tráfico se divide a partes iguales entre ellos. Si tiene dos criterios y dos diseños, el tráfico se divide equitativamente entre las cuatro combinaciones. También puede especificar el porcentaje de los visitantes del sitio que ven el contenido predeterminado, para su comparación. En ese caso, el porcentaje de visitantes especificado ve el contenido predeterminado y el resto se divide entre las combinaciones de algoritmo y plantilla.

1. Cree un nuevo criterio o seleccione uno existente y haga clic en **[!UICONTROL Editar]**.
1. Para cambiar la clave de recomendación, seleccione la nueva clave en la lista desplegable [!UICONTROL Clave de recomendación] y haga clic en **[!UICONTROL Guardar]** o **[!UICONTROL Actualizar]**.

   Dado que lógicas diferentes dirigen a claves de recomendaciones diferentes, estas últimas se prestan a colocarse en diferentes tipos de páginas. Consulte las secciones siguientes para obtener más información sobre cada clave de recomendación.

## Claves de recomendación

Las siguientes claves de recomendación están disponibles en la lista desplegable [!UICONTROL Clave de recomendación]:

### Artículo actual {#current-item}

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

### Categoría actual  {#current-category}

La recomendación está determinada por la categoría de producto que el visitante está viendo en ese momento.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

#### Lógica (criterio)

* Principales vendedores
* Más visitados

#### Ubicación en el sitio

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Atributo personalizado.   {#custom}

La recomendación viene determinada por un elemento almacenado en el perfil de un visitante, utilizando los atributos user.*x* o perfil.atributos *x*.

Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil.

Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación.

Puede realizar el filtrado en tiempo real sobre su propia salida de criterios personalizados. Por ejemplo, puede limitar sus artículos recomendados solo a aquellos de la categoría o marca favorita de un visitante. Esto le da la capacidad de combinar cálculos sin conexión con filtrado en tiempo real.

Esta funcionalidad significa que puede utilizar [!DNL Target] para agregar personalización además de las recomendaciones calculadas sin conexión o las listas depuradas personalizadas. Esto combina el poder de sus científicos e investigadores de datos con la entrega probada y comprobada de Adobe, el filtrado en tiempo de ejecución, las pruebas A/B, la orientación, los informes, las integraciones y más.

Con la adición de reglas de inclusión en Criterios personalizados, convierte las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses de los visitantes.

* Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.
* Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.

Los posibles casos de uso incluyen:

* Desea recomendar películas de una lista personalizada, pero solo si el visitante no las ha visto.
* Desea ejecutar un algoritmo sin conexión y usar los resultados para potenciar sus recomendaciones, pero debe asegurarse de que los artículos agotados no sean recomendados.
* Desea incluir solo los elementos que pertenecen a la categoría favorita de este visitante.

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

### Categoría favorita {#favorite-category}

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

### Último artículo comprado {#last-purchased}

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

### Último artículo visitado  {#last-viewed}

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

### Artículo más visitado  {#most-viewed}

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

### Popularidad  {#popularity}

La recomendación está determinada por la popularidad de los artículos del sitio. La popularidad incluye a los principales vendedores y a los más visitados según los datos del mbox, y si usa Adobe Analytics, todas las métricas disponibles en el informe de productos. Los elementos se clasifican según la lógica de recomendación seleccionada.

#### Lógica (criterio)

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]
* Métricas de informe de productos (si utiliza Adobe Analytics)

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Artículos vistos recientemente.   {#recently-viewed}

Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño.

El criterio Elementos vistos recientemente devuelve resultados específicos de un [entorno](/help/administrating-target/hosts.md) determinado. Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

>[!NOTE]
>
>No puede usar los criterios [!UICONTROL Elementos vistos recientemente] para las recomendaciones de copia de seguridad.

Los elementos/medios vistos recientemente se pueden filtrar para que solo se muestren los elementos con un atributo en particular.

* Los criterios visualizados recientemente se pueden configurar, como otros criterios en las recomendaciones.
* Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.

Los posibles casos de uso incluyen:

Una empresa multinacional con múltiples negocios podría tener elementos de visualización de visitantes en múltiples propiedades digitales. En este caso, se pueden limitar los elementos vistos recientemente para que solo se muestren en relación con la propiedad respectiva en la que se visualizaron. Esto evita que los artículos vistos recientemente se muestren en el sitio de otra propiedad digital.

#### Ubicación en el sitio

* Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

>[!NOTE]
>
>[!UICONTROL Los ] elementos vistos recientemente respetan tanto la configuración global de exclusiones como la configuración de colección seleccionada para la actividad. Si un elemento está excluido por una exclusión global o no está contenido en la colección seleccionada, no se mostrará. Por lo tanto, cuando se utiliza un criterio [!UICONTROL Elementos vistos recientemente], generalmente se debe utilizar la configuración &quot;Todas las colecciones&quot;.

## Lógica de recomendación

[!DNL Target Recommendations] emplea sofisticados algoritmos que determinan si las acciones de un visitante cumplen los criterios establecidos en su actividad. La clave de recomendación determina las opciones de lógica de recomendaciones que se encuentran disponibles.

La siguiente lógica de recomendación (criterios) está disponible en la lista desplegable [!UICONTROL Lógica de recomendación]:

### Elementos/Medios con atributos similares {#similar-attributes}

Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores.

Si selecciona Elementos/Medios con atributos similares, tiene la opción de establecer reglas de similitud de contenido.

El uso de la similitud de contenido para generar recomendaciones resulta especialmente eficaz para los nuevos artículos, que probablemente no se muestren en las recomendaciones con Personas que vieron esto, vieron aquello y otras lógicas basadas en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Para obtener más información, consulte [Similitud de contenido](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Más visitados {#most-viewed-logic}

Muestra los elementos o medios que se visitan con mayor frecuencia en el sitio.

Esta lógica le permite mostrar recomendaciones basadas en los artículos más vistos del sitio para aumentar las conversiones de otros artículos. Por ejemplo: un sitio de medios podría mostrar recomendaciones en su página de inicio para los vídeos más vistos a fin de animar a los visitantes a ver vídeos adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Categoría actual
* Atributo personalizado. 
* Categoría favorita
* Popularidad

### Los usuarios que compraron esto, compraron aquello.{#bought-bought}

Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado.

Esta lógica devuelve otros productos que las personas compraron después de comprar este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra los artículos que otros compradores también compraron. Por ejemplo, si el visitante compra un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y corbatas. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, compraron aquello.{#viewed-bought}

Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados.

Esta lógica devuelve otros productos que las personas compraron después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada al mostrar una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes vieron el artículo comprado. Por ejemplo, si el visitante está viendo un poste de pesca, la recomendación podría mostrar elementos adicionales que otros visitantes compraron, como cajas de abordaje, alcantarillas y lúpulos de pesca. A medida que los visitantes navegan por el sitio, usted les proporciona recomendaciones de compra adicionales.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, vieron aquello.{#viewed-viewed}

Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos que las personas vieron después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite crear oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que vista bicicletas de carretera en su sitio también pueden mirar cascos para bicicletas, kits para ciclismo, cerraduras, etc. Puede crear una recomendación con esta lógica que sugiera otros productos para ayudarle a aumentar los ingresos.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Atributo personalizado. 
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Afinidad del sitio {#site-affinity}

Recomienda elementos según la certeza de una relación entre artículos. Puede configurar este criterio para determinar la cantidad de datos que se requiere antes de presentar una recomendación con el regulador Reglas de inclusión. Por ejemplo, si selecciona Muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.

Por ejemplo, si establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y son reemplazados por sus artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.

Por ejemplo: un minorista en línea puede recomendar elementos en visitas posteriores en las que un visitante ha mostrado interés durante sesiones anteriores. La actividad de cada sesión de visitante se captura para calcular una afinidad en función de un modelo de actualización y frecuencia. A medida que este visitante regresa a su sitio, la afinidad del sitio se utiliza para mostrar las recomendaciones en base a acciones anteriores en el sitio.

Es posible que algunos clientes con diferentes colecciones de productos y diversos comportamientos de sitio obtengan mejores resultados si establecen una afinidad de sitio débil.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Principales vendedores {#top-sellers}

Muestra los artículos incluidos en los pedidos más completados. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido.

Esta lógica le permite crear recomendaciones para los artículos más vendidos del sitio para aumentar la conversión y los ingresos. Esta lógica es especialmente adecuada para los visitantes nuevos del sitio.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Categoría favorita
* Popularidad

### Recommendations basado en el usuario {#user-based}

Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como &quot;Recomendado para usted&quot;.

Este criterio le permite entregar contenido y experiencias personalizadas a visitantes nuevos y reincidentes. La lista de las recomendaciones está ponderada en función de la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el usuario navega por el sitio.

Tanto las vistas como las compras se utilizan para determinar los artículos recomendados. La clave de recomendación especificada (por ejemplo, Elemento actual) se utiliza para aplicar cualquier filtros de regla de inclusión que seleccione.

Por ejemplo, puede:

* Excluya los elementos que no cumplan determinados criterios (productos sin existencias, artículos publicados hace más de 30 días, películas clasificadas como R, etc.).
* Limitar los elementos incluidos a una sola categoría o a la categoría actual.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado