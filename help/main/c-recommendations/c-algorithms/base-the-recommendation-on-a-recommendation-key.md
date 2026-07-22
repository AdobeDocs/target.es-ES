---
keywords: clave de recomendación;lógica de recomendación;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;artículo más visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visto;más visto;favorito;visto recientemente
description: Aprenda a utilizar recomendaciones basadas en claves que utilizan el contexto de comportamiento del visitante para mostrar resultados relevantes en actividades de [!UICONTROL Recommendations].
title: ¿Cómo baso la [!UICONTROL Recomendación] en una [!UICONTROL Clave de recomendación]?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
TQID: https://experienceleague.adobe.com/1gI3rMMf9s5ogc4BvBz4fMUqxed1Nqad0XoaR8SlU58
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 220c828fc77e9022a3884de04b78ae5d107e4c7d
workflow-type: tm+mt
source-wordcount: 4405
ht-degree: 25%

---

# Basar la recomendación en una clave de recomendación

Las recomendaciones basadas en algoritmos utilizan el contexto de comportamiento del visitante para mostrar resultados relevantes en [!DNL Adobe Target] actividades [!DNL Recommendations].

Cada tipo de algoritmo proporciona diferentes algoritmos adecuados para su tipo, como se muestra en la siguiente tabla:

| Tipo de algoritmo | Cuándo utilizar / Algoritmos disponibles |
| --- | --- |
| [!UICONTROL Basado en el carro de compras] | Haga recomendaciones basadas en el contenido del carro de compras del usuario.<ul><li>[!UICONTROL Las Personas Que Vieron Esto, También Vieron]</li><li>[!UICONTROL Otras Personas Que Vieron Esto, También Compraron]</li><li>[!UICONTROL Otras Personas Que Compraron Esto, También Compraron]</li></ul> |
| [!UICONTROL Basado en popularidad] | Haga recomendaciones basadas en la popularidad general de un elemento en el sitio o en la popularidad de elementos dentro de la categoría, marca, género, etc. favoritos o más vistos de un usuario. <ul><li>[!UICONTROL Más visitados en todo el sitio]</li><li>[!UICONTROL Más visitados por categoría]</li><li>[!UICONTROL Más visitados por atributo de artículo]</li><li>[!UICONTROL Más visitados por atributo de perfil]</li><li>[!UICONTROL Principales vendedores en todo el sitio]</li><li>[!UICONTROL Principales vendedores por categoría]</li><li>[!UICONTROL Principales vendedores por atributo de artículo]</li><li>[!UICONTROL Principales vendedores por atributo de perfil]</li><li>[!UICONTROL Métrica superior por Analytics]</li></ul> |
| [!UICONTROL Basado en elementos] | Haga recomendaciones basadas en la búsqueda de artículos similares a los que el usuario está viendo en este momento o ha visto recientemente. <ul><li>[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]</li><li>[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]</li><li>[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]</li><li>[!UICONTROL Elementos con atributos similares]</li></ul> |
| [!UICONTROL Basado en usuario] | Haga recomendaciones basadas en el comportamiento del usuario. <ul><li>[!UICONTROL Artículos vistos recientemente]</li><li>[!UICONTROL Recomendado para usted]</li></ul> |
| [!UICONTROL Criterios personalizados] | Cree recomendaciones basadas en un archivo personalizado que haya cargado. <ul><li>Algoritmo personalizado</li></ul> |

Cada criterio está definido en su propia pestaña. El tráfico se divide equitativamente en las distintas pruebas de criterios. Es decir, si tiene dos criterios, el tráfico se divide a partes iguales entre ellos. Si tiene dos criterios y dos diseños, el tráfico se divide equitativamente entre las cuatro combinaciones. También puede especificar el porcentaje de los visitantes del sitio que ven el contenido predeterminado, para su comparación. En ese caso, el porcentaje especificado de visitantes ve el contenido predeterminado y el resto se divide entre los criterios y las combinaciones de diseño.

