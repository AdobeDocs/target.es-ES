---
keywords: Recommendations;introducción;seminario web;demostración
description: Obtenga información acerca de las actividades de Recommendations en Adobe [!DNL Target] que muestran automáticamente contenido que podría interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos.
title: ¿Qué son las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
TQID: 'https://experienceleague.adobe.com/6jmXI9CsdCnyyQrQXKzq5WF8OQPQSCbE2Zb8AnpUvks'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 4f38c80880eedd9b966cdb2f178f408bb529b60c
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 9%
---
# Introducción a Recommendations {#introduction-to-recommendations}

>[!BEGINSHADEBOX]

**En esta página:** aprenda cómo las actividades de [!DNL Recommendations] en [!DNL Adobe Target] muestran productos o contenido relevantes a los visitantes, y cómo planificar y generar una implementación y actividad de [!DNL Recommendations].

>[!ENDSHADEBOX]

Esta página se basa en el seminario web *Introducción a Recommendations*. Una actividad de [!DNL Recommendations] muestra automáticamente productos o contenido que podría interesar a los clientes optimizando las sugerencias en tiempo real en función de las visitas anteriores. La página también describe cómo generar una actividad [!DNL Recommendations] en la interfaz de usuario de [!DNL Target].

## Primeros pasos

Los clientes esperan cada vez más recomendaciones y las utilizan como punto de partida para explorar otras opciones disponibles. Casi todos han comprado un producto que vieron por primera vez en una recomendación, ya sea en una tienda o en una propiedad digital.

![Recomendación que muestra accesorios que comúnmente se compran con un nuevo teléfono, incluidas estaciones de carga, estuches y auriculares.](/help/main/c-recommendations/assets/intro-1.png)

La forma en que la gente consume medios y contenido está cada vez más impulsada por recomendaciones personalizadas, y marcas digitales como Netflix, Spotify y YouTube inician la experiencia del cliente con recomendaciones. Dado que hay más alternativas que nunca, es fundamental identificar el contenido más relevante para un cliente en el momento de la interacción.

Los especialistas en marketing utilizan [!DNL Adobe Target] para impulsar experiencias personalizadas en una amplia variedad de industrias, tipos de clientes y canales. En la tabla siguiente se muestran algunos ejemplos de cómo los clientes utilizan [!DNL Target] para ofrecer recomendaciones personalizadas.

| Caso de uso | Ejemplo |
|---|---|
| Publicación | Los editores web utilizan [!DNL Target Recommendations] para recomendar artículos a los visitantes del sitio y aumentar la participación. |
| Tutoriales en vídeo | [!DNL Adobe Creative Cloud] usa [!DNL Target] para recomendar tutoriales de vídeo a usuarios de Photoshop en la aplicación de Photoshop. |
| Juegos | Las empresas de juegos usan [!DNL Target] para recomendar juegos y contenido a los usuarios de sus consolas. |
| Ventas B2B | Las empresas entre empresas utilizan [!DNL Target] para recomendar vídeos, documentos técnicos y anuncios de blogs a posibles clientes B2B, entregar descargas y proporcionar ayuda a los clientes existentes. |
| Viajes | Un vendedor de viajes alemán usa [!DNL Target] para recomendar hoteles (entre otras cosas) a los viajeros. Para obtener más información, consulte [Adobe Summit session](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608){target=_blank}. |
| Comercial | Un retailer líder B2B usa [!DNL Target] para recomendar categorías y productos principales para los visitantes de retorno en el explorador y en su aplicación móvil. |

## Elementos de buenas recomendaciones

Las mejores recomendaciones son relevantes y personalizadas. Tres elementos impulsan la relevancia y la personalización:

* **Controles de experto en marketing** para aumentar la relevancia de los elementos recomendados. Los especialistas en marketing saben qué atributos de sus productos o contenido debe tener en cuenta un modelo de recomendaciones. Por ejemplo, en un sitio de vídeo, los usuarios pueden estar interesados en películas del mismo director, pero probablemente no en películas del mismo estudio. [!DNL Target] proporciona controles para mejorar los algoritmos con este conocimiento del dominio.
* **Modelos sofisticados** para dar sentido a los millones de elementos de catálogo y a los eventos de interacción. [!DNL Target] tiene capacidades de aprendizaje automático creadas durante más de una década de experiencia y administra miles de millones de recomendaciones por año.
* **Contexto de usuario** para garantizar que las recomendaciones sean oportunas y relevantes. Por ejemplo, las recomendaciones no deben incluir el vídeo que alguien acaba de ver ni la camiseta que alguien acaba de agregar al carro de compras. El perfil de usuario [!DNL Target] se puede usar en las recomendaciones para garantizar la personalización.

