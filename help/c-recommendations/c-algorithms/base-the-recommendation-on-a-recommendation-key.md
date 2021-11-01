---
keywords: clave de recomendación;lógica de recomendación;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;artículo más visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visitado;más visitado;favorito;visitado recientemente;más visto;más visto;más visto;más visto;más visto;más visto;más visto;más recientemente
description: Aprenda a utilizar las recomendaciones basadas en claves que usan el contexto de comportamiento del visitante para mostrar resultados relevantes en el Adobe [!DNL Target] Actividades de Recommendations.
title: ¿Cómo baso la recomendación en una clave de recomendación?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: cc260620cf87feebcd4c43f45f05406ac845cf5b
workflow-type: tm+mt
source-wordcount: '3850'
ht-degree: 41%

---

# Basar la recomendación en una clave de recomendación

Recommendations, basado en algoritmos, utiliza el contexto de comportamiento del visitante para mostrar resultados relevantes en [!DNL Adobe Target] [!DNL Recommendations] actividades.

Hay cinco tipos de algoritmos en [!DNL Target Recommendations]:

* [!UICONTROL Basado en el carro de compras]
* [!UICONTROL Basado en popularidad]
* [!UICONTROL Basado en elementos]
* [!UICONTROL Basado en el usuario]
* [!UICONTROL Criterios personalizados]

Cada tipo de algoritmo proporciona distintos algoritmos apropiados para su tipo, como se muestra en la siguiente tabla:

>[!NOTE]
>
>La variable [!UICONTROL Basado en el carro de compras] se describe en la siguiente tabla y está a punto de llegar.

| Tipo de algoritmo | Cuándo se utiliza | Algoritmos disponibles |
| --- | --- | --- |
| [!UICONTROL Basado en el carro de compras] | (Próximamente) Haga recomendaciones en función del contenido del carro de compras del usuario. | <ul><li>Los usuarios que vieron esto, vieron aquéllos</li><li>Los usuarios que vieron esto, compraron aquéllos</li><li>Las personas que compraron estos, compraron esos</li></ul> |
| [!UICONTROL Basado en popularidad] | Haga recomendaciones en función de la popularidad general de un artículo en todo el sitio o de la popularidad de artículos dentro de la categoría, marca, género, etc. favorita del usuario o los más vistos. | <ul><li>Más visitados en todo el sitio</li><li>Más visitados por categoría</li><li>Más visitados por atributo de artículo</li><li>Principales vendedores del sitio</li><li>Principales vendedores por categoría</li><li>Principales vendedores por atributo de artículo</li><li>Principales por métrica de Analytics</li></ul> |
| [!UICONTROL Basado en elementos] | Realice recomendaciones basadas en la búsqueda de artículos similares a un elemento que el usuario esté viendo o que haya visto recientemente. | <ul><li>Los usuarios que vieron esto, vieron aquello.</li><li>Los usuarios que vieron esto, compraron aquello.</li><li>Los usuarios que compraron esto, compraron aquello.</li><li>Elementos con atributos similares</li></ul> |
| [!UICONTROL Basado en el usuario] | Recomendaciones basadas en el comportamiento del usuario. | <ul><li>Artículos vistos recientemente. </li><li>Recomendado para usted</li></ul> |
| [!UICONTROL Criterios personalizados] | Realice recomendaciones basadas en un archivo personalizado que cargue. | <ul><li>Algoritmo personalizado</li></ul> |

Cada criterio está definido en su propia pestaña. El tráfico se divide equitativamente en las distintas pruebas de criterios. Es decir, si tiene dos criterios, el tráfico se divide a partes iguales entre ellos. Si tiene dos criterios y dos diseños, el tráfico se divide equitativamente entre las cuatro combinaciones. También puede especificar el porcentaje de los visitantes del sitio que ven el contenido predeterminado, para su comparación. En ese caso, el porcentaje especificado de visitantes ve el contenido predeterminado y el resto se divide entre las combinaciones de criterios y diseños.

