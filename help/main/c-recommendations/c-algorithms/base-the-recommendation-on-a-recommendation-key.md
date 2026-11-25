---
keywords: clave de recomendación;lógica de recomendación;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;artículo más visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visto;más visto;favorito;visto recientemente
description: Aprenda a utilizar recomendaciones basadas en claves que utilizan el contexto de comportamiento del visitante para mostrar resultados relevantes en actividades de [!UICONTROL Recommendations].
title: ¿Cómo baso la [!UICONTROL Recomendación] en una [!UICONTROL Clave de recomendación]?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
TQID: 'https://experienceleague.adobe.com/1gI3rMMf9s5ogc4BvBz4fMUqxed1Nqad0XoaR8SlU58'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '3740'
ht-degree: 12%
---
# Basar la recomendación en una clave de recomendación {#base-on-recommendation-key}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información acerca de los tipos de algoritmo, algoritmos y claves de recomendación disponibles para basar recomendaciones en actividades [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Las recomendaciones basadas en algoritmos utilizan el contexto del comportamiento de los visitantes para mostrar resultados relevantes en [!DNL Adobe Target] actividades [!DNL Recommendations]. Cada tipo de algoritmo ofrece su propio conjunto de algoritmos. Para obtener un resumen de los tipos de algoritmo y sus algoritmos, consulte [Introducción a los criterios](/help/main/c-recommendations/c-algorithms/algorithms.md#section_885B3BB1B43048A88A8926F6B76FC482).

Cada criterio está definido en su propia pestaña. El tráfico se divide a partes iguales en las pruebas de criterios: con dos criterios, el tráfico se divide a partes iguales entre ellos y, con dos criterios y dos diseños, el tráfico se divide a partes iguales entre las cuatro combinaciones. También se puede configurar un porcentaje de visitantes del sitio para que vean el contenido predeterminado, a modo de comparación. En ese caso, el porcentaje especificado de visitantes ve el contenido predeterminado y el resto se divide entre los criterios y las combinaciones de diseño.

