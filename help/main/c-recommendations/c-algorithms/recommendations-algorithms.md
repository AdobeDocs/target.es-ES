---
keywords: algoritmos de recomendaciones;formación sobre modelos;servicio de modelos;entrega de contenido;basado en elementos;basado en usuarios;basado en popularidad;basado en el carro de compras;criterios personalizados
description: Obtenga información acerca de los algoritmos utilizados en [!DNL Target Recommendations], incluidos la formación y el servicio de modelos.
title: ¿Dónde puedo obtener información acerca de la ciencia detrás de los algoritmos Recommendations de Target?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '2842'
ht-degree: 1%

---

# La ciencia detrás de los algoritmos de recomendaciones de Target

Una descripción detallada de los algoritmos utilizados en [!DNL Adobe Target Recommendations], incluidos los detalles lógicos y matemáticos de la formación de modelos y el proceso de servicio de modelos.

La formación de modelos es el proceso de generación de recomendaciones mediante [!DNL Adobe Target] algoritmos de aprendizaje. El servicio de modelos es cómo [!DNL Target] envía recomendaciones a los visitantes del sitio (también conocidas como entrega de contenido).

[!DNL Target] incluye los siguientes tipos generales de algoritmos en [!DNL Recommendations]:

* **Algoritmos basados en elementos**: Incluir algoritmos que sigan la lógica &quot;Las personas que vieron/compraron este artículo también vieron/compraron estos artículos&quot;. Estos algoritmos se agrupan bajo el término general de filtrado colaborativo elemento-elemento, así como [!UICONTROL Artículos con atributos similares] algoritmos.

* **Algoritmos basados en usuarios**: Incluya el [!UICONTROL Vistos recientemente] y [!UICONTROL Recomendado para usted] algoritmos.

* **Algoritmos basados en popularidad**: incluye algoritmos que devuelven los artículos más visitados o comprados en el sitio web, o los más visitados o los más comprados por categoría o atributo de artículo.

* **Algoritmos basados en el carro de compras**: incluya recomendaciones basadas en varios artículos con la lógica &quot;las personas que vieron o compraron estos artículos, también vieron o compraron esos artículos&quot;.

* **Criterios personalizados**: Incluir recomendaciones basadas en archivos personalizados cargados en [!DNL Target].

>[!NOTE]
>
>Para obtener información más general sobre cada tipo de algoritmo y los algoritmos individuales, consulte [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Muchos de los algoritmos enumerados arriba se basan en la presencia de una o varias claves. Estas claves se utilizan para recuperar artículos similares en el momento de la entrega de contenido (cuando se realizan recomendaciones). Las claves especificadas por el cliente pueden incluir el artículo actual que alguien está viendo, el último artículo que vio o compró, el artículo más visitado, la categoría actual o la categoría favorita de ese visitante. Otros algoritmos, como las recomendaciones basadas en el carro de compras o en las recomendaciones basadas en usuarios, utilizan claves implícitas (que el cliente no puede configurar). Para obtener más información, consulte *Claves de recomendación*, en [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). Sin embargo, tenga en cuenta que estas claves solo son relevantes a la hora de servir el modelo (entrega de contenido). Estas claves no afectan a la lógica del tiempo de formación del modelo o sin conexión.

Las secciones siguientes agrupan los algoritmos de una manera ligeramente diferente a los tipos de algoritmo descritos anteriormente. La siguiente agrupación se basa en la similitud de la lógica de formación del modelo.

## Filtrado colaborativo elemento-elemento

Los algoritmos incluyen:

* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]