Para obtener más información sobre la creación de criterios y la definición de sus tipos de algoritmos y algoritmos, consulte [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md).

Los distintos algoritmos de recomendaciones se prestan a colocarse en distintos tipos de páginas. Consulte las secciones siguientes para obtener más información sobre cada tipo de algoritmo y sus algoritmos disponibles.

## Basado en el carro de compras {#cart-based}

La variable [!UICONTROL Basado en el carro de compras] el tipo de algoritmo permite recomendar elementos en función del contenido del carro de compras actual del visitante.

La lógica de recomendación basada en el carro de compras es similar a la &quot;[!UICONTROL Recomendado]&quot; algoritmo basado en el usuario y a &quot;[!UICONTROL Los usuarios que vieron esto, compraron aquéllos]&quot; y &quot;[!UICONTROL Las personas que compraron estos, compraron esos]&quot; algoritmos basados en elementos.

[!DNL Target] utiliza técnicas de filtrado colaborativas para determinar las similitudes de cada elemento del carro de compras del visitante y, a continuación, combina estas similitudes de comportamiento en cada elemento para obtener una lista combinada.

[!DNL Target] también ofrece a los especialistas en marketing la opción de observar el comportamiento de los visitantes en una sola sesión o en varias sesiones:

* **Dentro de una sola sesión**: En función de lo que otros visitantes hicieron dentro de una sola sesión.

   Mirar el comportamiento dentro de una sola sesión puede tener sentido cuando existe la sensación de que los productos se &quot;unen&quot; estrechamente en función de un uso, ocasión o evento. Por ejemplo, un visitante está comprando una impresora y también puede necesitar tinta y papel. O, un visitante está comprando mantequilla de maní y también podría necesitar pan y gelatina.

* **En varias sesiones**: En función de lo que otros visitantes hicieron en varias sesiones.

   Ver el comportamiento en varias sesiones puede tener sentido cuando existe la sensación de que los productos &quot;van con&quot; fuerza unos con otros según la preferencia o el gusto del visitante. Por ejemplo, a un visitante le gusta Star Wars y también puede gustarle Indiana Jones, aunque no necesariamente quiera ver ambas películas en la misma sesión. O, a un visitante le gusta el juego de tablero &quot;Codenames&quot; y también el juego de tablero &quot;Avalon&quot;, aunque el visitante no pueda jugar ambos juegos simultáneamente. 

[!DNL Target] realiza recomendaciones para cada visitante en función de los artículos del carro de compras actual, independientemente de si observa el comportamiento de los visitantes en una sola sesión o en varias sesiones.

Los siguientes algoritmos están disponibles con la variable [!UICONTROL Basado en el carro de compras] tipo de algoritmo:

### [!UICONTROL Los usuarios que vieron esto, vieron aquellos]

Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos vistos por las personas después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite crear oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que ven las bicicletas de carretera en su sitio también pueden ver cascos para bicicletas, kits para bicicletas, cerraduras, etc. Puede crear una recomendación con esta lógica que sugiera que otros productos le ayudan a aumentar los ingresos.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, compraron aquéllos

Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados.

Esta lógica devuelve otros productos que otras personas compraron después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes vieron el artículo comprado. Por ejemplo, si el visitante está viendo un campo de pesca, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de direcciones, alcantarillas y lámparas de pesca. A medida que los visitantes navegan por el sitio, usted les proporciona recomendaciones de compra adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que compraron esto, compraron aquello.

Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado.

Esta lógica devuelve otros productos que otras personas compraron después de comprar este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra artículos que otros compradores también compraron. Por ejemplo, si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y cordones. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

## [!UICONTROL Basado en popularidad]

La variable [!UICONTROL Basado en popularidad] el tipo de algoritmo le permite hacer recomendaciones en función de la popularidad general de un elemento en el sitio o en función de la popularidad de los elementos dentro de la categoría, marca, género, etc. favorita del usuario o los más vistos.

Los siguientes algoritmos están disponibles con la variable [!UICONTROL Basado en popularidad] tipo de algoritmo:

