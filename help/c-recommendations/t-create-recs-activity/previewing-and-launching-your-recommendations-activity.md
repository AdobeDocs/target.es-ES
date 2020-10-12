---
keywords: Recommendations;offer;preview;launch;status;criteria;algorithm
description: 'Después de crear la actividad de Recommendations, Prueba A/B o Segmentación de experiencias (XT) que contenga ofertas de Adobe Target Recommendations, deberá previsualización para asegurarse de que los resultados están disponibles antes de iniciar la actividad. Destinatario Recommendations oferta varias formas de previsualización de las recomendaciones. '
title: 'Después de crear la actividad de Recommendations, Prueba A/B o Segmentación de experiencias (XT) que contenga ofertas de Adobe Target Recommendations, deberá previsualización para asegurarse de que los resultados están disponibles antes de iniciar la actividad. Destinatario Recommendations oferta varias formas de previsualización de las recomendaciones. '
feature: recs creation
subtopic: Recommendations
translation-type: tm+mt
source-git-commit: 8ae2bf479a9b53693f830515aee55573987bb05b
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 16%

---


# Previsualización e inicio de la actividad de Recommendations

Después de crear la actividad [!UICONTROL Recommendations], Prueba [!UICONTROL A/]B o Segmentación de [!UICONTROL experiencias] (XT) que contenga ofertas [de](/help/c-recommendations/recommendations-as-an-offer.md)Recommendations, deberá previsualización las recomendaciones para asegurarse de que los resultados están disponibles antes de iniciar la actividad. [!DNL Target Recommendations] oferta varias formas de previsualización de las recomendaciones.

## Comprobación del estado del algoritmo de Recommendations

Después de crear una actividad, [!DNL Recommendations] ejecuta un algoritmo para generar recomendaciones. Este algoritmo podría tardar unas horas en ejecutarse.

Puede comprobar si el algoritmo ha terminado de ejecutarse en el diagrama de información general de la [!UICONTROL Actividad] , donde se muestra el estado de los criterios. The following illustration shows the status in the activity diagram on a [!DNL Recommendations] activity&#39;s [!UICONTROL Overview] page:

