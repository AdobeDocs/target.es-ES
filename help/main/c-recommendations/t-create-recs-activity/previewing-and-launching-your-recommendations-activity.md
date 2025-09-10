---
keywords: Recommendations;oferta;previsualización;inicio;estado;criterios;algoritmo
description: Obtenga información sobre cómo obtener una vista previa de la actividad de Adobe [!DNL Target] Recommendations para garantizar que los resultados estén disponibles antes de iniciar la actividad.
title: ¿Cómo puedo obtener una vista previa e iniciar una actividad de Recommendations?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 26b0c5455e82014dab92c925ecc88bddb3947d2f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 15%

---

# Vista previa e inicio de su actividad de Recommendations

Después de crear su actividad [!UICONTROL Recommendations], [!UICONTROL A/B Test] o [!UICONTROL Experience Targeting] (XT) que contiene [ofertas de recomendaciones](/help/main/c-recommendations/recommendations-as-an-offer.md), necesitará previsualizar las recomendaciones para asegurarse de que los resultados estén disponibles antes de iniciar la actividad. [!DNL Target Recommendations] ofrece varias formas de obtener una vista previa de sus recomendaciones.

## Comprobación del estado del algoritmo de Recommendations

Después de crear una actividad, [!DNL Recommendations] ejecuta un algoritmo para generar recomendaciones. Este algoritmo puede tardar unas horas en ejecutarse.

Puede comprobar si el algoritmo ha terminado de ejecutarse en el diagrama de información general [!UICONTROL Activity], donde se muestra el estado de los criterios. La siguiente ilustración muestra el estado en el diagrama de actividad en la página [!DNL Recommendations] de una actividad [!UICONTROL Overview]:

![Página de información general de la actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

Los resultados de estado incluyen los siguientes, como se muestra a continuación:

* [!UICONTROL Results Ready]: indica que el algoritmo ha devuelto resultados
* [!UICONTROL Results Not Ready]: indica que el algoritmo no ha terminado de ejecutarse.
* [!UICONTROL Feed Failure]: indica que no se pudo recuperar el archivo de fuente de criterios personalizados.

![Cuadro de diálogo de resultados](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## ¿Cuánto tiempo tardará en ejecutarse el algoritmo?

Después de guardar una actividad que contiene un criterio, [!DNL Target] calcula las recomendaciones según la colección, los criterios, el diseño y las promociones seleccionados. Este cálculo tarda unos minutos en realizarse. El lapso de tiempo difiere según la lógica de recomendación, el intervalo de datos, el número de elementos del catálogo, la cantidad de datos de comportamiento que sus clientes hayan generado y la fuente de datos de comportamiento seleccionada.

La fuente de datos de comportamiento tiene el impacto mayor sobre el tiempo de procesamiento, como se indica a continuación:

### mboxes regionales clásicos

Si se seleccionan mboxes como fuente de datos de comportamiento, una vez creada, los criterios se ejecutan inmediatamente. Dependiendo de la cantidad de datos de comportamiento utilizados y del tamaño del catálogo, el algoritmo puede tardar hasta 12 horas en ejecutarse. Realizar cambios en la configuración de criterios suele resultar en una nueva ejecución del algoritmo. Según el cambio realizado, es posible que las recomendaciones calculadas anteriormente no estén disponibles hasta que se complete una nueva ejecución; o para cambios más grandes, solo el contenido predeterminado o de copia de seguridad estará disponible hasta que se complete una nueva ejecución. Si no se modifica un algoritmo, [!DNL Target] se vuelve a ejecutar automáticamente cada 12 a 48 horas, según el intervalo de datos seleccionado.

### [!DNL Adobe Analytics]

Si los criterios utilizan [!DNL Adobe Analytics] como fuente de datos de comportamiento, una vez creados, el tiempo de disponibilidad de los criterios depende de si el grupo de informes seleccionado y la ventana de vista al pasado se han utilizado para otros criterios.

* **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. Este periodo de tiempo depende de la carga del sistema de [!DNL Analytics].
* **Criterios nuevos o editados que usan un grupo de informes ya disponible**: Al crear un nuevo criterio o editar uno existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations], con un intervalo de datos igual o inferior al seleccionado, los datos estarán disponibles inmediatamente y no se requiere una configuración única. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
* **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación [!UICONTROL Viewed Affinity], cuando un usuario ve un producto, se pasa una llamada de seguimiento de vista de producto a [!DNL Analytics] casi en tiempo real. Los datos de [!DNL Analytics] se insertan en [!DNL Target] a principios del día siguiente y [!DNL Target] ejecuta el algoritmo en menos de 12 horas.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] no requiere la ejecución de ningún algoritmo sin conexión y los resultados están disponibles al instante. Los algoritmos [!UICONTROL Top Viewed] y [!UICONTROL Top Sellers] basados en datos de mbox generalmente producen resultados muy rápidamente debido al cálculo más sencillo requerido. Estas pueden ser buenas opciones cuando desea obtener una vista previa de un cambio de diseño o confirmar que los datos de comportamiento se recopilan correctamente.