Los algoritmos de recomendación de filtrado colaborativos elemento-elemento se basan en la idea de que debe utilizar los patrones de comportamiento de muchos usuarios (por lo tanto, colaborativos) para proporcionar recomendaciones útiles para un elemento determinado (por ejemplo, filtrar el catálogo de posibles elementos para recomendar). Aunque hay muchos algoritmos diferentes que caen bajo el paraguas general de [filtrado colaborativo](https://en.wikipedia.org/wiki/Collaborative_filtering)Sin embargo, estos algoritmos utilizan universalmente fuentes de datos de comportamiento como entradas. Entrada [!DNL Target Recommendations]Sin embargo, estas entradas son las vistas y compras únicas de elementos realizadas por los usuarios.

Para el algoritmo &quot;las personas que vieron/compraron este artículo también vieron/compraron estos artículos&quot;, el objetivo es calcular una similitud (A,B) entre todos los pares de artículos. Para un elemento A determinado, las recomendaciones principales se ordenan por su similitud s(A,B).

Un ejemplo de esta similitud es la coocurrencia entre artículos: un recuento simple del número de usuarios que compraron ambos artículos. Aunque intuitiva, esta métrica es ingenua, ya que está sesgada hacia la recomendación de artículos populares. Por ejemplo, si en un minorista de comestibles la mayoría de la gente compra pan, el pan tendrá una alta coocurrencia con todos los artículos, pero no es necesariamente una buena recomendación. [!DNL Target] en su lugar, utiliza una métrica de similitud más sofisticada conocida como proporción de probabilidad de registro (LLR). Esta cantidad es grande cuando la probabilidad de que dos artículos, A y B, coocurran es muy diferente a la probabilidad de que no ocurran. Para ser más concretos, considere un caso de [!UICONTROL Los ususarios que vieron esto, compraron aquello.] algoritmo. La similitud LLR es grande cuando la probabilidad de que B se haya comprado es *no* independientemente de si alguien vio A.

Por ejemplo, si

![Fórmula para el algoritmo visto/comprado](assets/formula.png)

entonces el artículo B no se debe recomendar con el artículo A. Se proporcionan todos los detalles de este cálculo de similitud de relación de probabilidad de registro [en este PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

El flujo lógico de la implementación del algoritmo real se muestra en el siguiente diagrama esquemático:

![Diagrama esquemático de un algoritmo visto/comprado](assets/diagram1.png)

Los detalles de estos pasos son los siguientes:

* **Datos de entrada**: Datos de comportamiento en forma de vistas y compras de visitantes recopilados al [implementación de Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Formación de modelo**:

   * **Limpieza y muestreo de datos**: Para los algoritmos con una retrospectiva de N días, los datos de comportamiento se filtran primero para incluir solo esos N días de datos. A continuación, se aplican reglas de recopilación y exclusiones globales para eliminar cualquier elemento que no deba recomendarse. Por último, los datos de uso de cualquier visitante que haya interactuado con más de 1000 elementos se han muestreado a solo 1000 elementos.
   * **Cálculo de similitud de elemento**: Este es el paso computacional central: calcular la similitud de la relación de probabilidad de registro entre todos los pares de elementos candidatos y clasificar los pares de elementos por esta puntuación de similitud.
   * **Filtrado sin conexión**: Finalmente, se aplican todos los filtros dinámicos aplicables adicionales (por ejemplo, exclusiones de categoría dinámica). Después de este paso, las recomendaciones precalculadas se almacenan en la caché global para que estén disponibles para su servicio.

* **Servicio de modelo**: el contenido de Recommendations se entrega desde [!DNL Target]de [red global &quot;Edge&quot;](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934). Cuando se realizan solicitudes de mbox a [!DNL Target] y se determina que el contenido de las recomendaciones debe entregarse a la página, en la solicitud del correspondiente [clave de elemento](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) para el algoritmo de recomendaciones se analiza desde la solicitud o se busca desde el perfil de usuario y, a continuación, se utiliza para recuperar las recomendaciones calculadas en los pasos anteriores. Se aplican más filtros dinámicos en este momento, antes de la [diseño](/help/main/c-recommendations/c-design-overview/create-design.md) se procesa.

## Similitud de contenido

Algoritmo incluido:

* [!UICONTROL Artículos con atributos similares]

En este tipo de algoritmo, dos elementos se consideran relacionados si sus nombres y descripciones textuales son semánticamente similares. A diferencia de la mayoría de los algoritmos de recomendaciones en los que se deben utilizar fuentes de datos de comportamiento, los algoritmos de similitud de contenido utilizan metadatos de catálogos de productos para derivar la similitud entre los elementos. [!DNL Target] por lo tanto, puede impulsar recomendaciones en los llamados escenarios de &quot;inicio en frío&quot;, en los que no se han recopilado datos de comportamiento (por ejemplo, al principio de una [!DNL Target] actividad).

Aunque el modelo sirve y entrega de contenido aspectos de [!DNL Target]Los algoritmos de similitud de contenido de son idénticos a otros algoritmos basados en elementos. Los pasos de aprendizaje del modelo son drásticamente diferentes e implican una serie de pasos de procesamiento y preprocesamiento de lenguaje natural, como se muestra en el siguiente diagrama. El núcleo del cálculo de similitud es el uso de la similitud de coseno de vectores tf-idf modificados que representan cada elemento del catálogo.

![Diagrama que muestra el flujo del proceso de similitud de contenido](assets/diagram2.png)

Los detalles de estos pasos son los siguientes:

* **Datos de entrada**: Como se ha descrito anteriormente, este algoritmo se basa exclusivamente en los datos del catálogo (introducidos en [!DNL Target] mediante una [Fuente de catálogo, API de entidades o desde actualizaciones en la página](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank}.

* **Formación de modelo**:

   * **Extracción de atributos**: Después de la aplicación de filtros estáticos regulares, reglas de catálogo y exclusiones globales, este algoritmo extrae campos de texto relevantes del esquema de entidad. [!DNL Target] utiliza automáticamente los campos nombre, mensaje y categoría de los atributos de entidad e intenta extraer cualquier campo de cadena de los campos personalizados [atributos de entidad](/help/main/c-recommendations/c-products/entity-attributes.md). Este proceso se realiza asegurándose de que la mayoría de los valores de ese campo no se puedan analizar como números, fechas o booleanos.
   * **Eliminación de vértices y palabras de parada**: para conseguir una coincidencia de similitud de texto más precisa, es prudente quitar las palabras muy comunes &quot;detener&quot; que no alteran significativamente el significado de un elemento (por ejemplo, &quot;era&quot;, &quot;es&quot;, &quot;y&quot;, etc.). Del mismo modo, la derivación se refiere al proceso de reducir las palabras con diferentes sufijos a su palabra raíz, que tiene un significado idéntico (por ejemplo, &quot;conectar&quot;, &quot;conectar&quot; y &quot;conexión&quot; tienen la misma palabra raíz: &quot;conectar&quot;). [!DNL Target] utiliza el programa Snowball. [!DNL Target] realiza primero la detección automática de idiomas y puede detener la eliminación de palabras en hasta 50 idiomas y la derivación en 18 idiomas.
   * **Creación de n-gramas**: Después de los pasos anteriores, cada palabra se trata como un token. El proceso de combinar secuencias contiguas de tokens en un único token se denomina creación de n-gramas. [!DNL Target]Los algoritmos de consideran hasta 2 gramos.
   * **cálculo de tf-idf**: El siguiente paso implica la creación de vectores tf-idf para reflejar la importancia relativa de los tokens en la descripción del elemento. Para cada token/término t de un elemento i, en un ID de catálogo con |D| elementos, el término frecuencia TF(t, i) se calcula primero (el número de veces que el término aparece en el elemento i), así como la frecuencia del documento DF(t, D). En esencia, el número de elementos donde existe el token. La medida tf-idf es entonces

      ![Fórmula que muestra la medida tf-idf](assets/formula2.png)

      [!DNL Target] utiliza Apache Spark *tf-idf* implementación de funcionalidades, que bajo el capó vincula cada token con un espacio de 218 tokens. En este paso, también se aplica la ampliación y el enterramiento de atributos especificados por el cliente ajustando las frecuencias de los términos en cada vector en función de la configuración especificada en la variable [criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **Cálculo de similitud de elemento**: el cálculo de similitud del elemento final se realiza mediante una similitud de coseno aproximada. Para dos elementos, *A* y *B*, con los vectores tA y tB, la similitud del coseno se define como:

      ![Fórmula que muestra el cálculo de similitud de artículos](assets/formula3.png)

      Para evitar una complejidad significativa al calcular similitudes entre todos los elementos N x N, la variable *tf-idf* el vector se trunca para contener sólo sus 500 entradas más grandes y, a continuación, calcular las similitudes de coseno entre los elementos utilizando esta representación vectorial truncada. Este enfoque resulta más robusto para cálculos de similitud de vectores dispersos, en comparación con otras técnicas aproximadas de vecino más cercano (ANN), como el hashing sensible a la localidad.

   * **Servicio de modelo**: Este proceso es idéntico a las técnicas de filtrado colaborativo elemento-elemento descritas en la sección anterior.

## Recomendaciones de claves múltiples

Los algoritmos incluyen:

* Recomendaciones basadas en el carro de compras
* [!UICONTROL Recomendado para usted]

Las adiciones más recientes a la [!DNL Target] el conjunto de algoritmos de recommendations son [!UICONTROL Recomendado para usted] y una serie de algoritmos de recomendaciones basados en el carro de compras. Ambos tipos de algoritmos utilizan técnicas de filtrado colaborativas para formar recomendaciones individuales basadas en elementos. A continuación, en el momento del servicio, varios elementos en el historial de navegación del usuario (por ejemplo, [!UICONTROL Recomendado para usted]), o el carro de compras actual del usuario (para recomendaciones basadas en el carro de compras) se usan para recuperar estas recomendaciones basadas en elementos, que luego se combinan para formar la lista final de recomendaciones. Tenga en cuenta que existen muchos tipos de algoritmos de recomendación personalizados. La elección de un algoritmo de claves múltiples significa que las recomendaciones están disponibles inmediatamente después de que un visitante tenga un historial de navegación y que las recomendaciones se puedan actualizar para responder al comportamiento del visitante más reciente.

Estos algoritmos se basan en las técnicas de filtrado colaborativas básicas descritas en la sección de recomendaciones basadas en elementos, pero también incorporan ajustes de hiperparámetros para determinar la métrica de similitud óptima entre los elementos. El algoritmo realiza una división cronológica de los datos de comportamiento de cada usuario y entrena los modelos de recomendación en los datos anteriores al intentar predecir los elementos que un usuario ve o compra más tarde. La métrica de similitud que produce el óptimo [Precisión media media](A continuación, se elige https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval).

La lógica del aprendizaje del modelo y los pasos de puntuación se muestran en el siguiente diagrama:

![Diagrama que muestra la lógica del aprendizaje del modelo y los pasos de puntuación](assets/diagram3.png)

Los detalles de estos pasos son los siguientes:

* **Datos de entrada**: Es idéntico a los métodos de filtrado colaborativo (CF) entre elementos. [!UICONTROL Ambos Recomendados Para Usted] y los algoritmos basados en el carro de compras utilizan datos de comportamiento en forma de vistas y compras de usuarios recopilados al [implementación de Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Formación de modelo**:

   * **Limpieza y muestreo de datos**: Esto es igual que para los métodos de filtrado colaborativos, donde la ventana retrospectiva se aplica para filtrar los datos de comportamiento a un intervalo de fechas adecuado, seguido de la aplicación de reglas de catálogo y exclusiones globales. Los visitantes que han interactuado con más de 1000 elementos solo tienen en cuenta sus 1000 usos más recientes.
   * **División de prueba del tren**: realice una división cronológica de los usos de cada usuario, asignando el primer 80 % de sus usos a los datos de formación, y el 20 % restante a los datos de prueba.
   * **Formación del modelo de similitud de elementos**: el cálculo de similitud de elementos principales difiere para [!UICONTROL Recomendado para usted] y los algoritmos basados en el carro de compras en la forma en que se construyen los vectores de elementos candidatos. Para [!UICONTROL Recomendado para usted]Sin embargo, los vectores de elementos tienen usuarios NU de dimensión, donde cada entrada representa la suma de clasificaciones implícitas para ese usuario del elemento: las compras de un elemento tienen un peso del doble que las vistas del elemento. Para las recomendaciones basadas en el carro de compras, los vectores de elementos tienen entradas binarias; si solo se debe considerar el comportamiento dentro de la sesión, hay una nueva entrada para cada sesión. De lo contrario, hay una entrada en este vector de elemento para cada visitante.

   El paso de formación calcula varios tipos de similitudes vectoriales: Similitud LLR ([discutido aquí](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), similitud de coseno (definida anteriormente) y una similitud de L2 normalizada, definida como:

   ![Fórmula que muestra cálculo de formación](assets/formula4.png)

   * **Evaluación del modelo de similitud de elementos**: la evaluación del modelo se realiza tomando las recomendaciones generadas en el paso anterior y haciendo predicciones sobre el conjunto de datos de prueba. La fase de puntuación en línea se imita ordenando cronológicamente los usos de los elementos de cada usuario en el conjunto de datos de prueba y, a continuación, realizando 100 recomendaciones para subconjuntos de elementos ordenados en un intento de predecir vistas y compras posteriores. Una métrica de recuperación de información, la [Precisión media media](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)) se utiliza para evaluar la calidad de estas recomendaciones. Esta métrica tiene en cuenta el orden de las recomendaciones y favorece los elementos relevantes que están más arriba en la lista de recomendaciones, lo que es una propiedad importante para los sistemas de clasificación.
   * **Selección de modelo**: después de la evaluación sin conexión, se selecciona el modelo que tiene la precisión media media más alta y se calculan todas las recomendaciones de elementos individuales para él.
   * **Filtrado sin conexión**: la etapa final del aprendizaje del modelo es la aplicación de cualquier filtro dinámico aplicable. Después de este paso, las recomendaciones precalculadas se almacenan en la caché global para que estén disponibles para su servicio.


* **Servicio de modelo**: A diferencia de los algoritmos anteriores en los que las recomendaciones de servicio implican la especificación de una sola clave para la recuperación, seguida de la aplicación de reglas empresariales, la variable [!UICONTROL Recomendado para usted] y los algoritmos basados en el carro de compras emplean un proceso de tiempo de ejecución más complejo.

   * **Recuperación y combinación de varias claves**: Para las recomendaciones basadas en el carro de compras, hasta diez artículos que se pasan en el carro de compras se consideran claves para la recuperación y las recomendaciones de cada uno se ponderan de forma equitativa. Para [!UICONTROL Recomendado para usted]Sin embargo, hasta los últimos cinco artículos vistos únicos y los últimos cinco artículos comprados únicos se consideran claves para la recuperación, con recomendaciones que surgen de artículos comprados ponderados el doble que las recomendaciones que surgen de artículos vistos. Al combinar recomendaciones, si un elemento aparece en varias listas individuales de recomendaciones, se añaden sus puntuaciones de similitud ponderadas. La lista final de recomendaciones de esta fase es la lista combinada de recomendaciones ponderadas de nuevo, clasificadas en orden descendente.
   * **Filtrado**: a continuación, se aplican reglas de filtrado como la eliminación de los elementos vistos o comprados anteriormente, así como otras reglas comerciales dinámicas.

Estos procesos se ilustran en la siguiente imagen, donde un visitante ha visto el elemento A y ha comprado el elemento B. Las recomendaciones individuales se recuperan con las puntuaciones de similitud sin conexión que se muestran debajo de cada etiqueta de elemento. Después de la recuperación, las recomendaciones se combinan con puntuaciones de similitud ponderadas sumadas. Por último, en un escenario en el que el cliente haya especificado que los artículos vistos y comprados anteriormente deben filtrarse, el paso de filtrado elimina los artículos A y B de la lista de recomendaciones.

![Diagrama que muestra el procesamiento de algoritmos de varias claves](assets/diagram4.png)

## Basado en popularidad

Los algoritmos incluyen:

* [!UICONTROL Más visitados en todo el sitio]
* [!UICONTROL Más visitados por categoría]
* [!UICONTROL Más visitados por atributo de artículo]
* [!UICONTROL Principales vendedores en todo el sitio]
* [!UICONTROL Principales vendedores por categoría]
* [!UICONTROL Principales vendedores por atributo de artículo]

[!DNL Target] proporciona algoritmos basados en la popularidad para los artículos más vistos, así como para los artículos más vendidos en un sitio web o desglosados por atributo o categoría de artículo. Los algoritmos basados en popularidad clasifican los elementos según el número de sesiones en las que se vieron o compraron en un lapso de tiempo determinado.

Todos estos algoritmos combinan datos de comportamiento agregados donde el número total de sesiones en las que se vieron y compraron artículos se registra tanto a resoluciones horarias como diarias. A continuación, los algoritmos individuales buscan los artículos más vistos o comprados para la ventana retrospectiva configurada por el cliente.

Los matices de algoritmo individuales son los siguientes:

* [!UICONTROL Más visitados en todo el sitio] y [!UICONTROL Principales vendedores en todo el sitio] clasifique los elementos según el recuento total de sesiones en las que se vieron o compraron respectivamente. El resultado es una lista única (sin clave) de elementos recomendados.
* Los artículos más visitados/más vendidos por categoría/atributo de artículo son recomendaciones en las que los artículos se ordenan según el recuento acumulado de sesiones en las que se vieron o compraron, pero agrupados por la categoría del artículo o el atributo del artículo específico. Los resultados son listas de elementos recomendados, escritas por valores de categorías o valores de atributos de elementos.

## Vistos recientemente

El algoritmo de recomendaciones &quot;vistas recientemente&quot; permite la personalización de recomendaciones en la sesión. Este algoritmo no requiere &quot;formación de modelo&quot; sin conexión. En su lugar, [!DNL Target] utiliza el único [Perfil del visitante](/help/main/c-target/c-visitor-profile/visitor-profile.md) para mantener una lista en ejecución de los elementos que se han visto en una sesión determinada y que pueden aparecer en las actividades de recommendations. Esto permite realizar actualizaciones en tiempo real de las recomendaciones y la personalización de la página siguiente.

## Criterios personalizados

Los criterios personalizados permiten a los clientes lo siguiente [cargar sus propias recomendaciones en [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md), lo que proporciona una flexibilidad importante y permite capacidades de &quot;traer su propio modelo&quot;. Los criterios personalizados sustituyen la parte &quot;formación sin conexión&quot; de [!UICONTROL Basado en elementos] Las recomendaciones de, pero se comportan de manera similar a los algoritmos de recomendación basados en elementos durante la fase de entrega de contenido en línea, en el sentido de que se utiliza una sola clave para la recuperación de recomendaciones y luego se aplican reglas/filtros empresariales.
