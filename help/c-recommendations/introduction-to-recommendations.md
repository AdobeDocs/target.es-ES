---
keywords: Recommendations;introducción;seminario web;demostración
description: Conozca las actividades de Recommendations en Adobe  [!DNL Target]  que muestran automáticamente contenido que podría interesar a sus clientes en función de la actividad previa del usuario o de otros algoritmos.
title: ¿Qué son las actividades de Recommendations?
feature: Recomendaciones
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
translation-type: ht
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: ht
source-wordcount: '2115'
ht-degree: 100%

---

# ![PREMIUM](/help/assets/premium.png) Introducción a Recommendations

El texto de este artículo se obtiene del seminario web *Introducción a Recommendations*, que puede ver íntegramente a continuación.

El seminario web *Introducción a Recommendations* incluye una exploración exhaustiva de cómo aprovechar el valor de [!DNL Adobe Target Recommendations]. Descubra cómo esta actividad [!DNL Target] muestra automáticamente los productos o el contenido que pueda interesar a sus clientes optimizando las sugerencias en tiempo real en función de las visitas anteriores. Además, sumérjase en la interfaz de usuario de [!DNL Target] para obtener información general paso a paso sobre cómo generar una actividad de [!DNL Recommendations].

## Primeros pasos

Todos conocemos los tipos de recomendaciones que vemos en el comercio minorista. Los clientes esperan cada vez más este tipo de recomendaciones y las utilizan como punto de partida para explorar otras opciones disponibles. Si piensa en sus propios comportamientos al ir a la compra, este tipo de recomendaciones funcionan bien. Casi todos hemos comprado un producto que vimos primero en una recomendación en algún lugar, ya sea en una tienda o en una propiedad digital.

La siguiente ilustración muestra una recomendación con accesorios que comúnmente se compran con un nuevo teléfono, incluidas estaciones de carga, carcasas y auriculares.

![Recomendación que muestra accesorios que otros usuarios compraron junto a un nuevo teléfono.](/help/c-recommendations/assets/intro-1.png)

Sin embargo, lo que no solemos pensar es cómo las marcas digitales aumentan las expectativas de los clientes. Cada vez más, la forma en la que consumimos medios y contenido depende de recomendaciones personalizadas. Piense en lo primero que ve al abrir Netflix, Spotify o YouTube. Estas marcas inician la experiencia del cliente con recomendaciones. En un mundo en el que hay más alternativas que nunca, es fundamental que identifique el contenido más relevante para su cliente en el momento de la interacción.

![Recomendación que muestra marcas digitales](/help/c-recommendations/assets/intro-2.png)

Los especialistas en marketing utilizan [!DNL Adobe Target] para impulsar experiencias personalizadas en una amplia variedad de industrias, tipos de clientes y canales.

[!DNL Adobe Target] ofrece contenido personalizado en todas partes.

![Ilustración que muestra cómo Target entrega recomendaciones en varios lugares](/help/c-recommendations/assets/intro-3.png)

