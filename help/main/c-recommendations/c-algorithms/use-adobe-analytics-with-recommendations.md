---
keywords: fuente de datos de comportamiento;analytics;recomendaciones;criterios;variables de producto
description: Aprenda a utilizar [!DNL Adobe Analytics] como fuente de datos de comportamiento desde la que se utilizan los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] en [!DNL Target Recommendations].
title: Cómo Uso [!DNL Adobe Analytics] con [!DNL Target Recommendations]?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# ![PREMIUM](/help/main/assets/premium.png) Uso [!DNL Adobe Analytics] con [!DNL Recommendations]

Uso [!DNL Adobe Analytics] ya que la fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] en [!DNL Adobe Target] [!DNL Recommendations] actividades. Esta función es especialmente útil en situaciones en las que la variable [!DNL Target Recommendations] la configuración es nueva y [!DNL Analytics] tiene muchos datos históricos que usar.

Uso [!DNL Analytics] ya que la fuente de datos de comportamiento puede actuar como una fuente enriquecida de información sobre el comportamiento del usuario. Esta información puede incluir datos de una fuente o fuente de terceros que solo se comparten con [!DNL Analytics].

While [creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) en [!DNL Recommendations], hay dos botones de opción que le permiten elegir qué fuente de datos se utilizará: [!UICONTROL mboxes] o [!UICONTROL Analytics]. Para crear un criterio, haga clic en [!UICONTROL Recommendations] > [!UICONTROL Criterios] > [!UICONTROL Crear criterios] > [!UICONTROL Crear criterios]. Para obtener más información, consulte [Creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

![Botones de fuentes de datos de comportamiento](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no se muestran en la cuenta, póngase en contacto con [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso de datos de Analytics en Target

Uso [!DNL Analytics] como la fuente de datos de comportamiento para recommendations también permite implementar casos de uso específicos sin el requisito de etiquetar páginas de entidad con todas las [!DNL Target] parámetros de entidad. Aunque esto requiere que haya ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y Props normales no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede usar [!DNL Analytics] como fuente de datos de comportamiento para:

* Mostrar recomendaciones en un sitio de venta minorista a los usuarios en una página de detalles del producto, según lo que otros usuarios hayan comprado en la misma categoría en el último mes, utilizando [!DNL Analytics] datos.
* Muestre contenido en la pantalla principal de un sitio multimedia para el contenido más popular de una categoría concreta que actualmente es tendencia, en función de [!DNL Analytics] datos.

## Implementación en [!DNL Analytics]

Las siguientes secciones le ayudan a implementar esta función en la [!DNL Analytics] lado.

### Requisitos previos: configure variables de producto en [!DNL Analytics]

Implemente variables de producto en [!DNL Analytics] con los atributos necesarios que son necesarios para [!DNL Target Recommendations].

A [!DNL Target Recommendations] el formato de fuente de muestra actúa como guía sobre la cual deben definirse todos los atributos en las variables de producto. Posteriormente, esos valores deben &quot;asignarse&quot; dentro de la variable [!DNL Target] IU para las [!DNL Target] valores de entidad.

>[!NOTE]
>
>Si se trata de un sitio de contenido, los fragmentos de contenido respectivos deben tratarse como &quot;productos&quot; y los atributos asociados a dicho contenido deben pasarse como atributos. Estos atributos pueden incluir el nombre del autor, la fecha de publicación, el título del contenido, el mes de lanzamiento, etc. La granularidad del nivel de categoría, o los tipos de categoría, debe determinarla la empresa en función de los requisitos de caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en el *Implementación de Adobe Analytics* guía. Algunas de las notas de esa documentación necesitan discreción del equipo que la está implementando (ejemplo: Categoría). Siempre se recomienda consultar con [!DNL Adobe] antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían a través de una fuente diaria. Los resultados de comportamiento pueden tardar hasta 24 horas en reflejarse en los resultados de recomendaciones del sitio. Como con todos [!DNL Recommendations] configuración de criterios, esta fuente de datos puede y debe probarse.

Para una toma de decisiones rápida sobre la fuente de datos que se va a utilizar, si hay muchos datos orgánicos generados diariamente por los usuarios y no se requiere mucha dependencia de los datos históricos, entonces use un [!DNL Target] mbox como fuente de datos de comportamiento puede ser un buen ajuste. En casos de menor disponibilidad de datos orgánicos generados recientemente, si desea acumular [!DNL Analytics] datos y, a continuación, el uso de [!DNL Analytics] ya que la fuente de datos de comportamiento es adecuada.

Ahora es el momento de asignar estas variables en [!DNL Target] para el suministro continuo de datos de comportamiento.

## Implementar en [!DNL Target]

1. En [!DNL Target], haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en el botón **[!UICONTROL Fuentes]** pestaña .

   ![Fuentes](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Haga clic en **[!UICONTROL Crear fuente]**.

1. Select **[!UICONTROL Clasificaciones de Analytics]** y, a continuación, especifique el grupo de informes.

   ![Opción Clasificaciones de Analytics](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Haga clic en **[!UICONTROL Siguiente]** para avanzar al **[!UICONTROL Programación]** , seleccione un periodo de frecuencia para la fuente:

   * [!UICONTROL Diaria]
   * [!UICONTROL Semanal]
   * [!UICONTROL Cada 2 semanas]
   * [!UICONTROL Nunca]

   También puede seleccionar la hora del día para que la fuente se procese.

1. Haga clic en **[!UICONTROL Siguiente]** para avanzar al  **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a la [!UICONTROL Recommendations] nombres de campo.

   ![Sección Asignación](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas frecuentes mientras utiliza [!DNL Analytics] con [!DNL Target]:

### ¿Son las variables `entity.id` y `entity.categoryId` los valores necesarios para pasarse dentro de la variable [!DNL Target] llamada de mbox?

Sí, estos dos valores siguen siendo necesarios. El resto de los atributos se pueden pasar mediante un [!DNL Analytics] fuente, tal como se explica en este documento.

### ¿Puedo usar reglas de inclusión dinámica, como parámetros de entidad que coincidan con atributos de perfil usando la variable [!DNL Analytics] enfoque de fuente

Sí, puedes. El método es similar al usar [!DNL Target] independiente. En este caso, sin embargo, debe tener en cuenta el factor de tiempo. Las variables de entidad que se supone que deben coincidir con las variables de perfil dependen de la capa de datos que podría aparecer mucho más adelante en la página.