## Implementación de Recommendations de [!DNL Target]

Comience con una estrategia que defina los siguientes puntos:

* **Elementos para recomendar**: Productos, vídeos o contenido.
* **Ubicaciones para recomendaciones**: Los canales (web, móvil, en tienda, un quiosco, etc.), las partes del recorrido del cliente y las páginas del sitio que contienen recomendaciones.
* **Medición de éxito**: Cómo determinar si las recomendaciones son exitosas, por ejemplo, comparando una experiencia sin recomendaciones con una experiencia con recomendaciones, o comparando dos tipos diferentes de recomendaciones. Algunas métricas, como el impacto en el valor de duración del cliente, son difíciles de medir directamente, por lo que una métrica más concreta suele ser más fácil de usar, como los ingresos por visita, el valor de pedido promedio o el número de clics. En algunos casos, el objetivo es minimizar una métrica, por ejemplo, el número de llamadas de asistencia.

Una vez definida la estrategia, la implementación de [!DNL Target Recommendations] implica tres pasos amplios:

![Ilustración que muestra los tres pasos de una implementación de recomendaciones: enseñe a Target sobre su contenido o productos, capture el comportamiento del usuario y obtenga recomendaciones con el contexto correcto.](assets/intro-6.png)

### Enseñe a [!DNL Target] sobre su contenido o productos

Al comenzar con [!DNL Recommendations], pasa información sobre todos los elementos que desea recomendar.

![Ilustración que muestra cómo enseñar a Target sobre su contenido o productos: fuentes en formato CSV o fuente de Google, la capa de datos con Target, la API y la integración de Analytics.](assets/intro-7.png)

El método más sencillo y usado es enviar un archivo CSV diaria o semanalmente desde un sistema de administración de la información de productos o desde un sistema de administración de contenido. Otras opciones son pasar información sobre la capa de datos desde la página mediante la biblioteca de JavaScript [!DNL Adobe Target], usar las API para pasar información directamente desde el sistema de origen o usar la integración [!DNL Adobe Analytics] si ya está pasando datos del catálogo a [!DNL Analytics]. Puede utilizar varias opciones juntas, por ejemplo, al pasar la mayoría de los datos diariamente a través de un archivo CSV y las actualizaciones de inventario con más frecuencia a través de una API. El departamento de TI suele participar en la configuración de este paso.

Sea el que sea el método que elija, incluya metadatos sobre cada elemento en tres categorías:

* **Datos que desea mostrar al usuario que recibe la recomendación.** Por ejemplo, el nombre de la película y una URL de imagen de miniatura.
* **Datos que son útiles para aplicar controles de mercadotecnia y comercialización.** Por ejemplo, la clasificación de la película, para que no recomiende las de mayores de 17 años.
* **Datos que son útiles para determinar la similitud de elementos con otros elementos.** Por ejemplo, el género de la película o los actores que salen en ella.

### Capturar el comportamiento del usuario

![Ilustración que muestra cómo capturar el comportamiento del usuario: las vistas y los clics conducen a compras, conversiones, descargas, suscripciones y reproducciones, seguidos con Target, Analytics o la API.](assets/intro-9.png)

Agregue etiquetas o use la implementación de [!DNL Analytics] existente para que [!DNL Target] tenga en cuenta los elementos que los usuarios ven y compran. Si la compra no es relevante para su contexto, realice un seguimiento de un tipo diferente de evento de conversión, por ejemplo, descargar un PDF, completar una encuesta, suscribirse a una newsletter o ver un vídeo.

Si ya usa [!DNL Target] para ejecutar actividades de prueba A/B en el sitio, es posible que ya haya completado este paso. Si ya usa [!DNL Adobe Analytics] para informar sobre las visitas al sitio y el comportamiento de conversión, puede usar [!DNL Analytics] como fuente de datos de comportamiento. De lo contrario, la opción más sencilla es configurarlo con un administrador de etiquetas como las etiquetas en [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=es){target=_blank}. Las interacciones sin conexión o en la aplicación también se pueden enviar a [!DNL Target] mediante la API en tiempo real.