Para obtener más información sobre cómo crear criterios y definir sus algoritmos y tipos de algoritmos, consulte [Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Los distintos algoritmos de recomendaciones se prestan a colocarse en diferentes tipos de páginas. Consulte las secciones siguientes para obtener más información sobre cada tipo de algoritmo y sus algoritmos disponibles.

## Basado en el carro {#cart-based}

El tipo de algoritmo [!UICONTROL Basado en el carro de compras] permite recomendar elementos según el contenido del carro de compras actual del visitante. Las claves de recomendación se proporcionan a través del [parámetro de mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} en valores separados por comas. Solo se tienen en cuenta los 10 primeros valores.

La lógica de recomendación basada en el carro de compras es similar al algoritmo basado en usuarios de &quot;[!UICONTROL Recomendado para ti]&quot; y a las &quot;[!UICONTROL Personas que vieron esto, compraron aquello]&quot; y &quot;[!UICONTROL Personas que compraron esto, compraron aquello]&quot;.

[!DNL Target] utiliza técnicas de filtrado colaborativas para determinar las similitudes de cada elemento en el carro de compras del visitante y, a continuación, combina estas similitudes de comportamiento en cada elemento para obtener una lista combinada.

[!DNL Target] también ofrece a los especialistas en mercadotecnia la opción de observar el comportamiento de los visitantes en una sola sesión o en varias:

* **[!UICONTROL Sesión única]**: según lo que hayan hecho otros visitantes en una sola sesión.

  Observar el comportamiento dentro de una sola sesión puede tener sentido cuando existe la sensación de que los productos &quot;van con&quot; los unos a los otros en función de un uso, una ocasión o un evento. Por ejemplo, un visitante está comprando una impresora y también podría necesitar tinta y papel. O bien, un visitante está comprando mantequilla de maní y también podría necesitar pan y gelatina.

* **[!UICONTROL En varias sesiones]**: según lo que hayan hecho otros visitantes en varias sesiones.

  Observar el comportamiento en varias sesiones puede tener sentido cuando existe la sensación de que los productos se &quot;acompañan&quot; mutuamente en función de las preferencias o los gustos de los visitantes. Por ejemplo, a un visitante le gusta Star Wars y puede que también le guste Indiana Jones, aunque el visitante no quiera necesariamente ver ambas películas en la misma sesión. O bien, a un visitante le gusta el juego de mesa &quot;Codenames&quot; y también le puede gustar el juego de mesa &quot;Avalon&quot;, incluso si el visitante no puede jugar ambos juegos simultáneamente.

[!DNL Target] realiza recomendaciones para cada visitante basadas en los elementos de su carro de compras actual, independientemente de si observa el comportamiento de los visitantes en una sola sesión o en varias.

Los siguientes algoritmos están disponibles con el tipo de algoritmo [!UICONTROL Basado en el carro de compras]:

### [!UICONTROL Las Personas Que Vieron Esto, También Vieron]

Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos que vieron las personas después de ver este. El producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite crear oportunidades de conversión adicionales mediante la recomendación de artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que ven bicicletas de carretera en el sitio también pueden ver cascos de bicicleta, kits de ciclismo, cerraduras, etc. Puede crear una recomendación utilizando esta lógica que sugiere que otros productos le ayudan a aumentar los ingresos.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

### [!UICONTROL Otras Personas Que Vieron Esto, También Compraron]

Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos que compraron otras personas después de ver este. El producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes que vieron el artículo compraron. Por ejemplo, si el visitante está viendo una caña de pescar, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de aparejos, zancudos y señuelos de pesca. A medida que los visitantes navegan por el sitio, les proporciona recomendaciones de compra adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

### [!UICONTROL Otras Personas Que Compraron Esto, También Compraron]

Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado.

Esta lógica devuelve otros productos que la gente compró después de comprar este. El producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra artículos que otros compradores también han comprado. Por ejemplo, si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y gemelos. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones adicionales.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de Recommendations:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

## [!UICONTROL Basado en popularidad]

El tipo de algoritmo [!UICONTROL Basado en la popularidad] le permite hacer recomendaciones basadas en la popularidad general de un elemento en su sitio o en la popularidad de los elementos dentro de la categoría, marca, género, etc. favoritos o más vistos de un usuario.

Los siguientes algoritmos están disponibles con el tipo de algoritmo [!UICONTROL Basado en popularidad]:

### [!UICONTROL Más visitados en todo el sitio] {#most-viewed}

La recomendación viene determinada por el artículo que se ha visto con mayor frecuencia. Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de producto
* 5 puntos por cada visualización subsiguiente
* Al final de la sesión, se dividen todos los valores por 2

Por ejemplo, ver la tabla de surf A y luego la B en una sesión resulta en A: 10, B: 5. Cuando finaliza la sesión, tiene A: 5, B: 2.5. Si ve los mismos elementos en la siguiente sesión, los valores cambian a A: 15 B: 7,5.

Utilice este algoritmo en páginas generales, como páginas de inicio o de destino y anuncios externos.

### [!UICONTROL Más visitados por categoría] {#most-viewed-category}

La recomendación está determinada por la categoría que recibió la mayor cantidad de actividad, usando el mismo método empleado con el “artículo más visitado”, excepto que se clasifican las categorías en lugar de los productos.

Se determina por el criterio de frecuencia y actualización que funciona de la siguiente manera:

* 10 puntos por primera visualización de categoría
* 5 puntos por cada visualización subsiguiente

Las categorías visitadas por primera vez reciben 10 puntos. Por las siguientes visitas a la misma categoría, se conceden 5 puntos. Con cada visita, la puntuación de las categorías antiguas que se vieron con anterioridad se reduce 1 punto.

Por ejemplo, ver la categoría A y luego la categoría B en una sesión resulta en A: 9, B: 10. Si ve los mismos elementos en la próxima sesión, los valores serán A: 20 B: 9.

Utilice este algoritmo en páginas generales, como páginas de inicio o de destino y anuncios externos.

Si selecciona el algoritmo Más visitados por categoría, puede seleccionar las siguientes claves de Recommendations:

* [!UICONTROL Categoría actual]
* [!UICONTROL Categoría favorita]

### [!UICONTROL Más visitados por atributo de artículo]

Recomienda elementos o medios similares a los elementos o medios más vistos del sitio.

Este algoritmo le permite seleccionar en qué atributo de artículo desea basar la recomendación, por ejemplo, &quot;Nombre&quot; o &quot;Marca&quot;.

A continuación, puede seleccionar qué atributos de perfil almacenados en el perfil del visitante coinciden, por ejemplo, &quot;Marca favorita&quot;, &quot;Último elemento añadido al carro de compras&quot; o &quot;Programa más visitado&quot;.

### [!UICONTROL Principales vendedores en todo el sitio] {#top-sellers}

Muestra los artículos incluidos en los pedidos más finalizados de la dirección. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido.

Este algoritmo le permite crear recomendaciones para los artículos más vendidos del sitio a fin de aumentar la conversión y los ingresos. Esta lógica es especialmente adecuada para los visitantes nuevos del sitio.

### [!UICONTROL Principales vendedores por categoría]

Muestra los artículos incluidos en los pedidos más finalizados por categoría. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido.

Este algoritmo le permite crear recomendaciones para los artículos más vendidos del sitio según la categoría, a fin de aumentar la conversión y los ingresos. Esta lógica es especialmente adecuada para los visitantes nuevos del sitio.

Si selecciona el algoritmo [!UICONTROL Más visitados por categoría], puede seleccionar las siguientes [!UICONTROL Claves de Recommendations]:

* [!UICONTROL Categoría actual]
* [!UICONTROL Categoría favorita]

### [!UICONTROL Principales vendedores por atributo de artículo]

Recomienda elementos o medios similares a los elementos o medios más comprados en el sitio.

Este algoritmo le permite seleccionar en qué atributo de artículo desea basar la recomendación, por ejemplo, &quot;Nombre&quot; o &quot;Marca&quot;.

A continuación, puede seleccionar qué atributos de perfil almacenados en el perfil del visitante coinciden, por ejemplo, &quot;Marca favorita&quot;, &quot;Último elemento añadido al carro de compras&quot; o &quot;Programa más visitado&quot;.

### [!UICONTROL Más visitados por atributo de perfil]

Recomienda los artículos más vistos agrupados por un atributo de perfil de visitante en lugar de por información de artículo, como hacen [!UICONTROL Más vistos por categoría] y [!UICONTROL Más vistos por atributo de artículo]. [!DNL Target] mantiene una lista clasificada separada por valor de atributo y, a la hora de envío, muestra a cada visitante la lista que coincide con su propio valor almacenado.

Este algoritmo depende de un script de perfil para rellenar el atributo, y el nombre del script debe comenzar con el prefijo `recsAttribute` para que [!DNL Target] lo almacene como `user.recsAttribute<Name>`. Puede escribir una secuencia de comandos para cualquier característica del visitante relevante para su caso de uso.

Obtenga más información acerca de cómo establecer atributos de perfil mediante scripts de perfil en [esta página](https://experienceleague.adobe.com/en/docs/target/using/audiences/visitor-profiles/profile-parameters).

Por ejemplo, un script denominado `recsAttributeRegion` que basa las recomendaciones en la región del visitante podría tener el siguiente aspecto:

```
var region = mbox.param('userRegion');
if (region) return region;
```

Una vez que el script se haya creado y activado, la entrada [!UICONTROL Region] correspondiente estará disponible en la lista desplegable de atributos de perfil de la ventana Crear criterios. Tenga en cuenta que el prefijo `recsAttribute` en sí no se muestra en la lista desplegable.

### [!UICONTROL Principales vendedores por atributo de perfil]

Recomienda los artículos más vendidos agrupados por un atributo de perfil de visitante en lugar de por información de artículo, como hacen [!UICONTROL Principales vendedores por categoría] y [!UICONTROL Principales vendedores por atributo de artículo]. [!DNL Target] mantiene una lista de los principales vendedores independiente por valor de atributo y, a la hora de envío, muestra a cada visitante la lista que coincide con su propio valor almacenado.

Al igual que con [!UICONTROL Más visitados por atributo de perfil], este algoritmo depende de un script de perfil para rellenar el atributo y el nombre del script debe comenzar con el prefijo `recsAttribute`, de modo que [!DNL Target] lo almacena como `user.recsAttribute<Name>`. Puede escribir una secuencia de comandos para cualquier característica del visitante relevante para su caso de uso. Obtenga más información acerca de cómo establecer atributos de perfil mediante scripts de perfil en [esta página](https://experienceleague.adobe.com/en/docs/target/using/audiences/visitor-profiles/profile-parameters).

Por ejemplo, un script de nombre `recsAttributeLoyaltyTier` que base las recomendaciones en el nivel de fidelidad del visitante podría tener este aspecto:

```
var tier = mbox.param('visitorLoyaltyTier');
if (tier) return tier;
```

Una vez que el script se haya creado y activado, la entrada [!UICONTROL Nivel de fidelidad] correspondiente estará disponible en el menú desplegable de atributos de perfil de la ventana Crear criterios. Tenga en cuenta que el prefijo `recsAttribute` en sí no se muestra en la lista desplegable.

### [!UICONTROL Métrica superior por Analytics]

Muestra la &quot;x superior&quot; donde *x* es una métrica [!DNL Analytics] arbitraria. Al usar datos de comportamiento de mboxes, puede usar [!UICONTROL Más vendidos] o [!UICONTROL Más visitados] (x = &quot;Vendidos&quot; o x = &quot;Vistos&quot;). Si está usando datos de comportamiento de [!DNL Adobe Analytics], podría usar x = &quot;Adiciones al carro de compras&quot; o alguna otra métrica de [!DNL Analytics].

## [!UICONTROL Basado en elementos]

El tipo de recomendación [!UICONTROL Basada en elementos] le permite hacer recomendaciones basadas en la búsqueda de artículos similares a un artículo que el usuario está viendo en este momento o que ha visto recientemente.

Los siguientes algoritmos están disponibles con el tipo de algoritmo [!UICONTROL Basado en elementos]:

### [!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello] {#viewed-viewed}

Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado.

Esta lógica devuelve otros productos que vieron las personas después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite crear oportunidades de conversión adicionales mediante la recomendación de artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo: los visitantes que ven bicicletas de carretera en el sitio también pueden ver cascos de bicicleta, kits de ciclismo, cerraduras, etc. Puede crear una recomendación utilizando esta lógica que sugiere que otros productos le ayudan a aumentar los ingresos.

Si selecciona este algoritmo, puede seleccionar las [!UICONTROL Claves de Recommendations] siguientes:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

### [!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello] {#viewed-bought}

Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados.

Esta lógica devuelve otros productos que compraron otras personas después de ver este; el producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de producto, por ejemplo, que muestra artículos que otros visitantes que vieron el artículo compraron. Por ejemplo, si el visitante está viendo una caña de pescar, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de aparejos, zancudos y señuelos de pesca. A medida que los visitantes navegan por el sitio, les proporciona recomendaciones de compra adicionales.

Si selecciona este algoritmo, puede seleccionar las [!UICONTROL Claves de Recommendations] siguientes:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

### [!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello] {#bought-bought}

Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado.

Esta lógica devuelve otros productos que la gente compró después de comprar este. El producto especificado no se incluye en el conjunto de resultados.

Esta lógica le permite aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestra artículos que otros compradores también han comprado. Por ejemplo, si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y gemelos. A medida que los visitantes revisan sus compras, usted les proporciona recomendaciones adicionales.

Si selecciona este algoritmo, puede seleccionar las [!UICONTROL Claves de Recommendations] siguientes:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

### [!UICONTROL Elementos con atributos similares] {#similar-attributes}

Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores.

Si selecciona [!UICONTROL Elementos con atributos similares] o [!UICONTROL Medios con atributos similares], tiene la opción de establecer reglas de similitud de contenido.

El uso de la similitud de contenido para generar recomendaciones es especialmente efectivo para nuevos elementos, que probablemente no aparezcan en las recomendaciones con [!UICONTROL Personas que vieron esto], [!UICONTROL Vieron aquello] y otra lógica basada en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Si selecciona este algoritmo, puede seleccionar las [!UICONTROL Claves de Recommendations] siguientes:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

Para obtener más información, consulte [Similitud de contenido](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL Basado en usuario]

El tipo de algoritmo [!UICONTROL Basado en el usuario] le permite hacer recomendaciones basadas en el comportamiento del usuario.

Los siguientes algoritmos están disponibles con el tipo de algoritmo [!UICONTROL Basado en el usuario]:

### [!UICONTROL Artículos vistos recientemente] {#recently-viewed}

Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño.

El algoritmo [!UICONTROL Elementos vistos recientemente] devuelve el resultado específico de un [entorno](/help/main/administrating-target/hosts.md) determinado. Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

>[!NOTE]
>
>No puede usar los criterios de [!UICONTROL Artículos vistos recientemente] para las recomendaciones de copia de seguridad.

[!UICONTROL Elementos vistos recientemente] o [!UICONTROL Medios vistos recientemente] se pueden filtrar para que solo se muestren los elementos con un atributo en particular.

* Los criterios [!UICONTROL Vistos recientemente] se pueden configurar, al igual que otros criterios de las recomendaciones.
* Puede usar [colecciones](/help/main/c-recommendations/c-products/collections.md), [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluidas las reglas especiales para Precio e Inventario) de la misma manera que cualquier otro criterio.

Los posibles casos de uso incluyen, una compañía multinacional con varios negocios puede tener un visitante que vea elementos en varias propiedades digitales. En este caso, se pueden limitar los elementos vistos recientemente para que solo se muestren en relación con la propiedad respectiva en la que se visualizaron. Esto evita que los elementos vistos recientemente se muestren en el sitio de otra propiedad digital.

Utilice este algoritmo en páginas generales, como páginas de inicio o de destino y anuncios externos.

>[!NOTE]
>
>[!UICONTROL Elementos vistos recientemente] respeta tanto la configuración global de exclusiones como la configuración de colección seleccionada para la actividad. Si un elemento queda excluido por una exclusión global o no está contenido en la colección seleccionada, no se muestra. Por lo tanto, cuando se usa un criterio de [!UICONTROL Artículos vistos recientemente], se debería usar la configuración &quot;Todas las colecciones&quot;.

### [!UICONTROL Recomendado para usted] {#recommended-for-you}

Recomienda artículos en función del historial de navegación, visualización y compra de cada visitante.

Este algoritmo le permite enviar contenido y experiencias personalizados tanto a los visitantes nuevos como a los que vuelven. La lista de recomendaciones se basa en la actividad más reciente del visitante y se actualiza durante la sesión; asimismo, se personaliza a medida que el usuario navega por el sitio.

Las vistas y las compras se utilizan para determinar los artículos recomendados. La clave de recomendación especificada (por ejemplo, [!UICONTROL Elemento actual]) se usa para aplicar los filtros de regla de inclusión que seleccione.

Por ejemplo, puede:

* Excluir elementos que no cumplan determinados criterios (productos agotados, artículos publicados hace más de 30 días, películas con clasificación R, etc.).
* Limitar los elementos incluidos a una sola categoría o a la categoría actual.

Si selecciona este algoritmo, puede seleccionar las siguientes claves de filtrado:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]

## Criterios personalizados {#custom}

El tipo de algoritmo [!UICONTROL Criterios personalizados] le permite hacer recomendaciones basadas en un archivo personalizado que haya cargado.

La recomendación está determinada por un elemento almacenado en el perfil de un visitante, que usa los atributos user.*x* o profile.*x*.

Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil.

Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación.

Puede realizar el filtrado en tiempo real sobre su propia salida de criterios personalizados. Por ejemplo, puede limitar sus artículos recomendados solo a aquellos de la categoría o marca favorita de un visitante. Esto le da la capacidad de combinar cálculos sin conexión con filtrado en tiempo real.

Esta funcionalidad significa que puede usar [!DNL Target] para agregar personalización además de sus recomendaciones calculadas sin conexión o listas personalizadas. Esto combina el poder de sus científicos e investigadores de datos con la entrega probada y comprobada de Adobe, el filtrado en tiempo de ejecución, las pruebas A/B, la segmentación, los informes, las integraciones y más.

Con la adición de reglas de inclusión en [!UICONTROL Criterios personalizados], convierte las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses de los visitantes.

* Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.
* Puede usar [colecciones](/help/main/c-recommendations/c-products/collections.md), [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluidas las reglas especiales para Precio e Inventario) de la misma manera que cualquier otro criterio.

Los posibles casos de uso incluyen:

* Desea recomendar películas de una lista personalizada, pero solo si el visitante no las ha visto.
* Desea ejecutar un algoritmo sin conexión y utilizar los resultados para impulsar las recomendaciones, pero debe asegurarse de que nunca se recomienden los artículos sin existencias.
* Desea incluir solo los elementos que pertenecen a la categoría favorita de este visitante.

## Claves de recomendación {#keys}

Las siguientes claves de recomendación están disponibles en la lista desplegable [!UICONTROL Clave de recomendación]:

### [!UICONTROL Elemento actual] {#current-item}

La recomendación está determinada por el artículo que el visitante está viendo en ese momento.

Las recomendaciones muestran otros artículos que pueden ser de interés para los visitantes interesados en el artículo especificado.

Si se selecciona está opción, el valor `entity.id` debe pasarse como parámetro en mbox de visualización.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares]
* [!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]
* [!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]
* [!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]

Usar la clave de recomendaciones [!UICONTROL Elemento actual] en el sitio en:

* Páginas con un solo elemento, como las páginas de productos.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### [!UICONTROL Último artículo comprado] {#last-purchased}

La recomendación está determinada por el último artículo que compró cada visitante único. Esto se captura automáticamente, por lo que no se deben pasar valores en la página.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares]
* [!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]
* [!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]
* [!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]

