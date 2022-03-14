---
keywords: solución de problemas;preguntas más frecuentes;FAQ;recomendaciones;caracteres especiales;ponderación de atributos;similitud de contenido
description: Consulte la lista preguntas frecuentes y sus respuestas acerca de las actividades de Recommendations de Adobe [!DNL Target] .
title: ¿Dónde puedo encontrar preguntas y respuestas acerca de Recommendations de  [!DNL Target] ?
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '3128'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Preguntas más frecuentes sobre Recommendations

Lista de las preguntas frecuentes (FAQ) acerca de actividades de [!DNL Adobe Target] [!DNL Recommendations].

## ¿Por qué [!UICONTROL la búsqueda en el catálogo] no muestra los resultados correctos cuando busco en un atributo personalizado con un valor numérico?

Cuando se realiza una búsqueda en el catálogo de un atributo personalizado con un valor numérico, los resultados tratan al atributo personalizado como un tipo de cadena en lugar de un valor numérico.

Actualmente, no hay ninguna funcionalidad disponible que permita a los clientes cambiar el tipo de un atributo. Para realizar un cambio, [abra un problema con el cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que haga referencia a los atributos cuyo tipo necesitan que cambie de cadena a numérico.

## ¿Cuánto tiempo llevará ver las actualizaciones de los elementos del catálogo en mi sitio?

El lapso de tiempo y los resultados varían en función de cómo se actualicen los elementos.

| Fuente | Detalles |
| --- | --- |
| Atributos de elemento actualizados mediante mbox o API | <ul><li>Las recomendaciones se actualizan en 15 minutos.</li><li>Las recomendaciones existentes y los atributos de artículos se muestran hasta que haya actualizaciones disponibles.</li><li>La búsqueda en el catálogo se actualiza después del índice del catálogo (de 3 a 8 horas).</li></ul> |
| Atributos de elemento actualizados a través de la fuente | <ul><li>Las recomendaciones se actualizan después de la ingesta de fuentes (de 2 a 8 horas).</li><li>Las recomendaciones existentes y los atributos de artículos se muestran hasta que haya actualizaciones disponibles.</li><li>La búsqueda en el catálogo se actualiza después de la ingesta de fuentes (de 2 a 8 horas) y después del siguiente índice de catálogo (de 3 a 8 horas). La búsqueda en el catálogo se actualiza en un total de 5 a 16 horas.</li></ul> |
| Elemento eliminado del catálogo a través de la IU o API de [!DNL Target] | <ul><li>Las recomendaciones se actualizan en 15 minutos.</li><li>Las recomendaciones existentes y los atributos de artículos se muestran hasta que haya actualizaciones disponibles.</li><li>La búsqueda en el catálogo se actualiza después del índice del catálogo (de 3 a 8 horas).</li></ul> |
| Elemento añadido al catálogo mediante mbox o API | <ul><li>Las recomendaciones se actualizan después de ejecutar el algoritmo. Las ejecuciones de algoritmos se programan cada 12 horas para algoritmos de 1 a 2 días, y cada 24 horas para algoritmos de más de 7 días.</li><li>Las recomendaciones existentes se muestran hasta que haya actualizaciones disponibles si el elemento añadido no es una clave solicitada.</li><li>Las recomendaciones de copia de seguridad se muestran hasta que haya actualizaciones disponibles si el elemento añadido es una clave solicitada.</li><li>La búsqueda en el catálogo se actualiza después del índice del catálogo (de 3 a 8 horas).</li></ul> |
| Elemento añadido al catálogo mediante fuente | <ul><li>Las recomendaciones se actualizan después de ingerir la fuente (de 2 a 8 horas). Las ejecuciones de algoritmos posteriores se programan cada 12 horas para algoritmos de 1 a 2 días, y cada 24 horas para algoritmos de más de 7 días. Las recomendaciones se actualizan en un plazo total de 2 a 32 horas.</li><li>Las recomendaciones existentes se muestran hasta que haya actualizaciones disponibles si el elemento añadido no es una clave solicitada.</li><li>Las recomendaciones de copia de seguridad se muestran hasta que haya actualizaciones disponibles si el elemento añadido es una clave solicitada.</li><li>La búsqueda en el catálogo se actualiza después de la ingesta de fuentes (de 2 a 8 horas) y después del índice del catálogo (de 3 a 8 horas). La búsqueda en el catálogo se actualiza en un total de 5 a 16 horas.</li></ul> |

Tras importar un archivo de fuente o recibir actualizaciones de entidad mediante API o mbox, los cambios siguientes se reflejarán en menos de 60 minutos:

* Si un elemento se ha excluido anteriormente, pero ahora debe incluirse, este se incluirá en la próxima ejecución del algoritmo (de 12 a 24 horas).

   Esta situación se produce porque [!DNL Target] aplica exclusiones tanto en línea como sin conexión. Cuando se excluye un elemento recientemente, la exclusión en línea se aplica rápidamente. Cuando se incluye un elemento reciente, la exclusión en línea desaparece al instante, pero la exclusión sin conexión no desaparece hasta que se ejecuta el siguiente algoritmo.

* Si un elemento se incluyó anteriormente, pero ahora debe excluirse, este se excluye por la línea de tiempo “atributos de elemento actualizados...” analizada anteriormente en función de la fuente (15 minutos a través de mbox/API o de 12 a 24 horas a través de la fuente).

Los siguientes cambios no se reflejan hasta que se ejecute el siguiente algoritmo (en 12-24 horas):

* Atributos de elemento utilizados en las reglas de recopilación usadas para la actividad.
* Atributos de elemento utilizados en una promoción en función de un atributo o una colección asociada con la actividad.
* Categoría del elemento en la que este aparece para una “Categoría actual” o “Categoría favorita” en los algoritmos Principales vendedores o Más visitados.
* “Clasificación de los elementos recomendados cuando el atributo ha cambiado” es un atributo personalizado que se usa como clave personalizada para un algoritmo.
* Clasificación de los artículos recomendados en función de uno o más atributos modificados cuando la lógica de recomendación es “Elementos con atributos similares”, cuando se utilizan factores de ponderación de “Similitud de contenido” o cuando se utilizan factores de “Ponderación de atributos”.

>[!NOTE]
>
>Un archivo de fuente se considera importado cuando su estado cambia de “Importación de elementos” a “Preparación de las actualizaciones del índice de búsqueda”. Las actualizaciones pueden tardar más de 60 minutos en reflejarse en la interfaz de usuario Búsqueda en el catálogo. La Búsqueda en el catálogo está actualizada cuando el estado de la fuente cambia a Actualizaciones completadas. Incluso si la búsqueda en el catálogo aún no está actualizada, su sitio reflejará las actualizaciones en los periodos de tiempo enumerados arriba. El tiempo de actualización del índice de Búsqueda en el catálogo más reciente se muestra en la página Búsqueda en el catálogo.

## ¿Cuánto tiempo se tarda en reflejar en mi sitio un cambio en la configuración de mi actividad de [!UICONTROL Recommendations], oferta, promociones o configuración de criterios?

* Un cambio en la configuración de la promoción puede tardar hasta cinco horas en reflejarse en el sitio.
* Es posible que un cambio en la configuración de otros criterios no se refleje hasta que se ejecute el siguiente algoritmo:

   * Algunas configuraciones de criterios (por ejemplo, “adición de una regla de inclusión dinámica”) se reflejan instantáneamente.
   * Otra configuración de criterios (por ejemplo, “eliminación de una regla de inclusión dinámica”, cambio de ventana retrospectiva, etc.) no se pueden incorporar hasta que se ejecute el siguiente algoritmo.
   * Los cambios activan las ejecuciones de algoritmos, pero pueden tardar hasta 24 horas en completarse. Los algoritmos también se ejecutan de forma programada cada 12 a 24 horas.

## ¿Cuánto tiempo tarda un usuario en mostrar su comportamiento (por ejemplo, haciendo clic en el producto A y comprando el producto B) en las recomendaciones que *recibe?*

* El producto/contenido que se está viendo/comprando influye en las recomendaciones que el usuario recibe en la misma vista de página/solicitud de contenido de [!DNL Target].
* El comportamiento histórico del usuario, como “último producto visualizado”, “producto más visualizado” y el historial general de visualización/compra se actualiza con esa solicitud, lo que influye en las recomendaciones que el usuario recibe en la siguiente vista de página/solicitud de contenido de [!DNL Target]. Por ejemplo, los algoritmos de “Artículos vistos recientemente” y “Recomendados para ti” se actualizan con cada vista/compra de producto y se reflejan en la solicitud de contenido posterior.

## ¿Cuánto tiempo tardan los usuarios en reflejar el comportamiento de un usuario (por ejemplo, hacer clic en el producto A y comprar el producto B) en las recomendaciones que reciben *otros usuarios*?

El comportamiento de los usuarios en conjunto se incorpora al procesamiento de algoritmos sin conexión, con cada algoritmo ejecutado cada 12 a 24 horas.

## ¿Qué debo hacer si hay caracteres especiales que rompen la matriz? {#section_D27214116EE443638A60887C7D1C534E}

Utilice valores escapados en JavaScript. Las comillas ( &quot; ) pueden romper la matriz. El siguiente fragmento de código es un ejemplo de valores escapados:

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## ¿Por qué no están disponibles para su selección todos los criterios, incluidos los personalizados, al crear una actividad de Recommendations? {#section_B2265AC8B8A94E0298D495A05C5D817F}

Los criterios disponibles dependen de la categoría actual. Cuando crea ofertas de recomendaciones, el selector de algoritmo muestra criterios basados en el ID de la categoría.

Si la ubicación en la que aplica los criterios no contiene el Id. de categoría, determinados criterios no están disponibles en el selector de algoritmo.

Si utiliza una ubicación en la que el ID de categoría está presente en el mbox, el selector de criterio contendrá todos los criterios aplicables.

[!DNL Target] tiene una configuración de [Filtrar los criterios no compatibles](/help/main/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) para controlar el filtrado inteligente del selector de algoritmo.

>[!NOTE]
>
>Este ajuste se aplica únicamente a las actividades creadas en el [!UICONTROL Compositor de experiencias visuales] (VEC). Esta configuración no se aplica a las actividades creadas en el Compositor de experiencias basadas en formularios ([!DNL Target] carece de contexto de ubicación).

Para acceder al ajuste [!UICONTROL Filtrar los criterios no compatibles], haga clic en [!UICONTROL Recomendaciones] > [!UICONTROL Configuración]:

![](assets/recs_settings_filter.png)

Si el ajuste [!UICONTROL Filtrar los criterios no compatibles] no está habilitado, [!DNL Target] no filtra los algoritmos en el selector de algoritmos y muestra todos ellos.

Si el ajuste de la configuración [!UICONTROL Filtrar los criterios no compatibles] está habilitado, en las actividades VEC, [!DNL Target] lee entityId y el ID de la categoría de la ubicación seleccionada y, a continuación, se muestran los algoritmos basados en `currentItem|currentCategory` (si los valores respectivos están presentes en esa ubicación). Como resultado, de forma predeterminada solo se muestran en el selector de algoritmos aquellos compatibles con la ubicación seleccionada.

Aunque el ajuste [!UICONTROL Filtrar los criterios no compatibles] esté habilitado, puede ver los algoritmos no compatibles anulando la selección de la casilla [!UICONTROL Compatibles] al seleccionar los criterios.

![](assets/compatible_checkbox.png)

La siguiente lista contiene casos especiales en los que [!DNL Target] no muestra la casilla [!UICONTROL Compatible]:

* Tanto entityId como el Id. de categoría están presentes en la ubicación, por lo que no se filtra ningún resultado.
* Utiliza la versión 55 o anterior de [!DNL mbox.js].
* No se activa ninguna llamada a mbox desde la página (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* Los parámetros de [!DNL Target] no están definidos.

## ¿Qué debería hacer si una colección en Recommendations resulta en cero (0)? {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

Tenga en cuenta la siguiente información si ve que una colección que era distinta de cero resulta en cero:

* Puede volver a guardar la colección para comprobar si el número se actualiza. Al volver a guardar, la colección vuelve a ejecutar todos los algoritmos que utilizan esa colección.
* ¿Está viendo el entorno correcto? Vaya a [!DNL /target/products.html#recsSettings] para asegurarse (como se muestra a continuación).

   ![](assets/product_catalog.png)

* ¿Está actualizado el índice? Vaya a [!DNL /target/products.html#productSearch] y compruebe cuántas horas hace que se actualizó el índice (por ejemplo, “Indexado hace 3 horas”). Puede actualizar el índice si lo desea.
* ¿Ha cambiado algo en la fuente o en la capa de datos que resulte en que sus entidades ya no cumplan las reglas de la colección? Compruebe que las mayúsculas y minúsculas concuerden.
* ¿Se ejecutó correctamente la fuente? ¿Ha cambiado alguien el directorio FTP, la contraseña, etc.?
* [!DNL Target] intenta que las actualizaciones del envío (en la página/aplicación del cliente) se produzcan lo más rápido posible. No obstante, [!DNL Target] también debe proporcionar determinada representación en la IU para el experto en marketing. [!DNL Target] no retrasa las actualizaciones de entrega hasta que las actualizaciones de la IU se sincronizan con ellas. Puede utilizar [mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md) para comprobar el contenido del sistema en el momento de recibirse una solicitud.

## ¿Cuál es la diferencia entre la ponderación de atributos general y la específica para similitud de contenido? {#section_FCD96598CBB44B16A4C6C084649928FF}

Existen dos formas de ponderación de atributos: la “ponderación de atributos estándar” y la “ponderación de atributos de similitud de contenido”.

La “ponderación de atributos estándar” se aplica a la mayoría de los tipos de criterio, si no a todos (no solo a los de Similitud de contenido). Este tipo de ponderación da más peso a determinados valores de atributo. En el ejemplo siguiente, los productos de Nike reciben un empujón en las recomendaciones generadas.

![](assets/attribute_weighting_example.png)

La “ponderación de atributos de similitud de contenido” se aplica únicamente a los criterios de Similitud de contenido.

Este tipo de ponderación es más dinámico y se basa en la “clave de recomendación” actual (el elemento que se está viendo en ese momento). En el siguiente ejemplo (marca x 16), si un visitante estuviera viendo zapatillas de Nike, sería más probable que se le recomendaran otros productos de Nike (no necesariamente zapatillas) que zapatillas de otras marcas. Si un visitante estuviera viendo zapatillas de Adidas, tendría más probabilidades de recibir la recomendación de otros productos de Adidas.

![](assets/content_similarity_example.png)

## ¿Por qué, a veces, [!DNL Target] no puede mostrar recomendaciones? {#section_DB3F40673AED42228E407C05437D99E9}

[!DNL Target] a veces no puede mostrar recomendaciones debido al bajo número de recomendaciones disponibles.

La cantidad de valores generados por criterio es tres veces el número de entidades especificadas en el diseño. El filtrado en tiempo de ejecución (por ejemplo, el inventario, la coincidencia de atributos de mbox) se aplica después de que se generen los valores de 3x, por lo que es posible terminar con menos de 3 valores en el momento de la entrega. Para mitigar esta situación, aumente el número de entidades en el diseño ocultando entidades adicionales.

Puede usar el siguiente JavaScript al comienzo del diseño para incrementar el número de entidades solicitadas. En este ejemplo, el recuento de entidades solicitadas sería 30 (3 x 10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## ¿Cuál es el límite de tamaño de una llamada API para insertar/actualizar productos? ¿Puedo actualizar 50 000 productos en una llamada usando la API en vez de una fuente? {#section_434FE1F187B7436AA39B7C14C7895168}

[!DNL Target] impone a las publicaciones un límite de 50 MB en el nivel de aplicación. Sin embargo, eso ocurre solamente cuando pasa el encabezado de tipo de contenido `application/x-www-form-urlencoded`.

Bien podría probar enviar 50 000 productos en una sola llamada. Si da error, debería dividir ese número en lotes. Adobe suele recomendar que los clientes dividan sus llamadas en lotes de 5000 o 10 000 productos para reducir la probabilidad de tiempo de espera agotado debido a la carga del sistema.

## ¿Es necesario especificar el nombre del mbox al crear en criterios, promociones o reglas de prueba de plantillas de Recommendations? {#section_FFA42ABCC5954B48A46526E32A3A88A2}

Cuando se crean criterios, promociones o reglas de prueba de plantilla basadas en un parámetro de mbox de Recommendations, `mboxParameter` ya no le solicita `mboxName`. El nombre del mbox es ahora opcional. Este cambio le permite usar parámetros de varios mboxes o hacer referencia a un parámetro que aún no se haya registrado en el perímetro.

Para seleccionar el parámetro deseado:

* Al crear un criterio, una promoción o una regla de prueba de plantilla, seleccione un nombre de parámetro en la lista. Comience a escribir los primeros caracteres del nombre de parámetro deseado o escriba el nombre completo del parámetro deseado.
* Si recuerda el nombre del mbox pero no el del parámetro, utilice la casilla de verificación para filtrar en función de un mbox conocido que pase el parámetro deseado.

Con ninguno de estos métodos existe vínculo entre el mbox y el parámetro. Los criterios, las promociones y las reglas de prueba de plantilla funcionarán sobre la base del parámetro en todos los mboxes que pasen dicho parámetro.

Si edita un criterio, promoción o regla de prueba de plantilla existente, el criterio de filtrado se muestra con el nombre de mbox que se suministró durante la creación.

## ¿Por qué no puedo guardar la actividad de Recommendations heredada después de definir una nueva audiencia? {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

Asegúrese de que la audiencia tiene un nombre único. Si le dio a la audiencia el mismo nombre que una audiencia existente, no puede guardar su actividad de Recommendations heredada (una actividad de Recommendations creada antes de octubre de 2016).

## ¿Cuál es el tamaño máximo de un archivo CSV para una carga de fuente? {#section_20F1AF4839A447B9889B246D6E873538}

No hay un límite estricto en el número de filas o el tamaño del archivo para la carga del archivo CSV de una fuente. Sin embargo, como práctica recomendada, Adobe recomienda limitar el tamaño del archivo CSV a 1 GB para evitar errores durante el proceso de carga del archivo. Si el tamaño del archivo excede 1 GB, lo ideal es que se divida en varios archivos de fuentes. El número máximo de columnas de atributos personalizados es 100 y los atributos personalizados están limitados a 4096 caracteres. Hay otros límites en la longitud de las columnas requeridas disponibles en la página Limitaciones de [[!DNL Target] ](/help/main/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1).

## ¿Puedo excluir dinámicamente una entidad? {#exclude}

En la cadena de consulta, puede pasar los ID de entidad de las entidades que desee excluir de las recomendaciones. Por ejemplo, quizás desee excluir artículos que ya se encuentren en el carro de compras.

Para habilitar la funcionalidad de exclusión, utilice el parámetro mbox `excludedIds`. Este parámetro apunta a una lista de ID de entidad separados por comas. Por ejemplo, `mboxCreate(..., "excludedIds=1,2,3,4,5")`. El valor se envía al solicitar recomendaciones.

La exclusión solo se realiza para la llamada de [!DNL Target] actual; los elementos no se excluyen en llamadas de [!DNL Target] subsiguientes a menos que se vuelva a pasar el valor `excludedIds`. Para excluir artículos del carro de compras de las recomendaciones de cada página, siga pasando el valor `excludedIds` en cada página.

>[!NOTE]
>
>Si se excluyen demasiadas entidades, las recomendaciones se comportan como si no hubiera suficientes entidades para rellenar la plantilla de recomendaciones.

Para excluir `entityIds`, añada el token `&excludes=${mbox.excludedIds}` a la dirección URL de contenido de la oferta. Cuando se extrae la dirección URL de contenido, se substituyen los parámetros requeridos mediante parámetros de solicitud de mbox actuales.

De forma predeterminada, esta característica está activada para las recomendaciones de nueva creación. Las recomendaciones existentes deben guardarse para permitir entidades dinámicamente excluidas.

## ¿Qué significa la respuesta NO_CONTENT que a veces se devuelve en el seguimiento de contenido de Recommendations?

NO_CONTENT se devuelve cuando las recomendaciones no están disponibles para la combinación de algoritmo y clave solicitada. En términos generales, esta situación se produce cuando las copias de seguridad están desactivadas para el algoritmo y una o más de las siguientes situaciones también son ciertas:

* Los resultados aún no están listos.

   Esta situación suele producirse al guardar por primera vez una actividad recién creada o después de realizar cambios de configuración en la colección, los criterios o las promociones utilizados en la actividad.

* Los resultados están listos, pero aún no se han almacenado en caché en el servidor Edge más cercano, para la combinación de algoritmo y clave solicitada.

   La solicitud inicia una operación de almacenamiento en caché, por lo que este problema debe resolverse después de que se vuelva a cargar la página o transcurran unos minutos.

* Los resultados están listos, pero no están disponibles para el valor de clave proporcionado.

   Esta situación suele ocurrir cuando se solicitan recomendaciones para un artículo que se añadió al catálogo después de que se ejecute el algoritmo más reciente y se resuelve después de que se ejecute el siguiente.

* El procesamiento parcial de la plantilla está deshabilitado y no hay suficientes resultados disponibles para rellenarla.

   Esta situación suele ocurrir cuando se tiene una regla de inclusión dinámica, que filtra de forma agresiva muchos elementos de los posibles resultados. Para evitar situaciones, habilite las copias de seguridad y no aplique la regla de inclusión a las copias de seguridad, o utilice los criterios en secuencia con criterios filtrados de manera menos agresiva.

## ¿Persisten las recomendaciones basadas en artículos vistos recientemente en varios dispositivos para un único visitante? {#persist-across-devices}

Cuando un visitante inicia una sesión, el ID de sesión está vinculado a un solo equipo Edge y se almacena una caché de perfiles temporal en este equipo Edge. Las solicitudes posteriores de la misma sesión leen esta caché de perfil, incluidos los artículos vistos recientemente.

Cuando finaliza la sesión (por lo general, cuando caduca tras 30 minutos sin actividad), el estado de la sesión, incluidos los artículos vistos recientemente, persiste en un almacenamiento de perfiles más permanente en el mismo perímetro geográfico.

Las sesiones posteriores de distintos dispositivos pueden acceder a estos elementos vistos recientemente, siempre que la nueva sesión esté vinculada al perfil del cliente mediante el mismo ID de Marketing Cloud (MCID), ID de Experience Cloud (ECID) o CustomerID/mbox3rdPartyId.

Si un visitante tiene dos sesiones activas a la vez, los elementos visualizados recientemente en un dispositivo no actualizan los elementos visualizados recientemente en el otro dispositivo, a menos que los dispositivos se vean obligados a compartir el ID de sesión. Existe una solución alternativa para el problema, pero [!DNL Target] no admite directamente el uso compartido de un ID de sesión entre varios dispositivos. El cliente debe administrar por sí mismo este uso compartido de ID.

Este comportamiento sigue ocurriendo si un visitante está activo en un dispositivo y luego se activa en el otro dispositivo unos minutos después. La primera sesión del dispositivo no caduca durante 30 minutos y puede haber hasta cinco minutos de retraso antes de que el estado del perfil se escriba en el estado permanente y se procese. Espere 35 minutos para que la sesión caduque y el perfil se almacene al probar este comportamiento.

Si el visitante no tiene dos sesiones activas a la vez, los artículos vistos recientemente en un dispositivo actualizarán los vistos recientemente en el otro dispositivo siempre y cuando la sesión haya finalizado. Espere 35 minutos para que la sesión caduque al probar este comportamiento.

## ¿Puedo usar un algoritmo creado en [!DNL Adobe Recommendations Classic] en [!DNL Recommendations Premium]?

Un algoritmo creado en [!DNL Recommendations Classic] no es compatible con [!DNL Recommendations Premium]. Puede utilizar el algoritmo heredado en [!DNL Target Premium]; sin embargo, el algoritmo puede crear problemas de sincronización al desactivar o eliminar la actividad en la IU de [!DNL Target Premium]. Para obtener más información acerca de las diferencias entre las dos soluciones, consulte Actividades de [[!DNL Recommendations Classic] versus [!DNL Recommendations] en [!DNL Target Premium]](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md).

## ¿Cómo puedo recomendar solo nuevos artículos o vídeos? {#recommend-new-articles}

Algunos clientes de medios y publicaciones desean asegurarse de que los artículos recomendados incluyan solo los artículos o vídeos más recientes. Por ejemplo, un cliente de [!DNL Target] utilizó el siguiente método para recomendar artículos con menos de 60 días de antigüedad:

1. Pase la fecha de publicación del artículo, en formato AAMMDD, como atributo de entidad personalizado.
1. Cree un script de perfil que sea la fecha actual menos 60 días, también en formato AAAAMMDD.
1. Utilice un filtro de inclusión dinámica en los criterios para que `publish date > today’s date minus 60 days`.

### Transfiera la fecha de publicación como un atributo de entidad personalizado:

| Atributo de la entidad | Ejemplo |
| --- | --- |
| issueDate | 2021218 |
| lastViewDate | 2021701 |
| parentCategory | comentario |
| publishDate | 20210113 |
| publishDateDisplay | 13 de enero de 2021 |

### Configure el script de perfil:

![Ejemplo de script de perfil](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

### Configure la regla de inclusión:

![Regla de inclusión de muestra](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)

>[!NOTE]
>
>Este ejemplo también se puede realizar utilizando la coincidencia de parámetros y pasando el valor `priorDate60` como parámetro de mbox.