### Obtener recomendaciones con el contexto correcto

![Ilustración que muestra cómo obtener recomendaciones con el contexto correcto: se pasan a Target el producto visualizado actual, la categoría del producto actual, la categoría favorita del usuario, la marca favorita del usuario y el nivel de lealtad del usuario.](assets/intro-10.png)

Además del comportamiento del usuario en suma, [!DNL Target] necesita el contexto específico donde se muestran las recomendaciones, que incluye información sobre la página y perfil de usuario. [!DNL Target] utiliza esta información para filtrar elementos y mejorar la personalización de las recomendaciones.

## Cree su primera actividad de Recommendations

Una actividad de [!DNL Recommendations] combina una audiencia, criterios y un diseño. [!DNL Target] incluye 14 audiencias integradas, 42 criterios integrados y 10 plantillas de diseño integradas. Puede personalizar cada uno de estos elementos o agregarlos.

![Ilustración que muestra las partes que constituyen una buena actividad de recomendaciones: la audiencia (que debería ver estas recomendaciones), los criterios (qué artículos se deberían recomendar) y el diseño (cómo se muestran los artículos recomendados).](assets/intro-11.png)

[!DNL Target] utiliza el concepto de la tarjeta de criterios, que es como una fórmula de personalización. Elegir o crear los criterios adecuados es importante para lograr los resultados de personalización deseados. Una tarjeta de criterios funciona como una funnel que le lleva a través de todo el catálogo hasta el conjunto final de recomendaciones.

![Ilustración del criterio funnel: contenido del catálogo, filtros estáticos (colecciones y exclusiones), algoritmo (lógica y clave de recomendación), reglas de negocio en línea (filtrado dinámico y ponderación de atributos) y recomendaciones finales, junto a una tarjeta de criterios de ejemplo.](assets/intro-14.png)

Las secciones siguientes describen las partes de este funnel y cómo funcionan en [!DNL Target].

### Filtros estáticos (colecciones y exclusiones)

Los filtros estáticos son reglas aplicables ampliamente relacionadas con atributos de catálogo que no espera cambiar con frecuencia, por lo que puede utilizarlos en varias recomendaciones.

![Ilustración de filtros estáticos. Contenido: incluya todas las películas y excluya las películas clasificadas como NC-17 de las recomendaciones. Productos: incluye todos los productos disponibles en Estados Unidos y excluye los productos de una etiqueta privada regional.](assets/intro-16.png)

### Algoritmo (lógica y clave de recomendación)

El siguiente paso es elegir una lógica y clave de recomendación, que son la base de la recomendación. La clave de recomendación es lo que está “buscando” para elegir la recomendación.

![Ilustración del paso de algoritmo. Clave de recomendación: artículo visualizado actualmente, categoría visualizada actualmente, último artículo comprado o atributo personalizado. Lógica de recomendación: artículos con atributos similares, artículos más vistos en la categoría, clientes que compraron este artículo también compraron estos artículos o algoritmo personalizado.](assets/intro-17.png)

[!DNL Target] incluye un catálogo de algoritmos.

![Ilustración del portafolio de algoritmos: basados en popularidad (más visitados, más vendidos), basados en contenido (similitud de contenido), filtrados de colaboración basados en elementos (visualizados/visualizados, vistos/comprados, comprados/comprados, donde comprar puede ser cualquier conversión), personalizados (visualizados recientemente, afinidad del sitio, colaboración con perfil mejorado. Filtrado) y traiga los suyos propios (algoritmos personalizados).](assets/intro-15.png)

### Reglas empresariales en línea

El último paso es la aplicación de reglas empresariales en línea, que mejoran los algoritmos con conocimiento del dominio y contexto actual, en función de lo que el visitante esté haciendo en su propiedad digital.

![Ilustración de reglas comerciales en línea. Contenido: excluir las películas vistas anteriormente, mostrar películas del mismo director y aumentar las películas con el mismo género. Productos: excluir productos sin existencias, mostrar artículos con un precio de 5 a 500 dólares y aumentar el número de artículos de la misma marca.](/help/main/c-recommendations/assets/intro-18.png)
