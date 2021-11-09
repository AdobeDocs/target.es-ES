---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;segmentación de audiencia;informe de audiencia;audiencia de informe;segmento;parámetros de perfil personalizados;definición de audiencia;lista de audiencias
description: Aprenda a utilizar la variable [!UICONTROL Audiencias] en [!DNL Adobe Target].
title: ¿Cómo utilizo la lista de audiencias?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: d8b18c77d6df2fb9db01b64268e555f9a4b10adf
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 33%

---

# Crear audiencias

Audiencias en [!DNL Adobe Target] determine quién ve el contenido y las experiencias en una actividad segmentada.

Las audiencias se utilizan siempre que está disponible la determinación de objetivos. Al segmentar una actividad, tiene las siguientes opciones:

* Seleccione una audiencia reutilizable de [!UICONTROL Audiencias] list
* [Crear una audiencia específica de actividad](/help/c-target/creating-activity-only-audience.md) y segmentarlo
* [Combinación de varias audiencias](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear una audiencia ad-hoc

También puede utilizar datos de audiencia recopilados por [!DNL Adobe Analytics] para personalización y segmentación en tiempo real en [!DNL Target] y otros [!DNL Adobe Experience Cloud] aplicaciones. Consulte [Audiencias de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en el *Componentes de la interfaz central del Experience Cloud* guía.

Existen dos tipos de audiencias en [!DNL Target]:

* **Segmentación de audiencias:** Se utiliza para entregar distintos contenidos a distintos tipos de visitantes.
* **Informes de audiencia:** Se utiliza para determinar cómo los distintos tipos de visitantes responden al mismo contenido y, así, analizar los resultados de las pruebas.

   En [!DNL Target], las audiencias de informes solo se pueden configurar si se usa [!DNL Target] como fuente de informes. Si utiliza [ Adobe Analytics como fuente de informes](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), tiene que configurar la audiencia de informe en [!DNL Analytics].

## Utilice la variable [!UICONTROL Audiencias] list {#use-list}

Para acceder a la lista [!UICONTROL Audiencias], haga clic en **[!UICONTROL Audiencias]** en la barra de menús superior:

![Lista de audiencias](assets/audiences_list.png)

La variable [!UICONTROL Audiencias] contiene las audiencias que puede utilizar en sus actividades. Utilice la variable [!UICONTROL Audiencias] para crear, editar, duplicar, copiar o combinar audiencias. La lista también indica la fuente donde se creó la audiencia:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >La variable [!DNL Adobe Experience Platform] el origen está disponible para todos [!DNL Target] clientes que utilizan la variable [SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Audiencias disponibles en el [!DNL Adobe Experience Platform] se puede usar tal cual o [combinado con audiencias existentes](/help/c-target/combining-multiple-audiences.md).
   >
   >Los usuarios deben tener [!UICONTROL Aprobador] o estado superior en [!DNL Target] para configurar [!DNL Target] [!UICONTROL Destinos] tarjetas en AEP/RTCDP ([!DNL Real-Time Customer Data Platform]).

Audiencias predefinidas, como &quot;[!UICONTROL Visitantes nuevos]&quot; y &quot;[!UICONTROL Visitantes que regresan],&quot; no se puede cambiar el nombre.

Cuando se trabaja con audiencias creadas originalmente en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform], [!DNL Target] le alerta si hace referencia a una audiencia en [!DNL Target] actividades que posteriormente se eliminaron en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform].

* Si se eliminó una audiencia en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform], un icono de advertencia en las dos [!UICONTROL Audiencia] y se muestra el selector de audiencia. Información sobre herramientas en la variable [!DNL Target] La interfaz de usuario también indica que la audiencia se eliminó en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform].
* Si intenta combinar varias audiencias con una audiencia eliminada, o si intenta guardar una actividad que hace referencia a una audiencia eliminada, aparecerá un mensaje de advertencia.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al crear una audiencia, arrastre los atributos que desee utilizar para segmentar la actividad a la ventana del generador de audiencias. Si no se muestra el atributo deseado, un mbox no lo ha activado. Encontrará otros parámetros personalizados disponibles de mbox en la lista desplegable [!UICONTROL Parámetros personalizados].

Utilice la variable [!UICONTROL Filtros] para filtrar la variable [!UICONTROL Audiencias] lista por fuente: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud]y [!DNL Adobe Experience Platform].

![Filtros en la [!UICONTROL Audiencias] list](assets/filters.png)

Utilice la variable [!UICONTROL Buscar audiencias] para buscar [!UICONTROL Audiencias] lista. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audiencias] por nombre o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Ver definiciones de audiencia {#section_11B9C4A777E14D36BA1E925021945780}

Puede ver los detalles de definición de una audiencia en una tarjeta emergente en varios lugares de la sección [!DNL Target] IU sin abrir la audiencia. Esta funcionalidad se aplica a las audiencias creadas en [!DNL Target Standard/Premium] y audiencias importadas de [!DNL Target Classic] o creada mediante API.

Por ejemplo, para acceder a la siguiente definición de audiencia, haga clic en el botón [!UICONTROL Ver detalles] para la audiencia deseada:

![Actividades > Definición de audiencia](assets/audience_definition_list.png)

Para acceder a la siguiente definición de audiencia, haga clic en la [!UICONTROL Ver detalles] en el [!UICONTROL Información general] página:

![Actividades > Definición de audiencia](assets/view-details-activity-overview.png)

La tarjeta de definición de audiencia muestra el tipo, la fuente y los atributos de la audiencia. Haga clic en **[!UICONTROL Ver detalles completos]** para ver otras actividades que hacen referencia a esa audiencia, si corresponde. Si está viendo una tarjeta de definición de audiencia desde la [!UICONTROL Información general] página, haga clic en **[!UICONTROL Uso de la audiencia]**.

La información de uso de la audiencia puede ayudarle a evitar impactos accidentales en otras actividades mientras edita audiencias. La información incluye [!UICONTROL Actividades en directo], [!UICONTROL Actividades inactivas], [!UICONTROL Actividades archivadas]y [!UICONTROL Sincronización de actividades]. Esta función está disponible para todas las audiencias (audiencias de biblioteca y  [audiencias solo de actividad](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si una audiencia es [combinado con otra audiencia](/help/c-target/combining-multiple-audiences.md) y la audiencia combinada se utiliza para crear una actividad, la información de uso para ambas audiencias enumera esa actividad recién creada.

![](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Vídeo de formación: Uso de audiencias ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las audiencias.

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)
