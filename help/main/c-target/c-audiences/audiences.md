---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;segmentación de audiencia;informe de audiencia;audiencia de informe;segmento;parámetros de perfil personalizados;definición de audiencia;lista de audiencias
description: Aprenda a utilizar las audiencias de en [!DNL Adobe Target].
title: ¿Cómo se utiliza la lista de audiencias?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 26%

---

# Crear audiencias

Audiencias en [!DNL Adobe Target] determine quién ve el contenido y las experiencias en una actividad segmentada.

Las audiencias se utilizan siempre que está disponible la determinación de objetivos. Al segmentar una actividad, tiene las siguientes opciones:

* Seleccione una audiencia reutilizable del [!UICONTROL Audiencias] lista
* [Crear una audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) y segmentarlo
* [Combinación de varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear una audiencia ad hoc

También puede utilizar los datos de audiencia recopilados por [!DNL Adobe Analytics] para personalización y segmentación en tiempo real en [!DNL Target] y otros [!DNL Adobe Experience Cloud] aplicaciones. Consulte [Audiencias de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en el *Componentes de la interfaz central de Experience Cloud* guía.

Existen dos tipos de audiencias en [!DNL Target]:

* **Audiencias objetivo:** Se utiliza para entregar contenido diferente a diferentes tipos de visitantes.
* **Audiencias de informes:** Se utiliza para determinar cómo responden los distintos tipos de visitantes al mismo contenido y así poder analizar los resultados de la prueba.

  En [!DNL Target], las audiencias de informes solo se pueden configurar si se usa [!DNL Target] como fuente de informes. Si utiliza [Adobe Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), debe configurar las audiencias de informes en [!DNL Analytics].

## Utilice el [!UICONTROL Audiencias] lista {#use-list}

Para acceder a la lista [!UICONTROL Audiencias], haga clic en **[!UICONTROL Audiencias]** en la barra de menús superior:

![[!UICONTROL Audiencias] lista](assets/audiences_list.png)

El [!UICONTROL Audiencias] Esta lista contiene las audiencias que puede utilizar en sus actividades de. Utilice el [!UICONTROL Audiencias] lista para crear, editar, duplicar, copiar o combinar audiencias. La lista también muestra la fuente en la que se creó la audiencia:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

  >[!NOTE]
  >
  >El [!DNL Adobe Experience Platform] fuente disponible para todos [!DNL Target] clientes que utilizan [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}. Audiencias disponibles en el [!DNL Adobe Experience Platform] se puede usar tal cual o [combinado con audiencias existentes](/help/main/c-target/combining-multiple-audiences.md).
  >
  >Los usuarios deben tener [!UICONTROL Aprobador] o estado superior en [!DNL Target] para configurar [!DNL Target] [!UICONTROL Destinos] tarjetas en AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
  >
  >Para obtener más información, consulte [Usar audiencias de Adobe Experience Platform](#aep).

Audiencias predefinidas, como &quot;[!UICONTROL Nuevos visitantes]&quot; y &quot;[!UICONTROL Visitantes que regresan],&quot; no se puede cambiar de nombre.

Al trabajar con audiencias que se crearon originalmente en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform], [!DNL Target] le avisa si hace referencia a una audiencia en [!DNL Target] actividades que se han eliminado posteriormente en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform].

* Si una audiencia se eliminó en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform], un icono de advertencia en ambos [!UICONTROL Audiencia] y se muestra el selector de audiencias. Información de objeto en [!DNL Target] La interfaz de usuario también indica que la audiencia se eliminó en [!DNL Experience Cloud] o [!DNL Adobe Experience Platform].
* Si intenta combinar varias audiencias con una audiencia eliminada, o si intenta guardar una actividad que hace referencia a una audiencia eliminada, aparecerá un mensaje de advertencia.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al crear una audiencia, arrastre los atributos que desee utilizar para segmentar la actividad en la ventana del generador de audiencias. Si el atributo deseado no se muestra, significa que un mbox no ha activado el atributo. Encontrará otros parámetros personalizados disponibles de mbox en la lista desplegable [!UICONTROL Parámetros personalizados].

Utilice el [!UICONTROL Filtros] para filtrar el [!UICONTROL Audiencias] lista por origen: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud], y [!DNL Adobe Experience Platform].

![Opción Filtros en la [!UICONTROL Audiencias] lista](assets/filters.png)

Utilice el [!UICONTROL Buscar audiencias] para buscar en su [!UICONTROL Audiencias] lista. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audiencias] por nombre o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Ver definiciones de audiencia {#section_11B9C4A777E14D36BA1E925021945780}

Puede ver los detalles de definición de la audiencia en una tarjeta emergente en varios lugares de la [!DNL Target] IU sin abrir la audiencia. Esta funcionalidad se aplica a las audiencias creadas en [!DNL Target Standard/Premium] y audiencias importadas de [!DNL Target Classic] o creado mediante API.

Por ejemplo, para acceder a la siguiente definición de audiencia de la tarjeta, haga clic en [!UICONTROL Ver detalles] para la audiencia deseada:

![Actividades > Definición de audiencia](assets/audience_definition_list.png)

Para acceder a la siguiente definición de audiencia, haga clic en [!UICONTROL Ver detalles] en el icono de una actividad [!UICONTROL Información general] página:

![Actividades > Definición de audiencia](assets/view-details-activity-overview.png)

La tarjeta de definición de audiencia muestra el tipo, la fuente y los atributos de la audiencia. Clic **[!UICONTROL Ver detalles completos]** para ver otras actividades que hagan referencia a esa audiencia, si corresponde. Si está viendo una tarjeta de definición de audiencia desde la actividad de [!UICONTROL Información general] página, haga clic en **[!UICONTROL Uso de audiencia]**.

La información de uso de la audiencia puede ayudarle a evitar un impacto accidental en otras actividades al editar audiencias. La información incluye [!UICONTROL Actividades activas], [!UICONTROL Actividades inactivas], [!UICONTROL Actividades archivadas], y [!UICONTROL Sincronizando actividades]. Esta función está disponible para todas las audiencias (audiencias de biblioteca y [audiencias solo de actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si una audiencia es [combinado con otra audiencia](/help/main/c-target/combining-multiple-audiences.md) y la audiencia combinada se utiliza para crear una actividad, la información de uso de ambas audiencias enumera la actividad recién creada.

![imagen audience_definition_list_usage](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Uso de audiencias de [!DNL Adobe Experience Platform] {#aep}

Uso de audiencias creadas en [!DNL Adobe Experience Platform] proporciona datos de clientes más completos que conducen a una personalización más impactante.

Para obtener más información, consulte [Usar audiencias de [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## Vídeo de formación: Uso de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las audiencias.

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)
