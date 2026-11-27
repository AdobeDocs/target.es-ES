---
keywords: Recommendations;oferta;previsualización;inicio;estado;criterios;algoritmo
description: Obtenga información sobre cómo obtener una vista previa de la actividad de Recommendations de Adobe [!DNL Target] para asegurarse de que los resultados estén disponibles antes de iniciar la actividad.
title: ¿Cómo puedo obtener una vista previa e iniciar una actividad de Recommendations?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
TQID: 'https://experienceleague.adobe.com/21swhpZie0QN09m0LB7VwVO-9U6GWxQ0kbthPlnns18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 0%
---
# Vista previa e inicio de su actividad de Recommendations {#preview-launch-recs-activity}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información sobre cómo comprobar el estado del algoritmo, obtener una vista previa de las recomendaciones y activar una actividad de [!DNL Recommendations].

>[!ENDSHADEBOX]

La vista previa de las recomendaciones antes de iniciar una actividad confirma que los resultados están disponibles. Esto se aplica a las actividades de [!UICONTROL Recommendations], [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) que contienen [ofertas de Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md). [!DNL Target Recommendations] ofrece varias formas de obtener una vista previa de las recomendaciones.

## Comprobación del estado del algoritmo {#check-status}

Después de crear una actividad, [!DNL Recommendations] ejecuta un algoritmo para generar las recomendaciones. Este algoritmo puede tardar unas horas en ejecutarse.

El estado del algoritmo se enumera con los criterios del diagrama de actividad en la página **[!UICONTROL Información general]** de la actividad [!DNL Recommendations].

