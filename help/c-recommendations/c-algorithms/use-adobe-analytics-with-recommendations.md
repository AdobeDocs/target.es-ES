---
keywords: fuente de datos de comportamiento;análisis;recomendaciones;criterios;variables de producto
description: Aprenda a utilizar Adobe Analytics como la fuente de datos de comportamiento para utilizar los datos de comportamiento basados en vistas o en compras de Analytics en Destinatario Recommendations.
title: ¿Cómo se usa Adobe Analytics con Destinatario Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: 87877502d25fe8da830f70126820d1ca825ebc9d
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---


# Usar Adobe Analytics con Recommendations

El uso de [!DNL Adobe Analytics] como la fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas y/o en compras de [!DNL Analytics] en las actividades de recomendaciones [!DNL Adobe Target]. Esta función es especialmente útil en situaciones en las que la configuración [!DNL Target Recommendations] es nueva y [!DNL Analytics] tiene muchos datos históricos que aprovechar.

El uso de [!DNL Analytics] como la fuente de datos de comportamiento puede actuar como una fuente enriquecida de información sobre el comportamiento del usuario. Esto puede incluir datos de una fuente o fuente de terceros que se comparte solamente con [!DNL Analytics].

Mientras [crea criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) en Recommendations, hay dos botones de opción que permiten elegir qué fuente de datos se va a utilizar: [!UICONTROL mboxes] o [!UICONTROL Analytics].

![Botones de fuentes de datos de comportamiento](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no se muestran en su cuenta, póngase en contacto con [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para datos de Analytics en Destinatario

El uso de [!DNL Analytics] como fuente de datos de comportamiento para recomendaciones también permite implementar casos de uso específicos sin necesidad de etiquetar páginas de entidades con todos los parámetros de entidad [!DNL Target]. Aunque esto requiere que haya ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y Props regulares no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede utilizar [!DNL Analytics] como fuente de datos de comportamiento para:

* Muestre las recomendaciones en un sitio de venta minorista a los usuarios en una página PDP, en función de lo que otros usuarios compraron en la misma categoría en el último mes, mediante datos de Analytics.
* Muestre contenido en la pantalla de inicio de un sitio de medios para el contenido más popular de una categoría en particular que actualmente es tendencia, basado en datos [!DNL Analytics].

## Implementación en Analytics

Las siguientes secciones le ayudarán a implementar esta función en el lado [!DNL Analytics].

### Requisitos previos: configurar variables de producto en Analytics

Debe implementar las variables de producto en [!DNL Analytics] con los atributos necesarios para [!DNL Target Recommendations].

Un formato de fuente de muestra [!DNL Target Recommendations] actuará como guía sobre la cual deben definirse todos los atributos en las variables de producto. Más adelante, esos valores se deben &quot;asignar&quot; dentro de la interfaz de usuario [!DNL Target] para los valores de entidad [!DNL Target] respectivos.

>[!NOTE]
>
>Si se trata de un sitio de contenido, las partes de contenido respectivas deben tratarse como &quot;productos&quot; y atributos asociados a dicho contenido (ejemplo: nombre del autor, fecha de publicación, título del contenido, mes de lanzamiento, etc.) debe pasarse como atributos. La granularidad del nivel de categoría, o tipos de categoría, debe ser decidida por la empresa en función de los requisitos del caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en la *Guía de implementación de Analytics*. Algunas de las notas de esa documentación necesitan discreción del equipo que la implementa (ejemplo: Categoría). Siempre se aconseja consultar con Adobe antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían mediante una fuente diaria. Los resultados conductuales tardarán hasta 24 horas en reflejarse en los resultados de las recomendaciones del sitio. Al igual que con todos los criterios [!DNL Recommendations], esta fuente de datos puede y debe probarse.

Para tomar decisiones rápidas sobre la fuente de datos que se va a utilizar, si hay muchos datos orgánicos que los usuarios generan todos los días y no se requiere mucha dependencia de los datos históricos, entonces usar un mbox [!DNL Target] como la fuente de datos de comportamiento puede ser un buen ajuste. En casos de menor disponibilidad de datos orgánicos generados recientemente, si desea obtener datos [!DNL Analytics] bancarios, entonces el uso de [!DNL Analytics] como la fuente de datos de comportamiento es un buen ajuste.

Ahora es el momento de asignar estas variables en [!DNL Target] lado para el suministro continuo de datos de comportamiento.

## Implementar en Destinatario

1. En Destinatario, haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en la ficha **[!UICONTROL Fuentes]**.

   ![Fuentes](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Haga clic en **[!UICONTROL Crear fuente]**.

1. Seleccione **[!UICONTROL Clasificaciones de Analytics]** y luego especifique el grupo de informes.

   ![Clasificaciones de Analytics, opción](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Haga clic en **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a los nombres de campo [!UICONTROL Recommendations] correspondientes.

   ![Sección Asignación](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas más frecuentes cuando utilice [!DNL Analytics] con [!DNL Target]:

### ¿Es necesario pasar los valores `entity.id` y `entity.categoryId` dentro de la llamada de mbox [!DNL Target]?

Sí, esos dos valores siguen siendo obligatorios. El resto de los atributos se pueden pasar a través de una fuente [!DNL Analytics], como se explica en este documento.

### ¿Puedo utilizar reglas de inclusión dinámica, como parámetros de entidad que coincidan con atributos de perfil mediante el método de fuente [!DNL Analytics]?

Sí, puedes. El método es similar cuando se utiliza [!DNL Target] independiente. En este caso, sin embargo, debe tener en cuenta el factor de tiempo. Las variables de entidad que se supone que deben coincidir con las variables de perfil dependen de la capa de datos que pueda aparecer mucho más tarde en la página.

