---
keywords: fuente de datos de comportamiento;analytics;recommendations;criterios;variables de producto
description: Aprenda a usar [!DNL Adobe Analytics] como fuente de datos de comportamiento en [!DNL Target Recommendations].
title: ¿Cómo se usa  [!DNL Adobe Analytics] con [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# Usar [!DNL Adobe Analytics] con [!DNL Recommendations]

El uso de [!DNL Adobe Analytics] como fuente de datos de comportamiento permite a los clientes usar los datos de comportamiento basados en vistas y en compras de [!DNL Analytics] en [!DNL Adobe Target Recommendations] actividades. Esta característica es especialmente útil en situaciones en las que la configuración de [!DNL Target Recommendations] es nueva y [!DNL Analytics] tiene muchos datos históricos que usar.

El uso de [!DNL Analytics] como origen de datos de comportamiento puede actuar como una fuente de información enriquecida sobre el comportamiento del usuario. Esta información puede incluir datos de una fuente de terceros que se comparte solamente con [!DNL Analytics].

Mientras [crea criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) en [!DNL Recommendations], hay dos botones de opción que le permiten elegir el origen de datos que se va a usar: [!UICONTROL mboxes] o [!UICONTROL Analytics]. Para crear un criterio, haga clic en [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Para obtener más información, consulte [Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

>[!NOTE]
>
>Si estos dos botones no aparecen en tu cuenta, ponte en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para datos de [!DNL Analytics] en [!DNL Target]

El uso de [!DNL Analytics] como fuente de datos de comportamiento para Recommendations también le permite implementar casos de uso específicos sin el requisito de etiquetar páginas de entidad con todos los parámetros de entidad [!DNL Target]. Aunque para ello se requieren ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y props normales no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede usar [!DNL Analytics] como fuente de datos de comportamiento para lo siguiente:

* Mostrar recomendaciones en un sitio de venta minorista a los usuarios en una página de detalles del producto, en función de lo que otros usuarios compraron en la misma categoría el mes pasado y con datos de [!DNL Analytics].
* Mostrar contenido en la pantalla de inicio de un sitio multimedia para el contenido más popular de una categoría en particular que sea tendencia actual, según los datos de [!DNL Analytics].

## Implementación en [!DNL Analytics]

Las secciones siguientes le ayudan a implementar esta característica en el lado [!DNL Analytics].

### Requisitos previos: configurar variables de producto en [!DNL Analytics]

Implemente variables de producto en [!DNL Analytics] con los atributos necesarios para [!DNL Target Recommendations].

Un formato de fuente de ejemplo [!DNL Target Recommendations] actúa como guía sobre el cual todos los atributos deben definirse en las variables de producto. Posteriormente, esos valores deben &quot;asignarse&quot; en la interfaz de usuario de [!DNL Target] para los valores de entidad de [!DNL Target] correspondientes.

>[!NOTE]
>
>Si es un sitio de contenido, las partes de contenido respectivas deben tratarse como &quot;productos&quot; y los atributos asociados sobre ese contenido deben pasarse como atributos. Estos atributos pueden incluir el nombre del autor, la fecha de publicación, el título del contenido, el mes de lanzamiento, etc. La granularidad del nivel de categoría, o los tipos de categoría, debe decidirla la empresa en función de los requisitos de los casos de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [productos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=es) en la guía *Implementar Adobe Analytics*. Algunas de las notas de esa documentación necesitan la discreción del equipo que las está implementando (por ejemplo: Categoría). Siempre se recomienda consultar con [!DNL Adobe] antes de realizar esta actividad.

### Consideraciones

Los datos de [!DNL Analytics] se envían a través de una fuente diaria. Los resultados de comportamiento pueden tardar hasta 24 horas en reflejarse dentro de los resultados de recomendaciones del sitio. Al igual que con toda la configuración de criterios de [!DNL Recommendations], este origen de datos puede y debe probarse.

Para tomar una decisión rápida sobre el origen de datos que se va a usar, si hay muchos datos orgánicos generados diariamente por los usuarios y no se requiere mucha dependencia de los datos históricos, entonces usar un mbox [!DNL Target] como origen de datos de comportamiento puede ser una buena opción. En casos de menos disponibilidad de datos orgánicos generados recientemente, si desea utilizar datos de [!DNL Analytics], el uso de [!DNL Analytics] como fuente de datos de comportamiento es una buena opción.

Ahora es el momento de asignar estas variables en el lado [!DNL Target] para el suministro continuo de datos de comportamiento.

## Implementar en [!DNL Target]

1. En [!DNL Target], haga clic en **[!UICONTROL Recommendations]** y, a continuación, haga clic en la ficha **[!UICONTROL Feeds]**.

1. Haga clic en **[!UICONTROL Create Feed]**.

1. Seleccione **[!UICONTROL Analytics Classifications]** y luego especifique el grupo de informes.

1. Haga clic en **[!UICONTROL Next]** para avanzar a la configuración de **[!UICONTROL Schedule]** y, a continuación, seleccione un período de frecuencia para la fuente:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   También puede seleccionar la hora del día a la que la fuente se procesará.

1. Haga clic en **[!UICONTROL Next]** para avanzar a la configuración de **[!UICONTROL Mapping]** y, a continuación, asigne los encabezados de columna de campo a los nombres de campo de [!UICONTROL Recommendations] correspondientes.

1. Haga clic en **[!UICONTROL Save]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas frecuentes al usar [!DNL Analytics] con [!DNL Target]:

### ¿Es necesario pasar los valores `entity.id` y `entity.categoryId` en la llamada de mbox [!DNL Target]?

Sí, esos dos valores siguen siendo obligatorios. El resto de los atributos se pueden pasar a través de una fuente [!DNL Analytics], como se describe en este documento.

### ¿Puedo utilizar reglas de inclusión dinámica, como parámetros de entidad que coinciden con atributos de perfil utilizando el enfoque de fuente [!DNL Analytics]?

Sí, puedes. El método es similar cuando se utiliza [!DNL Target] de forma independiente. En este caso, sin embargo, debe tener en cuenta el factor tiempo. Las variables de entidad que se supone que coinciden con las variables de perfil dependen de la capa de datos que pueda aparecer mucho más adelante en la página.
