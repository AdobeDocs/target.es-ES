---
keywords: fuente de datos de comportamiento;analytics;recomendaciones;criterios;variables de producto
description: Aprenda a utilizar Adobe Analytics como la fuente de datos de comportamiento para utilizar los datos de comportamiento basados en vistas o en compras de Analytics en  [!DNL Target] Recommendations.
title: ¿Cómo utilizo Adobe Analytics con [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# Uso de Adobe Analytics con Recommendations

El uso de [!DNL Adobe Analytics] como fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] en [!DNL Adobe Target] actividades de recomendaciones. Esta función es especialmente útil en situaciones en las que la configuración [!DNL Target Recommendations] es nueva y [!DNL Analytics] tiene muchos datos históricos que aprovechar.

El uso de [!DNL Analytics] como fuente de datos de comportamiento puede actuar como fuente enriquecida de información sobre el comportamiento del usuario. Esto puede incluir datos de un origen o fuente de terceros que solo se comparten con [!DNL Analytics].

Mientras [crea criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) en Recommendations, hay dos botones de opción que le permiten elegir qué fuente de datos se utilizará: [!UICONTROL mboxes] o [!UICONTROL Analytics].

![Botones de fuentes de datos de comportamiento](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no aparecen en la cuenta, póngase en contacto con el [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso de datos de Analytics en Target

El uso de [!DNL Analytics] como fuente de datos de comportamiento para recomendaciones también proporciona la capacidad de implementar casos de uso específicos sin el requisito de etiquetar páginas de entidad con todos los parámetros de entidad [!DNL Target]. Aunque esto requiere que haya ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y Props regulares no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede utilizar [!DNL Analytics] como fuente de datos de comportamiento para:

* Muestre recomendaciones en un sitio de venta minorista a usuarios en una página de PDP, en función de lo que otros usuarios compraron en la misma categoría en el último mes, con datos de Analytics.
* Muestre contenido en la pantalla principal de un sitio multimedia para el contenido más popular de una categoría en particular que actualmente es tendencia, en función de los datos [!DNL Analytics].

## Implementación en Analytics

Las siguientes secciones le ayudarán a implementar esta función en el lado [!DNL Analytics].

### Requisitos previos: configuración de variables de producto en Analytics

Debe implementar variables de producto en [!DNL Analytics] con los atributos necesarios que son necesarios para [!DNL Target Recommendations].

Un formato de fuente de muestra [!DNL Target Recommendations] actuará como guía sobre la cual deben definirse todos los atributos en las variables de producto. Posteriormente, esos valores deben &quot;asignarse&quot; dentro de la interfaz de usuario [!DNL Target] para los valores de entidad [!DNL Target] respectivos.

>[!NOTE]
>
>Si se trata de un sitio de contenido, los fragmentos de contenido respectivos deben tratarse como &quot;productos&quot; y atributos asociados a dicho contenido (por ejemplo: nombre de autor, fecha de publicación, título del contenido, mes de lanzamiento, etc.) debe pasarse como atributos. La granularidad del nivel de categoría, o los tipos de categoría, debe determinarla la empresa en función de los requisitos de caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en la *Guía de implementación de Analytics*. Algunas de las notas de esa documentación necesitan discreción del equipo que la está implementando (ejemplo: Categoría). Siempre se recomienda consultar con Adobe antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían a través de una fuente diaria. Los resultados de comportamiento tardarán hasta 24 horas en reflejarse en los resultados de recomendaciones del sitio. Al igual que con todas las configuraciones de criterios [!DNL Recommendations], esta fuente de datos puede y debe probarse.

Para una toma de decisiones rápida sobre la fuente de datos que se va a utilizar, si hay muchos datos orgánicos generados diariamente por los usuarios y no se requiere mucha dependencia en los datos históricos, entonces usar un mbox [!DNL Target] como fuente de datos de comportamiento puede ser un buen ajuste. En casos de menor disponibilidad de datos orgánicos generados recientemente, si desea utilizar datos [!DNL Analytics], el uso de [!DNL Analytics] como fuente de datos de comportamiento es un buen ajuste.

Ahora es el momento de asignar estas variables del lado [!DNL Target] para el suministro continuo de datos de comportamiento.

## Implementación en Target

1. En Target, haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en la pestaña **[!UICONTROL Fuentes]**.

   ![Fuentes](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Haga clic en **[!UICONTROL Crear fuente]**.

1. Seleccione **[!UICONTROL Clasificaciones de Analytics]** y luego especifique el grupo de informes.

   ![Opción Clasificaciones de Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Haga clic en **[!UICONTROL Mapping]** y, a continuación, asigne los encabezados de columna de campo a los nombres de campo [!UICONTROL Recommendations] correspondientes.

   ![Sección Asignación](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas frecuentes mientras utiliza [!DNL Analytics] con [!DNL Target]:

### ¿Es necesario pasar los valores `entity.id` y `entity.categoryId` dentro de la llamada de mbox [!DNL Target]?

Sí, estos dos valores siguen siendo necesarios. El resto de los atributos se pueden pasar a través de una fuente [!DNL Analytics], tal como se explica en este documento.

### ¿Puedo usar reglas de inclusión dinámica, como parámetros de entidad que coincidan con atributos de perfil mediante el enfoque de fuente [!DNL Analytics]?

Sí, puedes. El método es similar cuando se utiliza [!DNL Target] independiente. En este caso, sin embargo, debe tener en cuenta el factor de tiempo. Las variables de entidad que se supone que deben coincidir con las variables de perfil dependen de la capa de datos que podría aparecer mucho más adelante en la página.
