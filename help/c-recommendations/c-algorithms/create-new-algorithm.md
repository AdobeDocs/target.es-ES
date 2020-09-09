---
keywords: criteria;algorithm;industry vertical;page type;recommendation key;recommendation logic;logic;data range;behavior data source;partial design;backup recommendations;inclusion rules;attribute weighting;
description: Los criterios controlan el contenido de sus actividades de Adobe Recommendations. Cree criterios para mostrar las recomendaciones que más se ajusten a su actividad.
title: Crear criterios
feature: criteria
uuid: 603d4b02-cdb6-40aa-9654-0086c23b0c8e
translation-type: tm+mt
source-git-commit: 250cf8be318cf67257b822b62dc81dfcce0fe88b
workflow-type: tm+mt
source-wordcount: '3609'
ht-degree: 85%

---


# ![PREMIUM](/help/assets/premium.png) Crear criterios{#create-criteria}

Los criterios controlan el contenido de sus actividades de [!UICONTROL Recomendaciones]. Cree criterios para mostrar las recomendaciones que más se ajusten a su actividad.

## Crear nuevos criterios

Las siguientes secciones explican cómo crear un nuevo criterio.

### Acceso a la pantalla Crear nuevo criterio

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* When you are creating a [!DNL Recommendations] activity, click **[!UICONTROL Create Criteria]** on the [!UICONTROL Select Criteria] screen. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!DNL Recommendations].
* Cuando esté editando una [!DNL Recommendations]actividad, haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!DNL Recommendations].

