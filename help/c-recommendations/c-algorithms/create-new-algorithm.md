---
keywords: criterios;algoritmo;sector vertical;tipo de página;clave de recomendación;lógica;lógica;rango de datos;origen de datos de comportamiento;diseño parcial;recomendaciones de copia de seguridad;reglas de inclusión;ponderación de atributos;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;último artículo visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visitado;favorito;favorito;último artículo visto;recientemente visto
description: Los criterios controlan el contenido de sus actividades de Adobe Recommendations. Cree criterios para mostrar las recomendaciones que más se ajusten a su actividad.
title: Crear criterios
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2477'
ht-degree: 65%

---


# ![PREMIUM](/help/assets/premium.png) Crear criterios{#create-criteria}

Los criterios de [!UICONTROL Adobe Target] [!UICONTROL Recommendations] controlan el contenido de sus actividades [!UICONTROL Recommendations]. Cree criterios para mostrar las recomendaciones que más se ajusten a su actividad. Estos criterios utilizan las acciones del visitante para determinar qué contenido o productos mostrar.

Las siguientes secciones explican cómo crear un nuevo criterio.

## Acceso a la pantalla Crear nuevo criterio

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear nuevos criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].
* Al crear una actividad [!DNL Recommendations] mediante el [!UICONTROL Compositor de experiencias visuales] (VEC), se le dirigirá inmediatamente a la pantalla [!UICONTROL Seleccionar criterios] después de seleccionar un elemento en la página y hacer clic en [!UICONTROL Reemplazar con Recommendations], [!UICONTROL Insertar Recommendations antes de] o [!UICONTROL Insertar Después de]. Luego puede seleccionar un criterio disponible o puede hacer clic en **[!UICONTROL Crear criterios]**. Si crea un nuevo criterio, tiene la opción de guardar los criterios para usarlos con otras [!DNL Recommendations] actividades. Para obtener más información, consulte [Creación de una actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Cuando esté editando una [!DNL Recommendations]actividad, haga clic en el cuadro [!UICONTROL Ubicación de Recommendations] de la página y seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear criterios]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!DNL Recommendations].