## Uso de vínculos de control de calidad para previsualizar Recommendations

Una vez que el algoritmo tenga los resultados listos, puede obtener una vista previa de esos resultados mediante la funcionalidad [QA link](/help/main/c-activities/c-activity-qa/activity-qa.md) de [!DNL Adobe Target]. Los vínculos de control de calidad están disponibles en la sección [!UICONTROL Activity Location] de la página de información general de [!UICONTROL Activity]:

>[!NOTE]
>
>De manera predeterminada, [!DNL Target] le agrega automáticamente a la audiencia requerida para el vínculo de control de calidad. Si esta configuración está desactivada y la actividad tiene reglas de segmentación, el perfil de usuario debe cumplir esas reglas de segmentación para ver la experiencia que contiene recomendaciones.

El uso de un vínculo de control de calidad le permite obtener una vista previa de las recomendaciones de su página:

![Productos destacados](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* El modo de control de calidad de Target es &quot;adhesivo&quot; y se guarda en una cookie. Si no sale del modo de control de calidad, seguirá viendo los resultados de control de calidad en todo el sitio. Para salir del modo de control de calidad, use [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* En modo de control de calidad, explorar el sitio no afectará a [!UICONTROL Recently Viewed Items] ni a [!UICONTROL Recently Purchased Items] de su perfil. Este comportamiento se produce por diseño para evitar la contaminación no intencionada de los datos de comportamiento de la producción. Para obtener una vista previa de los resultados de los criterios de [!UICONTROL Recently Viewed Items] o [!UICONTROL User-Based Recommendations], primero examine el sitio fuera del modo de control de calidad y, a continuación, utilice la misma sesión para abrir un vínculo del modo de control de calidad.

## Uso de la descarga de CSV para previsualizar las recomendaciones

En algunos casos, es posible que desee auditar los elementos específicos recomendados. Esto es especialmente útil cuando se usan algoritmos como [!UICONTROL People Who Viewed This, Viewed That], en los que se recomienda un conjunto diferente de elementos según el elemento que el usuario esté viendo en ese momento y es posible que tenga miles o millones de elementos diferentes en el catálogo.

Los resultados no están disponibles para su descarga hasta que se muestre un estado [!UICONTROL Results Ready] para al menos un algoritmo en la actividad.

Para descargar los resultados para previsualizarlos, haga clic en el icono de menú en la esquina superior derecha de la página Información general de actividad y, a continuación, haga clic en **[!UICONTROL Download data]**.

![Opción de descarga de datos](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Se descargará un archivo CSV. Ábralo para ver los artículos recomendados:

![Archivo CSV de elementos recomendados](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De izquierda a derecha se muestra una lista de los artículos recomendados, en este caso los más vistos. Las recomendaciones están separadas por entorno, en este caso solo el entorno Producción tiene recomendaciones.

Si un asterisco (*) es el primer valor de una fila, indica [elementos de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md). Los elementos de copia de seguridad se muestran si no todas las ranuras de un diseño se pueden rellenar con los elementos recomendados del algoritmo (criterios).

Para otros tipos de algoritmo basados en un valor de clave, como [!UICONTROL People Who Viewed This, Viewed That], los valores de clave (es decir, los elementos &quot;Este&quot;) se muestran en la columna situada más a la izquierda y los elementos recomendados (es decir, los elementos &quot;Ese&quot;) se muestran de izquierda a derecha en las columnas Recommendations_X.

>[!NOTE]
>
>Las descargas de resultados no están disponibles para las actividades que contienen un algoritmo [!UICONTROL User-Based Recommendations]. Las descargas de resultados no están disponibles para los criterios que usan la lógica de recomendación [!UICONTROL Recently-Viewed Items].

### Formato de descarga CSV para algoritmos basados en popularidad y en claves {#format}

El archivo de descarga CSV refleja de forma coherente los resultados generados tras la ejecución de criterios de back-end.

* **Para los algoritmos basados en popularidad (no basados en claves), el archivo incluye:**

   * Una fila de recomendaciones de copia de seguridad con el prefijo * (un asterisco)
   * Una fila independiente que enumera recomendaciones basadas en la configuración del algoritmo

* **Para algoritmos basados en claves, el archivo incluye:**

   * Una fila de copia de seguridad similar a los algoritmos basados en popularidad
   * Varias filas en formato de clave-valor, donde la primera entrada es el ID de producto de la clave, seguido de ID de producto separados por comas que representan candidatos de recomendación

## Activación de la actividad de Recommendations

En la ficha [!UICONTROL Activity Overview], haga clic en la flecha desplegable Estado y seleccione **[!UICONTROL Activate]**.

Si su actividad [!UICONTROL Recommendations] se encuentra en el estado [!UICONTROL Inactive], la lista desplegable tiene la etiqueta [!UICONTROL Inactive].

Después de unos segundos o un par de minutos, el estado cambia a [!UICONTROL Live].

También puede desactivar o archivar la actividad mediante la misma lista desplegable.

## Evitar interrupciones al cambiar la configuración de Recommendations

Si se cambian [!DNL Recommendations] colecciones, criterios, promociones o configuraciones de diseño en una actividad activa, es posible que los resultados del algoritmo no sean válidos y que el estado de un algoritmo cambie a [!UICONTROL Results Not Ready].

Para evitar interrumpir una actividad activa, se recomienda seguir el siguiente método al modificarla:

1. Duplique la actividad original (actividad 1) y los criterios que desea modificar para crear una nueva actividad (actividad 2).
1. Realice cambios en la actividad duplicada (actividad 2) y en los criterios y espere a que el algoritmo genere resultados.
1. Previsualice la nueva actividad modificada (actividad 2) y confirme que los resultados son los deseados.
1. Active la nueva actividad (actividad 2).
1. Desactive la actividad original (actividad 1).

Si necesita conservar los resultados del historial de informes en la misma actividad, es posible un enfoque alternativo que podría provocar una interrupción temporal en la disponibilidad de las recomendaciones:

1. Duplique la actividad original (actividad 1) y los criterios que desea modificar para crear una nueva actividad (actividad 2).
1. Realice cambios en la actividad duplicada (actividad 2) y en los criterios y espere a que el algoritmo genere resultados.
1. Previsualice la nueva actividad modificada (actividad 2) y confirme que los resultados son los deseados.
1. Ponga en pausa la nueva actividad modificada (actividad 2) y cambie los ajustes/criterios por la actividad original (actividad 1).
1. Previsualice la actividad original (actividad 1) y confirme que los resultados son los deseados.
1. Vuelva a activar la actividad original (actividad 1).