* **Publicación**: Los editores web utilizan [!DNL Target Recommendations] para recomendar artículos a los visitantes del sitio y aumentar la participación.
* **Tutoriales de vídeo**: [!DNL Adobe Creative Cloud] Utiliza [!DNL Target] para recomendar tutoriales de vídeo a usuarios de Photoshop en la aplicación Photoshop.
* **Juegos**: Las empresas de juegos utilizan [!DNL Target] para recomendar juegos y contenido a los usuarios de sus consolas.
* **Ventas B2B**: [Las empresas B2B utilizan Target para recomendar vídeos, documentos técnicos y anuncios de blogs a posibles clientes B2B; proporcionar descargas y ayudar a los clientes existentes](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Viajes**: [Un vendedor de viajes alemán usa Target para recomendar hoteles (entre otras cosas) a los viajeros](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Comercio minorista**: [Un minorista líder B2B usa Target para recomendar categorías y productos principales para los visitantes de retorno en el explorador y en su aplicación móvil](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Estas son solo algunas de las formas en que los clientes utilizan Target para ofrecer recomendaciones personalizadas.

¿Cuál es el secreto de una buena recomendación?

![Ilustración que muestra los tres elementos clave de las recomendaciones](/help/c-recommendations/assets/intro-4.png)

Las mejores recomendaciones son relevantes y personalizadas. Esto significa que necesita tres cosas para potenciar la relevancia y la personalización:

* **Controles de experto en marketing** para ayudar a aumentar la relevancia de los artículos recomendados. Como experto en marketing, proporciona un contexto valioso y sabe qué atributos de los productos o del contenido son relevantes para considerar en un modelo de recomendaciones. Si lleva un sitio web de películas, sabrá que los usuarios suelen estar interesados en ver películas del mismo director, pero probablemente no les importe ver películas producidas por el mismo estudio. [!DNL Target] le otorga los controles que le permiten mejorar los algoritmos con este conocimiento del dominio.
* **Modelos sofisticados** para dar sentido a los millones de artículos en los eventos de catálogo y de interacción. [!DNL Target] tiene funcionalidades sofisticadas de aprendizaje automático creadas durante más una década de experiencia. Gestionamos miles de millones de recomendaciones al año.
* **Contexto del usuario** para garantizar que las recomendaciones sean oportunas y relevantes para el mismo. No sirve de nada recomendar el vídeo que alguien acaba de ver o la camiseta que alguien acaba de agregar al carro de compras. El perfil de usuario enriquecido de Target se puede usar en las recomendaciones para garantizar la personalización.

## Implementación de Recommendations de [!DNL Target]

Comience con una estrategia.

![Ilustración que muestra la estrategia de recomendaciones](/help/c-recommendations/assets/intro-5.png)

* **¿Qué artículos desea recomendar?** Primero, piense en qué artículos desea recomendar. Pueden ser productos, vídeos o contenido.
* **¿Dónde desea mostrar las recomendaciones?** A continuación, piense en dónde desea hacer recomendaciones. En decir, piensé qué canales le convienen más (web, móvil, en la tienda, un quiosco, etc.). ¿Qué partes del recorrido del cliente contendrán recomendaciones? ¿Qué páginas del sitio contendrán recomendaciones?
* **¿Cómo determinará si las recomendaciones son exitosas?** Supongamos que tiene una experiencia sin recomendaciones y otra con recomendaciones, o que tiene dos tipos diferentes de recomendaciones. ¿Cómo determina qué experiencia ofrece el mejor servicio a sus clientes? Algunas métricas podrían ser más difíciles de medir que otras. Por ejemplo, el impacto de las recomendaciones en el valor de duración del cliente suele ser difícil de obtener directamente. Por lo tanto, a menudo resulta más fácil obtener una métrica menos abstracta y más específica, por ejemplo, ingresos por visita, valor de pedido promedio o cantidad de clics. En algunos casos, es posible que busque minimizar una métrica, por ejemplo, la cantidad de llamadas de asistencia.

Una vez que haya pensado su estrategia, todo está listo para iniciar la implementación de [!DNL Target Recommendations].

Existen tres pasos amplios para la creación de la implementación de las recomendaciones:

![Ilustración que muestra los pasos para crear la implementación de las recomendaciones](/help/c-recommendations/assets/intro-6.png)

1. Enseñe a [!DNL Target] sobre su contexto o productos.
1. Capture el comportamiento del usuario.
1. Obtenga recomendaciones con el contexto adecuado.

### Enseñe a [!DNL Target] sobre su contexto o productos

Al comenzar con [!DNL Recommendations], pase información sobre cada artículo que desee recomendar. [!DNL Target] ofrece varias opciones de integración para crear su catálogo.

![Ilustración que muestra cómo enseñar a Target sobre su contexto o productos](/help/c-recommendations/assets/intro-7.png)

El método más sencillo y usado es enviar un archivo CSV diaria o semanalmente desde el sistema de administración de la información de productos o desde el de administración de contenido. Pero también puede pasar información sobre la capa de datos desde la página con la biblioteca [!DNL Adobe Target] Javascript, aprovechar nuestras API para pasar información directamente desde el sistema de origen o utilizar nuestra integración [!DNL Adobe Analytics] si ya está pasando datos del catálogo a [!DNL Analytics].

En ocasiones, es posible que desee utilizar varias opciones juntas, por ejemplo, al pasar la mayoría de los datos diariamente a través de un archivo CSV y las actualizaciones de inventario con más frecuencia a través de una API.

El departamento de TI suele estar implicado en la configuración de este paso.

Sea el que sea el método que elija, debe incluir metadatos sobre cada elemento en tres categorías:

![Ilustración que muestra información de metadatos del catálogo](/help/c-recommendations/assets/intro-8.png)

* Datos que desea mostrar al usuario que recibe la recomendación. Por ejemplo, el nombre de la película y una URL de imagen de miniatura.
* Datos que son útiles para aplicar controles de marketing y comercialización. Por ejemplo, la clasificación de la película, para que no recomiende las de mayores de 17 años.
* Datos que son útiles para determinar la similitud de unos elementos a otros. Por ejemplo, el género de la película o los actores que salen en ella.

### Capturar el comportamiento del usuario

A continuación, debe agregar etiquetas o aprovechar la implementación existente de [!DNL Analytics] para hacer un seguimiento de los eventos de conversión (tales como vistas y compras) que controlan los algoritmos de [!DNL Target].

![Ilustración que muestra cómo capturar el comportamiento del usuario](/help/c-recommendations/assets/intro-9.png)

Compruebe que [!DNL Target] tenga en cuenta los artículos que los usuarios están viendo y comprando. Si la compra no es relevante para su contexto, es posible que desee rastrear un tipo diferente de evento de conversión, por ejemplo, descargar un PDF, completar una encuesta, suscribirse a una newsletter, ver un vídeo, etc.

Si ya está utilizando [!DNL Target] para ejecutar actividades A/B en su sitio, es posible que ya haya completado este paso. O si ya utiliza [!DNL Adobe Analytics] para informar sobre las visitas del sitio y el comportamiento de conversión, puede utilizar [!DNL Analytics] como fuente de datos de comportamiento. Si no es así, es más fácil configurarlo con un administrador de etiquetas como [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). También es posible enviar interacciones sin conexión o dentro de la aplicación a [!DNL Target] a través de una API en tiempo real.

### Obtener recomendaciones con el contexto correcto

Pase información sobre el usuario y el contexto en el punto de interacción a [!DNL Target] para devolver recomendaciones relevantes y personalizadas.

![Ilustración que muestra cómo obtener recomendaciones con el contexto correcto](/help/c-recommendations/assets/intro-10.png)

Además del comportamiento del usuario en suma, debe pasar [!DNL Target] en el contexto específico donde se muestran las recomendaciones. Esto incluye información sobre la página y perfil de usuario. [!DNL Target] utiliza esta información para realizar recomendaciones personalizadas. Por ejemplo, en un sitio web de venta minorista, debe conocer los productos y la categoría de productos que el visitante está viendo en este momento. También desea conocer información sobre ese usuario (marca favorita, categoría de producto favorita, nivel de lealtad, etc.). Esta información es importante para que [!DNL Target] pueda filtrar elementos y mejorar la personalización de las recomendaciones.

## Cree su primera actividad de Recommendations

¿Qué es una actividad de [!DNL Recommendations]?

![Ilustración que muestra las partes que ayudan a mejorar una actividad de recomendaciones](/help/c-recommendations/assets/intro-11.png)

Una actividad de [!DNL Recommendations] consta de los siguientes componentes:

* **Audiencia**: ¿Quién debe ver estas recomendaciones?
* **Criterios**: ¿Qué artículos se deben recomendar?
* **Diseño**: ¿Cómo se deben mostrar los artículos recomendados?

![Ilustración que muestra los elementos que constituyen una actividad de recomendaciones: Audiencias, criterios y diseños](/help/c-recommendations/assets/intro-12.png)

De serie, [!DNL Target] incluye 14 audiencias, 42 criterios y 10 plantillas de diseño integradas. Puede personalizar cada uno de estos elementos o agregarlos. En el pasado, hemos tenido [seminarios web sobre la creación de audiencias](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) en [!DNL Target]. Esta sección se centra en definir los criterios que definen qué artículos se recomendarán.

Target usa el concepto de la tarjeta de criterios. Una tarjeta de criterios es como una fórmula para personalizar.

![Ilustración de la tarjeta de criterios](/help/c-recommendations/assets/intro-13.png)

Es importante elegir o crear los criterios adecuados para conseguir los resultados de personalización que desea. Los criterios son como un canal que le lleva a través del catálogo hasta el conjunto final de recomendaciones.

![Ilustración de canal](/help/c-recommendations/assets/intro-14.png)

Las secciones siguientes describen las distintas partes de este canal y cómo funcionan en [!DNL Target]:

### Filtros estáticos (colecciones y exclusiones)

Los filtros estáticos son reglas aplicables ampliamente relacionadas con atributos de catálogo que no espera cambiar con frecuencia.

![Ilustración de colecciones y exclusiones](/help/c-recommendations/assets/intro-16.png)

Por ejemplo, en un contexto de contenido, es posible que desee incluir todas las películas en recomendaciones, pero excluir películas no recomendadas para menores de 17 años. En un contexto minorista, puede tener varias marcas en diferentes partes del mundo, pero quizá solo quiera recomendar productos disponibles en Estados Unidos. También es posible que desee excluir productos de una marca privada regional.

Estos son todos atributos de catálogo que son aplicables en gran medida y que es posible que desee utilizar en varias recomendaciones y no se espera que cambien con frecuencia.

### Algoritmo (lógica y clave de recomendación)

El siguiente paso es elegir una lógica y clave de recomendación. Aquí es donde decide cuál es la base de la recomendación.

![Ilustración de algoritmo](/help/c-recommendations/assets/intro-17.png)

Lo primero que debe elegir es la clave de recomendación. La clave de recomendación es lo que está “buscando” para elegir la recomendación. Esto es en lo que basa la recomendación.

Puede basar su recomendación en:

* El artículo que el visitante está viendo en este momento
* La categoría que el visitante está viendo en este momento
* El artículo que el visitante compró o agregó por última vez al carro de compras
* Un atributo personalizado relacionado con un visitante o un artículo

Según estas claves, elija la lógica de recomendación que desee:

* Elementos con atributos similares.
* Los elementos más vistos de una categoría en particular
* Los clientes que compraron este artículo también compraron estos otros
* Un atributo personalizado

De serie, [!DNL Target] incluye un portafolio de algoritmos.

![Ilustración de portafolio de algoritmos](/help/c-recommendations/assets/intro-15.png)

* **Los algoritmos basados en popularidad** incluyen Más visitantes y Más vendidos.
* **Los algoritmos basados en contenido** incluyen Similitud de contenido.
* **Los algoritmos de filtrado colaborativos basados en elementos** incluyen Visto/Visto, Visto/Comprado y Comprado/Comprado. Tenga en cuenta que “comprado” puede ser cualquier conversión.
* **Los algoritmos personalizados** incluyen filtros de colaboración de perfil mejorado, Vistos recientemente y Afinidad del sitio.
* **Los algoritmos propios** le permiten utilizar sus propios algoritmos personalizados.

### Reglas de negocios en línea

El último paso es aplicar reglas de negocio en línea. Aquí es donde puede potenciar los algoritmos con conocimientos de dominio y contexto actual según lo que haga el visitante en su propiedad digital.

![Ilustración de reglas comerciales en línea](/help/c-recommendations/assets/intro-18.png)

Por ejemplo, en el contexto de contenido, es posible que quiera excluir películas que el visitante haya visto anteriormente, recomendar películas por el mismo director o impulsar películas en el mismo género. En el contexto de los comercios minoristas, es posible que quiera excluir productos de los que no tiene existencias, mostrar artículos en un rango de precios de 5 a 500 dólares o aumentar el número de elementos de la misma marca.

## Demostración

Después de completar las tareas ilustradas en el canal de recomendaciones descrito arriba, se le deja con la recomendación final. Si desea ver una demostración del producto dentro de [!DNL Target], la demostración comienza a las 21:00 en el *Seminario web de funciones básicas de Adobe Target*, y tiene el vínculo a continuación.

## Seminario web de conceptos básicos de Adobe [!DNL Target]: Introducción a Recommendations {#intro-to-recs}

[Introducción a Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
