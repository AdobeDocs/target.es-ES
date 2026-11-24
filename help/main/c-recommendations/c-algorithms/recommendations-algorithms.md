---
keywords: algoritmos de recomendaciones;formación sobre modelos;servicio de modelos;entrega de contenido;basado en elementos;basado en usuarios;basado en popularidad;basado en el carro de compras;criterios personalizados
description: Obtenga información acerca de los algoritmos utilizados en [!DNL Target Recommendations], incluidos la formación y el servicio de modelos.
title: La ciencia detrás de los algoritmos de recomendaciones de Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
TQID: 'https://experienceleague.adobe.com/goYsorjFUweT4Aw0XvzQSeiqON7orDcLntZaJliqGl4'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2755'
ht-degree: 0%
---
# La ciencia detrás de los algoritmos de recomendaciones de Target {#recommendations-algorithms}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda cómo funcionan los algoritmos de [!DNL Adobe Target Recommendations], incluidos la lógica y los detalles matemáticos de la formación y el servicio de modelos.

>[!ENDSHADEBOX]

La formación de modelos es el proceso mediante el cual los algoritmos de aprendizaje de [!DNL Adobe Target] generan recomendaciones. El servicio de modelos, también conocido como envío de contenido, es la forma en que [!DNL Target] envía esas recomendaciones a los visitantes del sitio.

[!DNL Target] ofrece los siguientes tipos de algoritmos en [!DNL Recommendations]:

* **Algoritmos basados en elementos**: siga la lógica &quot;Las personas que vieron/compraron este artículo también vieron/compraron estos artículos&quot;. Estos algoritmos se agrupan bajo el término filtrado colaborativo elemento-elemento. Este tipo también incluye los **[!UICONTROL elementos con atributos similares]**.

* **Algoritmos basados en usuarios**: Incluya los algoritmos **[!UICONTROL Elementos vistos recientemente]** y **[!UICONTROL Recomendados para usted]**.

* **Algoritmos basados en popularidad**: devuelve los artículos más visitados o comprados en el sitio web, o por categoría o atributo de artículo.

* **Algoritmos basados en el carro de compras**: haga recomendaciones de varios artículos con la lógica &quot;las personas que vieron o compraron estos artículos también vieron o compraron esos artículos&quot;.

* **Criterios personalizados**: Use archivos personalizados cargados en [!DNL Target] como origen de recomendaciones.

