---
description: Use el Compositor de experiencias visuales (VEC) de Target para crear una actividad de Recommendations directamente en una página con Target habilitado y modificar partes de la página en Target.
keywords: crear recomendaciones;actividad de recomendaciones;nuevas recomendaciones;información general de recomendaciones
seo-description: Use el Compositor de experiencias visuales (VEC) de Target para crear una actividad de Recommendations directamente en una página con Target habilitado y modificar partes de la página en Target.
seo-title: Crear una actividad de Recommendations
solution: Target
title: Crear una actividad de Recommendations
title-outputclass: premium
topic: Premium
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
badge: premium
translation-type: tm+mt
source-git-commit: 1f3b3be385cad4e7e87f27b566fc1266eef649b8

---


# ![PREMIUM](/help/assets/premium.png) Crear una actividad de Recommendations{#create-a-recommendations-activity}

Use el Compositor de experiencias visuales (VEC) de Target para crear una actividad de Recommendations directamente en una página con Target habilitado y modificar partes de la página en Target.

1. Haga clic en **[!UICONTROL Crear actividad]** &gt; **[!UICONTROL Recommendations]**.

   ![Crear actividad de Recomendaciones](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Cuadro de diálogo Crear actividad de Recomendaciones](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >Además del Compositor de experiencias visuales y el Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Su organización tiene una licencia de Target Standard si no ve esta opción.]

