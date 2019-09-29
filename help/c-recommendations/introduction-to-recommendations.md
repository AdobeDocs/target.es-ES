---
description: Introducción a las actividades de Recomendaciones de Target que muestran automáticamente productos o contenido que puede interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.
keywords: Recomendaciones;introducción;introducción;seminario web;demostración
seo-description: Introducción a las actividades de Recomendaciones de Adobe Target que muestran automáticamente productos o contenido que puede interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.
seo-title: Introducción a las actividades de Recomendaciones en Adobe Target
solution: Target
title: Introducción a Recomendaciones
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: 516433edd366fad5950c99d748aa7f6f718dd5fd

---


# ![PREMIO](/help/assets/premium.png) Introducción a las Recomendaciones

El texto de este artículo proviene del seminario web *Introducción a Recomendaciones* , que puede ver en su totalidad a continuación.

El seminario web *Introducción a Recommendations* incluye una exploración exhaustiva de cómo aprovechar el valor de [!DNL Adobe Target Recommendations]. Descubra cómo esta actividad [!DNL Target] muestra automáticamente los productos o el contenido que pueda interesar a sus clientes optimizando las sugerencias en tiempo real en función de las visitas anteriores. Además, sumérjase en la interfaz de usuario [!DNL Target] para obtener información general paso a paso sobre cómo generar una actividad [!DNL Recommendations].

## Primeros pasos

Todos conocemos el tipo de recomendaciones que vemos en el comercio minorista. Cada vez más, los clientes esperan este tipo de recomendaciones y las utilizan como punto de partida para explorar otras opciones disponibles. Si piensas en tu propio comportamiento de compra, este tipo de recomendaciones funcionan muy bien. Casi todos nosotros hemos comprado un producto que vimos primero en una recomendación en algún lugar, ya sea en una tienda o en una propiedad digital.

La siguiente ilustración muestra una recomendación que muestra los accesorios que se compran comúnmente con un teléfono nuevo, incluidas las estaciones de carga, los estuches y los auriculares.

![Recomendación que muestra los accesorios que otros han comprado con un teléfono nuevo.](/help/c-recommendations/assets/intro-1.png)

Pero lo que no siempre pensamos es cómo las marcas digitales de primer nivel están elevando el nivel de expectativas de los clientes. Cada vez más, la manera en que consumimos contenido y medios está impulsada por recomendaciones personalizadas. Piense en lo primero que ve al abrir Netflix, Spotify o YouTube. Estas marcas inician la experiencia del cliente con recomendaciones. En un mundo en el que hay más alternativas disponibles que nunca, es fundamental que pueda identificar el contenido más relevante para su cliente en el punto de interacción.

![Recomendación que muestra marcas de origen digital](/help/c-recommendations/assets/intro-2.png)

Los especialistas en marketing utilizan [!DNL Adobe Target] para impulsar experiencias personalizadas en una amplia variedad de industrias, tipos de clientes y canales.

[!DNL Adobe Target] ofrece contenido personalizado en todas partes.

![Ilustración que muestra cómo Target ofrece recomendaciones en varios lugares](/help/c-recommendations/assets/intro-3.png)

