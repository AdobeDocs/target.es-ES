---
keywords: fuente de datos de comportamiento;analytics;recommendations;criterios;variables de producto
description: Aprenda a usar [!DNL Adobe Analytics] como origen de datos de comportamiento en [!DNL Target Recommendations].
title: Uso de Adobe Analytics con Recommendations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
TQID: 'https://experienceleague.adobe.com/2ryixOT-YoKjDlMbqs8g2DJElNVmlCUFhbdZzpfSnNs'
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 374d176c5c40826d958a8b87d220422466433690
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 1%
---
# Usar [!DNL Adobe Analytics] con [!DNL Recommendations] {#use-analytics-with-recommendations}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a usar [!DNL Adobe Analytics] como fuente de datos de comportamiento en [!DNL Adobe Target Recommendations] actividades.

>[!ENDSHADEBOX]

El uso de [!DNL Adobe Analytics] como fuente de datos de comportamiento permite que las actividades de [!DNL Adobe Target Recommendations] utilicen los datos de comportamiento basados en vistas y en compras de [!DNL Analytics]. Esto resulta útil cuando la configuración de [!DNL Target Recommendations] es nueva y [!DNL Analytics] tiene que usar muchos datos históricos. Los datos también pueden incluir información de una fuente de terceros que se comparte solamente con [!DNL Analytics].

El origen de datos está seleccionado con la opción **[!UICONTROL Source de datos de comportamiento]** al [crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) en [!DNL Recommendations]: **[!UICONTROL Adobe Target]** o **[!UICONTROL Analytics]**.

>[!NOTE]
>
>Si estas dos opciones no aparecen en la cuenta, comuníquese con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para datos de [!DNL Analytics] en [!DNL Target] {#use-cases}

El uso de [!DNL Analytics] como fuente de datos de comportamiento también permite implementar casos de uso específicos sin etiquetar páginas de entidad con todos los parámetros de entidad [!DNL Target]. Esto requiere ciertos requisitos previos, y la disponibilidad de &quot;Variables de producto&quot; es la más importante. Las eVars y props normales no son suficientes para que [!DNL Analytics] y [!DNL Target] intercambien estos datos automáticamente.

[!DNL Analytics] se puede usar como origen de datos de comportamiento para:

* Mostrar recomendaciones en un sitio de venta minorista a los usuarios en una página de detalles del producto, en función de lo que otros usuarios compraron en la misma categoría el mes pasado y con datos de [!DNL Analytics].
* Mostrar contenido en la pantalla de inicio de un sitio multimedia para el contenido más popular de una categoría en particular que sea tendencia actual, según los datos de [!DNL Analytics].

## Implementación en [!DNL Analytics]

### Requisitos previos: configurar variables de producto en [!DNL Analytics] {#prerequisites}

Implementar variables de producto en [!DNL Analytics] con los atributos necesarios para [!DNL Target Recommendations]. Un formato de fuente de ejemplo [!DNL Target Recommendations] guía qué atributos deben definirse en las variables de producto. Estos valores deben &quot;asignarse&quot; posteriormente en la interfaz de usuario de [!DNL Target] a los valores de entidad de [!DNL Target] correspondientes.

>[!NOTE]
>
>Si es un sitio de contenido, las partes de contenido respectivas deben tratarse como &quot;productos&quot; y los atributos asociados de ese contenido deben pasarse como atributos. Estos atributos pueden incluir el nombre del autor, la fecha de publicación, el título del contenido, el mes de lanzamiento, etc. La empresa debe decidir la granularidad del nivel de categoría o los tipos de categoría, según los requisitos del caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [productos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en la guía *Implementar Adobe Analytics*. Algunas de las notas de esa documentación, por ejemplo sobre Categoría, requieren el criterio del equipo que la implementa. Se recomienda consultar [!DNL Adobe] antes de esta actividad.

### Consideraciones {#considerations}

Los datos de [!DNL Analytics] se envían a través de una fuente diaria. Los resultados de comportamiento pueden tardar hasta 24 horas en reflejarse en los resultados de recomendaciones del sitio. Al igual que con la configuración de criterios de [!DNL Recommendations], se debe probar este origen de datos.

Para elegir una fuente de datos:

* Un mbox [!DNL Target] es un buen ajuste cuando los usuarios generan muchos datos orgánicos todos los días y se requiere poca dependencia de los datos históricos.
* [!DNL Analytics] encaja bien cuando se han generado menos datos orgánicos recientemente y se van a utilizar los datos [!DNL Analytics].

Los valores `entity.id` y `entity.categoryId` aún deben pasarse en la llamada de mbox [!DNL Target]. Los demás atributos se pueden pasar a través de una fuente [!DNL Analytics], como se describe en esta página.

Las reglas de inclusión dinámica, como hacer coincidir un parámetro de entidad con un atributo de perfil, se pueden usar con el método de fuente [!DNL Analytics]. El método es similar a usar [!DNL Target] de forma independiente, pero se debe tener en cuenta el tiempo: las variables de entidad que se supone que coinciden con las variables de perfil dependen de la capa de datos, que podría aparecer mucho más adelante en la página.

## Implementar en [!DNL Target] {#implement-target}

Las variables de producto se asignan en [!DNL Target] para proporcionar un suministro continuo de datos de comportamiento.

1. En [!DNL Target], haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en la ficha **[!UICONTROL Fuentes]**.

1. Haga clic en **[!UICONTROL Crear fuente]**.

   ![Página de fuentes con el botón Crear fuente resaltado](../assets/feeds_1.png)

1. Seleccione **[!UICONTROL Clasificaciones de Analytics]** y, a continuación, especifique el grupo de informes.

1. Haga clic en **[!UICONTROL Siguiente]** para avanzar a la configuración de **[!UICONTROL Programar]** y, a continuación, seleccione una frecuencia para la fuente: **[!UICONTROL Diario]**, **[!UICONTROL Semanal]**, **[!UICONTROL Cada 2 semanas]** o **[!UICONTROL Nunca]**. También se puede seleccionar la hora del día a la que se procesará la fuente.

   ![Paso Programar del cuadro de diálogo Crear fuente con las opciones Frecuencia diaria, Semanal, Cada 2 semanas y Nunca y el campo Hora del día](../assets/feeds_3.png)

1. Haga clic en **[!UICONTROL Siguiente]** para avanzar a la configuración de **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a los nombres de campo de **[!UICONTROL Recommendations]** adecuados.

1. Haga clic en **[!UICONTROL Guardar]**.

Para obtener más información sobre cómo crear una fuente, consulte [Crear una fuente](/help/main/c-recommendations/c-products/feeds.md#steps).
