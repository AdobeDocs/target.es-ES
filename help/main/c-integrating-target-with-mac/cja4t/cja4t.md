---
keywords: cja4t;Customer Journey Analytics;Customer Journey Analytics para Target;fuente de creación de informes de Customer Journey Analytics;Customer Journey Analytics como fuente de creación de informes para Target
description: Use  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) para crear actividades basadas en métricas de conversión y segmentos de audiencia de  [!DNL Customer Journey Analytics]  y use informes de  [!DNL Customer Journey Analytics]  para examinar los resultados.
title: ¿Qué es  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 2480578b3e26cfbb5881700c2a09b5b6e2dabba2
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 100%

---

# [!DNL Adobe Customer Journey Analytics] como fuente de creación de informes para [!DNL Adobe Target] (CJA4T)

La integración de [!DNL Customer Journey Analytics for Target] (CJA4T) entre [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html?lang=es){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo a su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] como fuente de creación de informes para [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de [!DNL Customer Journey Analytics] a informes de actividad de [!DNL Target] en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Aproveche las ventajas de las funciones de [!DNL Customer Journey Analytics], como el [Panel de experimentación](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html?lang=es){target=_blank}, para seguir analizando la personalización del sitio web.
* Tenga una única fuente de creación de informes para [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/cja-ajo.html?lang=es){target=_blank} y [!DNL Target]. Ambos productos de personalización se pueden conectar a [!DNL Customer Journey Analytics] para obtener una vista más integral de la personalización web.

## Consideraciones

Tenga en cuenta la siguiente información antes de usar la integración de CJA4T:

* Para usar [!DNL Customer Journey Analytics] como la fuente de creación de informes para [!DNL Target], tanto el usuario como la empresa deben tener acceso a [!DNL Customer Journey Analytics] y a [!DNL Target]. Si necesita acceder a alguna de las soluciones, póngase en contacto con el administrador de su organización o con el representante de la cuenta.
* Para crear actividades de [!DNL Target] con creación de informes de [!DNL Customer Journey Analytics], debe tener función de “[!UICONTROL Aprobador]” o “[!UICONTROL Editor]” en [!DNL Target].
   * Si tiene una cuenta [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*.
   * Si tiene una cuenta [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) en *Permisos de usuario de la empresa*.

* Debe formar parte de una función en [!DNL Adobe Experience Platform] para configurar una actividad de [!DNL Target] con [!DNL Customer Journey Analytics] como fuente de creación de informes. Para obtener más información, consulte [Agregar una función en [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions.html?lang=es){target=_blank} en *Configuración de permisos* en el *Tutorial de arquitecto de datos e ingeniero.*
* Según la configuración, la creación de informes se puede cambiar por actividad o por organización. Consulte [Solución en la nube para la creación de informes](/help/main/administrating-target/reporting.md#solution) en *Configuración de creación de informes en Target*.
* Debe usar una de las dos fuentes de creación de informes. No puede recopilar datos de una única actividad a varias fuentes de creación de informes.
* Cuando establezca [!DNL Customer Journey Analytics] como fuente de creación de informes, se le pedirá que especifique la zona protegida para su creación de informes. Durante la configuración, solo verá las zonas protegidas a las que tiene acceso.
* Las actividades de [!DNL Target] existentes seguirán utilizando la recopilación de datos de [!DNL Target] y no se verán afectadas por la habilitación de CJA4T.
* Para utilizar CJA4T, el método de implementación preferido es tener [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es){target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}. Si actualmente no tiene el [!DNL Adobe Experience Platform Web SDK] implementado, también puede crear una [[!DNL Adobe Analytics] conexión de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) para introducir los datos en [!DNL Adobe Experience Platform].
* Si tiene alguna pregunta acerca de los plazos, consulte [Consideraciones de latencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#latency){target=_blank} en *Preguntas frecuentes* en la *[!DNL Adobe Customer Analytics]Guía de*.

## Tipos de actividades compatibles {#supported-activities}

Se admiten los siguientes tipos de actividades al usar la biblioteca JavaScript de [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=es){target=_blank}:

| Tipos de actividad | ¿Es compatible con CJA4T? |
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

1. En la lista de **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]**, luego seleccione el tipo de actividad (según el [gráfico de actividades compatibles anterior](#supported-activities)) y comience a configurar la actividad.
1. Cuando llegue a la página **[!UICONTROL Objetivos y configuración]** del flujo de trabajo de creación de actividades en tres partes, seleccione **[!DNL Customer Journey Analytics]** como fuente de creación de informes.

   ![Customer Journey Analytics como opción de fuente de creación de informes](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La fuente de creación de informes no se puede cambiar después de iniciada la actividad de [!DNL Target].

1. Seleccionar una zona protegida.

   Solo puede ver las zonas protegidas a las que tiene acceso en esta lista desplegable. Si una o varias zonas protegidas a las que tiene acceso no aparecen en la lista, compruebe que tiene acceso a la zona protegida. Póngase en contacto con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si sigue teniendo problemas.

   ![Seleccione la opción de zona protegida](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Especifique la meta de la actividad.

   Seleccione una métrica de éxito para utilizarla como meta para cada actividad. Puede elegir una de las métricas de conversión de [!DNL Target] o usar una métrica de [!DNL Customer Journey Analytics].

   ![Use una opción de métrica de Customer Journey Analytics en Métrica de meta](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Haga clic en **[!UICONTROL Guardar y cerrar]**.

## Configuración de una conexión de [!DNL Customer Journey Analytics]

Después de crear una actividad de [!DNL Target], debe crear una conexión en [!DNL Customer Journey Analytics]. Si ya tiene una conexión configurada, puede utilizar la conexión existente y avanzar al paso 4 siguiente. La conexión permite que [!DNL Customer Journey Analytics] empiece a extraer datos del conjunto de datos para crear informes.

1. En [!DNL Customer Journey Analytics], en la página **[!UICONTROL Conexiones]**, haga clic en **[!UICONTROL Crear una nueva conexión]**.

   ![Cree un nuevo vínculo de conexión en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configure la [conexión y los datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=es){target=_blank} con la información correcta.
1. Añada el conjunto de datos del evento que utilizó al configurar la secuencia de datos.
1. Añada el conjunto de datos de búsqueda de **[!UICONTROL Eventos de clasificación de Adobe Target]** y haga clic en **[!UICONTROL Siguiente]**.

   ![Añada un cuadro de diálogo de conjuntos de datos en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configure el conjunto de datos del evento.

   Para obtener más información, consulte [Añadir y configurar conjuntos de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#add-dataset){target=_blank} en *Crear una conexión* en la *Guía de Adobe Customer Journey Analytics*.

1. Configure el conjunto de datos de búsqueda con el campo [!UICONTROL Clave] como “key” y el campo Clave correspondiente con la siguiente ruta:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Cuadro de diálogo de evento Clasificaciones de Adobe Target en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Haga clic en **[!UICONTROL Añadir conjuntos de datos]**, luego haga clic en **[!UICONTROL Guardar]** en la siguiente pantalla para finalizar la conexión.

## Configuración de vistas de datos

Configuración de una vista de datos en [!DNL Customer Journey Analytics]. Las vistas de datos garantizan que los datos de la conexión se puedan utilizar correctamente.

1. Configure la vista de datos y asegúrese de que apunta a la conexión creada anteriormente.

   Para obtener más información, consulte [Creación o edición de una vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=es){target=_blank} en la *Guía de Adobe Customer Journey Analytics*.

1. Para ver correctamente sus [!DNL Target] datos en [!DNL Customer Journey Analytics], debe añadir los siguientes campos del conjunto de datos de búsqueda como dimensiones:

   * Nombre de la experiencia
   * ID de experiencia
   * Nombre de la actividad
   * ID de actividad

   ![Opciones de nombres e ID en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Termine de configurar cualquier otro campo y haga clic en **[!UICONTROL Guardar y continuar]** cuando termine.
