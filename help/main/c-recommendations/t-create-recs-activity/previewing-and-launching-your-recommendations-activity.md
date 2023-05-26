---
keywords: Recommendations;oferta;previsualización;inicio;estado;criterios;algoritmo
description: Obtenga información sobre cómo previsualizar el Adobe [!DNL Target] Actividad de Recommendations para garantizar que los resultados estén disponibles antes de iniciar la actividad.
title: ¿Cómo puedo obtener una vista previa e iniciar una actividad de Recommendations?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 17%

---

# Vista previa e inicio de su actividad de Recommendations

Después de crear su [!UICONTROL Recommendations], [!UICONTROL Prueba A/B], o [!UICONTROL Segmentación de experiencias] Actividad (XT) que contiene [Ofertas de Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md), le recomendamos que previsualice las recomendaciones para asegurarse de que los resultados estén disponibles antes de iniciar la actividad. [!DNL Target Recommendations] ofrece varias formas de previsualizar las recomendaciones.

## Comprobación del estado del algoritmo Recommendations

Después de crear una actividad de, [!DNL Recommendations] ejecuta un algoritmo para generar recomendaciones. Este algoritmo puede tardar unas horas en ejecutarse.

Puede comprobar si el algoritmo ha terminado de ejecutarse en [!UICONTROL Actividad] diagrama de información general, donde se muestra el estado de los criterios. La siguiente ilustración muestra el estado en el diagrama de actividad en una [!DNL Recommendations] de la actividad [!UICONTROL Información general] página:

