---
keywords: cja4t;Customer Journey Analytics;Customer Journey Analytics para Target;fuente de creación de informes de Customer Journey Analytics;Customer Journey Analytics como fuente de creación de informes para Target
description: Uso [!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics] para crear actividades basadas en [!DNL Customer Journey Analytics] métricas de conversión y segmentos de audiencia y usar [!DNL Customer Journey Analytics] para examinar los resultados.
title: Qué es [!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]?
feature: Integrations
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 07b7dd8e0e2dbf2b57d5b847f89886208eb66614
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 64%

---

# [!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]

La integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] como fuente de creación de informes para [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de [!DNL Customer Journey Analytics] a informes de actividad de [!DNL Target] en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en marketing pueden aprovechar [!DNL Customer Journey Analytics] funciones, como la [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para seguir analizando la personalización de su sitio web.
* Los especialistas en marketing pueden tener una única fuente de informes para [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} y [!DNL Target]. Ambos productos de personalización se pueden conectar a [!DNL Customer Journey Analytics] para obtener una vista más integral de la personalización web.

## Consideraciones

Tenga en cuenta la siguiente información antes de utilizar [!DNL Customer Journey Analytics] y [!DNL Target] integración:

>[!IMPORTANT]
>
>Esta integración no es lo mismo que [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Los tipos de actividades de implementación y compatibles son diferentes. Asegúrese de leer detenidamente este artículo antes de utilizar esta integración para su [!DNL Target] actividades.

* Para usar [!DNL Customer Journey Analytics] como la fuente de creación de informes para [!DNL Target], tanto el usuario como la empresa deben tener acceso a [!DNL Customer Journey Analytics] y a [!DNL Target]. Si necesita acceder a alguna de las soluciones, póngase en contacto con el administrador de su organización o con el representante de la cuenta.
* Para crear [!DNL Target] actividades con [!DNL Customer Journey Analytics] para informar, debe tener el &quot;[!UICONTROL Approver]&quot; o &#39;[!UICONTROL Editor]Función &quot; en [!DNL Target].
   * Si tiene una cuenta [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*.
   * Si tiene una cuenta [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) en *Permisos de usuario de la empresa*.

* Debe formar parte de una función en [!DNL Adobe Experience Platform] para configurar una actividad de [!DNL Target] con [!DNL Customer Journey Analytics] como fuente de creación de informes. Para obtener más información, consulte [Agregar una función en [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} en *Configuración de permisos* en el *Tutorial de arquitecto de datos e ingeniero.*
* Según la configuración, la creación de informes se puede cambiar por actividad o por organización. Consulte [Solución en la nube para la creación de informes](/help/main/administrating-target/reporting.md#solution) en *Configuración de creación de informes en Target*.
* Debe usar una de las dos fuentes de creación de informes. No puede recopilar datos de una única actividad a varias fuentes de creación de informes.
* Cuando establezca [!DNL Customer Journey Analytics] como fuente de creación de informes, se le pedirá que especifique la zona protegida para su creación de informes. Durante la configuración, solo verá las zonas protegidas a las que tiene acceso.
* Cualquier existente [!DNL Target] Las actividades de siguen utilizando [!DNL Target] la recopilación de datos de y no se ven afectados por la activación de esta integración.
* Para utilizar esta integración, el método de implementación preferido es tener [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Si actualmente no tiene el [!DNL Adobe Experience Platform Web SDK] implementado, también puede crear una [[!DNL Adobe Analytics] conexión de origen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para introducir los datos en [!DNL Adobe Experience Platform].

  >[!NOTE]
  >
  >Si utiliza un [!DNL Adobe Analytics] conexión de origen, tendrá informes en ambos [!DNL Adobe Analytics] y [!DNL Customer Journey Analytics]. Sin embargo, debido a los diferentes algoritmos entre ambas soluciones, es poco probable que los resultados coincidan.

* Si tiene alguna pregunta acerca de los plazos, consulte [Consideraciones de latencia](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} en *Preguntas frecuentes* en la *[!DNL Adobe Customer Analytics]Guía de*.

## Tipos de actividades compatibles {#supported-activities}

Se admiten los siguientes tipos de actividades al usar la biblioteca JavaScript de [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} or the [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank}:

| Tipos de actividades.  | Compatible? |
|--- |--- |
| [Actividad A/B con división de tráfico manual](/help/main/c-activities/t-test-ab/test-ab.md) | Sí |
| [Actividad A/B con asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Actividad A/B con segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | No |
| [Segmentación de experiencias (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sí |
| [Prueba multivariable (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sí |
| [Actividad de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | No |
| [Actividad de Recommendations](/help/main/c-recommendations/recommendations.md) | Sí |

## Creación de una actividad que use [!DNL Customer Journey Analytics] como fuente de creación de informes

La creación de una actividad de [!DNL Target] que use [!DNL Customer Journey Analytics] como la fuente de creación de informes es similar a la configuración de una actividad de [!DNL Target] habitual.

1. Desde el **[!UICONTROL Activities]** , haga clic en **[!UICONTROL Create Activity]**, luego seleccione el tipo de actividad (según el [gráfico de actividades compatibles anterior](#supported-activities)) y comience a configurar la actividad.
1. Cuando llegue a la **[!UICONTROL Goals & Settings]** del flujo de trabajo de creación de actividades en tres partes, seleccione **[!DNL Customer Journey Analytics]** como fuente de informes.

   ![Customer Journey Analytics como opción de fuente de creación de informes](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La fuente de creación de informes no se puede cambiar después de iniciada la actividad de [!DNL Target].

1. Seleccionar una zona protegida.

   En esta lista desplegable solo verá los entornos limitados a los que tiene acceso. Si una o varias zonas protegidas a las que tiene acceso no aparecen en la lista, compruebe que tiene acceso a la zona protegida. Póngase en contacto con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si sigue teniendo problemas.

   ![Seleccione la opción de zona protegida](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Especifique la meta de la actividad.

   Seleccione una métrica de éxito para utilizarla como meta para cada actividad. Puede elegir una de las métricas de conversión de [!DNL Target] o usar una métrica de [!DNL Customer Journey Analytics].

   ![Use una opción de métrica de Customer Journey Analytics en Métrica de meta](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Haga clic en **[!UICONTROL Save & Close]**.

## Configuración de una conexión de [!DNL Customer Journey Analytics]

Después de crear una actividad de [!DNL Target], debe crear una conexión en [!DNL Customer Journey Analytics]. Si ya tiene una conexión configurada, puede utilizar la conexión existente y avanzar al paso 4 siguiente. La conexión permite que [!DNL Customer Journey Analytics] empiece a extraer datos del conjunto de datos para crear informes.

1. Entrada [!DNL Customer Journey Analytics], en el **[!UICONTROL Connections]** página, haga clic en **[!UICONTROL Create a new connection]**.

   ![Crear nuevo vínculo de conexión en [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configure la [conexión y los datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank} con la información correcta.
1. Añada el conjunto de datos del evento que utilizó al configurar la secuencia de datos.
1. Añada el **[!UICONTROL Adobe Target Classification Events]** conjunto de datos de búsqueda y haga clic en **[!UICONTROL Next]**.

   ![Añada un cuadro de diálogo de conjuntos de datos en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configure el conjunto de datos del evento.

   Para obtener más información, consulte [Adición y configuración de conjuntos de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} in *Crear una conexión* en el *[!DNL Adobe Customer Journey Analytics]Guía*.

1. Configure el conjunto de datos de búsqueda con [!UICONTROL Key] como &quot;key&quot; y la variable [!UICONTROL Matching] Campo clave con la siguiente ruta:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Cuadro de diálogo de evento Clasificaciones de Adobe Target en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Clic **[!UICONTROL Add datasets]**, luego haga clic en **[!UICONTROL Save]** en la siguiente pantalla para finalizar la conexión.

## Configuración de vistas de datos

Configuración de una vista de datos en [!DNL Customer Journey Analytics]. Las vistas de datos garantizan que los datos de la conexión se puedan utilizar correctamente.

1. Configure la vista de datos y asegúrese de que apunta a la conexión creada anteriormente.

   Para obtener más información, consulte [Creación o edición de una vista de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} en el *[!DNL Adobe Customer Journey Analytics]Guía*.

1. Para ver correctamente sus [!DNL Target] datos en [!DNL Customer Journey Analytics], debe añadir los siguientes campos del conjunto de datos de búsqueda como dimensiones:

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Opciones de nombres e ID en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Para usar [!DNL Target] dimensiones en la [!UICONTROL Experimentation] , configure las siguientes etiquetas de contexto:

   * Para [!UICONTROL Activity Name], use &quot;Experimento de experimentación&quot;.
   * [!UICONTROL Experience Name], utilice &quot;Variante de experimento&quot;.

   ![Etiquetas de contexto del panel Experimentación](/help/main/c-integrating-target-with-mac/cja4t/assets/context-labels.png){width="600" zoomable="yes"}

1. Termine de configurar cualquier otro campo y haga clic en **[!UICONTROL Save and continue]** cuando termine.
