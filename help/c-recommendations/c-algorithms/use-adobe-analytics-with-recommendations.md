---
keywords: fuente de datos de comportamiento;analytics;recomendaciones;criterios;variables de producto
description: Aprenda a utilizar Adobe Analytics como la fuente de datos de comportamiento para utilizar los datos de comportamiento basados en vistas o en compras de Analytics en [!DNL Target] Recommendations.
title: ¿Cómo utilizo Adobe Analytics con [!DNL Target] ¿Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2a4cae206bf634bf3fbec65c5c4b289aadefede1
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 1%

---

# Uso de Adobe Analytics con Recommendations

Uso [!DNL Adobe Analytics] ya que la fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] en [!DNL Adobe Target] actividades de recommendations . Esta función es especialmente útil en situaciones en las que la variable [!DNL Target Recommendations] la configuración es nueva y [!DNL Analytics] tiene muchos datos históricos que aprovechar.

Uso [!DNL Analytics] ya que la fuente de datos de comportamiento puede actuar como una fuente enriquecida de información sobre el comportamiento del usuario. Esto puede incluir datos de una fuente o fuente de terceros que solo se comparten con [!DNL Analytics].

While [creación de criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) en Recommendations, hay dos botones de opción que le permiten elegir qué fuente de datos se utilizará: [!UICONTROL mboxes] o [!UICONTROL Analytics].

![Botones de fuentes de datos de comportamiento](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no se muestran en la cuenta, póngase en contacto con [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso de datos de Analytics en Target

Uso [!DNL Analytics] como fuente de datos de comportamiento para recomendaciones también proporciona la capacidad de implementar casos de uso específicos sin el requisito de etiquetar páginas de entidad con todas las [!DNL Target] parámetros de entidad. Aunque esto requiere que haya ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y Props normales no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede usar [!DNL Analytics] como fuente de datos de comportamiento para:

* Muestre recomendaciones en un sitio de venta minorista a usuarios en una página de PDP, en función de lo que otros usuarios compraron en la misma categoría en el último mes, con datos de Analytics.
* Muestre contenido en la pantalla principal de un sitio multimedia para el contenido más popular de una categoría concreta que actualmente es tendencia, en función de [!DNL Analytics] datos.

## Implementación en Analytics

Las secciones siguientes le ayudarán a implementar esta función en la [!DNL Analytics] lado.

### Requisitos previos: configuración de variables de producto en Analytics

Debe implementar variables de producto en [!DNL Analytics] con los atributos necesarios que son necesarios para [!DNL Target Recommendations].

A [!DNL Target Recommendations] el formato de fuente de ejemplo actuará como guía sobre la cual deben definirse todos los atributos en las variables de producto. Posteriormente, esos valores deben &quot;asignarse&quot; dentro de la variable [!DNL Target] IU para las [!DNL Target] valores de entidad.

>[!NOTE]
>
>Si se trata de un sitio de contenido, los fragmentos de contenido respectivos deben tratarse como &quot;productos&quot; y atributos asociados a dicho contenido (por ejemplo: nombre de autor, fecha de publicación, título del contenido, mes de lanzamiento, etc.) debe pasarse como atributos. La granularidad del nivel de categoría, o los tipos de categoría, debe determinarla la empresa en función de los requisitos de caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en el *Guía de implementación de Analytics*. Algunas de las notas de esa documentación necesitan discreción del equipo que la está implementando (ejemplo: Categoría). Siempre se recomienda consultar con Adobe antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían a través de una fuente diaria. Los resultados de comportamiento tardarán hasta 24 horas en reflejarse en los resultados de recomendaciones del sitio. Como con todos [!DNL Recommendations] configuración de criterios, esta fuente de datos puede y debe probarse.

Para una toma de decisiones rápida sobre qué fuente de datos se utilizará, si hay muchos datos orgánicos generados diariamente por los usuarios, y no se requiere mucha dependencia de los datos históricos, entonces se usa un [!DNL Target] mbox como fuente de datos de comportamiento puede ser un buen ajuste. En casos de menor disponibilidad de datos orgánicos generados recientemente, si desea acumular [!DNL Analytics] datos y, a continuación, el uso de [!DNL Analytics] ya que la fuente de datos de comportamiento es adecuada.

Ahora es el momento de asignar estas variables en [!DNL Target] para el suministro continuo de datos de comportamiento.

## Implementación en Target

1. En Target, haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en el botón **[!UICONTROL Fuentes]** pestaña .

   ![Fuentes](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Haga clic en **[!UICONTROL Crear fuente]**.

1. Select **[!UICONTROL Clasificaciones de Analytics]** y, a continuación, especifique el grupo de informes.

   ![Opción Clasificaciones de Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Haga clic en **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a los correspondientes [!UICONTROL Recommendations] nombres de campo.

   ![Sección Asignación](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas frecuentes mientras utiliza [!DNL Analytics] con [!DNL Target]:

### ¿Son las variables `entity.id` y `entity.categoryId` los valores necesarios para pasarse dentro de la variable [!DNL Target] llamada de mbox?

Sí, estos dos valores siguen siendo necesarios. El resto de los atributos se pueden pasar mediante un [!DNL Analytics] fuente, tal como se explica en este documento.

### ¿Puedo usar reglas de inclusión dinámica, como parámetros de entidad que coincidan con atributos de perfil usando la variable [!DNL Analytics] enfoque de fuente

Sí, puedes. El método es similar al usar [!DNL Target] independiente. En este caso, sin embargo, debe tener en cuenta el factor de tiempo. Las variables de entidad que se supone que deben coincidir con las variables de perfil dependen de la capa de datos que podría aparecer mucho más adelante en la página.
