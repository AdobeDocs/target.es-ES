---
keywords: cja4t;customer recorrido analytics;customer recorrido analytics for target;fuente de informes de customer recorrido analytics;customer recorrido analytics como fuente de informes para target
description: Use  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) para crear actividades basadas en métricas de conversión y segmentos de audiencia de  [!DNL Customer Journey Analytics]  y use informes de  [!DNL Customer Journey Analytics]  para examinar los resultados.
title: Qué es [!DNL Adobe Customer Journey Analytics] para [!DNL Target] (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 12%

---

# [!DNL Adobe Customer Journey Analytics] como fuente de informes para [!DNL Adobe Target] (CJA4T)

El [!DNL Customer Journey Analytics for Target] Integración de (CJA4T) entre [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] datos en [!DNL Target] son:

* Los especialistas en marketing pueden aplicar dinámicamente [!DNL Customer Journey Analytics] métricas de éxito a [!DNL Target] informes de actividad en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Una única fuente de datos minimiza la variación que se produce al recopilar datos en dos sistemas independientes.

## Consideraciones

Tenga en cuenta la siguiente información antes de utilizar la integración de CJA4T:

* Para usar [!DNL Customer Journey Analytics] como la fuente de informes para [!DNL Target], tanto el usuario como la empresa deben tener acceso a [!DNL Customer Journey Analytics] y a [!DNL Target]. Si necesita acceder a alguna de las soluciones, póngase en contacto con el administrador de su organización o con el representante de la cuenta.
* Para crear [!DNL Target] actividades con [!DNL Customer Journey Analytics] para informar, debe tener el &quot;[!UICONTROL Aprobador]&quot; o &#39;[!UICONTROL Editor]Función &quot; en [!DNL Target].
   * Si tiene un [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) cuenta de, consulte [Especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Usuarios*.
   * Si tiene un [Target Premium](/help/main/c-intro/intro.md#premium) cuenta de, consulte [Funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) in *Permisos de usuario de Enterprise*.

* Según la configuración, los informes se pueden cambiar por actividad o por organización. Consulte [Solución de Reporting Cloud](/help/main/administrating-target/reporting.md#solution) in *Configuración de informes en Target*.
* Debe usar una de las dos fuentes de informes. No se pueden recopilar datos de una sola actividad para varias fuentes de informes.
* Cuando se establece [!DNL Customer Journey Analytics] como fuente de informes, se le pedirá que especifique la zona protegida para los informes. Durante la configuración, solo verá las zonas protegidas a las que tiene acceso.
* Cualquier existente [!DNL Target] Las actividades de siguen utilizando [!DNL Target] recopilación de datos de y no se ven afectados por la activación de CJA4T.
* CJA4T solo está disponible si tiene [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. Compatibilidad con el [!DNL Analytics Data Connector] está planificado para el futuro.
* Si tiene alguna pregunta sobre la temporización, consulte [Consideraciones de latencia](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank} in *Preguntas más frecuentes* en el *Adobe Guía de Customer Analytics*.

## Tipos de actividades compatibles {#supported-activities}

Se admiten los siguientes tipos de actividades al utilizar [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} Biblioteca JavaScript:

| Tipos de actividad | ¿Compatible con CJA4T? |
|--- |--- |
| [Actividad A/B con división de tráfico manual](/help/main/c-activities/t-test-ab/test-ab.md) | Sí |
| [Actividad A/B con asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | No |
| [Actividad A/B con segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | No |
| [Segmentación de experiencias (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sí |
| [Prueba multivariable (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sí |
| [Actividad de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | No |
| [Actividad de Recommendations](/help/main/c-recommendations/recommendations.md) | Sí |

## Cree una actividad que utilice [!DNL Customer Journey Analytics] como fuente de informes

Creación de un [!DNL Target] actividad que utiliza [!DNL Customer Journey Analytics] como la fuente de informes es similar a la configuración de una [!DNL Target] actividad.

1. Desde el **[!UICONTROL Actividades]** , haga clic en **[!UICONTROL Crear actividad]**, luego seleccione el tipo de actividad (según el [gráfico de actividades compatibles anterior](#supported-activities)) y comience a configurar la actividad.
1. Cuando llegue a la **[!UICONTROL Objetivos y configuración]** del flujo de trabajo de creación de actividades en tres partes, seleccione **[!DNL Customer Journey Analytics]** como fuente de informes.

   ![Customer Journey Analytics como opción de fuente de informes](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La fuente de informes no se puede cambiar después de [!DNL Target] la actividad se activa.

1. Seleccionar una zona protegida.

   Solo puede ver los entornos limitados a los que tiene acceso en esta lista desplegable. Si una o más de las zonas protegidas a las que tiene acceso no aparecen en la lista, compruebe que tiene acceso a la zona protegida. Contacto [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si sigue viendo problemas.

   ![Seleccionar opción de zona protegida](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Especifique el objetivo de la actividad.

   Seleccione una métrica de éxito para utilizarla como objetivo para cada actividad. Puede elegir una de las [!DNL Target] métricas de conversión o use una variable [!DNL Customer Journey Analytics] métrica.

   ![Usar una opción de métrica de Customer Journey Analytics en Métrica de objetivo](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Haga clic en **[!UICONTROL Guardar y cerrar]**.

## Configuración de un [!DNL Customer Journey Analytics] conexión

Después de un [!DNL Target] se ha creado la actividad, debe crear una conexión en [!DNL Customer Journey Analytics]. Si ya tiene una conexión configurada, puede utilizar la conexión existente y pasar al paso 4 siguiente. La conexión permite [!DNL Customer Journey Analytics] para empezar a extraer datos del conjunto de datos para crear informes.

1. Entrada [!DNL Customer Journey Analytics], en el **[!UICONTROL Conexiones]** página, haga clic en **[!UICONTROL Crear una nueva conexión]**.

   ![Crear nuevo vínculo de conexión en el Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configure su [configuración de conexión y datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} con la información correcta.
1. Añada el conjunto de datos de evento que utilizó al configurar el conjunto de datos.
1. Añada el **[!UICONTROL Eventos de clasificación de Adobe Target]** conjunto de datos de búsqueda y haga clic en **[!UICONTROL Siguiente]**.

   ![Cuadro de diálogo Agregar conjuntos de datos en el Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configure el conjunto de datos de evento.

   Para obtener más información, consulte [Adición y configuración de conjuntos de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} in *Crear una conexión* en el *Guía de Adobe Customer Journey Analytics*.

1. Configure el conjunto de datos de búsqueda con [!UICONTROL Clave] como &quot;key&quot; y el campo Matching key con la siguiente ruta:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Cuadro de diálogo de evento Clasificaciones de Adobe Target en el Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Clic **[!UICONTROL Añadir conjuntos de datos]**, luego haga clic en **[!UICONTROL Guardar]** en la siguiente pantalla para finalizar la conexión.

## Configuración de vistas de datos

Configuración de una vista de datos en [!DNL Customer Journey Analytics]. Una vista de datos garantiza que los datos de su conexión se puedan utilizar correctamente.

1. Configure la vista de datos y asegúrese de que apunta a la conexión creada anteriormente.

   Para obtener más información, consulte [Creación o edición de una vista de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} en el *Guía de Adobe Customer Journey Analytics*.

1. Para ver correctamente su [!DNL Target] datos en [!DNL Customer Journey Analytics]Además, debe agregar los siguientes campos del conjunto de datos de búsqueda como dimensiones:

   * Nombre de la experiencia
   * ID de experiencia
   * Nombre de la actividad
   * ID de actividad

   ![Opciones de nombres e ID en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Termine de configurar cualquier otro campo y haga clic en **[!UICONTROL Guardar y continuar]** cuando termine.