![Página de información general de la actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

El estado puede ser uno de los siguientes:

* **[!UICONTROL Resultados preparados]**: el algoritmo ha devuelto resultados.
* **[!UICONTROL Resultados no preparados]**: el algoritmo no ha terminado de ejecutarse.
* **[!UICONTROL Error de fuente]**: no se pudo recuperar el archivo de fuente de criterios personalizados.

![Cuadro de diálogo de resultados](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Calcular el tiempo de ejecución del algoritmo {#algorithm-run-time}

Una vez guardada una actividad que contiene un criterio, [!DNL Target] calcula las recomendaciones según la colección, los criterios, el diseño y las promociones seleccionados. El tiempo necesario depende de la lógica de recomendación, el intervalo de datos, el número de elementos del catálogo, la cantidad de datos de comportamiento que los clientes hayan generado y la fuente de datos de comportamiento. La fuente de datos de comportamiento tiene el mayor impacto en el tiempo de procesamiento.

### mboxes regionales clásicos

Cuando mboxes es la fuente de datos de comportamiento, el criterio se ejecuta inmediatamente después de crearse. Según la cantidad de datos de comportamiento y el tamaño del catálogo, el algoritmo puede tardar hasta 12 horas en ejecutarse.

Los cambios en la configuración de criterios generalmente hacen que el algoritmo se vuelva a ejecutar. Según el cambio, es posible que las recomendaciones calculadas anteriormente no estén disponibles hasta que se complete la nueva ejecución. Para cambios más grandes, solo el contenido predeterminado o de copia de seguridad estará disponible hasta que se complete la nueva ejecución.

[!DNL Target] vuelve a ejecutar automáticamente un algoritmo que no se ha modificado cada 12 a 48 horas, según el intervalo de datos seleccionado.

### [!DNL Adobe Analytics]

Si [!DNL Adobe Analytics] es el origen de datos de comportamiento, el tiempo hasta que los criterios estén disponibles depende de si el grupo de informes seleccionado y la ventana de vista al pasado ya se utilizaron para otros criterios. La primera vez que se usa un grupo de informes con una ventana retrospectiva determinada, [!DNL Target Recommendations] puede tardar de dos a siete días en descargar los datos de comportamiento de [!DNL Analytics].

Para ver la temporización de los criterios nuevos o editados y de las ejecuciones de algoritmos en curso, consulte la lista desplegable **Disponibilidad de criterios cuando Analytics es la fuente de datos** en [Data Source](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source).

>[!NOTE]
>
>**[!UICONTROL Elementos vistos recientemente]** no requieren la ejecución de algoritmos sin conexión, y los resultados están disponibles al instante. Los algoritmos **[!UICONTROL Más visitados]** y **[!UICONTROL Más vendidos]** basados en datos de mbox generalmente producen resultados muy rápidamente porque el cálculo es más sencillo. Estos algoritmos son buenas opciones para previsualizar un cambio de diseño o para confirmar que los datos de comportamiento se recopilan correctamente.

## Vista previa con un vínculo de control de calidad {#preview-qa-link}

Una vez que el algoritmo tenga los resultados listos, se puede obtener una vista previa de los mismos con la funcionalidad [QA link](/help/main/c-activities/c-activity-qa/activity-qa.md) de [!DNL Adobe Target]. Los vínculos de control de calidad están disponibles en la sección **[!UICONTROL Ubicación de la actividad]** de la página de información general de **[!UICONTROL Actividad]** y muestran las recomendaciones en la página.

![Productos destacados](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>De manera predeterminada, [!DNL Target] agrega automáticamente al usuario a la audiencia necesaria para el vínculo de control de calidad. Si esta configuración está desactivada y la actividad tiene reglas de segmentación, el perfil de usuario debe cumplir esas reglas de segmentación para ver la experiencia que contiene recomendaciones.

El modo de control de calidad tiene los siguientes comportamientos:

* El modo de control de calidad [!DNL Target] se guardó en una cookie y persiste entre páginas. Si no se sale del modo de control de calidad, los resultados de dicho control seguirán apareciendo en todo el sitio. Para salir del modo de control de calidad, use [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
* En el modo de control de calidad, la exploración del sitio no afecta los **[!UICONTROL elementos vistos recientemente]** ni los **[!UICONTROL elementos comprados recientemente]** del perfil. Este comportamiento es intencional, para evitar la contaminación no intencional de los datos de comportamiento de la producción. Para obtener una vista previa de los resultados de los criterios de **[!UICONTROL Elementos vistos recientemente]** o **[!UICONTROL Recomendaciones basadas en las preferencias del usuario]**, primero examine el sitio fuera del modo de control de calidad y, a continuación, utilice la misma sesión para abrir un vínculo del modo de control de calidad.

## Vista previa con la descarga de CSV {#preview-csv}

La descarga de los resultados permite auditar los elementos recomendados específicos. Esto es especialmente útil en algoritmos como **[!UICONTROL Personas que vieron esto, Vieron aquello]**, donde los elementos recomendados dependen del elemento que el visitante está viendo en ese momento y el catálogo puede contener miles o millones de elementos diferentes.

1. Espere a que se muestre el estado **[!UICONTROL Resultados preparados]** para al menos un algoritmo en la actividad. Los resultados no están disponibles para su descarga antes de esa fecha.

1. En la página de información general de **[!UICONTROL Actividad]**, haga clic en el icono de menú en la esquina superior derecha y, a continuación, haga clic en **[!UICONTROL Descargar datos]**.

   ![Opción de descarga de datos](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

1. Abra el archivo CSV descargado para ver los elementos recomendados.

   ![Archivo CSV de elementos recomendados](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

El archivo enumera los elementos recomendados de izquierda a derecha, en este ejemplo los más vistos. Las recomendaciones están separadas por el entorno. En este ejemplo, solo el entorno de producción tiene recomendaciones.

Una fila que comienza con un asterisco (*) enumera [elementos de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md). Los elementos de copia de seguridad se muestran cuando los elementos recomendados del algoritmo (criterios) no pueden llenar todas las ranuras de un diseño.

Para algoritmos basados en un valor clave, como **[!UICONTROL Personas que vieron esto, Vieron aquello]**, los valores de clave (los elementos &quot;Este&quot;) se encuentran en la columna situada más a la izquierda. Los elementos recomendados (los elementos &quot;Que&quot;) se muestran de izquierda a derecha en las columnas Recommendations_X.

Para las actividades con conjuntos de resultados muy grandes, la opción **[!UICONTROL Descargar datos]** puede fallar con el error `Error while fetching recommendation data file.`. Esto sucede cuando el CSV generado supera el tamaño de respuesta que la interfaz de usuario puede devolver en una sola descarga.

>[!NOTE]
>
>Las descargas de resultados no están disponibles para las actividades que contienen un algoritmo de **[!UICONTROL Recomendaciones basadas en las preferencias del usuario]** ni para los criterios que usan la lógica de recomendación de **[!UICONTROL Elementos vistos recientemente]**.

### Formato de descarga CSV para algoritmos basados en popularidad y en claves {#format}

El archivo de descarga CSV refleja de forma coherente los resultados generados después de la ejecución de los criterios del servidor.

* **Algoritmos basados en popularidad (no basados en claves)**: el archivo incluye:

  * Una fila de recomendaciones de copia de seguridad con el prefijo (*)
  * Una fila independiente que enumera las recomendaciones en función de la configuración del algoritmo

* **Algoritmos basados en claves**: El archivo incluye:

  * Una fila de copia de seguridad, como para los algoritmos basados en popularidad
  * Varias filas en formato clave-valor, donde la primera entrada es el ID de producto de la clave, seguido de ID de producto separados por comas que representan los candidatos de recomendación

## Activar la actividad {#activate-activity}

Al activar la actividad, esta se iniciará y su estado cambiará a **[!UICONTROL Activo]**.

En la ficha **[!UICONTROL Información general de la actividad]**, haga clic en la flecha desplegable **[!UICONTROL Estado]** y, a continuación, seleccione **[!UICONTROL Activar]**. Si la actividad se encuentra en el estado **[!UICONTROL Inactiva]**, la lista desplegable tiene la etiqueta **[!UICONTROL Inactiva]**. Después de unos segundos o un par de minutos, el estado cambia a **[!UICONTROL Activo]**.

La misma lista desplegable también se puede utilizar para desactivar o archivar la actividad.

## Evite interrupciones al cambiar la configuración {#avoid-disruptions}

Si cambia [!DNL Recommendations] colecciones, criterios, promociones o configuraciones de diseño en una actividad activa, podría invalidar los resultados del algoritmo y cambiar el estado de un algoritmo a **[!UICONTROL Resultados no preparados]**.

Para evitar interrumpir una actividad activa, el método recomendado es modificar una copia de la actividad y luego reemplazar la original:

1. Duplique la actividad original (actividad 1) y los criterios que desea modificar para crear una nueva actividad (actividad 2).
1. Realice los cambios en la actividad duplicada (actividad 2) y sus criterios y espere a que el algoritmo genere resultados.
1. Previsualice la actividad modificada (actividad 2) y confirme que los resultados son los deseados.
1. Active la nueva actividad (actividad 2).
1. Desactive la actividad original (actividad 1).

Cuando los resultados históricos de la creación de informes deban conservarse en la misma actividad, es posible otro método. Este método podría provocar una interrupción temporal en la disponibilidad de las recomendaciones:

1. Duplique la actividad original (actividad 1) y los criterios que desea modificar para crear una nueva actividad (actividad 2).
1. Realice los cambios en la actividad duplicada (actividad 2) y sus criterios y espere a que el algoritmo genere resultados.
1. Previsualice la actividad modificada (actividad 2) y confirme que los resultados son los deseados.
1. Ponga en pausa la actividad modificada (actividad 2) y cambie la configuración y los criterios por la actividad original (actividad 1).
1. Previsualice la actividad original (actividad 1) y confirme que los resultados son los deseados.
1. Vuelva a activar la actividad original (actividad 1).
