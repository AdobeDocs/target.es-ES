---
description: Introducción a las actividades de Recomendaciones de Target que muestran automáticamente productos o contenido que pueda interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.
keywords: Recommendations;
seo-description: Introducción a las actividades de Recomendaciones de Adobe Target que muestran automáticamente productos o contenido que pueda interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.
seo-title: Introducción a las actividades de Recomendaciones en Adobe Target
solution: Target
title: Introducción a Recommendations
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: b487392873f18899168ed5aab3963b7e75614cf7

---


# ![Introducción PREMIUM](/help/assets/premium.png) a Recommendations

El texto de este artículo se obtiene del seminario web *Introduction to Recommendations* , que puede ver íntegramente a continuación.

El seminario web *Introducción a Recommendations* incluye una exploración exhaustiva de cómo aprovechar el valor de [!DNL Adobe Target Recommendations]. Descubra cómo esta actividad [!DNL Target] muestra automáticamente los productos o el contenido que pueda interesar a sus clientes optimizando las sugerencias en tiempo real en función de las visitas anteriores. Además, sumérjase en la interfaz de usuario [!DNL Target] para obtener información general paso a paso sobre cómo generar una actividad [!DNL Recommendations].

## Primeros pasos

Todos conocemos los tipos de recomendaciones que vemos en el comercio minorista. Cada vez más, los clientes esperan este tipo de recomendaciones y los utilizan como punto de partida para explorar otras opciones disponibles. Si piensa en su propio comportamiento de compras, este tipo de recomendaciones funcionan bien. Casi todos los demás usuarios compraron un producto que vimos primero en una recomendación en algún lugar, ya sea en una tienda o en una propiedad digital.

La siguiente ilustración muestra una recomendación que muestra accesorios que comúnmente se compran con un nuevo teléfono, incluso estaciones de carga, casos y auriculares.

![La recomendación que muestra los accesorios otros usuarios compró con un nuevo teléfono.](/help/c-recommendations/assets/intro-1.png)

Sin embargo, lo que no siempre pensamos es cómo las marcas digitales aumentan la barra de expectativas de los clientes. Cada vez más, la forma en que consumen medios y el contenido se impulsa mediante recomendaciones personalizadas. Piense lo primero que ve al abrir Netflix, Spotify o YouTube. Estas marcas inician la experiencia del cliente con recomendaciones. En un mundo en el que hay más alternativas que nunca, es fundamental que identifique el contenido más relevante para su cliente en el punto de interacción.

![Recomendación que muestra marcas digitales](/help/c-recommendations/assets/intro-2.png)

Los especialistas en marketing utilizan [!DNL Adobe Target] para impulsar experiencias personalizadas en una amplia variedad de industrias, tipos de clientes y canales.

[!DNL Adobe Target] ofrece contenido personalizado en todas partes.

![Ilustración que muestra cómo Target entrega recomendaciones en varios lugares](/help/c-recommendations/assets/intro-3.png)