![Página de información general de actividad Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

La siguiente ilustración muestra el estado de una [!UICONTROL Prueba A/B] o la actividad XT de [!UICONTROL Información general] página:

![Página Resumen de las Pruebas A/B](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Los resultados de estado incluyen los siguientes, como se muestra a continuación:

* [!UICONTROL Resultados disponibles]: indica que el algoritmo ha devuelto resultados
* [!UICONTROL Resultados no preparados]: indica que el algoritmo no ha terminado de ejecutarse.
* [!UICONTROL Error de fuente]: indica que no se pudo recuperar el archivo de fuente de criterios personalizados.

![Cuadro de diálogo Resultados](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## ¿Cuánto tiempo tardará en ejecutarse el algoritmo?

Después de guardar una actividad que contiene un criterio, [!DNL Target] calcula las recomendaciones en función de la colección, los criterios, el diseño y las promociones seleccionados. Este cálculo tarda unos minutos en realizarse. El lapso de tiempo difiere según la lógica de recomendación, el intervalo de datos, el número de elementos del catálogo, la cantidad de datos de comportamiento que sus clientes hayan generado y la fuente de datos de comportamiento seleccionada.

La fuente de datos de comportamiento tiene el impacto mayor sobre el tiempo de procesamiento, como se indica a continuación:

### mboxes regionales clásicos

Si se seleccionan mboxes como fuente de datos de comportamiento, una vez creada, los criterios se ejecutan inmediatamente. Dependiendo de la cantidad de datos de comportamiento utilizados y del tamaño del catálogo, el algoritmo puede tardar hasta 12 horas en ejecutarse. Realizar cambios en la configuración de criterios suele resultar en una nueva ejecución del algoritmo. Según el cambio realizado, es posible que las recomendaciones calculadas anteriormente no estén disponibles hasta que se complete una nueva ejecución; o para cambios más grandes, solo el contenido predeterminado o de copia de seguridad estará disponible hasta que se complete una nueva ejecución. Si no se modifica un algoritmo, [!DNL Target] se vuelve a ejecutar automáticamente cada 12 a 48 horas, según el intervalo de datos seleccionado.

### Adobe Analytics.

Si los criterios utilizan [!DNL Adobe Analytics] como fuente de datos de comportamiento, una vez creados, el tiempo de disponibilidad de los criterios depende de si el grupo de informes seleccionado y la ventana de vista al pasado se han utilizado para otros criterios.

* **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. Este periodo de tiempo depende de la carga del sistema de [!DNL Analytics].
* **Criterios nuevos o editados que usan un grupo de informes ya disponible**: Al crear un nuevo criterio o al editar uno existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations]Sin embargo, con un rango de datos igual o menor que el rango de datos seleccionado, los datos están disponibles inmediatamente y no se requiere una configuración única. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
* **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación [!UICONTROL Afinidad de visualización], cuando un usuario ve un producto, se pasa una llamada de seguimiento de visualización de producto a [!DNL Analytics] casi en tiempo real. El [!DNL Analytics] Los datos de se insertan en [!DNL Target] temprano al día siguiente y [!DNL Target] ejecuta el algoritmo en menos de 12 horas.

>[!NOTE]
>
>[!UICONTROL Artículos vistos recientemente] no requiere que se ejecute ningún algoritmo sin conexión y los resultados están disponibles al instante. [!UICONTROL Más visitados] y [!UICONTROL Principales vendedores] los algoritmos basados en datos de mbox generalmente producen resultados muy rápidamente debido al cálculo más sencillo requerido. Estas pueden ser buenas opciones cuando desea obtener una vista previa de un cambio de diseño o confirmar que los datos de comportamiento se recopilan correctamente.

## Uso de vínculos de control de calidad para previsualizar Recommendations

Una vez que el algoritmo tenga los resultados listos, puede obtener una vista previa de esos resultados mediante la variable [Vínculo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) funcionalidad de [!DNL Adobe Target]. Los vínculos de control de calidad están disponibles en [!UICONTROL Control de calidad de actividad] de la página Información general de actividad:

![Vínculo de control de calidad de la actividad](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>De forma predeterminada, [!DNL Target] le añade automáticamente a la audiencia necesaria para el vínculo de control de calidad. Si esta configuración está desactivada y la actividad tiene reglas de segmentación, el perfil de usuario debe cumplir esas reglas de segmentación para ver la experiencia que contiene recomendaciones.

El uso de un vínculo de control de calidad le permite obtener una vista previa de las recomendaciones de su página:

![Productos destacados](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* El modo de control de calidad de Target es &quot;adhesivo&quot; y se guarda en una cookie. Si no sale del modo de control de calidad, seguirá viendo los resultados de dicho control en todo el sitio. Para salir del modo de control de calidad, utilice el [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* En el modo de control de calidad, navegar por el sitio no afectará a la seguridad de su perfil. [!UICONTROL Artículos vistos recientemente] o [!UICONTROL Artículos comprados recientemente]. Este comportamiento se produce por diseño para evitar la contaminación no intencionada de los datos de comportamiento de la producción. Para obtener una vista previa de los resultados de [!UICONTROL Artículos vistos recientemente] o [!UICONTROL Recommendations basado en el usuario] , primero examine el sitio fuera del modo de control de calidad y, a continuación, utilice la misma sesión para abrir un vínculo del modo de control de calidad.


## Uso de la descarga de CSV para previsualizar las recomendaciones

En algunos casos, es posible que desee auditar los elementos específicos recomendados. Esto resulta especialmente útil cuando se utilizan algoritmos como [!UICONTROL Los ususarios que vieron esto, vieron aquello.], donde se recomienda un conjunto diferente de elementos en función del elemento que el usuario esté viendo en ese momento y es posible que tenga miles o millones de elementos diferentes en el catálogo.

Los resultados no están disponibles para su descarga hasta que [!UICONTROL Resultados disponibles] se muestra el estado de al menos un algoritmo en la actividad.

Para descargar los resultados para previsualizarlos, haga clic en el icono de menú en la esquina superior derecha de la página Información general de actividad y, a continuación, haga clic en **[!UICONTROL Descargar datos]**.

![Opción Descargar datos](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Se descargará un archivo CSV. Ábralo para ver los artículos recomendados:

![Archivo CSV de elementos recomendados](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De izquierda a derecha se muestra una lista de los artículos recomendados, en este caso los más vistos. Las recomendaciones están separadas por entorno, en este caso solo el entorno Producción tiene recomendaciones. Para este algoritmo, no se ha aplicado ninguna restricción basada en el valor clave, por lo que la fila etiquetada con un asterisco (*) contiene el conjunto completo de recomendaciones. Para otros tipos de algoritmo basados en un valor clave, como [!UICONTROL Los ususarios que vieron esto, vieron aquello.], los valores clave (es decir, los elementos &quot;Este&quot;) se enumeran en la columna situada más a la izquierda y los elementos recomendados (es decir, los elementos &quot;Ese&quot;) se enumeran de izquierda a derecha en las columnas Recommendations_X.

>[!NOTE]
>
>Las descargas de resultados no están disponibles para las actividades que contienen un [!UICONTROL Recommendations basado en el usuario] algoritmo. Las descargas de resultados no están disponibles para criterios que utilicen la variable [!UICONTROL Artículos vistos recientemente] lógica de recomendación.

## Activación de la actividad de Recommendations

Desde el [!UICONTROL Resumen de actividad] , haga clic en la flecha desplegable junto al estado y seleccione **[!UICONTROL Activar]**.

![Opción Activar](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

Tenga en cuenta que el estado se convierte en [!UICONTROL Activando]:

![Activar](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

Después de unos segundos o un par de minutos, el estado cambia a [!UICONTROL Activo]:

![Activo](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

Tenga en cuenta que también puede desactivar o archivar la actividad mediante la misma lista desplegable.

## Evitar interrupciones al cambiar la configuración de Recommendations

Cambio [!DNL Recommendations] las colecciones, los criterios, las promociones o la configuración de diseño de una actividad en directo pueden provocar que los resultados del algoritmo no sean válidos y que el estado de un algoritmo cambie a [!UICONTROL Resultados no preparados].

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
