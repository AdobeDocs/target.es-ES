---
keywords: customer recorrido analytics;customer recorrido analytics for target;fuente de informes de customer recorrido analytics;customer recorrido analytics como fuente de informes para target;informes de target en cja; informes de target en Customer Journey Analytics
description: Use [!DNL Target] informes en [!DNL Adobe Customer Journey Analytics] para crear actividades basadas en [!DNL Customer Journey Analytics] métricas de conversión y segmentos de audiencia y use [!DNL Customer Journey Analytics] informes para examinar los resultados.
title: ¿Qué está informando [!DNL Target] en [!DNL Adobe Customer Journey Analytics]?
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
TQID: https://experienceleague.adobe.com/bEwtqdwOsXyDbBUdxZKMl3I3LLTgxdxURvXjrfco-WI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 5b60a40e83437c535ccb3a7e7800493619fc62c8
workflow-type: tm+mt
source-wordcount: 1754
ht-degree: 20%

---

# Informes de [!DNL Target] en [!DNL Adobe Customer Journey Analytics]

La integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] como fuente de creación de informes para [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de [!DNL Customer Journey Analytics] a informes de actividad de [!DNL Target] en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en mercadotecnia pueden aprovechar las características de [!DNL Customer Journey Analytics], como el [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analizar más a fondo la personalización de su sitio web.
* Los especialistas en marketing pueden tener una única fuente de informes para [!DNL Adobe Journey Optimizer] y [!DNL Target]. Ambos productos de personalización se pueden conectar a [!DNL Customer Journey Analytics] para obtener una vista más integral de la personalización web.

## Consideraciones

Tenga en cuenta la siguiente información antes de utilizar la integración de [!DNL Customer Journey Analytics] y [!DNL Target]:

>[!IMPORTANT]
>
>Esta integración no es la misma que [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Los tipos de actividades de implementación y compatibles son diferentes. Asegúrese de leer a fondo este artículo antes de utilizar esta integración para sus actividades [!DNL Target].

* Para usar [!DNL Customer Journey Analytics] como la fuente de creación de informes para [!DNL Target], tanto el usuario como la empresa deben tener acceso a [!DNL Customer Journey Analytics] y a [!DNL Target]. Si necesita acceder a alguna de las soluciones, póngase en contacto con el administrador de su organización o con el representante de la cuenta.
* Para crear actividades [!DNL Target] con informes de [!DNL Customer Journey Analytics], debe tener el rol &quot;[!UICONTROL Aprobador]&quot; o &#39;[!UICONTROL Editor]&quot; en [!DNL Target].
  * Si tiene una cuenta [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funciones y permisos](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*.
  * Si tiene una cuenta [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Funciones y permisos](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) en *Permisos de usuario de la empresa*.

* Forme parte de un rol en [!DNL Adobe Experience Platform] para configurar una actividad [!DNL Target] con [!DNL Customer Journey Analytics] como origen de informes. Para obtener más información, consulte [Agregar una función en [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} en *Configurar permisos* en el *Tutorial de arquitectos de datos e ingenieros.*
* Según la configuración, la creación de informes se puede cambiar por actividad o por organización. Consulte [Solución en la nube para la creación de informes](/help/main/administrating-target/reporting.md#solution) en *Configuración de creación de informes en Target*.
* Debe usar una de las dos fuentes de creación de informes. No puede recopilar datos de una única actividad a varias fuentes de creación de informes.
* Cuando establece [!DNL Customer Journey Analytics] como origen de informes, se le pedirá que especifique la zona protegida y la vista de datos para los informes. Durante la configuración, solo verá los entornos limitados y las vistas de datos a los que tiene acceso.
* Las actividades existentes de [!DNL Target] seguirán utilizando la recopilación de datos de [!DNL Target] y no se verán afectadas por la habilitación de esta integración.
* Para usar esta integración, el método de implementación preferido es tener [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} y [!DNL Target] implementados a través de [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}.

  Si actualmente no tiene implementado [!DNL Adobe Experience Platform Web SDK], también puede crear una [[!DNL Adobe Analytics] conexión de origen](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para llevar los datos a [!DNL Adobe Experience Platform]. Si planea usar este método, debe seleccionar un grupo de informes [!DNL Analytics] junto con la zona protegida [!DNL Adobe Experience Platform] que usa con [!DNL Customer Journey Analytics].

  ![Opción de espacio aislado en el cuadro de diálogo Configuración de informes](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >Si usa una conexión de origen de [!DNL Adobe Analytics], tiene informes en [!DNL Adobe Analytics] y en [!DNL Customer Journey Analytics]. Sin embargo, debido a los diferentes algoritmos entre ambas soluciones, es poco probable que los resultados coincidan.

* Si tiene alguna pregunta sobre la temporización, consulte [Consideraciones sobre la latencia](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} en *Preguntas más frecuentes* en la guía *[!DNL Adobe Customer Analytics]*.

## Tipos de actividades compatibles {#supported-activities}

Se admiten los siguientes tipos de actividades al usar [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} o la biblioteca de JavaScript [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank}:

| Tipos de actividades. | Compatible? |
|--- |--- |
| [Actividad A/B con división de tráfico manual](/help/main/c-activities/t-test-ab/test-ab.md) | Sí |
| [Actividad A/B con asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sí |
| [Actividad A/B con segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | No |
| [Segmentación de experiencias (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sí |
| [Prueba multivariable (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sí |
| [Actividad de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | No |
| [Actividad de Recommendations](/help/main/c-recommendations/recommendations.md) | Sí |

Las actividades de [!UICONTROL Segmentación automática] y [!UICONTROL Automated Personalization] todavía no admiten [!DNL Customer Journey Analytics] como fuente de informes.

## Creación de una actividad que use [!DNL Customer Journey Analytics] como fuente de creación de informes {#create-an-activity-that-uses-customer-journey-analytics-as-the-reporting-source}

La creación de una actividad de [!DNL Target] que use [!DNL Customer Journey Analytics] como la fuente de creación de informes es similar a la configuración de una actividad de [!DNL Target] habitual. Este flujo de trabajo se aplica a todos los tipos de actividades compatibles de la tabla anterior, incluidas las pruebas A/B de [!UICONTROL Asignación automática].

>[!TIP]
>
>También puede especificar que [!DNL Target] use la creación de informes en [!DNL Customer Journey Analytics] para todas las actividades creadas en su cuenta (**[!UICONTROL Administración]** > **[!UICONTROL Creación de informes]** > **[!UICONTROL Creación de informes en la solución de Experience Cloud]**). Para obtener más información, consulte *Solución de Reporting Cloud* en [Configurar la creación de informes en [!DNL Target]](/help/main/administrating-target/reporting.md#solution).

1. En la lista **[!UICONTROL Actividades]**, haga clic en **[!UICONTROL Crear actividad]**, luego seleccione el tipo de actividad (de acuerdo con el [gráfico de actividad admitido anterior](#supported-activities)) y comience a configurar la actividad.

1. Cuando llegue a la página **[!UICONTROL Objetivos y configuración]** del flujo de trabajo de creación de actividades en tres partes, seleccione **[!DNL Customer Journey Analytics]** como fuente de informes.

   ![Customer Journey Analytics como opción de fuente de creación de informes](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La fuente de creación de informes no se puede cambiar después de iniciada la actividad de [!DNL Target].

1. Seleccione la zona protegida [!DNL Adobe Experience Platform] que coincida con los datos utilizados para los informes de [!DNL Customer Journey Analytics]. En esta lista desplegable solo verá los entornos limitados a los que tiene acceso. Si una o varias zonas protegidas a las que tiene acceso no aparecen en la lista, compruebe que tiene acceso a la zona protegida. Póngase en contacto con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si sigue teniendo problemas.

   ![Seleccione la opción de zona protegida](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. Seleccione una **[!UICONTROL vista de datos]**. Una vista de datos funciona como un grupo de informes [!DNL Analytics] para los informes [!DNL Customer Journey Analytics]. Solo se muestran las vistas de datos de la zona protegida seleccionada a la que tiene acceso.

   ➡️ [Obtenga más información acerca de la vista de datos en la documentación de Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views)

1. Especifique la métrica de objetivo. Elija una de las siguientes opciones:

   * **[!UICONTROL Conversión]**: elige la acción que la audiencia debe realizar para indicar que se ha alcanzado el objetivo. [Más información sobre las métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md).

   * **[!UICONTROL Usar una métrica de Customer Journey Analytics]**: elija una métrica [!DNL Customer Journey Analytics] o una métrica calculada de la vista de datos seleccionada. Esta métrica sirve como criterio de optimización. El modelo se ejecuta en [!DNL Customer Journey Analytics] datos y actualiza los datos de rendimiento en la misma cadencia usada para los informes de [!DNL Customer Journey Analytics].

   ![Use una opción de métrica de Customer Journey Analytics en Métrica de meta](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. Haga clic en **[!UICONTROL Guardar y cerrar]**.

## Configuración de una conexión de [!DNL Customer Journey Analytics]

Después de crear la actividad [!DNL Target], configure [!DNL Customer Journey Analytics] para extraer los datos con el fin de crear informes. La configuración sigue el flujo de trabajo de conexión estándar de [!DNL Customer Journey Analytics]. Si ya tienes una conexión configurada, puedes usar tu conexión existente y saltar a [Configurar vistas de datos](#set-up-data-views).

1. En [!DNL Customer Journey Analytics], vaya a **[!UICONTROL Administración de datos]** > **[!UICONTROL Conexiones]** y haga clic en **[!UICONTROL Crear una nueva conexión]**.

   ![Crear nuevo vínculo de conexión en [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. Configure su [conexión y configuración de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank} con la información correcta, incluido el mismo espacio aislado de [!DNL Adobe Experience Platform] que seleccionó para la actividad.
1. Añada el conjunto de datos del evento que utilizó al configurar la secuencia de datos.
1. Agregue el conjunto de datos de búsqueda **[!UICONTROL Eventos de clasificación de Adobe Target]** y, a continuación, haga clic en **[!UICONTROL Siguiente]**.

   ![Añada un cuadro de diálogo de conjuntos de datos en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. Configure el conjunto de datos del evento.

   Para obtener más información, consulte [Agregar y configurar conjuntos de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} en *Crear una conexión* en la guía *[!DNL Adobe Customer Journey Analytics]*.

1. Configure el conjunto de datos de búsqueda con el campo [!UICONTROL Clave] como &quot;clave&quot; y el campo de clave [!UICONTROL Coincidencia] con la siguiente ruta:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Cuadro de diálogo de evento Clasificaciones de Adobe Target en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. Haga clic en **[!UICONTROL Agregar conjuntos de datos]** y, a continuación, haga clic en **[!UICONTROL Guardar]** en la siguiente pantalla para finalizar la conexión.

## Configuración de vistas de datos {#set-up-data-views}

Configure una vista de datos en [!DNL Customer Journey Analytics] que apunte a la conexión que creó. Una vista de datos garantiza que los datos de la conexión se puedan usar correctamente para el análisis y para el panel [!UICONTROL Experimentación].

1. Configure la vista de datos y asegúrese de que apunta a la conexión creada anteriormente.

   Para obtener más información, consulte [Crear o editar una vista de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} en la guía *[!DNL Adobe Customer Journey Analytics]*.

1. Para ver correctamente los datos de [!DNL Target] en [!DNL Customer Journey Analytics], agregue los siguientes campos del conjunto de datos de búsqueda como dimensiones (incluidos [!UICONTROL Experience ID] y [!UICONTROL Activity ID]):

   * [!UICONTROL Nombre de experiencia]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Nombre de actividad]
   * [!UICONTROL ID de actividad]

   ![Opciones de nombres e ID en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Para asegurarse de que [!DNL Customer Journey Analytics] atribuya las métricas a la experiencia [!DNL Target] correcta en el recorrido del visitante, configure la persistencia para las dimensiones [!UICONTROL Nombre de actividad] e [!UICONTROL ID de actividad].

   Sin la configuración de persistencia, [!DNL Customer Journey Analytics] vincula solamente las métricas que se producen en el mismo evento que la experiencia [!DNL Target]. Por ejemplo, si un visitante ve una experiencia de Target en la página de inicio, la métrica de ingresos de ese visitante tras una compra en una página posterior no se atribuye a la actividad de Target.

   Para obtener más información sobre persistencia, consulte [Documentación de Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence){target=_blank}.

1. Para usar [!DNL Target] dimensiones en el panel [!UICONTROL Experimentación], configure las siguientes etiquetas de contexto:

   * Para [!UICONTROL Nombre de actividad], use &quot;Experimento de experimentación&quot;.
   * [!UICONTROL Nombre de experiencia], use &quot;Variante de experimento&quot;.

   ![Etiquetas de contexto del panel Experimentación](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. Termine de configurar cualquier otro campo y, a continuación, haga clic en **[!UICONTROL Guardar y continuar]** cuando haya terminado.

## Crear y ver informes de actividad en [!DNL Customer Journey Analytics]

Una vez que la actividad esté activa y complete la configuración de conexión y vista de datos, los datos de informes estarán disponibles en [!DNL Customer Journey Analytics]. Desde la ficha **[!UICONTROL Informes]** de la actividad en [!DNL Target], use **[!UICONTROL Ver en Customer Journey Analytics]** para abrir [!DNL Customer Journey Analytics] para su análisis. Actualmente, este enlace lo redirige a la página de aterrizaje principal [!DNL Customer Journey Analytics].

![Vínculo de informes de CJA](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>Esta integración no es la misma que [!UICONTROL Adobe Analytics for Target] (A4T).
>
>* La integración de [!DNL Target]/[!DNL Customer Journey Analytics] no incluye un informe generado previamente como A4T. Los informes de actividad deben generarse en [!DNL Customer Journey Analytics].
>
>* Si se selecciona [!UICONTROL Usar una métrica de CJA] como métrica de objetivo de la actividad, esta opción proporciona flexibilidad para determinar cuándo se deben definir métricas de éxito específicas. La métrica de éxito se selecciona al configurar el panel [!UICONTROL Experimentación]. El alza y la confianza se calculan a partir de la métrica de CJA seleccionada.

1. En [!DNL Customer Journey Analytics], cree un panel Experimentación y luego seleccione la actividad en el menú desplegable **[!UICONTROL Experimento]**.

   Para obtener más información, consulte [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank} en *Panel de experimentación* en la guía *[!DNL Customer Journey Analytics]*.

   ![Panel de experimentación en Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >Si la actividad no aparece en la lista desplegable [!UICONTROL Experimento], compruebe que esté seleccionada la vista de datos correcta y que las dimensiones [!DNL Target] incluyan las etiquetas de contexto necesarias (consulte el Paso 3 en [Configurar vistas de datos](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}).

1. Haga clic en **[!UICONTROL Crear]**.

   El panel [!UICONTROL Experimentación] devuelve un conjunto completo de datos y visualizaciones para ayudarle a comprender mejor el rendimiento de sus experimentos. Para obtener más información, consulte [[!UICONTROL Salida de panel]](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank} en *Panel de experimentación* en la guía *[!DNL Customer Journey Analytics]*.

   ![Experimentación](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)