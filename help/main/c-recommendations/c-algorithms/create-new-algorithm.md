---
keywords: criterios;algoritmo;sector vertical;tipo de página;clave de recomendación;lógica de recomendación;intervalo de datos;ventana retrospectiva;fuente de datos de comportamiento;diseño parcial;recomendaciones de copia de seguridad;reglas de inclusión;ponderación de atributos;categoría actual;atributo personalizado;último artículo comprado;último artículo visto;artículo más visto;artículo más visto;categoría favorita;popularidad;artículo visto recientemente;último comprado;último visto;más visto;favorito;visto recientemente
description: Aprenda a crear criterios que controlen el contenido de sus actividades [!DNL Recommendations] para mostrar las recomendaciones que sean más apropiadas para su actividad.
title: ¿Cómo creo [!UICONTROL criterios] en [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
TQID: 'https://experienceleague.adobe.com/r9FWgHWw6NX1CmhqI-7MLoamNFDepeCq1bpiJ8eyISM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2840'
ht-degree: 17%
---
# Crear criterios {#create-criteria}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear criterios en [!DNL Adobe Target Recommendations] y a configurar cada sección de un criterio.

>[!ENDSHADEBOX]

Los criterios de [!DNL Adobe Target] [!DNL Recommendations] controlan el contenido de [!DNL Recommendations] actividades. Los criterios utilizan las acciones del visitante para determinar qué contenido o productos mostrar, de modo que los criterios adecuados muestren las recomendaciones que sean más apropiadas para la actividad.

## Acceso a la pantalla Crear nuevos criterios {#access-create-criteria}

Existen varias maneras de llegar a la pantalla **[!UICONTROL Crear nuevos criterios]**. Algunas opciones de pantalla varían según la forma en que se alcance la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**. Los criterios creados aquí quedan disponibles automáticamente para todas las actividades de [!DNL Recommendations].

  ![Página de criterios con el menú Crear criterios abierto, que muestra Crear criterio y Crear secuencia de criterios](../assets/criteria_create_1.png)

* Al crear una actividad [!DNL Recommendations] con el **[!UICONTROL Compositor de experiencias visuales]** (VEC), la pantalla **[!UICONTROL Seleccionar criterios]** se muestra inmediatamente después de seleccionar un elemento en la página y de hacer clic en **[!UICONTROL Reemplazar con Recommendations]**, **[!UICONTROL Insertar recomendaciones antes]** o **[!UICONTROL Insertar recomendaciones después]**. Seleccione un criterio disponible o haga clic en **[!UICONTROL Crear criterio]**. Se puede guardar un nuevo criterio para utilizarlo con otras [!DNL Recommendations] actividades. Para obtener más información, consulte [Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

  ![Pantalla Seleccionar criterios de una actividad de Recommendations con el botón Crear criterios](../assets/criteria_create_2.png)

* Al editar una actividad [!DNL Recommendations], haga clic en el cuadro **[!UICONTROL Ubicación de Recommendations]** de la página y seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla **[!UICONTROL Seleccionar criterios]**, haga clic en **[!UICONTROL Crear criterios]**. Los nuevos criterios se pueden guardar para usarlos con otras [!DNL Recommendations] actividades.

## [!UICONTROL Información básica] {#info}

La información básica identifica los criterios y los clasifica para su reutilización en otras actividades.

1. Escriba un **[!UICONTROL Nombre de criterio]**.

   Es el nombre interno que se usa para describir los criterios. Por ejemplo, un criterio puede llamarse &quot;Productos con mayor margen&quot; sin que ese título se muestre públicamente. El título orientado al público se establece en el siguiente paso.

1. Escriba un **[!UICONTROL Título para mostrar]** público para que aparezca en la página para todas las recomendaciones que usen este criterio.

   Por ejemplo, &quot;Las personas que vieron esto vieron aquello&quot; o &quot;Productos similares&quot; se pueden mostrar cuando se utiliza este criterio para mostrar las recomendaciones.

1. Escriba una breve **[!UICONTROL descripción]** de los criterios.

   La descripción debería ayudar a identificar los criterios y podría incluir información sobre su propósito.

1. Seleccione un sector vertical según los objetivos de la actividad de recomendaciones.

   | Sector | Objetivo |
   |--- |--- |
   | **[!UICONTROL Venta minorista/Comercio electrónico]** | Conversión que termina en compra |
   | **[!UICONTROL Generación de clientes potenciales/B2B/Servicios financieros]** | Conversión sin compra |
   | **[!UICONTROL Medios/Publicación]** | Participación |

   Otras opciones de criterios cambian según el sector seleccionado.

   ![Sección de información básica del cuadro de diálogo Crear criterios con la lista Sector/Vertical abierta y sus tres opciones resaltadas](../assets/criteria_create_3.png)

1. Seleccione un **[!UICONTROL tipo de página]**.

   Se pueden seleccionar varios tipos de página. En conjunto, el sector y los tipos de página ayudan a categorizar los criterios guardados, facilitando su reutilización para otras actividades de [!DNL Recommendations].

## [!UICONTROL Algoritmo de recomendaciones] {#rec-algo}

El algoritmo determina cómo se seleccionan los elementos de las recomendaciones.

>[!CONTEXTUALHELP]
>id="target_recommendations_profile_attribute"
>title="Atributo del perfil"
>abstract="Puede crear un atributo de perfil mediante los scripts de perfil."

1. Seleccione un **[!UICONTROL tipo de algoritmo]** y un **[!UICONTROL algoritmo]**:

   ![Sección de algoritmo recomendado](assets/recommended-algorithm.png)

   | Tipo de algoritmo | Cuándo utilizar / Algoritmos disponibles |
   | --- | --- |
   | **[!UICONTROL Basado en el carro de compras]** | Haga recomendaciones basadas en el contenido del carro de compras del usuario. <ul><li>**[!UICONTROL Las Personas Que Vieron Esto, También Vieron]** </li><li>**[!UICONTROL Otras Personas Que Vieron Esto, También Compraron]**</li><li>**[!UICONTROL Otras Personas Que Compraron Esto, También Compraron]**</li></ul> |
   | **[!UICONTROL Basado en popularidad]** | Haga recomendaciones basadas en la popularidad general de un elemento en todo el sitio o en la popularidad de elementos dentro de la categoría, marca, género, etc. favoritas o más vistas del usuario. <ul><li>**[!UICONTROL Más visitados en todo el sitio]**</li><li>**[!UICONTROL Más visitados por categoría]**</li><li>**[!UICONTROL Más visitados por atributo de artículo]**</li><li>**[!UICONTROL Más visitados por atributo de perfil]**</li><li>**[!UICONTROL Principales vendedores en todo el sitio]**</li><li>**[!UICONTROL Principales vendedores por categoría]**</li><li>**[!UICONTROL Principales vendedores por atributo de artículo]**</li><li>**[!UICONTROL Principales vendedores por atributo de perfil]**</li><li>**[!UICONTROL Métrica superior por Analytics]**</li></ul> |
   | **[!UICONTROL Basado en elementos]** | Haga recomendaciones basadas en artículos que sean similares a un artículo que el usuario esté viendo en este momento o que haya visto recientemente. <ul><li>**[!UICONTROL Las Personas Que Vieron Esto, Vieron Aquello]**</li><li>**[!UICONTROL Otras Personas Que Vieron Esto, Compraron Aquello]**</li><li>**[!UICONTROL Otras Personas Que Compraron Esto, Compraron Aquello]**</li><li>**[!UICONTROL Elementos con atributos similares]**</li></ul> |
   | **[!UICONTROL Basado en usuario]** | Haga recomendaciones basadas en el comportamiento del usuario.<ul><li>**[!UICONTROL Artículos vistos recientemente]**</li><li>**[!UICONTROL Recomendado para usted]**</li></ul> |
   | **[!UICONTROL Criterios personalizados]** | Haga recomendaciones basadas en un archivo personalizado cargado.<ul><li>Algoritmo personalizado</li></ul> |

   >[!NOTE]
   >
   >Cuando se seleccionan **[!UICONTROL Elementos]**/ **[!UICONTROL Medios con atributos similares]**, se pueden establecer [reglas de contenido similares](#similarity).

1. Configure el algoritmo según sea necesario seleccionando una **[!UICONTROL Clave de recomendación]**, **[!UICONTROL Clave de filtrado]**, **[!UICONTROL Base de coocurrencia]**, **[!UICONTROL Métrica de Analytics]**, y/o **[!UICONTROL Atributo de elemento]** y **[!UICONTROL Atributo de perfil que debe coincidir]**. Las opciones de configuración disponibles varían según el algoritmo seleccionado.

   Para obtener más información sobre cómo elegir una **[!UICONTROL clave de recomendación]**, consulte [Basar la recomendación en una clave de recomendación](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. (Condicional) Para **[!UICONTROL Más visitados por atributo de perfil]** o **[!UICONTROL Más vendidos por atributo de perfil]**, seleccione un **[!UICONTROL atributo de perfil]** por el que agrupar los datos de interacción.

   Los atributos de perfil provienen de un script de perfil que captura una característica del visitante, como la región o el país. El nombre del script debe llevar el prefijo `recsAttribute`, por lo que se almacena como `user.recsAttribute<Name>`, por ejemplo, `user.recsAttributeRegion`. En el momento de la entrega, [!DNL Target] indica a cada visitante la lista clasificada que corresponde a su propio valor de ese atributo.

## [!UICONTROL Contenido de copia de seguridad] {#content}

Las reglas de **[!UICONTROL Contenido de copia de seguridad]** determinan qué sucede si el número de elementos recomendados no cumple el [diseño de recomendaciones](/help/main/c-recommendations/c-design-overview/design-overview.md). Los criterios pueden arrojar menos recomendaciones que las que exige el diseño. Por ejemplo, si el diseño tiene espacios para cuatro artículos pero el criterio hace que solo se recomienden dos artículos, los espacios restantes se pueden dejar vacíos o rellenar con recomendaciones de copia de seguridad, o no se pueden mostrar recomendaciones.

1. (Opcional) Habilite la opción **[!UICONTROL Procesamiento parcial del diseño]**.

   Se rellenan tantas ranuras como sea posible, pero la plantilla de diseño puede incluir espacio en blanco para las ranuras restantes. Si esta opción está deshabilitada y no hay suficiente contenido para rellenar todas las ranuras disponibles, las recomendaciones no se proporcionan y se muestra el contenido predeterminado en su lugar.

   Active esta opción para ofrecer recomendaciones con espacios en blanco. Para rellenar las ranuras vacías con contenido similar o popular del sitio, utilice recomendaciones de copia de seguridad, tal como se explica en el siguiente paso.

1. (Opcional) Habilite la opción **[!UICONTROL Mostrar contenido de copia de seguridad]**.

   Las recomendaciones de copia de seguridad llenan cualquier ranura vacía restante en el diseño con una selección aleatoria de los productos más vistos de todo el sitio, por lo que el diseño siempre llena todas las ranuras disponibles. El ejemplo siguiente utiliza un diseño 4 x 1:

   ![4 x 1 diseño](../assets/velocity_example.png)

   Si los criterios hacen que solo se recomienden dos elementos y la opción **[!UICONTROL Procesamiento parcial del diseño]** está habilitada, las dos primeras ranuras se llenarán y las dos ranuras restantes permanecerán vacías. Si la opción **[!UICONTROL Mostrar contenido de copia de seguridad]** está habilitada, las dos primeras ranuras se rellenan según los criterios especificados y las dos ranuras restantes se rellenan según las recomendaciones de copia de seguridad.

   +++ La siguiente matriz muestra el resultado de cada combinación de las opciones **[!UICONTROL Procesamiento de diseño parcial]** y **[!UICONTROL Contenido de copia de seguridad]**

   | Procesamiento de diseño parcial | Contenido de copia | Resultado |
   |--- |--- |--- |
   | Deshabilitado | Deshabilitado | Si se devuelven menos recomendaciones que las que llama el diseño, el diseño de recomendaciones se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |
   | Habilitado | Deshabilitado | Se representa el diseño, pero puede incluir espacio en blanco si se devuelven menos recomendaciones que las que requiere el diseño. |
   | Habilitado | Habilitado | Las recomendaciones de copia de seguridad rellenan las &quot;ranuras&quot; de diseño disponibles, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, se procesa parcialmente el diseño.<br>Si el criterio no devuelve ninguna recomendación, y las reglas de inclusión restringen las recomendaciones de copia de seguridad a cero, el diseño se reemplaza por el Contenido predeterminado. |
   | Deshabilitado | Habilitado | Las recomendaciones de copia de seguridad rellenan las &quot;ranuras&quot; de diseño disponibles, procesando completamente el diseño.<br>Si la aplicación de reglas de inclusión a las recomendaciones de copia de seguridad restringe el número de recomendaciones de copia de seguridad correspondiente al punto de que no se pueda llenar el diseño, el diseño se reemplaza por el contenido predeterminado y no se muestran recomendaciones. |

   Para obtener más información, vea [Usar una recomendación de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md).
   +++

1. (Condicional) Si **[!UICONTROL Mostrar contenido de copia de seguridad]** está habilitado, también se pueden habilitar **[!UICONTROL Aplicar reglas de inclusión a recomendaciones de copia de seguridad]**.

   Las reglas de inclusión determinan qué artículos se incluyen en las recomendaciones. Las opciones disponibles dependen del sector.

   Para obtener más información, consulte [Especificar reglas de inclusión](#inclusion) a continuación.

## [!UICONTROL Source de datos] {#data-source}

La fuente de datos determina los datos de comportamiento que utilizan los criterios y el intervalo de tiempo de esos datos.

1. Seleccione el **[!UICONTROL Source de datos de comportamiento]** deseado: **[!UICONTROL Adobe Target]** o **[!UICONTROL Analytics]**.

   >[!NOTE]
   >
   >La sección **[!UICONTROL Source de datos de comportamiento]** solo se muestra si la implementación usa [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Sección Data Source con las opciones Behavioral Data Source resaltadas en Adobe Target y Analytics](../assets/criteria_create_4.png)

   Para **[!UICONTROL Analytics]**, seleccione el grupo de informes deseado.

   +++ Disponibilidad de criterios cuando Analytics es la fuente de datos

   Si [!DNL Adobe Analytics] es la fuente de datos de comportamiento, el tiempo hasta que haya disponible un nuevo criterio depende de si el grupo de informes seleccionado y la ventana de vista al pasado se han utilizado para otros criterios:

   * **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. Este lapso de tiempo depende de la carga del sistema [!DNL Analytics].
   * **Criterios nuevos o editados que usan un grupo de informes ya disponible**: Al crear un nuevo criterio o editar uno existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations], con un intervalo de datos igual o mayor que el seleccionado, entonces los datos estarán disponibles inmediatamente y no se requiere una configuración única. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
   * **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación **[!UICONTROL Afinidad de visualización]**, cuando un usuario ve un producto, se pasa una llamada de seguimiento de visualización de producto a [!DNL Analytics] en tiempo casi real. Los datos de [!DNL Analytics] se insertan en [!DNL Target] al principio del día siguiente y [!DNL Target] ejecuta el algoritmo en menos de 12 horas.

   Para obtener más información, consulte [Usar Adobe Analytics con Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

   +++



1. Establezca la **[!UICONTROL ventana retrospectiva]** para determinar el intervalo de tiempo de los datos de comportamiento del usuario históricos disponibles que se utilizarán al determinar qué recomendaciones mostrar. Esta opción está disponible para todos los algoritmos, excepto para **[!UICONTROL Elementos con atributos similares]** y **[!UICONTROL Algoritmos personalizados]**.

   Para un sitio con mucho tráfico donde los comportamientos cambian con frecuencia, elija un período de datos más breve. Una ventana más corta hace que [!DNL Recommendations] responda mejor a los cambios del mercado y de la empresa. Por ejemplo, [!DNL Recommendations] detecta los cambios en el comportamiento de los visitantes a medida que estos comienzan a realizar compras de temporada, como las compras de vuelta al colegio o las compras navideñas, y recomienda artículos apropiados para esas temporadas.

   Si el sitio no tiene muchos datos o el comportamiento de los visitantes no cambia con frecuencia, seleccione una ventana más larga. Sin embargo, para muchos sitios, una ventana más corta resulta en recomendaciones de mayor calidad.

   +++ Intervalos de datos disponibles

   | Opción Ventana retroactiva | Frecuencia actualizada (mostrada al pasar el ratón por encima) | Algoritmos admitidos |
   | --- | --- | --- |
   | Seis horas | El algoritmo se ejecuta cada 3 a 6 horas | **[!UICONTROL Algoritmos basados en popularidad]** cuando el **[!UICONTROL Source de datos de comportamiento]** seleccionado es [!DNL Adobe Target] |
   | Un día | El algoritmo se ejecuta cada 12 a 24 horas | **[!UICONTROL Algoritmos basados en popularidad]** |
   | Dos días | El algoritmo se ejecuta cada 12 a 24 horas | <ul><li>**[!UICONTROL Algoritmos basados en popularidad]**</li><li>Algoritmos **[!UICONTROL basados en elementos]**</li><li>Algoritmos **[!UICONTROL basados en usuarios]**</li><li>Algoritmos **[!UICONTROL basados en el carro de compras]**</li></ul> |
   | Una semana | El algoritmo se ejecuta cada 24 a 48 horas | <ul><li>**[!UICONTROL Algoritmos basados en popularidad]**</li><li>Algoritmos **[!UICONTROL basados en elementos]**</li><li>Algoritmos **[!UICONTROL basados en usuarios]**</li><li>Algoritmos **[!UICONTROL basados en el carro de compras]**</li></ul> |
   | Dos semanas | El algoritmo se ejecuta cada 24 a 48 horas | <ul><li>**[!UICONTROL Algoritmos basados en popularidad]**</li><li>Algoritmos **[!UICONTROL basados en elementos]**</li><li>Todos los algoritmos **[!UICONTROL basados en usuarios]**</li><li>Algoritmos **[!UICONTROL basados en el carro de compras]**</li></ul> |
   | Un mes (30 días) | El algoritmo se ejecuta cada 24 a 48 horas | <ul><li>**[!UICONTROL Algoritmos basados en popularidad]**</li><li>Algoritmos **[!UICONTROL basados en elementos]**</li><li>Algoritmos **[!UICONTROL basados en usuarios]**</li><li>Algoritmos **[!UICONTROL basados en el carro de compras]**</li></ul> |
   | Dos meses (61 días) | El algoritmo se ejecuta cada 24 a 48 horas | <ul><li>**[!UICONTROL Algoritmos basados en popularidad]**</li><li>Algoritmos **[!UICONTROL basados en elementos]**</li><li>Algoritmos **[!UICONTROL basados en usuarios]**</li><li>Algoritmos **[!UICONTROL basados en el carro de compras]**</li></ul> |

   +++

## Similitud de contenido {#similarity}

Use reglas de **[!UICONTROL similitud de contenido]** para hacer recomendaciones según los atributos de artículos o medios.

![Sección de similitud de contenido con una regla entity.name y los botones Agregar regla y Borrar reglas resaltados](../assets/criteria_create_5.png)

La similitud de contenido compara palabras clave de los atributos de los artículos y realiza recomendaciones basándose en la cantidad de palabras clave que los artículos tienen en común. Las recomendaciones basadas en la similitud de contenido no requieren datos pasados.

La similitud de contenido es efectiva para nuevos elementos, que probablemente no aparezcan en las recomendaciones usando *Personas que vieron esto, También vieron* y otra lógica basada en el comportamiento anterior. También puede generar recomendaciones para nuevos visitantes, que no tengan compras u otros datos históricos en el pasado.

Cuando se selecciona **[!UICONTROL Elemento basado en elementos]**/ **[!UICONTROL Elemento con atributos similares]**, se pueden crear reglas para aumentar o disminuir la importancia de atributos de elementos específicos al determinar las recomendaciones. Para elementos como libros, la importancia de atributos como *género*, *autor*, *serie*, etc., se puede aumentar para recomendar libros similares.

La similitud de contenido usa palabras clave para comparar elementos, por lo que algunos atributos, como *message* o *description*, pueden producir &quot;ruido&quot; en la comparación. Se pueden crear reglas para ignorar estos atributos.

De forma predeterminada, todos los atributos están definidos en *Línea de base*. Solo se necesita una regla para cambiar esta configuración.

>[!NOTE]
>
>El algoritmo de similitud de contenido puede utilizar muestreo aleatorio para calcular la similitud entre los elementos. Como resultado, las clasificaciones de similitud entre los elementos pueden variar entre las ejecuciones de algoritmos.

## Reglas de inclusión {#inclusion}

Las reglas de inclusión limitan los artículos que se muestran en las recomendaciones. Se pueden utilizar al crear criterios o promociones. Las reglas de inclusión son opcionales; sin embargo, al configurar estos detalles se obtiene más control sobre los elementos que aparecen en las recomendaciones. Cada detalle que se configura reduce aún más los criterios de visualización.

Por ejemplo, solo se pueden mostrar los zapatos de mujer que tengan un inventario de más de 50 y un precio entre 25 y 45 dólares. Cada atributo también se puede ponderar para que los elementos que son más importantes para la empresa sean los más propensos a aparecer. Otro ejemplo: las ofertas de empleo solo se pueden mostrar a los visitantes que visitan el sitio desde determinadas ciudades y que tienen los títulos universitarios requeridos.

Las opciones de reglas de inclusión varían por sector. De forma predeterminada, las reglas de inclusión se aplican a recomendaciones de copia de seguridad. Las reglas de inclusión se unen con un operador AND, por lo que todas las reglas deben cumplirse para incluir un elemento en una recomendación.

>[!IMPORTANT]
>
>Utilice las reglas de inclusión con cuidado. Resultan útiles si, por ejemplo, la organización tiene reglas que exigen que no se recomiende una marca mientras se muestra otra. Sin embargo, esta función tiene un coste de oportunidad: restringir artículos que los criterios de actividad mostrarían normalmente podría perder un porcentaje de alza.

Los siguientes pasos crean una regla de inclusión simple que muestra solo los zapatos de mujer que tienen un inventario de más de 50 y un precio entre 25 y 45 $:

1. (Condicional) Habilitar **[!UICONTROL Permitir que se recomienden los artículos comprados recientemente]**.

   Esta configuración se basa en `productPurchasedId`. El comportamiento predeterminado es no recomendar artículos comprados previamente. En la mayoría de los casos, los artículos que un cliente ha comprado recientemente no deben promocionarse. La configuración es útil para elementos que las personas compran normalmente solo una vez, como kayaks. Para los artículos que las personas compran repetidamente, como champú u otros artículos personales, habilite esta opción.

1. Establezca un rango de precios para que los productos se recomienden.

1. Establezca la cantidad mínima de inventario para los productos que se van a recomendar.

1. Configure la recomendación para que únicamente muestre los artículos cuando cumplan determinados criterios.

   Los artículos sólo se pueden incluir cuando uno de los atributos de la lista cumple o no una o varias condiciones especificadas.

   Los evaluadores disponibles dependen del valor elegido en la primera lista desplegable. Se pueden enumerar varios elementos y se evalúan con OR. Si hay varias reglas, se combinan con una Y.

   >[!NOTE]
   >
   >Esta opción limita los artículos mostrados en la recomendación. No afecta a las páginas en las que aparece la recomendación. Para limitar dónde se muestra la recomendación, seleccione las páginas en el Compositor de experiencias visuales.

Para obtener más información, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderación de atributos {#weighting}

Se pueden agregar varias reglas para &quot;desplazar&quot; el algoritmo basado en información o metadatos importantes acerca del catálogo de contenido, de modo que es más probable que se muestren determinados elementos.

Por ejemplo, se puede aplicar una ponderación más alta a los artículos en venta, de modo que aparezcan con mayor frecuencia en la recomendación. Los artículos que no están en liquidación no quedan completamente excluidos, pero aparecen con menos frecuencia. Se pueden aplicar múltiples atributos ponderados al mismo algoritmo y los atributos ponderados se pueden probar sobre el tráfico dividido en la recomendación.

1. Elija un valor.

   Determina el tipo de elemento que es más probable que se muestre, en función de uno de los numerosos criterios disponibles.

1. Elija un evaluador.

1. Escriba la palabra clave para completar los atributos de la regla.

   Por ejemplo, la regla completa podría ser &quot;La categoría contiene zapatos de subcadena&quot;.

1. Seleccione la ponderación para asignarla a la regla.

   Las opciones varían de 0 a 100 en incrementos de 25.

1. Si lo desea, agregue reglas adicionales.

Cuando termine, haga clic en **[!UICONTROL Crear]**.

Cuando se crea una nueva actividad de **[!UICONTROL Recommendations]** o se edita una existente, la casilla de verificación **[!UICONTROL Guardar criterios para más adelante]** está seleccionada de forma predeterminada. Para evitar el uso de criterios en otras actividades, desactive la casilla de verificación antes de guardar.