### Más visitados en todo el sitio {#most-viewed}

La recomendación está determinada por el artículo que se ha visto con más frecuencia. Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de producto
* 5 puntos por cada visualización subsiguiente
* Al final de la sesión, se dividen todos los valores por 2

Por ejemplo, si ve surfboardA y luego surfboardB en una misma sesión, el resultado es A: 10, B: 5. Cuando finaliza la sesión, tiene A: 5, B: 2.5. Si ve los mismos elementos en la siguiente sesión, los valores cambian a A: 15 B: 7.5.

Utilice este algoritmo en páginas generales, como páginas de inicio o de aterrizaje y anuncios externos.

### Más visitados por categoría {#most-viewed-category}

La recomendación está determinada por la categoría que recibió la mayor cantidad de actividad, usando el mismo método empleado con el “artículo más visitado”, excepto que se clasifican las categorías en lugar de los productos.

Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de categoría
* 5 puntos por cada visualización subsiguiente

Las categorías visitadas por primera vez reciben 10 puntos. Por las siguientes visitas a la misma categoría, se conceden 5 puntos. Con cada visita, la puntuación de las categorías antiguas que se vieron con anterioridad se reduce 1 punto.

Por ejemplo, si ve categoría A y luego categoría B en una sesión, el resultado es A: 9, B: 10. Si ve los mismos elementos en la próxima sesión, los valores serán A: 20 B: 9.

Utilice este algoritmo en páginas generales, como páginas de inicio o de aterrizaje y anuncios externos.

Si selecciona el algoritmo Más visitados por categoría , puede seleccionar las siguientes claves de Recommendations:

* Categoría actual
* Categoría favorita

### Más visitados por atributo de artículo

(Próximamente habrá información)

### Principales vendedores del sitio {#top-sellers}

Muestra los artículos que están incluidos en los pedidos más completados de todo el sitio. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido.

Este algoritmo le permite crear recomendaciones para los artículos más vendidos del sitio a fin de aumentar la conversión y los ingresos. Esta lógica es especialmente adecuada para los visitantes que ingresan al sitio por primera vez.

### Principales vendedores por categoría

Muestra los artículos incluidos en los pedidos más completados por categoría. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido.

Este algoritmo permite crear recomendaciones para los artículos más vendidos del sitio en función de la categoría para aumentar la conversión y los ingresos. Esta lógica es especialmente adecuada para los visitantes que ingresan al sitio por primera vez.

Si selecciona el algoritmo Más visitados por categoría , puede seleccionar las siguientes claves de Recommendations:

* Categoría actual
* Categoría favorita

### Principales vendedores por atributo de artículo

(Próximamente habrá información)

### Principales por métrica de Analytics

(Próximamente habrá información)

## [!UICONTROL Basado en elementos]

La variable [!UICONTROL Basado en elementos] el tipo de recomendación le permite hacer recomendaciones en función de encontrar artículos similares a los que el usuario está viendo o que ha visto recientemente.

Los siguientes algoritmos están disponibles con la variable [!UICONTROL Basado en elementos] tipo de algoritmo:

### Los usuarios que vieron esto, vieron aquello. {#viewed-viewed}

Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos vistos por las personas después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite crear oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que ven las bicicletas de carretera en su sitio también pueden ver cascos para bicicletas, kits para bicicletas, cerraduras, etc. Puede crear una recomendación con esta lógica que sugiera que otros productos le ayudan a aumentar los ingresos.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que vieron esto, compraron aquello. {#viewed-bought}

Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados.

Esta lógica devuelve otros productos que otras personas compraron después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes vieron el artículo comprado. Por ejemplo, si el visitante está viendo un campo de pesca, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de direcciones, alcantarillas y lámparas de pesca. A medida que los visitantes navegan por el sitio, usted les proporciona recomendaciones de compra adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Los usuarios que compraron esto, compraron aquello. {#bought-bought}

Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado.

Esta lógica devuelve otros productos que otras personas compraron después de comprar este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de venta cruzada mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra artículos que otros compradores también compraron. Por ejemplo, si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y cordones. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

### Elementos con atributos similares {#similar-attributes}

Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores.

Si selecciona Artículos/Medios con atributos similares, tiene la opción de establecer reglas de contenido similares.

Utilizar la similitud de contenido para generar recomendaciones es especialmente eficaz para los nuevos artículos, que probablemente no aparezcan en las recomendaciones usando Otras personas que vieron esto, Vieron aquello y otra lógica basada en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

Para obtener más información, consulte [Similitud de contenido](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL Basado en el usuario]

El tipo de algoritmo basado en usuarios le permite hacer recomendaciones en función del comportamiento del usuario.

Los siguientes algoritmos están disponibles con la variable [!UICONTROL Basado en el usuario] tipo de algoritmo:

### Artículos vistos recientemente {#recently-viewed}

Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño.

El algoritmo de artículos vistos recientemente devuelve un resultado específico de un [entorno](/help/administrating-target/hosts.md). Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

>[!NOTE]
>
>No puede usar la variable [!UICONTROL Artículos vistos recientemente] criterios para recomendaciones de copia de seguridad.

Los elementos/medios vistos recientemente se pueden filtrar para que solo se muestren los elementos con un atributo en particular.

* Los criterios visualizados recientemente se pueden configurar, como otros criterios en las recomendaciones.
* Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.

Los posibles casos de uso incluyen: una empresa multinacional con varias empresas puede tener elementos de vista de visitantes en varias propiedades digitales. En este caso, se pueden limitar los elementos vistos recientemente para que solo se muestren en relación con la propiedad respectiva en la que se visualizaron. Esto evita que los artículos vistos recientemente se muestren en el sitio de otra propiedad digital.

Utilice este algoritmo en páginas generales, como páginas de inicio o de aterrizaje y anuncios externos.

>[!NOTE]
>
>[!UICONTROL Artículos vistos recientemente] respeta tanto la configuración global de exclusiones como la configuración de recopilación seleccionada para la actividad. Si un elemento está excluido por una exclusión global o no está contenido en la colección seleccionada, no se mostrará. Por lo tanto, al usar un [!UICONTROL Artículos vistos recientemente] , generalmente se debe utilizar la configuración &quot;Todas las colecciones&quot;.

### Recomendado para usted {#recommended-for-you}

Recomienda artículos según el historial de navegación, visualización y compra de cada visitante.

Este algoritmo le permite enviar contenido y experiencias personalizados tanto a los visitantes nuevos como a los que regresan. La lista de recomendaciones se evalúa según la actividad más reciente del visitante y se actualiza en la sesión y se personaliza más a medida que el usuario navega por el sitio.

Tanto las vistas como las compras se utilizan para determinar los artículos recomendados. La clave de recomendación especificada (por ejemplo, Elemento actual) se usa para aplicar cualquier filtro de regla de inclusión que seleccione.

Por ejemplo, puede:

* Excluir elementos que no cumplan ciertos criterios (productos sin existencias, artículos publicados hace más de 30 días, películas clasificadas como R, etc.).
* Limite los artículos incluidos a una sola categoría o a la categoría actual.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de filtrado:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado

## Criterios personalizados {#custom}

El tipo de algoritmo de criterios personalizados permite realizar recomendaciones basadas en un archivo personalizado que se carga.

La recomendación viene determinada por un elemento almacenado en el perfil de un visitante, utilizando los atributos user.*x* o perfil.atributos *x*.

Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil.

Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación.

Puede realizar el filtrado en tiempo real sobre su propia salida de criterios personalizados. Por ejemplo, puede limitar sus artículos recomendados solo a aquellos de la categoría o marca favorita de un visitante. Esto le da la capacidad de combinar cálculos sin conexión con filtrado en tiempo real.

Esta funcionalidad significa que puede utilizar [!DNL Target] para añadir personalización además de sus recomendaciones calculadas sin conexión o listas personalizadas. Esto combina el poder de sus científicos e investigadores de datos con la entrega probada y comprobada de Adobe, el filtrado en tiempo de ejecución, las pruebas A/B, la orientación, los informes, las integraciones y más.

Con la adición de reglas de inclusión en Criterios personalizados, convierte las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses de los visitantes.

* Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.
* Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.

Los posibles casos de uso incluyen:

* Desea recomendar películas de una lista personalizada, pero solo si el visitante no las ha visto.
* Desea ejecutar un algoritmo sin conexión y usar los resultados para potenciar las recomendaciones, pero debe asegurarse de que los artículos sin existencias nunca se recomienden.
* Desea incluir solo los elementos que pertenecen a la categoría favorita de este visitante.

## Claves de recomendación

Las siguientes claves de recomendación están disponibles en la sección [!UICONTROL Clave de recomendación] lista desplegable:

### Artículo actual {#current-item}

La recomendación está determinada por el artículo que el visitante está viendo en ese momento.

Las recomendaciones muestran otros artículos que pueden ser de interés para los visitantes interesados en el artículo especificado.

Si se selecciona está opción, el valor `entity.id` debe pasarse como parámetro en mbox de visualización.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]

Utilice la variable [!UICONTROL Artículo actual] clave de recomendaciones del sitio en:

* Páginas con un solo elemento, como las páginas de productos.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Último artículo comprado {#last-purchased}

La recomendación está determinada por el último artículo que compró cada visitante único. Esto se captura automáticamente, por lo que no se debe pasar ningún valor a la página.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]

Utilice la variable [!UICONTROL Último artículo comprado] clave de recomendaciones del sitio en:

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

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

### Último artículo visitado {#last-viewed}

La recomendación está determinada por el último artículo que vio cada visitante único. Esto se captura automáticamente, por lo que no se debe pasar ningún valor a la página.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]