Usa la clave de recomendaciones [!UICONTROL Último artículo comprado] en tu sitio en:

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

#### Clave de recomendaciones personalizadas

Puede basar las recomendaciones en el valor de un atributo de perfil personalizado. Por ejemplo, supongamos que desea mostrar películas recomendadas basadas en la película que agregó un visitante recientemente a la cola.

1. Seleccione su atributo de perfil personalizado de la lista desplegable **[!UICONTROL Clave de recomendación]** (por ejemplo, &quot;[!UICONTROL Última visualización agregada a la lista de observación]&quot;).
1. A continuación, seleccione su **[!UICONTROL Lógica de recomendación]** (por ejemplo, &quot;[!UICONTROL Personas que vieron esto, Vieron aquello]&quot;).

Si el atributo de perfil personalizado no coincide directamente con un ID de entidad único, es necesario explicar cómo [!DNL Recommendations] desea que se produzca la coincidencia en una entidad. Por ejemplo, supongamos que desea mostrar los artículos más vendidos de la marca favorita de un visitante.

1. Seleccione su atributo de perfil personalizado de la lista desplegable **[!UICONTROL Clave de recomendación]** (por ejemplo, &quot;Marca favorita&quot;).

1. A continuación, seleccione la **[!UICONTROL Lógica de recomendación]** que desee usar con esta clave (por ejemplo, &quot;[!UICONTROL Principales vendedores]&quot;).

   Se muestra la opción [!UICONTROL Agrupar por valor único de].