Para obtener más información sobre cómo crear criterios y definir sus algoritmos y tipos de algoritmos, consulte [Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Los distintos algoritmos se adaptan a diferentes tipos de páginas. Las secciones siguientes describen cada tipo de algoritmo y sus algoritmos.

## Basado en el carro {#cart-based}

El tipo de algoritmo **[!UICONTROL Basado en el carro de compras]** recomienda artículos en función del contenido del carro de compras actual del visitante. Las claves de recomendación se proporcionan como valores separados por comas en el [parámetro de mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank}. Solo se tienen en cuenta los 10 primeros valores.

La lógica de recomendación basada en el carro de compras es similar al algoritmo basado en usuarios de &quot;**[!UICONTROL Recomendado para ti]**&quot; y a las &quot;**[!UICONTROL Personas que vieron esto, compraron aquello]**&quot; y &quot;**[!UICONTROL Personas que compraron esto, compraron aquello]**&quot;.

[!DNL Target] utiliza técnicas de filtrado colaborativas para determinar las similitudes de cada elemento en el carro de compras del visitante y, a continuación, combina las similitudes de comportamiento de todos los elementos en una lista combinada.

Los especialistas en marketing pueden elegir si [!DNL Target] observa el comportamiento de los visitantes en una sola sesión o en varias:

* **[!UICONTROL Sesión única]**: según lo que hayan hecho otros visitantes en una sola sesión.

  Una sola sesión se adapta a los productos que se &quot;acompañan&quot; entre sí en función de un uso, una ocasión o un evento. Por ejemplo, un visitante que compra una impresora también puede necesitar tinta y papel, y un visitante que compra mantequilla de maní también puede necesitar pan y gelatina.

* **[!UICONTROL En varias sesiones]**: según lo que hayan hecho otros visitantes en varias sesiones.

  Las sesiones múltiples se adaptan a productos que se &quot;acompañan&quot; mutuamente según las preferencias o los gustos de los visitantes. Por ejemplo, a un visitante al que le gusta Star Wars también le puede gustar Indiana Jones, aunque el visitante no quiera necesariamente ver ambas películas en la misma sesión. Del mismo modo, a un visitante que le guste el juego de mesa &quot;Codenames&quot; también le puede gustar el juego de mesa &quot;Avalon&quot;, incluso si el visitante no puede jugar ambos juegos simultáneamente.

[!DNL Target] realiza recomendaciones para cada visitante basadas en los elementos de su carro de compras actual, independientemente de si el comportamiento del visitante se considera dentro de una sola sesión o en varias.

Los siguientes algoritmos están disponibles con el tipo de algoritmo **[!UICONTROL Basado en el carro de compras]**:

| Algoritmo | Cómo funciona | Cuándo usar | Claves de recomendación |
| --- | --- | --- | --- |
| **[!UICONTROL Las Personas Que Vieron Esto, También Vieron]** | Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Devuelve otros productos que vieron otras personas después de ver este. El producto especificado no se incluye en el conjunto de resultados. | Cree oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo, los visitantes que ven bicicletas de carretera en el sitio también pueden ver cascos de bicicleta, kits de ciclismo, cerraduras, etc., por lo que una recomendación puede sugerir otros productos que ayuden a aumentar los ingresos. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |
| **[!UICONTROL Otras Personas Que Vieron Esto, También Compraron]** | Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Devuelve otros productos que compraron otras personas después de ver este. El producto especificado no se incluye en el conjunto de resultados. | Aumente las oportunidades de ventas cruzadas mostrando una recomendación en una página de producto, por ejemplo, que muestre artículos que otros visitantes que vieron el artículo compraron. Si el visitante está viendo una caña de pescar, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de aparejos, zancudos y señuelos de pesca. A medida que los visitantes navegan por el sitio, reciben recomendaciones de compra adicionales. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |
| **[!UICONTROL Otras Personas Que Compraron Esto, También Compraron]** | Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado. Devuelve otros productos que compraron otras personas después de comprar este. El producto especificado no se incluye en el conjunto de resultados. | Aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestre artículos que otros compradores también han comprado. Si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y gemelos. A medida que los visitantes revisan sus compras, reciben recomendaciones adicionales. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |

## [!UICONTROL Basado en popularidad]

El tipo de algoritmo **[!UICONTROL Basado en popularidad]** recomienda los elementos según su popularidad general en todo el sitio o según su popularidad en la categoría, marca, género, etc. favoritos o más vistos del usuario.

Los siguientes algoritmos están disponibles con el tipo de algoritmo **[!UICONTROL Basado en popularidad]**:

| Algoritmo | Cómo funciona | Cuándo usar | Claves de recomendación |
| --- | --- | --- | --- |
| **[!UICONTROL Más visitados en todo el sitio]** | La recomendación está determinada por el artículo que se ha visto con mayor frecuencia, según los criterios de actualización/frecuencia. Ver [Los más vistos en la puntuación del sitio](#most-viewed). | Páginas generales, como páginas principales o de aterrizaje y anuncios externos. | |
| **[!UICONTROL Más visitados por categoría]** | La recomendación está determinada por la categoría que recibió la mayor cantidad de actividad, usando el mismo método que para el artículo más visitado, excepto que se clasifican las categorías en lugar de los productos. Ver [Más vistos por puntuación de categoría](#most-viewed-category). | Páginas generales, como páginas principales o de aterrizaje y anuncios externos. | **[!UICONTROL Categoría actual]**, **[!UICONTROL Categoría favorita]** |
| **[!UICONTROL Más visitados por atributo de artículo]** | Recomienda elementos o medios similares a los elementos o medios más vistos del sitio. Se selecciona el atributo del elemento en el que se basa la recomendación, por ejemplo, &quot;Nombre&quot; o &quot;Marca&quot;. A continuación, se seleccionan los atributos de perfil almacenados en el perfil del visitante para que coincidan, como &quot;Marca favorita&quot;, &quot;Último elemento añadido al carro de compras&quot; o &quot;Programa más visitado&quot;. | | |
| **[!UICONTROL Más visitados por atributo de perfil]** | Recomienda los artículos más vistos agrupados por un atributo de perfil de visitante en lugar de por información de artículo, como hacen **[!UICONTROL Más vistos por categoría]** y **[!UICONTROL Más vistos por atributo de artículo]**. [!DNL Target] mantiene una lista clasificada separada por valor de atributo y, a la hora de envío, muestra a cada visitante la lista que coincide con su propio valor almacenado. Consulte [Algoritmos de atributo de perfil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Principales vendedores en todo el sitio]** | Muestra los artículos incluidos en los pedidos más finalizados de la dirección. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido. | Cree recomendaciones sobre los artículos más vendidos del sitio para aumentar la conversión y los ingresos. Esta lógica es adecuada para los visitantes que acceden al sitio por primera vez. | |
| **[!UICONTROL Principales vendedores por categoría]** | Muestra los artículos incluidos en los pedidos más finalizados por categoría. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido. | Cree recomendaciones para los artículos más vendidos del sitio según la categoría para aumentar la conversión y los ingresos. Esta lógica es adecuada para los visitantes que acceden al sitio por primera vez. | **[!UICONTROL Categoría actual]**, **[!UICONTROL Categoría favorita]** |
| **[!UICONTROL Principales vendedores por atributo de artículo]** | Recomienda artículos o medios similares a los artículos o medios más comprados en el sitio. Se selecciona el atributo del elemento en el que se basa la recomendación, por ejemplo, &quot;Nombre&quot; o &quot;Marca&quot;. A continuación, se seleccionan los atributos de perfil almacenados en el perfil del visitante para que coincidan, como &quot;Marca favorita&quot;, &quot;Último elemento añadido al carro de compras&quot; o &quot;Programa más visitado&quot;. | | |
| **[!UICONTROL Principales vendedores por atributo de perfil]** | Recomienda los artículos más vendidos agrupados por un atributo de perfil de visitante en lugar de por información de artículo, como hacen **[!UICONTROL Principales vendedores por categoría]** y **[!UICONTROL Principales vendedores por atributo de artículo]**. [!DNL Target] mantiene una lista de los principales vendedores independiente por valor de atributo y, a la hora de envío, muestra a cada visitante la lista que coincide con su propio valor almacenado. Consulte [Algoritmos de atributo de perfil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Métrica superior por Analytics]** | Muestra la &quot;x superior&quot; donde *x* es una métrica [!DNL Analytics] arbitraria. Al usar datos de comportamiento de mboxes, se pueden usar **[!UICONTROL Más vendidos]** o **[!UICONTROL Más visitados]** (x = &quot;Vendidos&quot; o x = &quot;Vistos&quot;). Cuando se usan datos de comportamiento de [!DNL Adobe Analytics], se puede usar x = &quot;Adiciones al carro de compras&quot; u otra métrica de [!DNL Analytics]. | | |

### Puntuación de [!UICONTROL Más visitados en todo el sitio] {#most-viewed}

La recomendación es el artículo que se ha visto con mayor frecuencia, determinado por criterios de actualización/frecuencia de la siguiente manera:

* 10 puntos por primera visualización de producto
* 5 puntos por cada visualización subsiguiente
* Al final de una sesión, se dividen todos los valores entre 2

Por ejemplo, ver la tabla de surf A y luego la B en una sesión resulta en A: 10, B: 5. Cuando finaliza la sesión, el resultado es A: 5, B: 2.5. Si se ven los mismos elementos en la siguiente sesión, los valores cambian a A: 15, B: 7,5.

### Puntuación [!UICONTROL más vista por categoría] {#most-viewed-category}

La recomendación es la categoría que ha recibido la mayor cantidad de actividad. Utiliza el mismo método que el &quot;artículo más visitado&quot;, excepto que se clasifican las categorías en lugar de los productos, con los criterios de actualización/frecuencia siguientes:

* 10 puntos por primera visualización de categoría
* 5 puntos por cada visualización subsiguiente

Con cada visita, la puntuación de cada categoría no actual que se ha visto antes se reduce en 1.

Por ejemplo, ver la categoría A y luego la categoría B en una sesión resulta en A: 9, B: 10. Si se ven los mismos elementos en la siguiente sesión, los valores cambian a A: 20, B: 9.

### Algoritmos de atributos de perfil {#profile-attribute-algorithms}

>[!CONTEXTUALHELP]
>id="target_recommendations_profile_attribute"
>title="Atributo del perfil"
>abstract="Puede crear un atributo de perfil mediante los scripts de perfil. Una vez creado y activado un script de perfil, su atributo de perfil correspondiente se puede utilizar con este algoritmo."

**[!UICONTROL Los más visitados por atributo de perfil]** y **[!UICONTROL los más vendidos por atributo de perfil]** dependen de un script de perfil para rellenar el atributo. El nombre del script debe comenzar con el prefijo `recsAttribute` para que [!DNL Target] lo almacene como `user.recsAttribute<Name>`. Se puede escribir una secuencia de comandos para cualquier característica del visitante que sea relevante para el caso de uso. Para obtener más información acerca de cómo establecer atributos de perfil con scripts de perfil, vea [Parámetros de perfil](https://experienceleague.adobe.com/es/docs/target/using/audiences/visitor-profiles/profile-parameters).

Por ejemplo, el siguiente script, denominado `recsAttributeRegion`, basa las recomendaciones en la región del visitante:

```
var region = mbox.param('userRegion');
if (region) return region;
```

Del mismo modo, el siguiente script, denominado `recsAttributeLoyaltyTier`, basa las recomendaciones en el nivel de lealtad del visitante:

```
var tier = mbox.param('visitorLoyaltyTier');
if (tier) return tier;
```

Una vez que el script se haya creado y activado, la entrada **[!UICONTROL Region]** o **[!UICONTROL Loyalty Tier]** correspondiente estará disponible en el menú desplegable de atributos de perfil de la ventana Crear criterios. El prefijo `recsAttribute` en sí no se muestra en la lista desplegable.

## [!UICONTROL Basado en elementos]

El tipo de algoritmo **[!UICONTROL Basado en elementos]** recomienda elementos que son similares a un elemento que el usuario está viendo en este momento o que ha visto recientemente.

Los siguientes algoritmos están disponibles con el tipo de algoritmo **[!UICONTROL Basado en elementos]**:

| Algoritmo | Cómo funciona | Cuándo usar | Claves de recomendación |
| --- | --- | --- | --- |
| **[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]** | Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Devuelve otros productos que vieron otras personas después de ver este. El producto especificado no se incluye en el conjunto de resultados. | Cree oportunidades de conversión adicionales recomendando artículos que otros visitantes que vieron un artículo también vieron. Por ejemplo, los visitantes que ven bicicletas de carretera en el sitio también pueden ver cascos de bicicleta, kits de ciclismo, cerraduras, etc., por lo que una recomendación puede sugerir otros productos que ayuden a aumentar los ingresos. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |
| **[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]** | Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Devuelve otros productos que compraron otras personas después de ver este. El producto especificado no se incluye en el conjunto de resultados. | Aumente las oportunidades de ventas cruzadas mostrando una recomendación en una página de producto, por ejemplo, que muestre artículos que otros visitantes que vieron el artículo compraron. Si el visitante está viendo una caña de pescar, la recomendación podría mostrar artículos adicionales que otros visitantes compraron, como cajas de aparejos, zancudos y señuelos de pesca. A medida que los visitantes navegan por el sitio, reciben recomendaciones de compra adicionales. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |
| **[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]** | Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado. Devuelve otros productos que compraron otras personas después de comprar este. El producto especificado no se incluye en el conjunto de resultados. | Aumentar las oportunidades de ventas cruzadas mostrando una recomendación en una página de resumen del carro de compras, por ejemplo, que muestre artículos que otros compradores también han comprado. Si el visitante está comprando un traje, la recomendación podría mostrar artículos adicionales que otros visitantes compraron junto con el traje, como corbatas, zapatos de vestir y gemelos. A medida que los visitantes revisan sus compras, reciben recomendaciones adicionales. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |
| **[!UICONTROL Elementos con atributos similares]** | Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores. Si se selecciona **[!UICONTROL Elementos con atributos similares]** o **[!UICONTROL Medios con atributos similares]**, se pueden establecer reglas de similitud de contenido. Para obtener más información, consulte [Similitud de contenido](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity). | La similitud de contenido es efectiva para nuevos elementos, que probablemente no aparezcan en las recomendaciones usando **[!UICONTROL Personas que vieron esto]**, **[!UICONTROL Vieron aquello]** y otra lógica basada en el comportamiento anterior. También puede generar recomendaciones para nuevos visitantes, que no tengan compras u otros datos históricos en el pasado. | **[!UICONTROL Artículo Actual]**, **[!UICONTROL Último Artículo Comprado]**, **[!UICONTROL Último Artículo Visto]**, **[!UICONTROL Artículo Más Visto]** |

## [!UICONTROL Basado en usuario]

El tipo de algoritmo **[!UICONTROL Basado en el usuario]** recomienda elementos según el comportamiento del usuario.

Los siguientes algoritmos están disponibles con el tipo de algoritmo **[!UICONTROL Basado en el usuario]**:

| Algoritmo | Cómo funciona | Cuándo usar | Claves de recomendación |
| --- | --- | --- | --- |
| **[!UICONTROL Artículos vistos recientemente]** | Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño. Ver [detalles de artículos vistos recientemente](#recently-viewed). | Páginas generales, como páginas principales o de aterrizaje y anuncios externos. | |
| **[!UICONTROL Recomendado para usted]** | Recomienda artículos en función del historial de navegación, visualización y compra de cada visitante. Las vistas y las compras se utilizan para determinar los artículos recomendados. La lista de recomendaciones se basa en la actividad más reciente del visitante, se actualiza en la sesión y se personaliza a medida que el usuario navega por el sitio. | Ofrezca contenido y experiencias personalizados tanto a los visitantes nuevos como a los que regresan. La clave de recomendación especificada (por ejemplo, **[!UICONTROL Elemento actual]**) se usa para aplicar cualquier filtro de regla de inclusión seleccionado, por ejemplo, para excluir elementos que no cumplen determinados criterios (productos agotados, artículos publicados hace más de 30 días, películas con clasificación R, etc.), o para limitar los elementos incluidos a una sola categoría o a la categoría actual. | Claves de filtrado: **[!UICONTROL Artículo actual]**, **[!UICONTROL Último artículo comprado]**, **[!UICONTROL Último artículo visto]**, **[!UICONTROL Artículo más visitado]** |

### [!UICONTROL Detalles de artículos vistos recientemente] {#recently-viewed}

El algoritmo **[!UICONTROL Elementos vistos recientemente]** devuelve resultados específicos de un [entorno](/help/main/administrating-target/hosts.md) determinado. Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

Los criterios de **[!UICONTROL Elementos vistos recientemente]** no se pueden usar para las recomendaciones de copia de seguridad.

**[!UICONTROL Elementos vistos recientemente]** o **[!UICONTROL Medios vistos recientemente]** se pueden filtrar para que solo se muestren los elementos con un atributo en particular.

* Los criterios **[!UICONTROL Vistos recientemente]** se pueden configurar, al igual que otros criterios de las recomendaciones.
* Las [colecciones](/help/main/c-recommendations/c-products/collections.md), [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluidas las reglas especiales para Precio e Inventario) se pueden usar de la misma manera que con cualquier otro criterio.

Un caso de uso es una compañía multinacional con varios negocios, en la que un visitante puede ver elementos en varias propiedades digitales. Los artículos vistos recientemente se pueden limitar a la propiedad donde se vieron, de modo que no se muestren en el sitio de otra propiedad.

>[!NOTE]
>
>**[!UICONTROL Elementos vistos recientemente]** respeta tanto la configuración de exclusiones globales como la configuración de colección seleccionada para la actividad. Si un elemento queda excluido por una exclusión global o no está contenido en la colección seleccionada, no se muestra. Por lo tanto, cuando se usa un criterio de **[!UICONTROL Artículos vistos recientemente]**, se debería usar la configuración &quot;Todas las colecciones&quot;.

## Criterios personalizados {#custom}

El tipo de algoritmo **[!UICONTROL Criterios personalizados]** recomienda los elementos en función de un archivo personalizado cargado.

La recomendación está determinada por un elemento almacenado en el perfil de un visitante, con atributos user.*x* o profile.*x*. Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil. Cuando las recomendaciones se basan en atributos personalizados, primero se debe seleccionar el atributo personalizado y, a continuación, el tipo de recomendación.

El filtrado en tiempo real se puede aplicar a la salida de los criterios personalizados. Por ejemplo, los artículos recomendados pueden limitarse a los de la categoría o marca favorita de un visitante. Esto combina los cálculos sin conexión con el filtrado en tiempo real, de modo que [!DNL Target] pueda agregar personalización a recomendaciones calculadas sin conexión o listas personalizadas. La ciencia de datos y la investigación de la organización se combinan entonces con la entrega, el filtrado en tiempo de ejecución, las pruebas A/B, la segmentación, la creación de informes y las integraciones de Adobe.

Las reglas de inclusión de **[!UICONTROL criterios personalizados]** convierten las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses del visitante.

* Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.
* Las [colecciones](/help/main/c-recommendations/c-products/collections.md), [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluidas las reglas especiales para Precio e Inventario) se pueden usar de la misma manera que con cualquier otro criterio.

Los posibles casos de uso incluyen:

* Recomendar películas a partir de una lista personalizada, pero solo si el visitante aún no las ha visto.
* Ejecute un algoritmo sin conexión y utilice los resultados para potenciar las recomendaciones, asegurándose al mismo tiempo de que nunca se recomienden los artículos sin existencias.
* Incluir solo los artículos de la categoría favorita de este visitante.

## Claves de recomendación {#keys}

Las siguientes claves de recomendación están disponibles en la lista desplegable **[!UICONTROL Clave de recomendación]**:

| Clave | Cómo se determina | Qué se debe pasar | Usar en | No usar en | Algoritmos |
| --- | --- | --- | --- | --- | --- |
| **[!UICONTROL Elemento actual]** | El artículo que el visitante está viendo en este momento. Las recomendaciones muestran otros artículos que pueden ser de interés para los visitantes interesados en el artículo especificado. | El valor `entity.id` debe pasarse como parámetro en el mbox de visualización. | Páginas con un solo elemento, como las páginas de productos. | Páginas de resultados de búsqueda nulas. | **[!UICONTROL Elementos con atributos similares]**, **[!UICONTROL Las personas que vieron esto, vieron aquello]**, **[!UICONTROL Las personas que vieron esto, compraron aquello]**, **[!UICONTROL Las personas que compraron esto, compraron aquello]** |
| **[!UICONTROL Último artículo comprado]** | El último artículo que compró cada visitante único. | Nada. Esto se captura automáticamente. | La página inicial, la página Mi cuenta o anuncios externos. | Páginas de productos o páginas relevantes para las compras. | **[!UICONTROL Elementos con atributos similares]**, **[!UICONTROL Las personas que vieron esto, vieron aquello]**, **[!UICONTROL Las personas que vieron esto, compraron aquello]**, **[!UICONTROL Las personas que compraron esto, compraron aquello]** |
| **[!UICONTROL Último artículo visitado]** | El último elemento que vio cada visitante único. | Nada. Esto se captura automáticamente. | La página inicial, la página Mi cuenta o anuncios externos. | Páginas de productos o páginas relevantes para las compras. | **[!UICONTROL Elementos con atributos similares]**, **[!UICONTROL Las personas que vieron esto, vieron aquello]**, **[!UICONTROL Las personas que vieron esto, compraron aquello]**, **[!UICONTROL Las personas que compraron esto, compraron aquello]** |
| **[!UICONTROL Artículo más visitado]** | Los elementos o medios que se ven con mayor frecuencia en el sitio. Esta lógica muestra recomendaciones basadas en los artículos más vistos para aumentar las conversiones de otros artículos. Por ejemplo: un sitio de medios podría mostrar recomendaciones en su página de inicio para los vídeos más vistos a fin de animar a los visitantes a ver vídeos adicionales. | | | | **[!UICONTROL Elementos con atributos similares]**, **[!UICONTROL Las personas que vieron esto, vieron aquello]**, **[!UICONTROL Las personas que vieron esto, compraron aquello]**, **[!UICONTROL Las personas que compraron esto, compraron aquello]** |
| **[!UICONTROL Categoría actual]** | La categoría de producto que el visitante está viendo en este momento. Recommendations muestra los elementos en la categoría del producto especificada. | El valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización. | Páginas de una sola categoría. | Páginas de resultados de búsqueda nulas. | **[!UICONTROL Principales vendedores]**, **[!UICONTROL Más visitados]** |
| **[!UICONTROL Categoría favorita]** | La categoría de producto favorita del visitante. Recommendations muestra los elementos en la categoría del producto especificada. | El valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización. | Páginas de una sola categoría. | Páginas de resultados de búsqueda nulas. | **[!UICONTROL Principales vendedores]**, **[!UICONTROL Más visitados]** |

### Clave de recomendación personalizada

Las recomendaciones pueden basarse en el valor de un atributo de perfil personalizado. Por ejemplo, las películas recomendadas se pueden mostrar en función de la película que agregó un visitante recientemente a la cola.

1. Seleccione el atributo de perfil personalizado de la lista desplegable **[!UICONTROL Clave de recomendación]** (por ejemplo, &quot;**[!UICONTROL Última visualización agregada a la lista de observación]**&quot;).

1. Seleccione la **[!UICONTROL Lógica de recomendación]** (por ejemplo, &quot;**[!UICONTROL Personas que vieron esto, Vieron aquello]**&quot;).

Si el atributo de perfil personalizado no coincide directamente con un ID de entidad único, especifique cómo coincide [!DNL Recommendations] con una entidad. Por ejemplo, para mostrar los artículos más vendidos de la marca favorita de un visitante:

1. Seleccione el atributo de perfil personalizado de la lista desplegable **[!UICONTROL Clave de recomendación]** (por ejemplo, &quot;Marca favorita&quot;).

1. Seleccione la **[!UICONTROL Lógica de recomendación]** que se usará con esta clave (por ejemplo, &quot;**[!UICONTROL Principales vendedores]**&quot;).

   Se muestra la opción **[!UICONTROL Agrupar por valor único de]**.

1. Seleccione el atributo de entidad que coincida con la clave elegida. En este caso &quot;**[!UICONTROL Marca favorita]**&quot; coincide con `entity.brand`.

   [!DNL Recommendations] genera ahora una lista &quot;**[!UICONTROL Principales vendedores]**&quot; para cada marca y muestra al visitante la lista &quot;**[!UICONTROL Principales vendedores]**&quot; adecuada en función del valor almacenado en el atributo de perfil **[!UICONTROL Marca favorita]** del visitante.

### [!UICONTROL Afinidad del sitio] {#site-affinity}

Recomienda elementos según la certeza de una relación entre artículos. Estos criterios se pueden configurar para establecer la cantidad de datos que se requiere antes de mostrar una recomendación mediante el control deslizante **[!UICONTROL Reglas de inclusión]**. Por ejemplo, cuando se selecciona muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.

Por ejemplo, si se establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y se sustituyen por los artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.

Otro ejemplo: un retailer en línea puede recomendar elementos en visitas posteriores en las que un visitante ha mostrado interés durante sesiones anteriores. La actividad de cada sesión del visitante se captura para calcular una afinidad basada en un modelo de actualización y frecuencia. A medida que el visitante regresa al sitio, la afinidad del sitio se utiliza para mostrar recomendaciones basadas en acciones pasadas en el sitio.

Una afinidad de sitio débil puede proporcionar los mejores resultados a los clientes con diversas colecciones de productos y diversos comportamientos del sitio.

Esta lógica se puede usar con las siguientes claves de recomendación: **[!UICONTROL Artículo actual]**, **[!UICONTROL Último artículo comprado]**, **[!UICONTROL Último artículo visto]**, **[!UICONTROL Artículo más visitado]**.