Utilice la variable [!UICONTROL Último artículo visitado] clave de recomendaciones del sitio en:

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

### Artículo más visitado {#most-viewed-logic}

Muestra los artículos o medios que se visitaron con mayor frecuencia en el sitio.

Esta lógica le permite mostrar recomendaciones basadas en los artículos más vistos del sitio para aumentar las conversiones de otros artículos. Por ejemplo, un sitio multimedia podría mostrar recomendaciones en su página principal para los vídeos más vistos para animar a los visitantes a ver otros vídeos.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]

### Categoría actual {#current-category}

La recomendación está determinada por la categoría de producto que el visitante está viendo en ese momento.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* Principales vendedores
* Más visitados

Utilice la variable [!UICONTROL Categoría actual] clave de recomendaciones del sitio en:

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Categoría favorita {#favorite-category}

La recomendación está determinada por la categoría de producto favorita del visitante.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* Principales vendedores
* Más visitados

Utilice la variable [!UICONTROL Categoría actual] clave de recomendaciones del sitio en:

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### Afinidad del sitio {#site-affinity}

Recomienda elementos según la certeza de una relación entre artículos. Puede configurar este criterio para determinar la cantidad de datos que se requiere antes de presentar una recomendación con el regulador Reglas de inclusión. Por ejemplo, si selecciona Muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.

Por ejemplo, si establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y son reemplazados por sus artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.

Por ejemplo, un comerciante en línea puede recomendar artículos en visitas posteriores en las que un visitante haya mostrado interés durante sesiones anteriores. La actividad de cada sesión de visitante se captura para calcular una afinidad basada en un modelo de actualización y frecuencia. A medida que este visitante regresa a su sitio, la afinidad del sitio se usa para mostrar recomendaciones basadas en acciones anteriores del sitio.

Es posible que algunos clientes con diferentes colecciones de productos y diversos comportamientos de sitio obtengan mejores resultados si establecen una afinidad de sitio débil.

Esta lógica se puede usar con las siguientes claves de recomendación:

* Artículo actual
* Último artículo comprado
* Último artículo visitado
* Artículo más visitado