Los pasos siguientes suponen que accede a la pantalla [!UICONTROL Crear nuevo criterio] mediante el primer método: la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]** .

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

   ![Crear nuevos criterios](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

### Complete la sección Información básica {#info}

1. Escriba un **[!UICONTROL Nombre de criterio]**.

   Es el nombre “interno” que se usa para describir los criterios. Por ejemplo, quizá use el nombre “Productos con más margen” para los criterios, pero es probable que no quiera que ese título se muestre al público. Consulte el paso siguiente para establecer el título que se presenta al público.

   ![Sección Información básica](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Escriba un **[!UICONTROL Título]** que se mostrará a la audiencia para que aparezca en la página para todas las recomendaciones que usen este criterio.

   Por ejemplo, una idea es mostrar “Las personas que han visto esto también vieron” o “Productos similares” cuando use estos criterios para mostrar recomendaciones.

1. Escriba una breve **[!UICONTROL Descripción]** del criterio.

   La descripción debería ayudarle a identificar los criterios y podría incluir información sobre el propósito de los mismos.

1. Seleccione un **[!UICONTROL Segmento de mercado vertical]**:

   * [!UICONTROL Venta minorista/Comercio electrónico]
   * [!UICONTROL Generación de vanguardia/B2B/Servicios financieros]
   * [!UICONTROL Medios/Publicación]

   Otras opciones de criterios cambiarán según el sector que seleccione.

1. Seleccione un **[!UICONTROL Tipo de página]**.

   Puede seleccionar varios tipos de página.

   En conjunto, el sector y los tipos de página se usan para categorizar los criterios guardados, facilitando su reutilización para otras actividades de [!DNL Recommendations].

1. Seleccione una **[!UICONTROL Clave de recomendación]**.

   Para obtener más información sobre cómo basar los criterios en una clave, consulte [Basar la recomendación en una clave de recomendación](#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

1. Seleccione la **[!UICONTROL Lógica de recomendación]**.

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](../../c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

### Especifique las opciones de fuente de datos

1. Establezca el **[!UICONTROL Intervalo de fechas]** para determinar el intervalo de fechas del historial de datos de comportamiento del usuario, para usarlo cuando determine qué recomendaciones mostrar.

   ![Control deslizante de rango de datos](/help/c-recommendations/c-algorithms/assets/data-range.png)

   Si el sitio tiene mucho tráfico y los comportamientos cambian con frecuencia, elija un período de datos más breve. Un periodo más breve permite a [!DNL Recommendations]responder mejor a los cambios del mercado y de su empresa. Por ejemplo, un periodo breve significa que [!DNL Recommendations]detectará cambios en el comportamiento de los visitantes a medida que estos comiencen a realizar compras de temporada, como las compras de vuelta al colegio o las compras navideñas, y recomendará artículos apropiados para esas temporadas.

   Si no dispone de muchos datos o el comportamiento de los visitantes no cambia con frecuencia, puede elegir un período de tiempo más largo. Sin embargo, para muchos sitios, un período más corto permite ofrecer mejores recomendaciones.

   Los intervalos de fechas que hay disponibles son:

   * Dos días
   * Una semana
   * Dos semanas
   * Un mes
   * Dos meses

1. (Conditional) Select the desired **[!UICONTROL Behavioral Data Source]**: [!UICONTROL mboxes] or [!UICONTROL Analytics].

   >[!NOTE]
   >
   >La sección Origen [!UICONTROL de datos de] comportamiento solo se muestra si la implementación utiliza [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Sección Origen de datos de comportamiento](/help/c-recommendations/c-algorithms/assets/behavioural-data-source.png)

   Si elige [!UICONTROL Analytics], seleccione el grupo de informes deseado.

   If the criteria uses [!DNL Adobe Analytics] as the behavioral data source, once created, the time for criteria availability depends on whether the selected report suite and lookback window has been used for any other criteria, as explained below:

   * **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. This time frame is dependent on the [!DNL Analytics] system load.
   * **Criterios nuevos o editados que usan un grupo de informes ya disponible**: Al crear un nuevo criterio o editar uno existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations] con un intervalo de datos igual o inferior al seleccionado, entonces los datos estarán disponibles inmediatamente y no se requiere una configuración única. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
   * **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación [!UICONTROL Afinidad de visualización], cuando un usuario ve un producto, se pasa una llamada de seguimiento de visualización de producto a [!DNL Analytics] casi en tiempo real. Los datos de [!DNL Analytics] se insertan en [!DNL Target] al principio del día siguiente y [!DNL Target] ejecuta el algoritmo en menos de 12 horas.

   Para obtener más información, consulte [Uso de Adobe Analytics con Destinatario Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

### Especificar la configuración del contenido {#content}

Las reglas de contenido determinan qué sucede si el número de artículos recomendados no completa su diseño. Es posible que algunos criterios de Recommendations devuelvan menos recomendaciones que las que exige el diseño. Por ejemplo, si el diseño tiene espacio para cinco artículos, pero los criterios hacen que solo se recomienden tres artículos, puede dejar el espacio restante vacío o puede utilizar las recomendaciones de copia de seguridad para llenar el espacio adicional.

![Sección Contenido](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Opcional) Deslice el conmutador Representación **[!UICONTROL de diseño]** parcial a la posición &quot;activado&quot;.

   Se rellenarán tantas ranuras como sea posible, pero la plantilla de diseño puede incluir espacio en blanco para las ranuras restantes.

1. (Opcional) Deslice el conmutador **[!UICONTROL Mostrar copia de seguridad de Recommendations]** a la posición &quot;activado&quot;.

   Llene los espacios vacíos restantes del diseño con una selección aleatoria de los productos más vistos de todo el sitio.

   Para obtener más información, consulte [Uso de una recomendación](/help/c-recommendations/c-algorithms/backup-recs.md)de copia de seguridad.

1. (Condicional) Si seleccionó **[!UICONTROL Mostrar copia de seguridad de Recommendations]** en el paso anterior, puede activar **[!UICONTROL Aplicar reglas de inclusión a las recomendaciones]** de copia de seguridad.

   Las Reglas de inclusión determinan qué artículos se incluirán en sus recomendaciones. Las opciones disponibles dependen del sector.

   For more details, see [Specify inclusion rules](#inclusion) below.

1. (Opcional) Deslice el botón **[!UICONTROL Recomendar artículos]** comprados anteriormente a la posición &quot;activado&quot;.

   Esta configuración se basa en `productPurchasedId`. El comportamiento predeterminado es no recomendar artículos comprados previamente. En la mayoría de los casos, no desea promocionar artículos que un cliente haya comprado recientemente. Es útil si vende artículos que la gente suele comprar solo una vez como, por ejemplo, canoas. Si vende artículos que las personas vuelven a comprar repetidamente, como champú u otros artículos personales, debe activar esta opción.

La siguiente matriz muestra el resultado que observará al utilizar las opciones Representación [!UICONTROL de diseño] parcial y [!UICONTROL Copia de seguridad de Recommendations] :

| Procesamiento de diseño parcial | Recomendaciones de copia de seguridad | Resultado |
|--- |--- |--- |
| Deshabilitado | Deshabilitado | Si se devuelven menos recomendaciones que las que llama el diseño, el diseño de recomendaciones se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |
| Habilitado | Deshabilitado | Se procesa el diseño, pero puede incluir espacio en blanco si se devuelven menos recomendaciones que las que llama el diseño. |
| Habilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, se procesa parcialmente el diseño.<br>Si el criterio no devuelve ninguna recomendación, y las reglas de inclusión restringen las recomendaciones de copia de seguridad a cero, el diseño se reemplaza por el Contenido predeterminado. |
| Deshabilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, el diseño se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |

### Specify content similarity rules {#similarity}

Use reglas de [!UICONTROL similitud de contenido] para hacer recomendaciones según los atributos de artículos o medios.

>[!NOTE]
>
>If you selected **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** as your [recommendation logic](#info), you will have the option to set content similarity rules.

La similitud de contenido compara palabras clave de los atributos de los artículos y realiza recomendaciones basándose en la cantidad de palabras clave que los artículos tienen en común. Las recomendaciones que se basan en la similitud de contenido no requieren información anterior para ofrecer buenos resultados.

Resulta especialmente eficaz usar la similitud de contenido para generar recomendaciones en los artículos nuevos, ya que es poco probable que estos aparezcan en las recomendaciones usando *Otras personas que vieron esto también vieron* y otras lógicas basadas en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Al seleccionar **[!UICONTROL Artículos]**/**[!UICONTROL Medios con atributos similares]**, tiene la opción de crear reglas para aumentar o reducir la importancia que ciertos atributos de artículo tienen a la hora de determinar las recomendaciones. En el caso de artículos como libros, puede aumentar la importancia de atributos como el *género*, el *autor* o la *serie* para recomendar libros parecidos.

![](assets/ContentSimilarity.png)

Como la similitud de contenido emplea palabras clave para comparar los artículos, algunos atributos, como *mensaje* o *descripción*, pueden producir “ruido” en la comparación. Puede crear reglas para pasar por alto estos atributos.

De forma predeterminada, todos los atributos están definidos en *Línea de base*. Solo es necesario crear una regla si quiere cambiar esta configuración.

>[!NOTE]
>
>El algoritmo de similitud de contenido puede usar muestras aleatorias para calcular similitudes entre elementos. Como resultado, las clasificaciones de similitud entre elementos pueden variar entre ejecuciones de algoritmos.

### Especificar reglas de inclusión {#inclusion}

![Reglas de inclusión](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Existen varias opciones que le ayudan a reducir el número de artículos que aparecen en las recomendaciones. Puede utilizar reglas de exclusión al crear criterios o promociones.

Las reglas de inclusión son opcionales, pero definir estos detalles permite controlar mejor los artículos que aparecen en las recomendaciones. Cada detalle que se configure reduce un poco más los criterios de visualización.

Por ejemplo, puede que desee mostrar únicamente los zapatos de mujer que tengan un precio entre 25 y 45 dólares y de los que haya más de 50 pares disponibles en el inventario. También puede ponderar cada atributo para que los artículos que son más importantes para su negocio tengan más posibilidades de aparecer.

Otro ejemplo: puede elegir mostrar ofertas de trabajo solo a quienes visiten su sitio desde determinadas ciudades, o tengan una determinada titulación universitaria.

Las opciones de reglas de inclusión varían por sector. De forma predeterminada, las reglas de inclusión se aplican a recomendaciones de copia de seguridad.

>[!IMPORTANT]
>
>Debería usar las reglas de inclusión con cautela. Estos filtros son útiles si, por ejemplo, su organización ha establecido reglas que exigen que una marca no se recomiende al mismo tiempo que se está viendo otra marca. Sin embargo, esta función tiene un coste de oportunidad, ya que posiblemente pueda perder un porcentaje de alza al restringir la presentación de algunos elementos que normalmente se mostrarían con los criterios de la actividad.

Las reglas de inclusión se unen mediante Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Para crear una regla de inclusión sencilla, como se mencionó, previamente, que muestre únicamente zapatos de mujer de entre 25 y 45 dólares y de los que haya más de 50 pares en el inventario, siga los pasos siguientes:

1. Establezca un rango de precios para los productos que desea recomendar.
1. Defina la cantidad mínima en inventario para los productos que desea recomendar.
1. Configure la recomendación para que únicamente muestre los artículos cuando cumplan determinados criterios.

   ![](assets/Recs_InclusionRules.png)

   Puede especificar que los artículos se incluyan solamente cuando uno de los atributos de la lista cumpla o no una o varias condiciones especificadas.

   Los evaluadores que hay disponibles dependen del valor que elija en la primera lista desplegable. Puede listar varios elementos. Estos artículos se evaluarán con O.

   Si hay varias reglas, se combinan con una Y.

   >[!NOTE]
   >
   >Esta opción limita los artículos mostrados en la recomendación. No afecta a las páginas en las que aparece la recomendación. Para limitar dónde se muestra la recomendación, seleccione las páginas en el Compositor de experiencias visuales.

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

### Especificar ponderación de atributos

Puede agregar varias reglas para &quot;desplazar&quot; el algoritmo en función de una descripción importante o de los metadatos sobre el catálogo de contenido, de modo que es más probable que se muestren determinados elementos.

Por ejemplo, puede aplicar una ponderación más alta para artículos en venta de modo que aparezcan con más frecuencia en la recomendación. Los artículos que no están en liquidación no quedan completamente excluidos, pero aparecen con menos frecuencia. Se pueden aplicar múltiples atributos ponderados al mismo algoritmo y los atributos ponderados se pueden probar sobre el tráfico dividido en la recomendación.

1. Elija un valor.

   Determina el tipo de elemento que es más probable que se muestre, en función de uno de los numerosos criterios disponibles.

1. Elija un evaluador.

1. Escriba la palabra clave para completar los atributos de la regla.

   Por ejemplo, la regla completa podría ser &quot;Categoría contiene zapatos de subcadena&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Seleccione la ponderación para asignarla a la regla.

   Las opciones varían de 0 a 100 en incrementos de 25.

1. Si lo desea, agregue reglas adicionales.

Cuando termine, haga clic en **[!UICONTROL Guardar]**.

Si está creando una nueva actividad de [!UICONTROL Recommendations] o está editando una existente, la casilla **[!UICONTROL Guardar criterios para más adelante]** está seleccionada de forma predeterminada. Si no desea usar los criterios en otras actividades, desmarque la casilla antes de guardar.

## Basar la recomendación en una clave de recomendación {#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B}

Las recomendaciones basadas en claves utilizan el contexto de comportamiento del visitante para mostrar resultados relevantes.

Existen dos tipos de recomendaciones:

* **Popularidad:** enumera los elementos según los más visitados, los más vendidos y las métricas principales. La clave está vacía para los criterios de popularidad.
* **Basado en claves:** comprende el resto de los criterios. Recommendations ofrece un conjunto diverso de opciones con respecto al tipo de clave. Las opciones van desde “elemento actual” a “parámetros de perfil”, que le permiten establecer programáticamente la clave de los valores para recomendar. Puede probar varios criterios uno frente a otro basando cada criterio en una clave diferente.

Cada criterio está definido en su propia pestaña. El tráfico se divide equitativamente en las distintas pruebas de criterios. Es decir, si tiene dos criterios, el tráfico se divide a partes iguales entre ellos. Si tiene dos criterios y dos diseños, el tráfico se divide equitativamente entre las cuatro combinaciones. También puede especificar el porcentaje de los visitantes del sitio que ven el contenido predeterminado, para su comparación. En ese caso, el porcentaje de visitantes especificado ve el contenido predeterminado y el resto se divide entre las combinaciones de algoritmo y plantilla.

1. Cree una recomendación nueva o seleccione una existente y haga clic en **[!UICONTROL Editar]**.
1. Para cambiar la clave de recomendación, seleccione la nueva clave en la lista desplegable [!UICONTROL Clave de recomendación] y haga clic en **[!UICONTROL Guardar]**.

   Dado que lógicas diferentes dirigen a claves de recomendaciones diferentes, estas últimas se prestan a colocarse en diferentes tipos de páginas. Consulte las secciones siguientes para obtener más información acerca de cada clave.

### Artículo actual

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

Páginas con un solo elemento, como las páginas de productos.

NO lo utilice en páginas de resultados de búsqueda nulos.

### Categoría actual

La recomendación está determinada por la categoría de producto que el visitante está viendo en ese momento.

Recommendations muestra los elementos en la categoría del producto especificada.

Si se selecciona está opción, el valor `entity.categoryId` debe pasarse como parámetro al mbox de visualización.

#### Lógica (criterio)

* Principales vendedores
* Más visitados

#### Ubicación en el sitio

Páginas de una sola categoría.

NO lo utilice en páginas de resultados de búsqueda nulos.

### Atributo personalizado.  {#custom}

La recomendación viene determinada por un elemento almacenado en el perfil de un visitante, utilizando los atributos user.*x* o perfil.atributos *x*.

Si se selecciona está opción, el valor `entity.id` debe estar presente en el atributo del perfil.

#### Lógica (criterio)

* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Comportamiento general.]
* [!UICONTROL Más visitados]
* [!UICONTROL Principales vendedores]

Si la clave es un atributo de perfil personalizado y el tipo de algoritmo es el más visitado o el más vendido, aparece una nueva lista desplegable llamada “Agrupar por valor único de” que tiene una lista de atributos de entidades conocidas (excepto ID, categoría, margen, valor, inventario y entorno). Este campo es obligatorio.

#### Ubicación en el sitio

Puede utilizarse en cualquier página.

#### Utilizar una clave de recomendaciones personalizada

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

### Último artículo comprado

La recomendación está determinada por el último artículo que compró cada visitante único. La captura se realiza de forma automática, por lo tanto no es necesario pasar valores a la página.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

La página inicial, la página Mi cuenta o anuncios externos.

NO lo utilice en páginas de productos o en páginas importantes para las compras.

### Último artículo visitado

La recomendación está determinada por el último artículo que vio cada visitante único. La captura se realiza de forma automática, por lo tanto no es necesario pasar valores a la página.

#### Lógica (criterio)

* [!UICONTROL Elementos con atributos similares.]
* [!UICONTROL Los usuarios que vieron esto, vieron aquello.]
* [!UICONTROL Los usuarios que vieron esto, compraron aquello.]
* [!UICONTROL Los usuarios que compraron esto, compraron aquello.]
* [!UICONTROL Afinidad del sitio]

#### Ubicación en el sitio

La página inicial, la página Mi cuenta o anuncios externos.

NO lo utilice en páginas de productos o en páginas importantes para las compras.

### Artículo más visitado

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

Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Categoría favorita

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

Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Popularidad

La recomendación está determinada por la popularidad de los artículos del sitio. La popularidad incluye a los principales vendedores y a los más visitados según los datos del mbox, y si usa Adobe Analytics, todas las métricas disponibles en el informe de productos. Los elementos se clasifican según la lógica de recomendación seleccionada.

#### Lógica (criterio)

* [!UICONTROL Principales vendedores]
* [!UICONTROL Más visitados]
* Métricas de informe de productos (si utiliza Adobe Analytics)

#### Ubicación en el sitio

Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

### Artículos vistos recientemente.  {#recently-viewed}

Utiliza el historial del visitante (sesiones de alcance) para presentar el último elemento *X* que el visitante haya visto, según el número de espacios en el diseño.

Los criterios de Elementos visualizados recientemente ahora devuelven resultados específicos de un [entorno](/help/administrating-target/hosts.md) determinado. Si dos sitios pertenecen a entornos distintos y un visitante alterna entre ellos, cada sitio muestra solo los elementos visualizados recientemente desde el sitio adecuado. Si dos sitios se encuentran en el mismo entorno y un visitante cambia entre los dos, el visitante verá los mismos artículos vistos recientemente en ambos.

#### Ubicación en el sitio

Páginas generales, como páginas principales o de aterrizaje y anuncios externos.

>[!NOTE]
>
>Elementos vistos recientemente respeta tanto la configuración global de Exclusiones como la configuración de Colección seleccionada para la Actividad. Si un elemento queda excluido por una Exclusión global o no está contenido en la Colección seleccionada, no se mostrará; por lo tanto, al utilizar los criterios de Artículos vistos recientemente, se suele utilizar la opción «Todas las colecciones».

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