![Página Información general de actividad de Recommendations](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

En la ilustración siguiente se muestra el estado en la página [!UICONTROL Prueba] A/B o [!UICONTROL Información general] de la actividad XT:

![Página Información general de la prueba A/B](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Los resultados de estado incluyen lo siguiente, como se ilustra a continuación:

* [!UICONTROL Resultados listos]: Indica que el algoritmo ha devuelto resultados
* [!UICONTROL Resultados no listos]: Indica que el algoritmo no ha terminado de ejecutarse.
* [!UICONTROL Error]de fuente: Indica que no se pudo recuperar el archivo de fuente de criterios personalizados.

![Cuadro de diálogo Resultados](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## ¿Cuánto tiempo tardará el algoritmo en ejecutarse?

Después de guardar una actividad que contiene un criterio, calcula las recomendaciones en función de la colección, los criterios, el diseño y las promociones seleccionados. [!DNL Target] Este cálculo tarda algún tiempo en realizarse y el intervalo de tiempo varía según la lógica de recomendación seleccionada, el intervalo de datos, el número de artículos en el catálogo, la cantidad de datos de comportamiento que han generado los clientes y la fuente de datos de comportamiento seleccionada.

La fuente de datos de comportamiento tiene el impacto mayor sobre el tiempo de procesamiento, como se indica a continuación:

### mboxes regionales clásicos

Si se seleccionan mboxes como fuente de datos de comportamiento, una vez creada, los criterios se ejecutan inmediatamente. Dependiendo de la cantidad de datos de comportamiento utilizados y del tamaño del catálogo, el algoritmo puede tardar hasta 12 horas en ejecutarse. Realizar cambios en la configuración de criterios suele resultar en una nueva ejecución del algoritmo. Según el cambio realizado, es posible que las recomendaciones calculadas anteriormente no estén disponibles hasta que se complete una nueva ejecución, o para cambios más grandes, solo el contenido predeterminado o de copia de seguridad estará disponible hasta que se complete una nueva ejecución. Si no se modifica un algoritmo, [!DNL Target] se vuelve a ejecutar automáticamente cada 12 a 48 horas, según el intervalo de datos seleccionado.

### Adobe Analytics.

Si los criterios utilizan [!DNL Adobe Analytics] como fuente de datos de comportamiento, una vez creados, el tiempo de disponibilidad de los criterios depende de si el grupo de informes seleccionado y la ventana de vista al pasado se han utilizado para otros criterios.

* **Configuración de grupos de informes única**: La primera vez que se utiliza un grupo de informes con una ventana retrospectiva de intervalo de datos determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar completamente los datos de comportamiento del grupo de informes seleccionado de [!DNL Analytics]. Este periodo de tiempo depende de la carga del sistema de [!DNL Analytics].
* **Criterios nuevos o editados con un grupo** de informes ya disponible: Al crear un nuevo criterio o editar un criterio existente, si el grupo de informes seleccionado ya se ha utilizado con [!DNL Target Recommendations], con un intervalo de datos igual o inferior al intervalo de datos seleccionado, los datos estarán disponibles inmediatamente y no se requerirá ninguna configuración por única vez. En este caso, o si la configuración de un algoritmo se edita sin modificar el grupo de informes o el intervalo de datos seleccionado, el algoritmo se ejecuta o vuelve a ejecutarse en un plazo de 12 horas.
* **Se ejecuta el algoritmo en curso**: Los datos fluyen desde [!DNL Analytics] a [!DNL Target Recommendations] diariamente. Por ejemplo, para la recomendación [!UICONTROL Afinidad de visualización], cuando un usuario ve un producto, se pasa una llamada de seguimiento de visualización de producto a [!DNL Analytics] casi en tiempo real. The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL Los elementos] vistos recientemente no requieren que se ejecute ningún algoritmo sin conexión y los resultados estarán disponibles al instante. [!UICONTROL Los algoritmos vistos] y [!UICONTROL principales vendedores] basados en datos de mbox generalmente producen resultados muy rápidamente debido al cálculo más simple requerido. Estas pueden ser buenas opciones cuando desea realizar una previsualización de un cambio de diseño o confirmar que los datos de comportamiento se recopilan correctamente.

## Uso de vínculos de control de calidad para previsualización de Recommendations

Una vez que el algoritmo tenga los resultados listos, puede realizar la previsualización mediante la funcionalidad de vínculo [de](/help/c-activities/c-activity-qa/activity-qa.md) control de calidad de [!DNL Adobe Target]. Los vínculos de control de calidad están disponibles en la sección de control de calidad [!UICONTROL de la] Actividad de la página de información general de la Actividad:

![Vínculo de control de calidad de la actividad](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>De forma predeterminada, [!DNL Target] le agrega automáticamente a la audiencia requerida para el vínculo de control de calidad. Si esta configuración está desactivada y la actividad tiene reglas de objetivo, el perfil del usuario debe cumplir esas reglas de objetivo para ver la experiencia que contiene las recomendaciones.

El uso de un vínculo de control de calidad le permite realizar previsualizaciones de las recomendaciones en la página:

![Productos destacados](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* El modo de control de calidad de destinatario es &quot;fijo&quot; y se guarda en una cookie. Si no sale del modo de control de calidad, seguirá viendo los resultados del control de calidad en todo el sitio. Para salir del modo de control de calidad, utilice el [bookmarklet](/help/c-activities/c-activity-qa/activity-qa-bookmark.md).
   >
   >
* Mientras esté en modo de control de calidad, explorar el sitio no afectará a los artículos [!UICONTROL vistos] recientemente o a los artículos [!UICONTROL comprados]recientemente en el perfil&quot;. Este comportamiento se produce por diseño para evitar la contaminación no intencionada de los datos de comportamiento de producción. Para realizar la previsualización de resultados a partir de elementos [!UICONTROL vistos] recientemente o criterios de Recommendations [!UICONTROL basados en el] usuario, primero navegue por el sitio fuera del modo de control de calidad y, a continuación, utilice la misma sesión para abrir un vínculo al modo de control de calidad.


## Uso de las recomendaciones de descarga en CSV para previsualización

En algunos casos, es posible que desee auditar los artículos específicos recomendados. Esto resulta especialmente útil cuando se utilizan algoritmos como [!UICONTROL Personas que vieron esto, vieron aquello], donde se recomienda un conjunto diferente de elementos en función del elemento que el usuario está viendo en ese momento, y es posible que tenga miles o millones de elementos diferentes en el catálogo.

Los resultados no están disponibles para la descarga hasta que se muestre un estado Listo [!UICONTROL para] resultados para al menos un algoritmo de la actividad.

Para descargar resultados para la previsualización, haga clic en el icono de menú en la esquina superior derecha de la página de información general de la Actividad y, a continuación, haga clic en **[!UICONTROL Descargar datos]**.

![Opción Descargar datos](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

Se descarga un archivo CSV. Ábralo para ver los elementos recomendados:

![Archivo CSV de elementos recomendados](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De izquierda a derecha es una lista de los artículos recomendados, en este caso los más visitados. Las recomendaciones están separadas por entornos, en este caso sólo el entorno de Producción tiene recomendaciones. Para este algoritmo, no hemos aplicado ninguna restricción basada en el valor clave, por lo que la fila etiquetada con un asterisco (*) contiene el conjunto completo de recomendaciones. Para otros tipos de algoritmos basados en un valor clave, como [!UICONTROL Personas que vieron esto, vieron aquello], los valores clave (es decir, los elementos &quot;Este&quot;) se enumeran en la columna situada más a la izquierda y los elementos recomendados (es decir, los elementos &quot;Que&quot;) se muestran de izquierda a derecha en las columnas de Recommendations_X.

>[!NOTE]
>
>Las descargas de resultados no están disponibles para actividades que contengan un algoritmo Recommendations [!UICONTROL basado en] usuarios. Las descargas de resultados no están disponibles para los criterios que utilizan la lógica de recomendación Artículos [!UICONTROL vistos] recientemente.

## Activación de la actividad de Recommendations

En la ficha Información general [!UICONTROL de] Actividad, haga clic en la flecha desplegable situada junto al estado y, a continuación, seleccione **[!UICONTROL Activar]**.

![Activar, opción](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

Tenga en cuenta que el estado se convierte en [!UICONTROL Activación]:

![Activar](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

Después de unos segundos o un par de minutos, el estado cambia a [!UICONTROL Activo]:

![Activo](/help/c-recommendations/t-create-recs-activity/assets/live.png)

Tenga en cuenta que también puede desactivar o archivar la actividad con la misma lista desplegable.

## Evitar interrupciones al cambiar la configuración de Recommendations

Si se cambia [!DNL Recommendations] la configuración de colecciones, criterios, promociones o diseños en una actividad activa, los resultados del algoritmo podrían no ser válidos y el estado de un algoritmo podría cambiar a [!UICONTROL Resultados no listos].

Para evitar la interrupción de una actividad en directo, recomendamos que adopte el siguiente enfoque al modificar una actividad en directo:

1. Duplicado la actividad y los criterios que desea modificar.
1. Realice cambios en la actividad y los criterios duplicados y espere a que el algoritmo genere resultados.
1. Previsualización la nueva actividad modificada y confirme que los resultados son los deseados.
1. Active la nueva actividad.
1. Desactive la actividad antigua.

Si necesita conservar los resultados de sistemas de informes históricos en la misma actividad, es posible un enfoque alternativo, que podría resultar en una interrupción temporal de la disponibilidad de las recomendaciones:

1. Duplicado la actividad y los criterios que desea modificar.
1. Realice cambios en la actividad y los criterios duplicados y espere a que el algoritmo genere resultados.
1. Previsualización la nueva actividad modificada y confirme que los resultados son los deseados.
1. Pause la actividad existente e intercambie la configuración/los criterios por los nuevos criterios.
1. Previsualización la actividad existente y confirme que los resultados son los deseados.
1. Vuelva a activar la actividad.