1. (Conditional) If you are a [Target Premium customer](/help/c-intro/intro.md#premium), choose a [workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Introduzca una URL de actividad y haga clic en **[!UICONTROL Siguiente]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://wwww.adobe.com`] coinciden.

   La dirección URL de actividad es la página donde se mostrarán las recomendaciones.

   Tras hacer clic en [!UICONTROL Siguiente], VEC se abre y muestra su página. Puede reemplazar un artículo actual por recomendaciones, o insertar recomendaciones.

1. Click an element on your page, then if recommendations are available where that element is located, click **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]**, or **[!UICONTROL Insert Recommendations After]**.

   ![Opciones de Recomendaciones](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   Al sustituir un elemento por recomendaciones, se elimina el contenido actual y se sustituye por las recomendaciones.

1. Seleccione un tipo de página.

   Los tipos de página pueden incluir:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de aterrizaje
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento 
   * Otro:
   ![Seleccionar opciones de tipo de página](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Select one or more [criteria](/help/c-recommendations/c-algorithms/algorithms.md).

   Los criterios se muestran como tarjetas que muestran información sobre cada criterio. De forma predeterminada, la pantalla [!UICONTROL Seleccionar criterios] muestra los criterios compatibles con el sector y el tipo de página seleccionados. Puede cambiar estas opciones para mostrar otros criterios.

   >[!NOTE]
   >
   >No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desmarque la casilla de verificación **[!UICONTROL Compatible]**. Es posible que no se muestre la opción [!UICONTROL Compatible], dependiendo de la configuración de Recommendations (**[!UICONTROL Recommendations]** &gt; **[!UICONTROL Configuración]** &gt; **[!UICONTROL Filtrar criterios incompatibles]**). Para obtener más información, consulte [Configuración](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

   ![Seleccionar criterios, cuadro de diálogo](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

   * To search for an existing criteria (for example, if a large number of criteria cards are displayed), type in the search field until the desired criteria appears, then select the criteria and click **[!UICONTROL Next]**.

      Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

   * To create a new criteria, click **[!UICONTROL Create Criteria]** &gt; **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. Para obtener información sobre la creación de criterios nuevos, consulte [Creación de criterios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)
   * También puede agrupar criterios en secuencias. To create a new criteria sequence, click **[!UICONTROL Create Criteria]** &gt; **[!UICONTROL Create Criteria Sequence]**. Consulte [Creación de secuencias de criterios](../../c-recommendations/c-algorithms/create-criteria-sequence.md#task_8A9CB465F28D44899F69F38AD27352FE) para obtener más información.

1. Haga clic en **[!UICONTROL Siguiente]**.
1. Select a [design](/help/c-recommendations/c-design-overview/design-overview.md).

   Un diseño es una plantilla que determina el aspecto de las ubicaciones en la página. [!DNL Target] incluye varios diseños preconfigurados. También puede crear sus propios diseños personalizados. Para obtener más información, consulte  [Creación de diseños](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) y [Personalización de diseños](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Seleccionar diseño, cuadro de diálogo](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   En cada diseño se muestra una representación gráfica del aspecto que tendrá, y los iconos muestran en cuántas actividades publicadas e inactivas se usa ese diseño.

   * To select one or more existing designs, click the designs, then click **[!UICONTROL Next]**.

      Si ha seleccionado varios criterios, puede seleccionar solo un diseño.

   * To create a custom design, click **[!UICONTROL Create Design]**, then fill in the name and code for the new design. Haga clic en **[!UICONTROL Siguiente]**, seleccione o cargue una imagen y haga clic en **[!UICONTROL Listo]** &gt; **[!UICONTROL Listo]**. Para obtener más información sobre cómo crear un diseño nuevo, consulte [Creación de diseños](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Haga clic en **[!UICONTROL Siguiente]**.

   Puede agregar promociones a sus recomendaciones. Para obtener más información sobre cómo agregar promociones principales y secundarias, consulte  [Añadir promociones](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).
1. Haga clic en **[!UICONTROL Guardar]**.

   La pantalla del compositor de experiencias visuales muestra el diseño de recomendaciones de su página.

1. (Opcional) Haga clic en **[!UICONTROL Vista previa]** para ver cómo aparecerá la actividad para los visitantes.

   El modo de [!UICONTROL Vista previa] permite interactuar con sus recomendaciones, como lo haría un visitante.

   Cuando termine con la vista previa de las recomendaciones, haga clic en **[!UICONTROL Componer]**.

1. Revise la recomendación en el VEC y, a continuación, haga clic en **[!UICONTROL Siguiente]**.

1. Revise su actividad de [!DNL Recommendations] en el diagrama de flujo y realice los cambios que sean necesarios.

   ![Diagrama de flujo de Recomendaciones](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad, la configuración de experiencias y la especificación de las métricas de éxito. 

   Desde el diagrama de flujo, puede hacer lo siguiente:

   * Cambiar la audiencia que verá las recomendaciones

      >[!NOTE]
      >
      >Además de seleccionar una audiencia existente, puede [crear audiencias de una actividad](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) o [combinar varias audiencias](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias específicas en vez de crear una nueva.

      De manera predeterminada, todos los usuarios ven las recomendaciones. Sin embargo, puede segmentar la recomendación a una audiencia en concreto.

      Para las actividades de [!DNL Recommendations], el grupo de control ve la página sin ninguna recomendación.

   * Ver los criterios
   * Cambie la colección (al lado de la etiqueta [!UICONTROL Criterios])
   * Cambiar el porcentaje de participantes que ven la experiencia de control
   * Ver el código del diseño
   * Cambiar o quitar un diseño

1. Haga clic en **[!UICONTROL Siguiente]cuando termine.**
1. Especifique la configuración de la actividad.

   Por ejemplo, escriba un nombre (obligatorio) y un objetivo (opcional) para la actividad. Para obtener información sobre la configuración, consulte [Configuración de actividad de Recommendations](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Si especifica el nombre de una actividad de [!DNL Recommendation] existente para otra actividad de [!DNL Recommendations Classic], la nueva actividad se vuelve a sincronizar con un nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. Ese nuevo nombre se muestra en [!DNL Target Standard/Premium] y en [!DNL Recommendations Classic].

1. When finished, click **[!UICONTROL Save &amp; Close]**.

   Se muestra la información general de la actividad.

   Desde la página [!UICONTROL Información general] puede:

   * Activar la actividad
   * Editar la actividad
   * Anclar la actividad al panel de Experience Cloud
   * Ver las direcciones URL de la experiencia
   * Descargar datos
   * Cambiar el porcentaje de participantes en la actividad que ven la experiencia de control
   * Mostrar u ocultar detalles de criterios
   * Ver el código de los diseños

1. (Opcional) Abra la página [!UICONTROL Informes] para ver el informe que muestra el rendimiento de la actividad de [!DNL Recommendations].
1. (Opcional) Abra la página [!UICONTROL Conflictos] para ver cualquier [conflicto de actividades](https://marketing.adobe.com/resources/help/en_US/target/target/c_activity_collisions.html) que pueda producirse.

   Se produce un conflicto de actividades cuando existen varias actividades configuradas para publicar contenido en la misma página, lo cual puede hacer que se muestre contenido inesperado.