1. Seleccione el atributo de entidad que coincida con la clave elegida. En este caso, &quot;[!UICONTROL Marca favorita]&quot; coincide con `entity.brand`.

   [!DNL Recommendations] genera ahora una lista &quot;[!UICONTROL Principales vendedores]&quot; para cada marca y muestra al visitante la lista &quot;[!UICONTROL Principales vendedores]&quot; adecuada en función del valor almacenado en el atributo de perfil [!UICONTROL Marca favorita] del visitante.

### [!UICONTROL Último artículo visitado] {#last-viewed}

La recomendación está determinada por el último artículo que vio cada visitante único. Esto se captura automáticamente, por lo que no se deben pasar valores en la página.

Se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares]
* [!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]
* [!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]
* [!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]

Usa la clave de recomendaciones [!UICONTROL Último artículo visto] en tu sitio en:

* La página inicial, la página Mi cuenta o anuncios externos.
* NO lo utilice en páginas de productos o en páginas importantes para las compras.

### [!UICONTROL Artículo más visitado] {#most-viewed-logic}

Muestra los elementos o medios que se ven con mayor frecuencia en el sitio.

Esta lógica le permite mostrar recomendaciones basadas en los artículos más vistos del sitio para aumentar las conversiones de otros artículos. Por ejemplo: un sitio de medios podría mostrar recomendaciones en su página de inicio para los vídeos más vistos a fin de animar a los visitantes a ver vídeos adicionales.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Elementos con atributos similares]
* [!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]
* [!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]
* [!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]