Para obtener más información acerca de cada tipo de algoritmo y sus algoritmos, vea [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Muchos de estos algoritmos dependen de una o más claves, que [!DNL Target] utiliza en el momento de la entrega del contenido (cuando se realizan recomendaciones) para recuperar elementos similares. Las claves especificadas por el cliente pueden ser el artículo actual que el visitante está viendo, el último artículo que vio o compró, el artículo más visitado, la categoría actual o la categoría favorita del visitante. Otros algoritmos, como los basados en el carro de compras y los basados en usuarios, utilizan claves implícitas que el cliente no puede configurar. Para obtener más información, consulte [Claves de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys).

Las claves solo se aplican a la hora de servir el modelo (entrega de contenido). No afectan a la lógica de formación del modelo sin conexión.

Las siguientes secciones agrupan los algoritmos por la similitud de su lógica de formación de modelo, por lo que los grupos difieren ligeramente de los tipos anteriores.

## Filtrado colaborativo elemento-elemento

Los algoritmos incluyen:

* **[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]**
* **[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]**
* **[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]**

Los algoritmos de filtrado colaborativos de elementos utilizan los patrones de comportamiento de muchos usuarios (por lo tanto, colaborativos) para recomendar elementos relacionados con un elemento determinado, lo que filtra el catálogo de elementos posibles. Muchos algoritmos diferentes caen dentro del paraguas general del filtrado colaborativo, y todos ellos utilizan datos de comportamiento como entrada. En [!DNL Target Recommendations], estas entradas son vistas únicas y compras de elementos por parte de los usuarios.

Para los algoritmos de &quot;personas que vieron/compraron este artículo también vieron/compraron estos artículos&quot;, el objetivo es calcular una similitud (A,B) entre todos los pares de artículos. Para un elemento A determinado, las recomendaciones principales son los elementos ordenados por su similitud s(A,B).

Un ejemplo de similitud es la coocurrencia entre elementos: un recuento de los usuarios que compraron ambos elementos. Esta métrica es intuitiva pero ingenua, porque está sesgada hacia la recomendación de artículos populares. Por ejemplo, en un retailer de comestibles donde la mayoría de la gente compra pan, el pan tiene una alta co-ocurrencia con todos los artículos, pero no es necesariamente una buena recomendación. [!DNL Target] utiliza en su lugar la proporción de probabilidad de registro (LLR). Esta cantidad es grande cuando la probabilidad de que dos artículos, A y B, coocurran es muy diferente de la probabilidad de que no coocurran. Por ejemplo, con el algoritmo **[!UICONTROL Personas que vieron esto, compraron aquello]**, la similitud LLR es grande cuando la probabilidad de que alguien haya comprado B es *no* independientemente de si ha visto A.

El artículo B no se recomienda con el artículo A cuando se aplica lo siguiente:

![Fórmula para el algoritmo visto/comprado](/help/main/c-recommendations/c-algorithms/assets/formula.png)

Para obtener todos los detalles del cálculo de similitud de relación de probabilidad de registro, consulte [esta PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

El siguiente diagrama esquemático muestra el flujo lógico de la implementación del algoritmo:

![Diagrama esquemático de un algoritmo visto o comprado](/help/main/c-recommendations/c-algorithms/assets/diagram1.png)

Los pasos son los siguientes:

* **Datos de entrada**: Datos de comportamiento en forma de compras y vistas de visitantes, recopilados al [implementar Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} o desde [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Formación de modelo**:

  * **Limpieza y muestreo de datos**: Para los algoritmos con una retrospectiva de N días, los datos de comportamiento se filtran primero para incluir solo esos N días de datos. A continuación, se aplican reglas de recopilación y exclusiones globales para eliminar cualquier elemento que no deba recomendarse. Por último, los datos de uso de cualquier visitante que haya interactuado con más de 1000 elementos se muestrean hasta 1000 elementos.
  * **Cálculo de similitud de elementos**: El paso de cálculo principal. [!DNL Target] calcula la similitud de la relación de probabilidad logarítmica entre todos los pares de elementos candidatos y clasifica los pares por esta puntuación.
  * **Filtro sin conexión**: se aplican todos los filtros dinámicos aplicables (por ejemplo, exclusiones de categoría dinámica). Las recomendaciones precalculadas se almacenan en la caché global, listas para usarse.

* **Servicio de modelos**: Las recomendaciones se entregan desde la [red global &quot;Edge&quot;](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) de [!DNL Target]. Cuando se realiza una solicitud de mbox a [!DNL Target] y se determina que el contenido de las recomendaciones debe entregarse a la página, la [clave de elemento](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) que necesita el algoritmo se analiza desde la solicitud o se busca desde el perfil del visitante. [!DNL Target] usa esta clave para recuperar las recomendaciones calculadas en los pasos anteriores, aplica más filtros dinámicos y, a continuación, procesa el [diseño](/help/main/c-recommendations/c-design-overview/create-design.md) apropiado.

## Similitud de contenido

Algoritmo incluido:

* **[!UICONTROL Elementos con atributos similares]**

Con este algoritmo, dos elementos están relacionados si sus nombres y descripciones textuales son semánticamente similares. A diferencia de la mayoría de los algoritmos de recomendaciones, que requieren datos de comportamiento, los algoritmos de similitud de contenido derivan la similitud entre los elementos de los metadatos del catálogo de productos. [!DNL Target] puede, por lo tanto, hacer recomendaciones en los llamados escenarios de &quot;inicio en frío&quot;, en los que aún no se han recopilado datos de comportamiento (por ejemplo, al principio de una actividad [!DNL Target]).

Los algoritmos de servicio de modelos y de entrega de contenido para similitud de contenido son idénticos a los de los otros algoritmos basados en elementos. La formación de modelos es muy diferente: implica una serie de pasos de procesamiento y preprocesamiento de lenguaje natural, que se muestran en el siguiente diagrama. El núcleo del cálculo de similitud es la similitud de coseno de los vectores tf-idf modificados que representan cada elemento del catálogo.

![Diagrama que muestra el flujo del proceso de similitud de contenido](/help/main/c-recommendations/c-algorithms/assets/diagram2.png)

Los pasos son los siguientes:

* **Datos de entrada**: este algoritmo solo usa datos de catálogo, ingeridos en [!DNL Target] a través de una fuente de catálogo [la API de entidades o actualizaciones en la página](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank}.

* **Formación de modelo**:

  * **Extracción de atributos**: una vez aplicados los filtros estáticos, las reglas de catálogo y las exclusiones globales, el algoritmo extrae los campos de texto relevantes del esquema de entidad. [!DNL Target] utiliza automáticamente los campos de nombre, mensaje y categoría de los atributos de entidad. También intenta extraer cualquier campo de cadena de los [atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md) personalizados. Un campo se trata como un campo de cadena cuando la mayoría de sus valores no se pueden analizar como un número, fecha o booleano.
  * **Eliminación de secuencias y palabras de detención**: Para que la coincidencia de similitud de texto sea más precisa, [!DNL Target] elimina las palabras &quot;detención&quot; muy comunes que no modifican significativamente el significado de un elemento (por ejemplo, &quot;era&quot;, &quot;es&quot; y &quot;y&quot;). La derivación reduce las palabras con diferentes sufijos a su palabra raíz, que tiene un significado idéntico (por ejemplo, &quot;conectar&quot;, &quot;conectar&quot; y &quot;conexión&quot; tienen la palabra raíz &quot;conectar&quot;). [!DNL Target] utiliza el programa de Snowball. Primero realiza la detección automática del idioma y puede eliminar las palabras de detención hasta en 50 idiomas y realizar la derivación para 18 idiomas.
  * **Creación de n-gramas**: Después de los pasos anteriores, cada palabra se trata como un token. La combinación de secuencias contiguas de tokens en un único token se denomina creación de n-gramas. [!DNL Target] considera hasta 2 gramos.
  * **cálculo de tf-idf**: en el siguiente paso se crean vectores de tf-idf que reflejan la importancia relativa de los tokens en la descripción del elemento. Para cada token o término t de un elemento i, en un ID de catálogo con |D| elementos, [!DNL Target] calcula primero el término frecuencia TF(t, i), que es el número de veces que el término aparece en el elemento i, y la frecuencia del documento DF(t, D), que es el número de elementos en los que existe el token t. La medida tf-idf es entonces:

    ![Fórmula que muestra la medida tf-idf](/help/main/c-recommendations/c-algorithms/assets/formula2.png)

    [!DNL Target] usa la implementación de característica *tf-idf* de Apache Spark, que vincula cada token con un espacio de 2<sup>18</sup> tokens. En este paso, también se aplica el atributo de ampliación y enterramiento especificado en [criteria](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity), ajustando las frecuencias de los términos en cada vector.

  * **Cálculo de similitud de elemento**: La similitud de elemento final se calcula con una similitud de coseno aproximada. Para dos elementos, *A* y *B*, con los vectores tA y tB, la similitud de coseno se define como:

    ![Fórmula que muestra el cálculo de similitud de elementos](/help/main/c-recommendations/c-algorithms/assets/formula3.png)

    Para evitar la complejidad significativa de calcular similitudes entre todos los elementos N x N, el vector *tf-idf* se trunca a sus 500 entradas más grandes y las similitudes de coseno entre los elementos se calculan a partir de esta representación truncada. Este enfoque es más robusto para cálculos de similitud de vectores dispersos que otras técnicas aproximadas de vecino más cercano (ANN), como el hashing sensible a la localidad.

* **Modelo sirviendo**: Este proceso es idéntico al del filtrado colaborativo elemento-elemento descrito en la sección anterior.

## Recomendaciones de claves múltiples

Los algoritmos incluyen:

* Recomendaciones basadas en el carro de compras
* **[!UICONTROL Recomendado para usted]**

**[!UICONTROL Recomendado para usted]** y los algoritmos basados en el carro de compras utilizan técnicas de filtrado colaborativas para formar recomendaciones individuales basadas en elementos. En el momento del servicio, se usan varios elementos como claves para recuperar estas recomendaciones basadas en elementos: los elementos en el historial de navegación del visitante (para **[!UICONTROL Recomendado para ti]**) o en el carro de compras actual del visitante (para recomendaciones basadas en el carro de compras). Las recomendaciones recuperadas se combinan para formar la lista final. Con un algoritmo de claves múltiples, las recomendaciones están disponibles en cuanto un visitante tiene historial de navegación y se actualizan para reflejar el comportamiento del visitante más reciente.

Estos algoritmos se basan en las técnicas de filtrado colaborativas descritas en la sección de recomendaciones basadas en elementos y también utilizan la optimización de hiperparámetros para determinar la métrica de similitud óptima entre los elementos. El algoritmo divide cronológicamente los datos de comportamiento de cada usuario y entrena los modelos de recomendación en los datos anteriores, a la vez que intenta predecir los elementos que el usuario ve o compra más adelante. A continuación, se elige la métrica de similitud con la mejor precisión media media.

El diagrama siguiente muestra la lógica de los pasos de formación y puntuación del modelo:

![Diagrama que muestra la lógica de los pasos de entrenamiento y puntuación del modelo](/help/main/c-recommendations/c-algorithms/assets/diagram3.png)

Los pasos son los siguientes:

* **Datos de entrada**: idénticos a los métodos de filtrado colaborativo (CF) de elementos. Los algoritmos de **[!UICONTROL Recomendado para ti]** y basados en el carro de compras usan datos de comportamiento en forma de compras y vistas de usuarios, recopilados al [implementar Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} o desde [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Formación de modelo**:

  * **Limpieza y muestreo de datos**: Igual que para los métodos de filtrado de colaboración. La ventana retrospectiva filtra los datos de comportamiento a un intervalo de fechas adecuado, y luego se aplican las reglas de catálogo y las exclusiones globales. Para los visitantes que interactuaron con más de 1000 elementos, solo se tienen en cuenta los 1000 usos más recientes.
  * **División de prueba de tren**: los usos de cada usuario se dividen cronológicamente. El primer 80 % se asigna a los datos de formación y el 20 % restante a los datos de prueba.
  * **Aprendizaje del modelo de similitud de elementos**: el cálculo de similitud de elementos principal difiere entre **[!UICONTROL Recomendado para usted]** y Basado en el carro de compras en la forma en que se construyen los vectores de elementos candidatos. Para **[!UICONTROL Recomendado para usted]**, los vectores de elementos tienen usuarios de dimensión y cada entrada es la suma de las clasificaciones implícitas que el usuario le dio al elemento. Las compras tienen un peso del doble que las vistas. Para las recomendaciones basadas en el carro de compras, los vectores de elementos tienen entradas binarias. Si solo se considera el comportamiento dentro de la sesión, hay una entrada para cada sesión. De lo contrario, hay una entrada por cada visitante.

    El paso de aprendizaje calcula varios tipos de similitudes vectoriales: similitud LLR ([vea el PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), similitud coseno (definida anteriormente) y una similitud L2 normalizada, definida como:

    ![Fórmula que muestra cálculo de formación](/help/main/c-recommendations/c-algorithms/assets/formula4.png)

  * **Evaluación del modelo de similitud de elementos**: Las recomendaciones generadas en el paso anterior se evalúan realizando predicciones sobre el conjunto de datos de prueba. La fase de puntuación en línea se imita ordenando cronológicamente los usos de los elementos de cada usuario en el conjunto de datos de prueba y, a continuación, realizando 100 recomendaciones para subconjuntos de elementos ordenados a fin de predecir las vistas y compras posteriores. La calidad de estas recomendaciones se evalúa con la precisión media media, una métrica de recuperación de información. Esta métrica tiene en cuenta el orden de las recomendaciones y favorece los elementos relevantes que se encuentran más arriba en la lista, lo que es una propiedad importante para los sistemas de clasificación.
  * **Selección de modelo**: después de la evaluación sin conexión, se selecciona el modelo con la precisión media media más alta y se calculan para él todas las recomendaciones de elementos individuales.
  * **Filtrado sin conexión**: la fase final del aprendizaje del modelo aplica los filtros dinámicos aplicables. Las recomendaciones precalculadas se almacenan en la caché global, listas para usarse.

* **Servicio de modelos**: a diferencia de los algoritmos anteriores, que especifican una sola clave para recuperarla y luego aplican reglas empresariales, **[!UICONTROL Recomendado para usted]** y Basado en el carro de compras utilizan un proceso de tiempo de ejecución más complejo:

  * **Recuperación y combinación de varias claves**: Para las recomendaciones basadas en el carro de compras, se usan hasta diez elementos pasados en el carro de compras como claves para la recuperación, y las recomendaciones de cada clave se ponderan de forma equitativa. Para **[!UICONTROL Recomendado para ti]**, hasta los últimos cinco artículos vistos únicos y los últimos cinco artículos comprados únicos se usan como claves, y las recomendaciones de artículos comprados se ponderan el doble que las de artículos vistos. Cuando se combinan recomendaciones, se agregan las puntuaciones de similitud ponderada de un elemento que aparece en varias listas. El resultado es la lista combinada de recomendaciones ponderadas de nuevo, clasificadas en orden descendente.
  * **Filtrado**: A continuación, se aplican reglas de filtrado, como la eliminación de elementos previamente vistos o comprados, y otras reglas comerciales dinámicas.

La siguiente imagen ilustra estos procesos para un visitante que vio el elemento A y compró el elemento B. Las recomendaciones individuales se recuperan con las puntuaciones de similitud sin conexión que se muestran debajo de cada etiqueta de elemento y, a continuación, se combinan con las puntuaciones de similitud ponderadas sumadas. Por último, cuando el cliente ha especificado que los artículos vistos y comprados anteriormente deben filtrarse, el paso de filtrado elimina los artículos A y B de la lista de recomendaciones.

![Diagrama que muestra el procesamiento de algoritmos de claves múltiples](/help/main/c-recommendations/c-algorithms/assets/diagram4.png)

## Basado en popularidad

Los algoritmos incluyen:

* **[!UICONTROL Más visitados en todo el sitio]**
* **[!UICONTROL Más visitados por categoría]**
* **[!UICONTROL Más visitados por atributo de artículo]**
* **[!UICONTROL Más visitados por atributo de perfil]**
* **[!UICONTROL Principales vendedores en todo el sitio]**
* **[!UICONTROL Principales vendedores por categoría]**
* **[!UICONTROL Principales vendedores por atributo de artículo]**
* **[!UICONTROL Principales vendedores por atributo de perfil]**

[!DNL Target] proporciona algoritmos basados en la popularidad para los artículos más vistos y para los artículos más vendidos, ya sea en el sitio web o desglosados por un atributo o categoría de artículo. Estos algoritmos clasifican los elementos según el número de sesiones en las que se vieron o compraron en un lapso de tiempo determinado.

Todos estos algoritmos combinan datos de comportamiento agregados que registran el número total de sesiones en las que se vieron y compraron artículos, con resoluciones horarias y diarias. A continuación, cada algoritmo encuentra los artículos más vistos o comprados para la ventana retrospectiva configurada por el cliente.

Los algoritmos difieren de la siguiente manera:

* Los **[!UICONTROL más visitados en todo el sitio]** y los **[!UICONTROL principales vendedores en todo el sitio]** clasifican los elementos según el recuento agregado de sesiones en las que se vieron o compraron los elementos, respectivamente. El resultado es una lista única (sin clave) de elementos recomendados.
* Los más visitados y los más vendidos por categoría o atributo de artículo también ordenan artículos según los recuentos de sesión agregados, pero los agrupan por categoría de artículo o por un atributo de artículo específico. El resultado son listas de artículos recomendados, marcadas por los valores de las categorías o atributos de artículos.
* **[!UICONTROL Más visitados por atributo de perfil]** y **[!UICONTROL Principales vendedores por atributo de perfil]** también clasifican elementos por recuento de compras o vistas agregadas, pero se agrupan por un atributo de perfil de visitante, como país, región o nivel de pertenencia, en lugar de por propiedad de elemento. El recuento de cada sesión se atribuye al valor de perfil que el visitante tenía en el momento de la interacción, no a ningún atributo del elemento. El resultado es un conjunto de listas de recomendación marcadas por los distintos valores de ese atributo de perfil.

## Vistos recientemente

El algoritmo &quot;Vistos recientemente&quot; proporciona una personalización de las recomendaciones durante la sesión. No requiere formación de modelos sin conexión. En su lugar, [!DNL Target] usa el [perfil del visitante](/help/main/c-target/c-visitor-profile/visitor-profile.md) único para mantener una lista en ejecución de los elementos vistos en una sesión y puede mostrarlos en las actividades de Recommendations. Esto permite realizar actualizaciones en tiempo real de las recomendaciones y la personalización de la página siguiente.

## Criterios personalizados

Los criterios personalizados permiten a los clientes [cargar sus propias recomendaciones en Target](/help/main/c-recommendations/c-algorithms/recommendations-csv.md), lo que proporciona flexibilidad y permite capacidades de &quot;traer su propio modelo&quot;. Los criterios personalizados reemplazan la parte de aprendizaje sin conexión de las recomendaciones **[!UICONTROL basadas en elementos]**. Durante la entrega de contenido en línea, se comportan como los algoritmos basados en elementos: se utiliza una sola clave para recuperar recomendaciones y, a continuación, se aplican reglas y filtros empresariales.