* **Publicación**: Los editores Web utilizan [!DNL Target Recommendations] para recomendar artículos a los visitantes del sitio y aumentar la participación.
* **Tutoriales de vídeo**: [!DNL Adobe Creative Cloud] utiliza [!DNL Target] para recomendar tutoriales de vídeo a usuarios de Photoshop en la aplicación Photoshop.
* **Juegos**: Las empresas de juegos utilizan [!DNL Target] para recomendar juegos y contenido a los usuarios de sus consolas.
* **Ventas B 2 B**: [Las empresas comerciales utilizan Target para recomendar vídeos, documentos técnicos y anuncios de blogs a posibles clientes B 2 B; entregar descargas; y proporcionar ayuda a los clientes existentes](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Turismo**: [Un comprador de turismo alemán usa Target para recomendar hoteles y más para viajeros](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Minorista**: [Un minorista líder B 2 B usa Target para recomendar categorías y productos principales para devolver visitantes en el explorador y en su aplicación móvil](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Estas son sólo algunas de las formas en que los clientes utilizan Target para ofrecer recomendaciones personalizadas.

¿Qué hace para las fantásticas recomendaciones?

![Ilustración que muestra los tres elementos que realizan grandes recomendaciones](/help/c-recommendations/assets/intro-4.png)

Las recomendaciones recomendadas deben ser relevantes y personalizadas. Esto significa que necesita tres cosas para fomentar la relevancia y la personalización:

* **Controles de especialista en marketing** para ayudar a impulsar la relevancia de los elementos recomendados. Como especialista en mercadotecnia, le lleva un contexto valioso a la tabla y sabe qué atributos de los productos o del contenido son relevantes para un modelo de recomendaciones que considerar. Si está ejecutando un sitio de vídeo, sabe que los usuarios pueden estar interesados en ver películas del mismo director, pero probablemente no le importen ver películas generadas por el mismo estudio. [!DNL Target] le otorga los controles que le permiten mejorar los algoritmos con este conocimiento de dominio.
* **Modelos sofisticados** para dar sentido a millones de elementos en los eventos de catálogo e interacción. [!DNL Target] tiene sofisticadas capacidades de aprendizaje automático creadas durante una década de experiencia y gestionamos miles de millones de recomendaciones al año.
* **Contexto de usuario** para garantizar que las recomendaciones sean oportunas y relevantes para los usuarios. No desea recomendar el video que alguien acaba de ver o la camiseta que alguien acaba de agregar al carro de compras. El perfil de usuario enriquecido de Target se puede usar en recomendaciones para garantizar la personalización.

## Implementar recomendaciones de Target

Comience con una estrategia.

![Ilustración que muestra la estrategia de Recomendaciones](/help/c-recommendations/assets/intro-5.png)

* **¿Qué elementos desea recomendar?** Primero, piense en qué elementos desea recomendar. Puede ser productos, videos o contenido.
* **¿Dónde desea mostrar las recomendaciones?** A continuación, piense en dónde desea hacer recomendaciones. En general, los canales (web, móvil, en la tienda, un quiosco, etc.). ¿Qué partes del viaje del cliente contendrán recomendaciones? ¿Qué páginas del sitio contendrán recomendaciones?
* **¿Cómo determinará si las recomendaciones son exitosas?** Supongamos que tiene una experiencia sin recomendaciones y una experiencia con recomendaciones, o que tiene dos tipos diferentes de recomendaciones. ¿Cómo determinaría qué experiencia ofrecía mejor experiencia a sus clientes? Algunas métricas podrían ser más difíciles de medir que otras. Por ejemplo, el impacto de las recomendaciones en el valor de duración del cliente suele ser difícil de obtener directamente. Por lo tanto, a menudo resulta más fácil obtener una métrica menos abstracta y una que es más específica, por ejemplo, ingresos por visita, valor promedio de pedido o cantidad de clics. En algunos casos, es posible que esté buscando minimizar una métrica, por ejemplo, la cantidad de llamadas de asistencia.

Una vez que viene con su estrategia, está listo para iniciar la implementación [!DNL Target Recommendations].

Existen tres pasos amplios para la creación de la implementación de Recomendaciones:

![Ilustración que muestra los pasos para crear la implementación de Recomendaciones](/help/c-recommendations/assets/intro-6.png)

1. Enseñe [!DNL Target] sobre su contexto o productos.
1. Capturar el comportamiento del usuario.
1. Obtener recomendaciones con el contexto adecuado.

### Enseñe [!DNL Target] sobre su contexto o productos

Al comenzar con [!DNL Recommendations], pasa información sobre cada elemento que desee recomendar. [!DNL Target] ofrece varias opciones de integración para crear su catálogo.

![Ilustración que muestra cómo enseñar Target sobre su contexto o productos](/help/c-recommendations/assets/intro-7.png)

El método más sencillo y usado es enviar un archivo CSV diariamente o semanalmente desde el sistema de administración de información de productos o desde su sistema de administración de contenido. Pero también puede pasar información sobre la capa de datos desde la página utilizando la biblioteca [!DNL Adobe Target] Javascript, aprovechar nuestras API para pasar información directamente desde el sistema de origen o utilizar nuestra [!DNL Adobe Analytics] integración si ya está pasando datos del catálogo.[!DNL Analytics]

En ocasiones, es posible que desee utilizar varias opciones juntas, por ejemplo, pasando la mayoría de los datos diariamente a través de un archivo CSV y pasando las actualizaciones de inventario con más frecuencia a través de una API.

El departamento de TI generalmente estará involucrado en ayudar a configurar este paso.

Cualquiera que sea el método que elija, debe incluir metadatos sobre cada elemento en tres categorías:

![Ilustración que muestra información de metadatos del catálogo](/help/c-recommendations/assets/intro-8.png)

* Datos que desea mostrar al usuario que recibe la recomendación. Por ejemplo, el nombre de la película y una URL de imagen en miniatura.
* Datos que son útiles para aplicar controles de mercadotecnia y comercialización. Por ejemplo, la clasificación de la película para que no recomiende películas NC -17.
* Datos que son útiles para determinar la similitud de elementos a otros elementos. Por ejemplo, el género de la película o los actores que están en la película.

### Capturar comportamiento del usuario

A continuación, debe agregar etiquetas o aprovechar [!DNL Analytics] la implementación existente para rastrear los eventos de conversión (tales como vistas y compras) que conducen [!DNL Target] a los algoritmos.

![Ilustración que muestra cómo capturar el comportamiento del usuario](/help/c-recommendations/assets/intro-9.png)

Debe asegurarse de [!DNL Target] tener en cuenta los artículos que los usuarios están viendo y comprando. Si la compra no es relevante para su contexto, es posible que desee rastrear un tipo diferente de evento de conversión, por ejemplo, descargar un PDF, completar un estudio, suscribirse a una newsletter, ver un video, etc.

Si ya se está utilizando [!DNL Target] para ejecutar actividades A/B en su sitio, es posible que ya haya completado este paso. O si ya utiliza [!DNL Adobe Analytics] para informar sobre las visitas del sitio y el comportamiento de conversión, puede utilizarlo [!DNL Analytics] como fuente de datos de comportamiento. Si no es así, es más fácil configurarlo con un administrador de etiquetas como [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). También es posible enviar interacciones sin conexión o dentro de la aplicación a [!DNL Target] través de API en tiempo real.

### Obtener recomendaciones con el contexto correcto

Pase información sobre el usuario y el contexto en el punto de interacción para [!DNL Target] devolver recomendaciones relevantes y personalizadas.

![Ilustración que muestra cómo obtener recomendaciones con el contexto correcto](/help/c-recommendations/assets/intro-10.png)

Además de la conducta del usuario en suma, debe pasar [!DNL Target] el contexto específico donde se muestran las recomendaciones. Esto incluye información sobre la página y la información del perfil de usuario. [!DNL Target] utiliza esta información para realizar recomendaciones personalizadas. Por ejemplo, en un sitio web de venta minorista, debe saber la categoría de productos y productos que el visitante está viendo en este momento. También desea conocer información sobre ese usuario (marca favorita, categoría de producto favorita, nivel de lealtad, etc.). Esta información es importante para [!DNL Target] filtrar elementos y mejorar la personalización de las recomendaciones.

## Cree su primera actividad de Recomendaciones

¿Qué es [!DNL Recommendations] una actividad?

![Ilustración que muestra las partes que realizan una buena actividad de recomendaciones](/help/c-recommendations/assets/intro-11.png)

[!DNL Recommendations] Una actividad consta de los siguientes componentes:

* **Audiencia**: ¿Quién debe ver estas recomendaciones?
* **Criterios**: ¿Qué elementos se deben recomendar?
* **Diseño**: ¿Cómo se deben mostrar los artículos recomendados?

![Ilustración que muestra lo que constituye una actividad de recomendaciones: Audiencias, criterios y diseños](/help/c-recommendations/assets/intro-12.png)

Fuera del cuadro [!DNL Target] incluye 14 audiencias integradas, 42 criterios integrados y 10 plantillas de diseño integradas. Puede personalizar cada uno de estos elementos o agregarlos. Hemos tenido [seminarios Web anteriores sobre la creación de audiencias](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) en [!DNL Target]. Esta sección se centra en definir los criterios, que definen qué elementos se recomiendan.

Target usa el concepto de la tarjeta de criterios. Una tarjeta de criterios es como una fórmula para personalización.

![Ilustración de la tarjeta de criterios](/help/c-recommendations/assets/intro-13.png)

Es importante elegir o crear los criterios adecuados para conseguir los resultados de personalización que desee. Los criterios son como un canal que le lleva de todo el catálogo al final de recomendaciones.

![Ilustración de canal](/help/c-recommendations/assets/intro-14.png)

Las secciones siguientes describen las distintas partes de este canal y cómo funcionan [!DNL Target]en:

### Filtros estáticos (colecciones y exclusiones)

Los filtros estáticos son reglas aplicables ampliamente relacionadas con atributos de catálogo que no se espera cambiar con frecuencia.

![Colecciones y ilustraciones de exclusiones](/help/c-recommendations/assets/intro-16.png)

Por ejemplo, en un contexto de contenido, es posible que desee incluir todas las películas en Recomendaciones, pero excluir películas clasificadas NC -17. En un contexto minorista, puede tener varias marcas en diferentes partes del mundo, pero solo quiere recomendar productos disponibles en Estados Unidos. También es posible que desee excluir productos de una etiqueta privada regional.

Son todos atributos de catálogo que son aplicables en gran medida y que es posible que desee utilizar en varias recomendaciones y no se espera que cambien con frecuencia.

### Algoritmo (clave y lógica de recomendación)

El siguiente paso es elegir una clave y clave de recomendación. Aquí es donde decide cuál es la base de la recomendación.

![Ilustración de algoritmo](/help/c-recommendations/assets/intro-17.png)

Lo primero que debe elegir es la clave de recomendación. La clave de recomendación es lo que está "buscando" para elegir la recomendación. Esto es lo que basa la recomendación.

Puede basar su recomendación en:

* El elemento que el visitante está viendo en este momento
* La categoría que el visitante está viendo actualmente
* El artículo que el visitante compró o agregó por última vez al carro de compras
* Un atributo personalizado relacionado con un visitante o un elemento

Según estas claves, elija la lógica de recomendación que desee:

* Elementos con atributos similares.
* Los elementos más vistos de una categoría en particular
* Los clientes que compraron este artículo también compraron estos elementos
* Un atributo personalizado

Fuera del cuadro [!DNL Target] , incluye un portafolio de algoritmos.

![Portafolio de la ilustración de algoritmos](/help/c-recommendations/assets/intro-15.png)

* **Los algoritmos basados en popularidad** incluyen Más visitantes y Más vendidos.
* **Los algoritmos basados en contenido** incluyen Similitud de contenido.
* **Los algoritmos de filtrado colaborativos basados en elementos** incluyen Visualizado/Visto, Visto/Comprado y Comprado/comprado. Tenga en cuenta que "comprado" puede ser cualquier conversión.
* **Los algoritmos personalizados** incluyen los filtros de colaboración vistos recientemente, afinidad del sitio y colaboración mejorada de perfil.
* **Los algoritmos propios** le permiten utilizar sus propios algoritmos personalizados.

### Reglas comerciales en línea

El último paso es aplicar reglas comerciales en línea. Aquí es donde puede potenciar los algoritmos con conocimientos de dominio y contexto actual según lo que hace el visitante en su propiedad digital.

![Ilustración de reglas comerciales en línea](/help/c-recommendations/assets/intro-18.png)

Por ejemplo, en el contexto de contenido, es posible que quiera excluir películas que el visitante haya visto anteriormente, recomendar películas por el mismo director o mejorar películas en el mismo género. En el contexto minorista, es posible que quiera excluir productos fuera de existencias, mostrar artículos en un rango de precios de 5 a 500 dólares o aumentar los elementos de la misma marca.

## Demostración

Después de completar las tareas ilustradas en el canal de recomendaciones descrito arriba, se le deja con la recomendación final. Para ver una demostración dentro del producto dentro [!DNL Target], la demostración comienza a las 21:00 en el seminario web básico *de Adobe Target*, vinculado a continuación.

## Seminario web básico de Adobe Target: Introducción a Recommendations {#intro-to-recs}

[Introducción a Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)