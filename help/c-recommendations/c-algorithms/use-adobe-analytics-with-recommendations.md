---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: El uso de Adobe Analytics como fuente de datos de comportamiento permite a los clientes utilizar datos de comportamiento basados en vistas o en compras de Analytics en Adobe Recommendations.
title: Uso de Adobe Analytics con Destinatario Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: abe28722199c74c8b57dbfd0ca893dbf2e862cad
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 2%

---


# Usar Adobe Analytics con Recommendations

El uso [!DNL Adobe Analytics] como fuente de datos de comportamiento permite a los clientes utilizar los datos de comportamiento basados en vistas o en compras de [!DNL Analytics] las actividades de [!DNL Adobe Target] Recomendaciones. Esta función es especialmente útil en situaciones en las que la [!DNL Target Recommendations] configuración es nueva y [!DNL Analytics] tiene muchos datos históricos que aprovechar.

El uso [!DNL Analytics] como la fuente de datos de comportamiento puede actuar como una fuente rica de información sobre el comportamiento del usuario. Esto puede incluir datos de una fuente o fuente de terceros que solo se comparte con [!DNL Analytics].

Al [crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) en Recommendations, hay dos botones de opción que permiten elegir qué fuente de datos se va a utilizar: [!UICONTROL mboxes] o [!UICONTROL Analytics].

![Botones de fuentes de datos de comportamiento](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Si estos dos botones no se muestran en su cuenta, póngase en contacto con el Servicio de atención [al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso

El uso [!DNL Analytics] como fuente de datos de comportamiento para recomendaciones también permite implementar casos de uso específicos sin necesidad de etiquetar páginas de entidades con todos los parámetros de [!DNL Target] entidad. Aunque esto requiere que haya ciertos requisitos previos, la disponibilidad de &quot;Variables de producto&quot; es lo más importante para que esa funcionalidad funcione sin problemas. Las eVars y props normales no son suficientes para que este protocolo de enlace se produzca automáticamente entre [!DNL Analytics] y [!DNL Target].

Puede usar [!DNL Analytics] como fuente de datos de comportamiento para:

* Muestre las recomendaciones en un sitio de venta minorista a los usuarios en una página PDP, en función de lo que otros usuarios compraron en la misma categoría en el último mes, mediante datos de Analytics.
* Muestre contenido en la pantalla de inicio de un sitio de medios para el contenido más popular de una categoría en particular que actualmente es tendencia, en base a [!DNL Analytics] datos.

## Implementación en Analytics

Las siguientes secciones le ayudarán a implementar esta función en el [!DNL Analytics] lateral.

### Requisitos previos: variables de producto en Analytics

Debe implementar las variables de producto [!DNL Analytics] con los atributos necesarios para los que se requiere [!DNL Target Recommendations].

Un formato de fuente de [!DNL Target Recommendations] muestra actuará como guía en la que se deben definir todos los atributos en las variables de producto. Más adelante, esos valores deben &quot;asignarse&quot; dentro de la interfaz de usuario para los valores de [!DNL Target] [!DNL Target] entidad correspondientes.

>[!NOTE]
>
>Si se trata de un sitio de contenido, las partes de contenido respectivas deben tratarse como &quot;productos&quot; y atributos asociados a dicho contenido (ejemplo: nombre del autor, fecha de publicación, título del contenido, mes de lanzamiento, etc.) debe pasarse como atributos. La granularidad del nivel de categoría, o tipos de categoría, debe ser decidida por la empresa en función de los requisitos del caso de uso.

Para obtener más información sobre cómo configurar variables de producto, consulte [products](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) en la Guía *de implementación de* Analytics. Algunas de las notas de esa documentación necesitan discreción del equipo que la implementa (ejemplo: Categoría). Siempre se aconseja consultar con Adobe antes de realizar esta actividad.

### Consideraciones

[!DNL Analytics] los datos se envían mediante una fuente diaria. Los resultados conductuales tardarán hasta 24 horas en reflejarse en los resultados de las recomendaciones del sitio. Al igual que con todas las configuraciones de [!DNL Recommendations] criterios, esta fuente de datos puede y debe probarse.

Para tomar decisiones rápidas sobre qué fuente de datos se va a utilizar, si hay muchos datos orgánicos que los usuarios generan todos los días y no se requiere mucha dependencia de los datos históricos, entonces usar un [!DNL Target] mbox como fuente de datos de comportamiento puede ser un buen ajuste. En casos de menor disponibilidad de los datos orgánicos generados recientemente, si se desea basar en [!DNL Analytics] datos, entonces el uso [!DNL Analytics] como fuente de datos de comportamiento es un buen ajuste.

### Pasos para implementar

Si se cumplen todos los requisitos previos, realice las siguientes tareas:

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]** para adquirir el código [!DNL Target] de cliente.

   ![Código de cliente](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Adquiera su grupo [!DNL Analytics] de informes.

   Utilice el grupo [!DNL Analytics] de informes del sitio de producción. Es el grupo de informes que rastrea el sitio en el que se ha [!DNL Recommendations] implementado.

1. En [!DNL Analytics], haga clic en **[!UICONTROL Administración]** > Fuentes **[!UICONTROL de datos]**.

   ![Configuración > Fuentes de datos](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Click **[!UICONTROL Add]** to create a new feed.

   ![Añadir fuente](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Rellene la información de la fuente:

   * **Nombre**: Fuente de producto Recs
   * **Grupo** de informes: Su grupo de informes predeterminado
   * **Correo electrónico**: Especifique la dirección adecuada para un usuario administrador
   * **Intervalo** de fuente: Seleccione el intervalo deseado
   * **Retrasar procesamiento**: Sin demora.
   * **Fechas** de inicio y finalización: Fuente continua

   ![Sección de información de fuentes](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fill in the details in the **[!UICONTROL Destination]** section:

   >[!NOTE]
   > 
   >Consulte con el [!DNL Adobe Analytics] equipo antes de realizar este paso.

   * **Tipo**: FTP
   * **Host**: xxx.yyy.com
   * **Ruta**: Su código de cliente Destinatario
   * **Nombre de usuario**: xxxyyy
   * **Contraseña**: xxxxxxxxxx

   La captura de pantalla es solo para fines de referencia. La implementación tendrá credenciales diferentes. Consulte con el equipo [!DNL Adobe Analytics] o el Servicio de atención al cliente durante este paso.

   ![Sección Destino](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Complete las definiciones de la columna **** de datos:

   * **Formato** de compresión: Gzip
   * **Tipo** de paquete:  Archivo único
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

Con esto, la configuración de [!DNL Analytics] lado está completa. Ahora es el momento de asignar estas variables en [!DNL Target] un lado para el suministro continuo de datos de comportamiento.

## Implementación en Destinatario

1. En Destinatario, haga clic en **[!UICONTROL Recommendations]** y, a continuación, en la ficha **[!UICONTROL Fuentes]** .

   ![Fuentes](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Haga clic en **[!UICONTROL Crear fuente]**.

1. Seleccione Clasificaciones **[!UICONTROL de Analytics]** y, a continuación, especifique el grupo de informes.

   ![Clasificaciones de Analytics, opción](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Haga clic en **[!UICONTROL Asignación]** y, a continuación, asigne los encabezados de columna de campo a los nombres de campo correspondientes de [!UICONTROL Recommendations] .

   ![Sección Asignación](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Haga clic en **[!UICONTROL Guardar]**.