---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;segmentación de audiencia;informe de audiencia;audiencia de informe;segmento;parámetros de perfil personalizados;definición de audiencia;lista de audiencias
description: Aprenda a utilizar audiencias en [!DNL Adobe Target].
title: ¿Cómo utilizo la lista de audiencias?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 24%

---

# Crear audiencias

Audiencias en [!DNL Adobe Target] determine quién ve el contenido y las experiencias en una actividad segmentada.

Las audiencias se utilizan siempre que está disponible la determinación de objetivos. Al segmentar una actividad, tiene las siguientes opciones:

* Seleccione una audiencia reutilizable de [!UICONTROL Audiencias] list
* [Crear una audiencia específica de actividad](/help/main/c-target/creating-activity-only-audience.md) y segmentarlo
* [Combinación de varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear una audiencia ad-hoc

También puede utilizar datos de audiencia recopilados por [!DNL Adobe Analytics] para personalización y segmentación en tiempo real en [!DNL Target] y otros [!DNL Adobe Experience Cloud] aplicaciones. Consulte [Audiencias de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en el *Componentes de la interfaz central del Experience Cloud* guía.

Existen dos tipos de audiencias en [!DNL Target]:

* **Segmentación de audiencias:** Se utiliza para entregar distintos contenidos a distintos tipos de visitantes.
* **Informes de audiencia:** Se utiliza para determinar cómo los distintos tipos de visitantes responden al mismo contenido y, así, analizar los resultados de las pruebas.

   En [!DNL Target], las audiencias de informes solo se pueden configurar si se usa [!DNL Target] como fuente de informes. Si utiliza [ Adobe Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), tiene que configurar la audiencia de informe en [!DNL Analytics].

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
   >La variable [!DNL Adobe Experience Platform] el origen está disponible para todos [!DNL Target] clientes que utilizan la variable [SDK web de Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Audiencias disponibles en el [!DNL Adobe Experience Platform] se puede usar tal cual o [combinado con audiencias existentes](/help/main/c-target/combining-multiple-audiences.md).
   >
   >Los usuarios deben tener [!UICONTROL Aprobador] o estado superior en [!DNL Target] para configurar [!DNL Target] [!UICONTROL Destinos] tarjetas en AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
   >
   >Para obtener más información, consulte [Usar audiencias de Adobe Experience Platform](#aep).

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

La información de uso de la audiencia puede ayudarle a evitar impactos accidentales en otras actividades mientras edita audiencias. La información incluye [!UICONTROL Actividades en directo], [!UICONTROL Actividades inactivas], [!UICONTROL Actividades archivadas]y [!UICONTROL Sincronización de actividades]. Esta función está disponible para todas las audiencias (audiencias de biblioteca y  [audiencias solo de actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si una audiencia es [combinado con otra audiencia](/help/main/c-target/combining-multiple-audiences.md) y la audiencia combinada se utiliza para crear una actividad, la información de uso para ambas audiencias enumera esa actividad recién creada.

![](assets/audience_definition_list_usage.png)

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

## Usar audiencias de [!DNL Adobe Experience Platform] {#aep}

Usar audiencias creadas en [!DNL Adobe Experience Platform] proporciona datos de clientes más completos que conducen a una personalización más impactante. La variable [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=es){target=_blank} (RTCDP), integrado en [!DNL Adobe Experience Platform], ayuda a las empresas a reunir datos conocidos y anónimos de varias fuentes empresariales. Este proceso le permite crear perfiles de cliente que se pueden utilizar para ofrecer experiencias de cliente personalizadas en todos los canales y dispositivos en tiempo real.

Conectando [!DNL Target] a [!DNL Real-time Customer Data Platform], los clientes pueden enriquecer su personalización web desbloqueando nuevos segmentos que anteriormente podrían haber sido inaccesibles para [!DNL Target] para habilitar la personalización en tiempo real en la primera página de la visita web de un cliente. Uso de audiencias creadas en [!DNL Adobe Experience Platform] permite ampliar los puntos de datos disponibles para una mejor personalización.

Esta integración desbloquea los casos de uso clave con RTCDP:

* Personalización de la misma página/siguiente visita individual
* Personalización de usuarios nuevos/desconocidos

Las funciones clave incluyen:

* Integración de Direct Target con RTCDP/[!DNL Adobe Experience Platform] en Edge (eliminando dependencia de [!DNL Audience Core services] - AAM)
* [!UICONTROL Tarjeta de destino perimetral de Target] con control de seguridad
* Segmentación de Edge y perfil de Edge con perfil unificado

Para obtener más información, consulte los temas siguientes:

* [Notas de la versión de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} en la sección *Notas de la versión de Adobe Experience Platform*
* [Configurar destinos de personalización para la personalización de la misma página y de la página siguiente](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} en la sección *Información general sobre destinos* guía.
* [Conexión personalizada personalizada](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} en la sección *Información general sobre destinos* guía
* [Conexión Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} en la sección *Información general sobre destinos* guía
* [Configurar destinos de personalización para los casos de uso de personalización de la misma página y de la página siguiente](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} en la sección *Información general sobre destinos* guía

### Información adicional

Tenga en cuenta la siguiente información cuando use audiencias de [!DNL Adobe Experience Platform]:

#### Casos de uso de personalización

La tabla siguiente muestra qué tipo de caso de uso de personalización (sesión siguiente o página misma) está disponible al usar la variable [!DNL Adobe Experience Platform Web SDK] en lugar de usar at.js:

| Implementación | Soluciones/Caso de uso habilitado |
| --- | --- |
| at.js | **Soluciones**:<ul><li>[!DNL Adobe Audience Manager] AAM) y [!DNL Target]</li><li>[!DNL RTCDP] (Premium o Ultimate) y [!DNL Target]</li><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalización de próxima sesión</li></ul> |
| [!DNL Platform Web SDK] ni [!DNL AEP Server-Side API] | **Soluciones**:<ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalización de próxima sesión</li><li>Personalización de la misma página mediante Edge</li><li>Gobernanza aplicada al compartir segmentos</li></ul>**Soluciones**:<ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalización de próxima sesión</li><ul><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul><li>Personalización de la misma página mediante Edge</li><ul><li>[!DNL RTCDP] segmentos</li><li>Gobernanza aplicada al compartir segmentos</li></ul> |
| Mezcla de [!UICONTROL at.js] y [!DNL Platform Web SDK] | **Soluciones**:<ul><li>[!DNL RTCDP] (cualquier SKU) y [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li></ul><li>Personalización de la misma página</li><ul><li>Para todas las páginas con [!DNL Platform Web SDK]</li></ul></ul>**Soluciones**:<ul><li>[!DNL RTCDP] (cualquier SKU), [!DNL AAM]y [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalización de próxima sesión</li><ul><li>Para todas las páginas con [!UICONTROL at.js]</li><li>[!DNL AAM] segmentos</li><li>Segmentos de terceros a través de [!DNL AAM]</li></ul> |

#### Tiempo de evaluación de segmentos

La tabla siguiente muestra el tiempo de evaluación de segmentos para eventos que provienen de diferentes escenarios de implementación:

| Situación | Segmento de Edge (evaluación de milisegundos) | Segmento de transmisión (evaluación por minuto) | Evaluación de segmentos por lotes |
| --- | --- | --- | --- |
| Eventos/datos de [!DNL Adobe Experience Platform] SDK | Sí | Sí | N/A |
| Eventos desde [!UICONTROL at.js] | No | Sí | N/D |
| Eventos desde [!DNL Target Mobile] SDK | No | Sí | N/D |
| Eventos desde la carga por lotes | No | No | Sí |
| Eventos de datos sin conexión (flujo) | No | Sí | Sí |

### Vídeo: Personalización de próxima visita con CDP en tiempo real y [!DNL Adobe Target]{#RTCDP}

Obtenga información sobre cómo personalizar en la siguiente visita individual con [!DNL Real-time Customer Data Platform] y [!DNL Adobe Target]. La variable [!DNL Adobe Target] destino en [!DNL Real-time CDP] le permite usar [!DNL Experience Platform] segmentos en [!DNL Adobe Target] para la personalización de la misma página y de la página siguiente con compatibilidad con la administración y la privacidad.

Para obtener más información, consulte [Personalización de próxima visita con CDP en tiempo real y Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} en la sección *Tutorials de plataforma* guía.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog y video de Adobe Target:

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] y [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## Vídeo de formación: Uso de audiencias ![Distintivo del tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las audiencias.

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)