### [!UICONTROL Categoría actual] {#current-category}

La recomendación está determinada por la categoría de producto que el visitante está viendo en ese momento.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]

Usar la clave de recomendaciones [!UICONTROL Categoría actual] en el sitio en:

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### [!UICONTROL Categoría favorita] {#favorite-category}

La recomendación está determinada por la categoría de producto favorita del visitante.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

Esta clave de recomendación se puede utilizar con los siguientes algoritmos:

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]

Usar la clave de recomendaciones [!UICONTROL Categoría actual] en el sitio en:

* Páginas de una sola categoría.
* NO lo utilice en páginas de resultados de búsqueda nulos.

### [!UICONTROL Afinidad del sitio] {#site-affinity}

Recomienda elementos según la certeza de una relación entre artículos. Puede configurar este criterio con el regulador [!UICONTROL Reglas de inclusión] para determinar la cantidad de datos que se requiere antes de presentar una recomendación. Por ejemplo, si selecciona Muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.

Por ejemplo, si establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y son reemplazados por sus artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.

Por ejemplo, un retailer en línea puede recomendar elementos en visitas posteriores en las que un visitante haya mostrado interés durante sesiones anteriores. La actividad de cada sesión del visitante se captura para calcular una afinidad basada en un modelo de actualización y frecuencia. A medida que este visitante regresa a su sitio, la afinidad del sitio se utiliza para mostrar recomendaciones basadas en acciones pasadas en el sitio.

Es posible que algunos clientes con diferentes colecciones de productos y diversos comportamientos de sitio obtengan mejores resultados si establecen una afinidad de sitio débil.

Esta lógica se puede utilizar con las siguientes claves de recomendación:

* [!UICONTROL Elemento actual]
* [!UICONTROL Último artículo comprado]
* [!UICONTROL Último artículo visitado]
* [!UICONTROL Artículo más visitado]