* **Publicación**: Los editores web utilizan [!DNL Target Recommendations] para recomendar artículos a los visitantes del sitio y fomentar una mayor participación.
* **Video Tutorials:  uses  to recommend video tutorials to Photoshop users in the Photoshop application.**[!DNL Adobe Creative Cloud][!DNL Target]
* **Gaming: Gaming companies use  to recommend games and content to users on their consoles.**[!DNL Target]
* **B2B Sales: Business-to-business companies use Target to recommend videos, whitepapers, and blog posts to B2B prospects; deliver downloads; and provide help to existing customers.**[](https://theblog.adobe.com/testing-shifts-high-gear-intel)

* **Travel: A German travel booker uses Target to recommend hotels and more to travelers.**[](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)

* **Retail: A leading B2B retailer uses Target to recommend top categories and products to return visitors in the browser and in its mobile app.**[](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)

These are just a few of the ways customers use Target to deliver personalized recommendations.

What makes for great recommendations?

![Illustration showing the three elements that make great recommendations](/help/c-recommendations/assets/intro-4.png)

Great recommendations should be relevant and personalized. This means you need three things to drive relevance and personalization:

* **Marketer controls to help drive relevance of the items that are recommended.** As a marketer, you bring valuable context to the table and you know what attributes of your products or content are relevant for a recommendations model to consider. Si está ejecutando un sitio de vídeos, sabe que los usuarios pueden estar interesados en ver películas del mismo director, pero probablemente no les importe ver películas producidas por el mismo estudio. [!DNL Target] le permite utilizar controles que le permiten mejorar sus algoritmos con este conocimiento de dominio.
* **Modelos** sofisticados para dar sentido a millones de artículos en el catálogo y eventos de interacción. [!DNL Target] cuenta con sofisticadas capacidades de aprendizaje automático, creadas a lo largo de una década de experiencia, y gestionamos miles de millones de recomendaciones al año.
* **Contexto** del usuario para garantizar que las recomendaciones sean oportunas y relevantes para los usuarios. No quiere recomendar el vídeo que alguien acaba de ver o la camisa que alguien acaba de añadir al carro. El perfil de usuario enriquecido de Target se puede usar en Recomendaciones para garantizar la personalización.

## Implementar recomendaciones de Target

Start with a strategy.

![Ilustración que muestra la estrategia de recomendaciones](/help/c-recommendations/assets/intro-5.png)

* **¿Qué elementos desea recomendar?** Primero, piense en qué elementos desea recomendar. Pueden ser productos, vídeos o contenido.
* **¿Dónde desea mostrar las recomendaciones?** Luego, piense dónde desea hacer las recomendaciones. En general, qué canales (web, móvil, en la tienda, quiosco, etc.). ¿Qué partes del viaje del cliente contendrán recomendaciones? ¿Qué páginas del sitio contendrán recomendaciones?
* **¿Cómo determinará si las recomendaciones son correctas?** Supongamos que tiene una experiencia sin recomendaciones y una experiencia con recomendaciones, o que tiene dos tipos diferentes de recomendaciones. ¿Cómo determinaría qué experiencia es mejor para sus clientes? Algunas métricas pueden ser más difíciles de medir que otras. Por ejemplo, el impacto de las recomendaciones en el valor de duración del cliente suele ser difícil de obtener directamente. Por lo tanto, a menudo es más fácil llegar a una métrica menos abstracta y a una más concreta, por ejemplo, los ingresos por visita, el valor de pedido promedio o la cantidad de clics. En algunos casos, es posible que esté buscando minimizar una métrica, por ejemplo, el número de llamadas de asistencia.

Una vez que haya ideado su estrategia, estará listo para comenzar la implementación de [!DNL Target Recommendations].

Existen tres pasos generales para crear la implementación de recomendaciones:

![Ilustración que muestra los pasos para crear la implementación de recomendaciones](/help/c-recommendations/assets/intro-6.png)

1. Enseñe [!DNL Target] sobre su contexto o productos.
1. Capturar el comportamiento del usuario.
1. Get recommendations with the right context.

### Teach  about your context or products[!DNL Target]

Al comenzar con [!DNL Recommendations], se pasa información sobre cada elemento que se desea recomendar. [!DNL Target] ofrece varias opciones de integración para crear el catálogo.

![Illustration showing how to teach Target about your context or products](/help/c-recommendations/assets/intro-7.png)

El método más sencillo y utilizado con más frecuencia es enviar un archivo CSV diario o semanalmente desde el sistema de administración de la información del producto o desde el sistema de administración de contenido. Pero también puede pasar información sobre la capa de datos de su página mediante la biblioteca [!DNL Adobe Target] Javascript, aprovechar nuestras API para pasar información directamente desde su sistema de origen o utilizar nuestra [!DNL Adobe Analytics] integración si ya está pasando datos de catálogo a [!DNL Analytics].

A veces, es posible que desee utilizar varias opciones juntas, por ejemplo, pasar la mayoría de los datos diariamente a través de un archivo CSV y pasar las actualizaciones de inventario con más frecuencia a través de una API.

Su departamento de TI generalmente colaborará en la configuración de este paso.

Independientemente del método que elija, debe incluir metadatos sobre cada elemento en tres categorías:

![Ilustración que muestra información de metadatos para el catálogo](/help/c-recommendations/assets/intro-8.png)

* Data that you want to display to the user receiving the recommendation. Por ejemplo, el nombre de la película y una URL de imagen en miniatura.
* Datos útiles para aplicar controles de marketing y comercialización. Por ejemplo, la clasificación de la película para que no se recomienden películas NC-17.
* Datos útiles para determinar la similitud de elementos con otros elementos. Por ejemplo, el género de la película o los actores que están en ella.

### Capturar el comportamiento del usuario

A continuación, debe agregar etiquetas o aprovechar la implementación existente [!DNL Analytics] para rastrear los eventos de conversión (como vistas y compras) que generan [!DNL Target] algoritmos.

![Ilustración que muestra cómo capturar el comportamiento del usuario](/help/c-recommendations/assets/intro-9.png)

Debe asegurarse de que [!DNL Target] conoce los elementos que ven y compran los usuarios. Si la compra no es relevante para su contexto, es posible que desee rastrear un tipo diferente de evento de conversión, por ejemplo, descargar un PDF, completar un estudio, suscribirse a una newsletter, ver un vídeo, etc.

Si ya está utilizando [!DNL Target] para ejecutar actividades de pruebas A/B en su sitio, es posible que ya haya completado este paso. O bien, si ya utiliza [!DNL Adobe Analytics] para informar sobre las visitas al sitio y el comportamiento de conversión, puede usar [!DNL Analytics] como fuente de datos de comportamiento. Si no es así, es más fácil configurarla con un administrador de etiquetas como [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). También es posible enviar interacciones sin conexión o en la aplicación a [!DNL Target] través de la API en tiempo real.

### Obtener recomendaciones con el contexto adecuado

Pasa información sobre el usuario y el contexto en el punto de interacción para [!DNL Target] devolver recomendaciones relevantes y personalizadas.

![Ilustración que muestra cómo obtener recomendaciones con el contexto adecuado](/help/c-recommendations/assets/intro-10.png)

Además del comportamiento agregado del usuario, debe pasar [!DNL Target] el contexto específico donde se muestran las recomendaciones. Esto incluye información sobre la página e información del perfil de usuario. [!DNL Target] utiliza esta información para realizar recomendaciones personalizadas. Por ejemplo: en un sitio web de venta minorista, desea conocer el producto y la categoría de producto que el visitante está viendo en ese momento. También desea obtener información sobre ese usuario (marca favorita, categoría de producto favorita, nivel de fidelidad, etc.). Esta información es importante para que [!DNL Target] pueda filtrar elementos y mejorar la personalización de las recomendaciones.

## Build your first Recommendations activity

¿Qué es una [!DNL Recommendations] actividad?

![Ilustración que muestra las partes que realizan una buena actividad de recomendaciones](/help/c-recommendations/assets/intro-11.png)

Una [!DNL Recommendations] actividad se compone de los siguientes componentes:

* **Audiencia**: ¿Quién debería ver estas recomendaciones?
* **Criterios**: ¿Qué elementos se deben recomendar?
* **Diseño**: ¿Cómo se deben mostrar los elementos recomendados?

![Ilustración que muestra qué constituye una actividad de recomendaciones: Audiencias, criterios y diseños](/help/c-recommendations/assets/intro-12.png)

De forma predeterminada, [!DNL Target] incluye 14 audiencias integradas, 42 criterios integrados y 10 plantillas de diseño integradas. Puede personalizar cada uno de estos elementos o agregar el suyo propio. Hemos tenido [seminarios web anteriores sobre la creación de audiencias](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) en [!DNL Target]. Esta sección se centra en definir los criterios, que definen qué elementos se recomendarán.

Target usa el concepto de la tarjeta de criterios. Una tarjeta de criterios es como una fórmula para la personalización.

![Ilustración de la tarjeta Criterios](/help/c-recommendations/assets/intro-13.png)

Es importante elegir o crear los criterios adecuados para lograr los resultados de personalización deseados. Un criterio es como un canal que lo lleva desde todo el catálogo hasta el último conjunto de recomendaciones.

![Ilustración de canal](/help/c-recommendations/assets/intro-14.png)

Las siguientes secciones describen las distintas partes de este canal y cómo funcionan [!DNL Target]:

### Filtros estáticos (colecciones y exclusiones)

Los filtros estáticos son reglas aplicables en general relacionadas con los atributos del catálogo que no se espera que cambien con frecuencia.

![Ilustración de colecciones y exclusiones](/help/c-recommendations/assets/intro-16.png)

Por ejemplo, en un contexto de contenido, es posible que desee incluir todas las películas en las recomendaciones, pero excluir las películas clasificadas como NC-17. En un contexto de venta minorista, es posible que tenga varias marcas en diferentes partes del mundo, pero desea recomendar solo productos disponibles en Estados Unidos. También es posible que desee excluir productos de una etiqueta privada regional.

Todos estos son atributos de catálogo que son aplicables en general y que puede que desee utilizar en varias recomendaciones y no espere que cambien con frecuencia.

### Algoritmo (lógica y clave de recomendación)

El siguiente paso es elegir una lógica y una clave de recomendación. Aquí es donde usted decide cuál es la base para su recomendación.

![Ilustración del algoritmo](/help/c-recommendations/assets/intro-17.png)

Lo primero que debe elegir es la clave de recomendación. La clave de recomendación es lo que está "buscando" para elegir la recomendación. En esto se basa la recomendación.

Puede basar la recomendación en:

* El elemento que el visitante está viendo actualmente
* La categoría que el visitante está viendo actualmente
* Elemento que el visitante compró o agregó por última vez al carro de compras
* Un atributo personalizado relacionado con un visitante o un elemento

En función de estas claves, elija la lógica de recomendación deseada:

* Elementos con atributos similares.
* Los artículos más vistos de una categoría en particular
* Los clientes que compraron este artículo también compraron estos artículos
* Un atributo personalizado

De forma predeterminada, [!DNL Target] incluye un portafolio de algoritmos.

![Ilustración de portafolios de algoritmos](/help/c-recommendations/assets/intro-15.png)

* **Los algoritmos** basados en la popularidad incluyen Mayor número de visitantes y Principales vendedores.
* **Los algoritmos** basados en contenido incluyen Similitud de contenido.
* **Los algoritmos** de filtrado colaborativo basados en elementos incluyen Visto/Visto, Visto/Comprado y Comprado/Comprado. Tenga en cuenta que "comprado" puede ser cualquier conversión.
* **Los algoritmos** personalizados incluyen los de vista reciente, afinidad del sitio y filtrado colaborativo mejorado por perfiles.
* **Los algoritmos** propios le permiten utilizar sus propios algoritmos personalizados.

### Reglas comerciales en línea

El último paso es aplicar reglas comerciales en línea. Aquí es donde se habilitan los algoritmos con conocimiento del dominio y contexto actual en función de lo que el visitante esté haciendo en la propiedad digital.

![Ilustración de reglas de negocios en línea](/help/c-recommendations/assets/intro-18.png)

Por ejemplo, en el contexto de contenido, es posible que desee excluir películas que el visitante haya visto anteriormente, recomendar películas del mismo director o impulsar películas en el mismo género. En el contexto de venta minorista, es posible que desee excluir productos fuera de existencias, mostrar artículos en un rango de precios de 5 a 500 dólares o aumentar artículos de la misma marca.

## Demostración

Después de completar las tareas que se ilustran en el canal de recomendaciones descrito anteriormente, se le dejará la recomendación final. Para ver una demostración interna del producto en el interior [!DNL Target], la demostración comienza a las 21:00 en el seminario web *de* Adobe Target Basics, vinculado a continuación.

## Seminario web básico de Adobe Target: Introducción a Recommendations {#intro-to-recs}

[Introducción a Recomendaciones](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)