Los siguientes pasos suponen que accede a la pantalla [!UICONTROL Crear nuevos criterios] mediante el primer método: la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**.

   ![Crear nuevos criterios](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

1. Configure la información en las siguientes secciones.

## Información básica    {#info}

1. Escriba un **[!UICONTROL Nombre de criterio]**.

   Es el nombre “interno” que se usa para describir los criterios. Por ejemplo, quizá use el nombre “Productos con más margen” para los criterios, pero es probable que no quiera que ese título se muestre al público. Consulte el paso siguiente para establecer el título que se presenta al público.

   ![Sección Información básica](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Escriba un **[!UICONTROL Título]** que se mostrará a la audiencia para que aparezca en la página para todas las recomendaciones que usen este criterio.

   Por ejemplo, una idea es mostrar “Las personas que han visto esto también vieron” o “Productos similares” cuando use estos criterios para mostrar recomendaciones.

1. Escriba una breve **[!UICONTROL Descripción]** del criterio.

   La descripción debería ayudarle a identificar los criterios y podría incluir información sobre el propósito de los mismos.

1. Seleccione un sector en función de los objetivos de la actividad de recomendaciones.

   | Sector | Objetivo |
   |--- |--- |
   | Venta minorista/Comercio electrónico | Conversión que termina en compra |
   | Generación de vanguardia/B2B/Servicios financieros | Conversión sin compra |
   | Medios/Publicación | Participación |

   Otras opciones de criterios cambiarán según el sector que seleccione.

1. Seleccione un **[!UICONTROL Tipo de página]**.

   Puede seleccionar varios tipos de página.

   En conjunto, el sector y los tipos de página se usan para categorizar los criterios guardados, facilitando su reutilización para otras actividades de [!DNL Recommendations].

1. Seleccione una **[!UICONTROL Clave de recomendación]**.

   Para obtener más información sobre cómo basar los criterios en una clave, consulte [Basar la recomendación en una clave de recomendación](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. Seleccione la **[!UICONTROL Lógica de recomendación]**.

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](/help/c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >Si selecciona **[!UICONTROL Elementos]**/ **[!UICONTROL Medios con atributos similares]**, tendrá la opción de establecer [reglas de similitud de contenido](#similarity).

## Fuente de datos {#data-source}

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

1. (Condicional) Seleccione la **[!UICONTROL Fuente de datos de comportamiento]** que desee: [!UICONTROL mboxes] o [!UICONTROL Analytics].

   >[!NOTE]
   >
   >La sección [!UICONTROL Behavioral Data Source] se muestra únicamente si la implementación utiliza [Analytics para Destinatario](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Sección Origen de datos de comportamiento](/help/c-recommendations/c-algorithms/assets/behavioural-data-source.png)

   Si elige [!UICONTROL Analytics], seleccione el grupo de informes deseado.

   Si el criterio utiliza [!DNL Adobe Analytics] como fuente de datos de comportamiento, una vez creada, el tiempo para la disponibilidad de los criterios depende de si el grupo de informes seleccionado y la ventana retrospectiva se han utilizado para cualquier otro criterio, como se explica a continuación:

   * **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. Este intervalo de tiempo depende de la carga del sistema [!DNL Analytics].
   * **Criterios nuevos o editados que usan un grupo de informes ya disponible**: Al crear un nuevo criterio o editar uno existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations] con un intervalo de datos igual o inferior al seleccionado, entonces los datos estarán disponibles inmediatamente y no se requiere una configuración única. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
   * **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación [!UICONTROL Afinidad de visualización], cuando un usuario ve un producto, se pasa una llamada de seguimiento de visualización de producto a [!DNL Analytics] casi en tiempo real. Los datos de [!DNL Analytics] se insertan en [!DNL Target] al principio del día siguiente y [!DNL Target] ejecuta el algoritmo en menos de 12 horas.

   Para obtener más información, consulte [Uso de Adobe Analytics con Destinatario Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

## Contenido {#content}

Las reglas de contenido determinan qué sucede si el número de artículos recomendados no completa el [diseño de recomendaciones](/help/c-recommendations/c-design-overview/design-overview.md). Es posible que algunos criterios de [!DNL Recommendations] devuelvan menos recomendaciones que las que exige el diseño. Por ejemplo, si el diseño tiene ranuras para cuatro artículos, pero los criterios hacen que solo se recomienden dos artículos, puede dejar las ranuras restantes vacías o puede utilizar las recomendaciones de copia de seguridad para rellenar las ranuras adicionales.

![Sección Contenido](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Opcional) Deslice el botón **[!UICONTROL Representación de diseño parcial]** para colocarlo en la posición &quot;on&quot;.

   Se rellenarán tantas ranuras como sea posible, pero la plantilla de diseño puede incluir espacio en blanco para las ranuras restantes. Si esta opción está deshabilitada y no hay suficiente contenido para llenar todas las ranuras disponibles, no se mostrarán las recomendaciones y se mostrará el contenido predeterminado.

   Active esta opción si desea que las recomendaciones se proporcionen con ranuras en blanco. Utilice las recomendaciones de copia de seguridad si desea que las ranuras de recomendación se llenen con contenido basado en sus criterios con ranuras vacías llenas de contenido popular o similar del sitio, como se explica en el paso siguiente.

1. (Opcional) Deslice el conmutador **[!UICONTROL Mostrar copia de seguridad de Recommendations]** a la posición &quot;activado&quot;.

   Llene los espacios vacíos restantes del diseño con una selección aleatoria de los productos más vistos de todo el sitio.

   El uso de recomendaciones de copia de seguridad garantiza que el diseño de la recomendación llene todos los espacios disponibles. Supongamos que tiene un diseño de 4 x 1, como se ilustra a continuación:

   ![Diseño de 4 x 1](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supongamos que los criterios hacen que solo se recomienden dos elementos. Si activa la opción [!UICONTROL Representación de diseño parcial], las dos primeras ranuras se rellenan, pero las dos restantes permanecen vacías. Sin embargo, si habilita la opción [!UICONTROL Mostrar copia de seguridad de Recommendations], las dos primeras ranuras se rellenan según los criterios especificados y las dos ranuras restantes se rellenan según las recomendaciones de copia de seguridad.

   La siguiente matriz muestra el resultado que observará al utilizar las opciones [!UICONTROL Representación de diseño parcial] y [!UICONTROL Copia de seguridad de Recommendations]:

   | Procesamiento de diseño parcial | Recomendaciones de copia de seguridad | Resultado |
   |--- |--- |--- |
   | Deshabilitado | Deshabilitado | Si se devuelven menos recomendaciones que las que llama el diseño, el diseño de recomendaciones se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |
   | Habilitado | Deshabilitado | Se procesa el diseño, pero puede incluir espacio en blanco si se devuelven menos recomendaciones que las que llama el diseño. |
   | Habilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, se procesa parcialmente el diseño.<br>Si el criterio no devuelve ninguna recomendación, y las reglas de inclusión restringen las recomendaciones de copia de seguridad a cero, el diseño se reemplaza por el Contenido predeterminado. |
   | Deshabilitado | Habilitado | Las recomendaciones de copia de seguridad llenarán “ranuras” de diseño disponible, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, el diseño se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |

   Para obtener más información, consulte [Usar una recomendación de copia de seguridad](/help/c-recommendations/c-algorithms/backup-recs.md).

1. (Condicional) Si seleccionó **[!UICONTROL Mostrar copia de seguridad de Recommendations]** en el paso anterior, puede habilitar **[!UICONTROL Aplicar reglas de inclusión a las recomendaciones de copia de seguridad]**.

   Las reglas de inclusión determinan qué artículos se incluyen en las recomendaciones. Las opciones disponibles dependen del sector.

   Para obtener más información, consulte [Especificación de reglas de inclusión](#inclusion) a continuación.

1. (Opcional) Deslice el conmutador **[!UICONTROL Recomendar elementos comprados anteriormente]** a la posición &quot;activado&quot;.

   Esta configuración se basa en `productPurchasedId`. El comportamiento predeterminado es no recomendar artículos comprados previamente. En la mayoría de los casos, no desea promocionar artículos que un cliente haya comprado recientemente. Es útil si vende artículos que la gente suele comprar solo una vez como, por ejemplo, canoas. Si vende artículos que las personas vuelven a comprar repetidamente, como champú u otros artículos personales, debe activar esta opción.

## Similitud de contenido {#similarity}

Use reglas de [!UICONTROL similitud de contenido] para hacer recomendaciones según los atributos de artículos o medios.

>[!NOTE]
>
>Si seleccionó **[!UICONTROL Elementos]**/ **[!UICONTROL Medios con atributos similares]** como [lógica de recomendación](#info), tendrá la opción de establecer reglas de similitud de contenido.

La similitud de contenido compara palabras clave de los atributos de los artículos y realiza recomendaciones basándose en la cantidad de palabras clave que los artículos tienen en común. Las recomendaciones que se basan en la similitud de contenido no requieren información anterior para ofrecer buenos resultados.

Resulta especialmente eficaz usar la similitud de contenido para generar recomendaciones en los artículos nuevos, ya que es poco probable que estos aparezcan en las recomendaciones usando *Otras personas que vieron esto también vieron* y otras lógicas basadas en el comportamiento anterior. También puede utilizar la similitud de contenido si quiere generar recomendaciones útiles para los nuevos visitantes, que no han hecho ninguna compra ni tienen datos históricos.

Al seleccionar **[!UICONTROL Artículos]**/**[!UICONTROL Medios con atributos similares]**, tiene la opción de crear reglas para aumentar o reducir la importancia que ciertos atributos de artículo tienen a la hora de determinar las recomendaciones. En el caso de artículos como libros, puede aumentar la importancia de atributos como el *género*, el *autor* o la *serie* para recomendar libros parecidos.

![](assets/ContentSimilarity.png)

Como la similitud de contenido emplea palabras clave para comparar los artículos, algunos atributos, como *mensaje* o *descripción*, pueden producir “ruido” en la comparación. Puede crear reglas para pasar por alto estos atributos.

De forma predeterminada, todos los atributos están definidos en *Línea de base*. Solo es necesario crear una regla si quiere cambiar esta configuración.

>[!NOTE]
>
>El algoritmo de similitud de contenido puede usar muestras aleatorias para calcular similitudes entre elementos. Como resultado, las clasificaciones de similitud entre elementos pueden variar entre ejecuciones de algoritmos.

## Reglas de inclusión {#inclusion}

Existen varias opciones que le ayudan a reducir el número de artículos que aparecen en las recomendaciones. Puede utilizar reglas de exclusión al crear criterios o promociones.

![Reglas de inclusión](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

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

Para obtener más información, consulte [Uso de reglas de inclusión dinámicas y estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderación de atributos {#weighting}

Puede agregar varias reglas para &quot;desplazar&quot; el algoritmo en base a información importante o metadatos sobre el catálogo de contenido, de modo que es más probable que se muestren ciertos elementos.

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

## Vídeo de capacitación: Crear criterios en Recommendations (12:33) ![distintivo de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
