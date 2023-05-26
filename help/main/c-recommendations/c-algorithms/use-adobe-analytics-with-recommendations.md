---
keywords: fuente de datos de comportamiento;analytics;recommendations;criterios;variables de producto
description: Aprenda a utilizar [!DNL Adobe Analytics] como fuente de datos de comportamiento para utilizar los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] in [!DNL Target Recommendations].
title: ¿Cómo utilizo [!DNL Adobe Analytics] con [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# Uso [!DNL Adobe Analytics] con [!DNL Recommendations]

Uso de [!DNL Adobe Analytics] ya que la fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas o compras de [!DNL Analytics] in [!DNL Adobe Target] [!DNL Recommendations] actividades. Esta función es especialmente útil en situaciones en las que la variable [!DNL Target Recommendations] la configuración es nueva y [!DNL Analytics] tiene muchos datos históricos para usar.

Uso de [!DNL Analytics] como fuente de datos de comportamiento puede actuar como una fuente enriquecida de información sobre el comportamiento del usuario. Esta información puede incluir datos de una fuente de terceros que solo se comparten con [!DNL Analytics].

While [creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) in [!DNL Recommendations]Además, hay dos botones de opción que permiten elegir qué fuente de datos se va a utilizar: [!UICONTROL mboxes] o [!UICONTROL Analytics]. Para crear un criterio, haga clic en [!UICONTROL Recommendations] > [!UICONTROL Criterios] > [!UICONTROL Crear criterios] > [!UICONTROL Crear criterios]. Para obtener más información, consulte [Creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

![Botones de fuente de datos de comportamiento](assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no se muestran en la cuenta, póngase en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para datos de Analytics en Target

Uso de [!DNL Analytics] ya que la fuente de datos de comportamiento de recommendations también le permite implementar casos de uso específicos sin el requisito de etiquetar páginas de entidad con todas las [!DNL Target] parámetros de entidad. Aunque para ello se requieren ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y props normales no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede utilizar [!DNL Analytics] como fuente de datos de comportamiento para:

* Mostrar recomendaciones en un sitio de venta minorista a los usuarios en una página de detalles del producto, en función de lo que hayan comprado otros usuarios de la misma categoría en el último mes, usando [!DNL Analytics] datos.
* Mostrar contenido en la pantalla de inicio de un sitio multimedia para el contenido más popular de una categoría en particular que sea tendencia, según [!DNL Analytics] datos.

## Implementación en [!DNL Analytics]

Las siguientes secciones le ayudan a implementar esta función en [!DNL Analytics] lado.

### Requisitos previos: configurar variables de producto en [!DNL Analytics]

Implementación de variables de producto en [!DNL Analytics] con los atributos necesarios para lo siguiente [!DNL Target Recommendations].

A [!DNL Target Recommendations] el formato de fuente de ejemplo actúa como guía sobre la que se deben definir todos los atributos en las variables de producto. Posteriormente, estos valores deben &quot;asignarse&quot; dentro de la variable [!DNL Target] Interfaz de usuario para los respectivos [!DNL Target] valores de entidad.

>[!NOTE]
>
>Si es un sitio de contenido, las partes de contenido respectivas deben tratarse como &quot;productos&quot; y los atributos asociados sobre ese contenido deben pasarse como atributos. Estos atributos pueden incluir el nombre del autor, la fecha de publicación, el título del contenido, el mes de lanzamiento, etc. La granularidad del nivel de categoría, o los tipos de categoría, debe decidirla la empresa en función de los requisitos de los casos de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) en el *Implementación de Adobe Analytics* guía. Algunas de las notas de esa documentación necesitan la discreción del equipo que las está implementando (por ejemplo: Categoría). Siempre se recomienda consultar con [!DNL Adobe] antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían a través de una fuente diaria. Los resultados de comportamiento pueden tardar hasta 24 horas en reflejarse dentro de los resultados de recomendaciones del sitio. Como con todos [!DNL Recommendations] la configuración de criterios, esta fuente de datos puede y debe probarse.

Para una toma de decisiones rápida sobre la fuente de datos que se va a utilizar, si hay muchos datos orgánicos generados cada día por los usuarios y no se requiere mucha dependencia de los datos históricos, utilice un [!DNL Target] mbox como fuente de datos de comportamiento puede ser una buena opción. En casos de menor disponibilidad de datos orgánicos generados recientemente, si desea contar con [!DNL Analytics] datos y, a continuación, el mediante [!DNL Analytics] ya que la fuente de datos de comportamiento es adecuada.

Ahora es el momento de asignar estas variables en [!DNL Target] para el suministro continuo de datos de comportamiento.

## Implementación en [!DNL Target]

1. Entrada [!DNL Target], haga clic en **[!UICONTROL Recommendations]**, luego haga clic en **[!UICONTROL Fuentes]** pestaña.

   ![Fuentes](/help/main/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Clic **[!UICONTROL Crear fuente]**.

1. Seleccionar **[!UICONTROL Clasificaciones de Analytics]**, luego especifique el grupo de informes.

   ![Opción Clasificaciones de Analytics](/help/main/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Clic **[!UICONTROL Siguiente]** para avanzar a la **[!UICONTROL Programación]** , seleccione un periodo de frecuencia para la fuente:

   * [!UICONTROL Diaria]
   * [!UICONTROL Semanal]
   * [!UICONTROL Cada 2 semanas]
   * [!UICONTROL Nunca]

   También puede seleccionar la hora del día a la que la fuente se procesará.

1. Clic **[!UICONTROL Siguiente]** para avanzar a la  **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a la variable correspondiente [!UICONTROL Recommendations] nombres de campo.

   ![Sección Asignación](/help/main/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Preguntas frecuentes

Tenga en cuenta las siguientes preguntas frecuentes al utilizar [!DNL Analytics] con [!DNL Target]:

### ¿Son las `entity.id` y `entity.categoryId` valores necesarios que se deben pasar dentro de [!DNL Target] ¿Llamada de mbox?

Sí, esos dos valores siguen siendo obligatorios. El resto de los atributos se pueden pasar mediante una [!DNL Analytics] fuente, tal como se describe en este documento.

### ¿Puedo utilizar las reglas de inclusión dinámica, como parámetros de entidad que coinciden con atributos de perfil utilizando? [!DNL Analytics] ¿enfoque de alimentación?

Sí, puedes. El método es similar cuando se utiliza [!DNL Target] independiente... En este caso, sin embargo, debe tener en cuenta el factor tiempo. Las variables de entidad que se supone que coinciden con las variables de perfil dependen de la capa de datos que pueda aparecer mucho más adelante en la página.
