---
keywords: crear recomendaciones;actividad de recomendaciones;nuevas recomendaciones;información general de recomendaciones
description: Aprenda a utilizar el  [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) para crear una  [!DNL Recommendations] actividad.
title: ¿Cómo se crea una actividad  [!DNL Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 52%

---

# Crear una actividad [!DNL Recommendations]

Use [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) para crear una actividad [!DNL Recommendations] directamente en una página habilitada para [!DNL Target] y para modificar partes de la página en [!DNL Target].

1. Haga clic en **[!UICONTROL Activities]** > **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.

1. Seleccione **[!UICONTROL Visual]**, si es necesario.

   Si prefiere usar [!UICONTROL Form-Based Experience Composer], seleccione [!UICONTROL Form]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y [!UICONTROL Form-Based Experience Composer], [!DNL Target] ofrece el VEC [!UICONTROL Single Page Application]. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Elija un [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique una URL de actividad y haga clic en **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://wwww.adobe.com`] coinciden.

   La dirección URL de actividad es la página donde se muestran las recomendaciones.

   Al hacer clic en [!UICONTROL Create], el VEC se abre y muestra la página. Puede reemplazar un artículo actual por recomendaciones, o insertar recomendaciones.

1. Haga clic en un elemento de la página. Si hay recomendaciones disponibles donde se encuentra ese elemento, haga clic en **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]** o **[!UICONTROL Insert Recommendations After]**.

   Los visitantes del sitio verán el contenido recomendado solo si cumplen los requisitos para la recomendación. Los visitantes que no cumplan los requisitos para la recomendación verán el contenido predeterminado.

   ![Opciones de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Replace w/ Recommendations]**: al reemplazar un elemento por recomendaciones, se elimina el contenido actual y se reemplaza por las recomendaciones. Cuando los visitantes visiten el sitio y cumplan los requisitos para la recomendación, verán los artículos recomendados en el área especificada en lugar del contenido existente.
   * **[!UICONTROL Insert Recommendations Before]**: al insertar recomendaciones antes del elemento seleccionado, se coloca el contenido recomendado antes de ese elemento. Según la construcción de la página, la recomendación se muestra encima o a la izquierda del elemento seleccionado.
   * **[!UICONTROL Insert Recommendations After]**: al insertar recomendaciones después del elemento seleccionado, se coloca el contenido recomendado después de ese elemento. Según la construcción de su página, la recomendación se muestra debajo o a la derecha del elemento seleccionado.

   La opción **[!UICONTROL Expand Selection]** le permite expandir la ubicación seleccionada (contenedor principal) para ayudarle a identificar e incluir fácilmente los elementos de página deseados.

1. Seleccione un tipo de página.

   Los tipos de página pueden incluir:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de destino
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento.
   * Otro:

   ![Seleccionar opciones de tipo de página](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Seleccione uno o más [criterios](/help/main/c-recommendations/c-algorithms/algorithms.md).

   Los criterios se muestran como tarjetas que muestran información sobre cada criterio. De manera predeterminada, la pantalla [!UICONTROL Select Criteria] muestra criterios compatibles con el sector y el tipo de página que seleccionó en el paso anterior. Puede cambiar estas opciones para mostrar otros criterios.

   >[!NOTE]
   >
   >No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desactive la casilla de verificación **[!UICONTROL Compatible]**. Es posible que no se muestre la opción [!UICONTROL Compatible], según la configuración de Recommendations ( **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL Filter Incompatible Criteria]**). Para obtener más información, consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank}.

   ![Cuadro de diálogo Seleccionar criterios](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

   * Para buscar un criterio existente (por ejemplo, si se muestran muchas tarjetas de criterios), escriba en el campo de búsqueda hasta que aparezca el criterio deseado y, después, seleccione el criterio y haga clic en **[!UICONTROL Next]**.

     Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

   * Para crear un nuevo criterio, haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** y rellene la información del nuevo criterio. Para obtener información sobre la creación de criterios nuevos, consulte [Creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)
   * También puede agrupar criterios en secuencias. Para crear una nueva secuencia de criterios, haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Consulte [Crear secuencia de criterios](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md) para obtener más información.

1. Haga clic en **[!UICONTROL Next]**.
1. Seleccionar un [diseño](/help/main/c-recommendations/c-design-overview/design-overview.md).

   Un diseño es una plantilla que determina el aspecto de las ubicaciones en la página. [!DNL Target] incluye varios diseños preconfigurados. También puede crear sus propios diseños personalizados. Para obtener más información, vea [Crear un diseño](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) y [Personalizar un diseño](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Cuadro de diálogo Seleccionar diseño](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   En cada diseño se muestra una representación gráfica del aspecto que tendrá, y los iconos muestran en cuántas actividades publicadas e inactivas se usa ese diseño.

   * Para seleccionar uno o más diseños existentes, haga clic en los diseños y luego haga clic en **[!UICONTROL Next]**.

     Si ha seleccionado varios criterios, solo puede seleccionar un diseño.

   * Para crear un diseño personalizado, haga clic en **[!UICONTROL Create Design]** y rellene el nombre y el código para el nuevo diseño. Haga clic en **[!UICONTROL Next]**, luego seleccione o cargue una imagen y haga clic en **[!UICONTROL Done]** > **[!UICONTROL Done]**. Para obtener más información sobre cómo crear un diseño nuevo, consulte [Creación de diseños](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Haga clic en **[!UICONTROL Next]**.

   Puede agregar promociones a sus recomendaciones. Para obtener más información sobre cómo agregar promociones principales y secundarias, consulte [Agregar promociones](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Haga clic en **[!UICONTROL Save]**.

   La pantalla del compositor de experiencias visuales muestra el diseño de recomendaciones de su página.

1. (Opcional) Haga clic **[!UICONTROL Preview]** para ver cómo aparecerá la actividad para los visitantes.

   El modo [!UICONTROL Preview] le permite interactuar con sus recomendaciones, como lo haría un visitante.

   Cuando termine de obtener una vista previa de las recomendaciones, haga clic en **[!UICONTROL Compose]**.

1. Revise su recomendación en el VEC y luego haga clic en **[!UICONTROL Next]**.

1. Revise su actividad de [!DNL Recommendations] en el diagrama de flujo y realice los cambios que sean necesarios.

   ![Diagrama de flujo de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   El diagrama de flujo le guía durante el procedimiento para seleccionar una audiencia para la actividad, la configuración de experiencias y la especificación de las métricas de éxito..

   Desde el diagrama de flujo, puede hacer lo siguiente:

   * Cambiar la audiencia que verá las recomendaciones

     >[!NOTE]
     >
     >Además de seleccionar una audiencia existente, puede [crear audiencias de una actividad](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) o [combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear audiencias específicas en vez de crear una nueva.

     De manera predeterminada, todos los usuarios ven las recomendaciones. Sin embargo, puede segmentar la recomendación a una audiencia en concreto.

     Para las actividades de [!DNL Recommendations], el grupo de control ve la página sin ninguna recomendación.

   * Ver los criterios
   * Cambiar la colección (junto a la etiqueta [!UICONTROL Criteria])
   * Cambiar el porcentaje de participantes que ven la experiencia de control
   * Ver el código del diseño
   * Cambiar o quitar un diseño

1. Haga clic en **[!UICONTROL Next]** cuando termine.
1. Especifique la configuración de la actividad.

   Por ejemplo, escriba un nombre (obligatorio) y un objetivo (opcional) para la actividad. Para obtener información sobre la configuración, consulte [Configuración de actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Si especifica el nombre de una actividad de [!DNL Recommendation] existente para otra actividad de [!DNL Recommendations Classic], la nueva actividad se vuelve a sincronizar con un nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. Ese nuevo nombre se muestra en [!DNL Target Standard/Premium] y en [!DNL Recommendations Classic].

1. Cuando termine, haga clic en **[!UICONTROL Save & Close]**.

   Se muestra la información general de la actividad.

   Desde la página [!UICONTROL Overview], puede:

   * Activar la actividad
   * Editar la actividad
   * Comparta la actividad en su fuente de Experience Cloud
   * Control de calidad de la actividad
   * Ver las direcciones URL de la experiencia
   * Descargar datos
   * Cambiar el porcentaje de participantes en la actividad que ven la experiencia de control
   * Mostrar u ocultar detalles de criterios
   * Ver el código de los diseños

1. (Opcional) Abra la página [!UICONTROL Reports] para ver el informe que muestra el rendimiento de su actividad [!DNL Recommendations].

1. (Opcional) Abra la página [!UICONTROL Collisions] para ver los [conflictos de actividades](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) que puedan producirse.

   Se produce un conflicto de actividades cuando existen varias actividades configuradas para publicar contenido en la misma página, lo cual puede hacer que se muestre contenido inesperado.

## Vídeo de formación: Crear una actividad de Recommendations (7:15) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/33946?captions=spa)
