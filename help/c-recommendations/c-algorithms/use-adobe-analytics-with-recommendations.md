---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: El uso de Adobe Analytics como fuente de datos de comportamiento permite a los clientes utilizar datos de comportamiento basados en vistas o en compras de Analytics en Adobe Recommendations.
title: Uso de Adobe Analytics con Destinatario Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 3%

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

### Pasos para implementar

Si se cumplen todos los requisitos previos, el equipo [!DNL Adobe Target Recommendations] debe realizar las siguientes tareas:

>[!IMPORTANT]
>
>Los pasos que se describen a continuación son sólo ilustrativos. Actualmente, un miembro del equipo [!DNL Recommendations] debe realizar estos pasos. [Para obtener más información, póngase en contacto con el Servicio de atención al cliente de ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** para adquirir su [!DNL Target] código de cliente.

   ![Código de cliente](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Adquiera su grupo de informes [!DNL Analytics].

   Utilice su grupo de informes del [!DNL Analytics] sitio de producción. Este es el grupo de informes que rastrea el sitio en el que [!DNL Recommendations] se ha implementado.

1. En [!DNL Analytics], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Fuentes de datos]**.

   ![Configuración > Fuentes de datos](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Haga clic en **[!UICONTROL Añadir]** para crear una nueva fuente.

   ![Añadir fuente](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Rellene la información de la fuente:

   * **Nombre**: Fuente de producto Recs
   * **Grupo** de informes: Su grupo de informes predeterminado
   * **Correo electrónico**: Especifique la dirección adecuada para un usuario administrador
   * **Intervalo** de fuente: Seleccione el intervalo deseado
   * **Retrasar procesamiento**: Sin demora.
   * **Fechas** de inicio y finalización: Fuente continua

   ![Sección de información de fuentes](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Complete los detalles en la sección **[!UICONTROL Destino]**:

   >[!NOTE]
   > 
   >Consulte con el equipo [!DNL Adobe Analytics] antes de realizar este paso.

   * **Tipo**: FTP
   * **Host**: `xxx.yyy.com`
   * **Ruta**: Su código  [!DNL Target] de cliente
   * **Nombre de usuario**: Especifique el nombre de usuario
   * **Contraseña**: Especifique la contraseña

   La captura de pantalla es solo para fines de referencia. La implementación tendrá credenciales diferentes. Consulte con el equipo de [!DNL Adobe Analytics] o con el Servicio de atención al cliente durante este paso.

   ![Sección Destino](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Rellene las definiciones de **[!UICONTROL Columna de datos]**:

   * **Formato** de compresión: Gzip
   * **Tipo** de paquete: Archivo único
   * **Manifiesto:** Finalizar archivo

      ![Ajustes de formato de compresión, tipo de paquete y manifiesto](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **Columnas incluidas**:

      >[!IMPORTANT]
      >
      >Las columnas deben agregarse en el mismo orden documentado aquí. Seleccione las columnas en el orden siguiente y haga clic en **[!UICONTROL Añadir]** para cada columna.

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. Haga clic en **[!UICONTROL Guardar]**.

   ![Sección de definiciones de columnas de datos](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

Con esto, se ha completado la configuración en [!DNL Analytics] lado. Ahora es el momento de asignar estas variables en [!DNL Target] lado para el suministro continuo de datos de comportamiento.

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

