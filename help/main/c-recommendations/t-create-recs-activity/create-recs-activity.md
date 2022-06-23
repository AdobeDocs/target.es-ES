---
keywords: crear recomendaciones;actividad de recomendaciones;nuevas recomendaciones;información general de recomendaciones
description: Aprenda a utilizar el Adobe [!DNL Target] Compositor de experiencias visuales (VEC) para crear una actividad de Recommendations directamente en una [!DNL Target]-habilitada.
title: ¿Cómo creo una actividad de Recommendations?
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 76%

---

# ![PREMIUM](/help/main/assets/premium.png) Crear una actividad de Recommendations

Use el Compositor de experiencias visuales (VEC) de Target para crear una actividad de Recommendations directamente en una página con Target habilitado y modificar partes de la página en Target.

1. Haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Recomendaciones]**.

   ![Crear una actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Seleccione **[!UICONTROL Visual (Predeterminado)]**, si es necesario.

   ![Cuadro de diálogo Crear actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Si prefiere usar el Compositor de experiencias basadas en formularios, seleccione [!UICONTROL Formulario]. Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener más información.

   >[!NOTE]
   >
   >Además del VEC y del Compositor de experiencias basadas en formularios, Target ofrece el VEC de aplicación de una sola página y el VEC para aplicaciones móviles. Para obtener más información sobre los distintos compositores, consulte [Experiencias y ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obtener información acerca de la solución de problemas del VEC, en caso de problemas, consulte [Solución de problemas del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >La variable [!UICONTROL [Elegir lugar de trabajo]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) en la ilustración anterior es una [Target Premium](/help/main/c-intro/intro.md) función. Su organización tiene una licencia de Target Standard si no ve esta opción.

1. (Condicional) Si es [cliente de Target Premium](/help/main/c-intro/intro.md#premium), elija un [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Introduzca una URL de actividad y haga clic en **[!UICONTROL Siguiente]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Esto quiere decir que tanto [!DNL `http://www.adobe.com`] como [!DNL `https://wwww.adobe.com`] coinciden.

   La dirección URL de actividad es la página donde se mostrarán las recomendaciones.

   Tras hacer clic en [!UICONTROL Siguiente], VEC se abre y muestra su página. Puede reemplazar un artículo actual por recomendaciones, o insertar recomendaciones.

1. Haga clic en un elemento de la página. Si hay recomendaciones disponibles donde se encuentra ese elemento, haga clic en **[!UICONTROL Reemplazar con Recommendations]**, **[!UICONTROL Insertar Recommendations antes]** o **[!UICONTROL Insertar Recommendations después]**.

   Los visitantes del sitio verán el contenido recomendado solo si cumplen los requisitos para la recomendación. Los visitantes que no cumplan los requisitos para la recomendación verán el contenido predeterminado.

   ![Opciones de Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Reemplazar con Recommendations]**: Sustituir un elemento por recomendaciones elimina el contenido actual y lo reemplaza por sus recomendaciones. Cuando los visitantes visiten el sitio y cumplan los requisitos para la recomendación, verán los artículos recomendados en el área especificada en lugar del contenido existente.
   * **[!UICONTROL Insertar Recommendations antes]**: Al insertar recomendaciones antes del elemento seleccionado, se coloca el contenido recomendado antes de ese elemento. Según la construcción de la página, la recomendación se muestra arriba o a la izquierda del elemento seleccionado.
   * **[!UICONTROL Insertar Recommendations después]**: Al insertar recomendaciones después del elemento seleccionado, se coloca el contenido recomendado después de ese elemento. En función de la construcción de la página, la recomendación se muestra a la derecha o debajo del elemento seleccionado.

   La variable **[!UICONTROL Expandir selección]** permite expandir la ubicación seleccionada (contenedor principal) para ayudarle a identificar e incluir fácilmente los elementos de página deseados.

1. Seleccione un tipo de página.

   Los tipos de página pueden incluir:

   * Página del carro de compras
   * Página de categoría
   * Página principal
   * Página de aterrizaje
   * Página de productos
   * Página de resultados de búsqueda
   * Página de agradecimiento.
   * Otro:

   ![Seleccionar opciones de tipo de página](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Seleccione uno o más [criterios](/help/main/c-recommendations/c-algorithms/algorithms.md).

   Los criterios se muestran como tarjetas que muestran información sobre cada criterio. De forma predeterminada, la variable [!UICONTROL Seleccionar criterios] muestra los criterios compatibles con el sector y el tipo de página seleccionado en el paso anterior. Puede cambiar estas opciones para mostrar otros criterios.

   >[!NOTE]
   >
   >No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desmarque la casilla de verificación **[!UICONTROL Compatible]**. Es posible que no se muestre la opción [!UICONTROL Compatible], dependiendo de la configuración de Recomendaciones (**[!UICONTROL Recomendaciones]** > **[!UICONTROL Configuración]** > **[!UICONTROL Filtrar criterios incompatibles]**). Para obtener más información, consulte [Configuración](https://developer.adobe.com/target/implement/recommendations/).

   ![Cuadro de diálogo Seleccionar criterios](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

   * Para buscar un criterio existente (por ejemplo, si se muestran muchas tarjetas de criterios), escriba en el campo de búsqueda hasta que aparezca el criterio deseado y, después, seleccione el criterio y haga clic en **[!UICONTROL Siguiente]**.

      Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

   * Para crear un nuevo criterio, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear criterios]**, rellene la información del nuevo criterio. Para obtener información sobre la creación de criterios nuevos, consulte [Creación de criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)
   * También puede agrupar criterios en secuencias. Para crear una nueva secuencia de criterios, haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear secuencia de criterios]**. Consulte [Crear secuencia de criterios](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md) para obtener más información.

1. Haga clic en **[!UICONTROL Siguiente]**.
1. Seleccionar un [diseño](/help/main/c-recommendations/c-design-overview/design-overview.md).

   Un diseño es una plantilla que determina el aspecto de las ubicaciones en la página. [!DNL Target] incluye varios diseños preconfigurados. También puede crear sus propios diseños personalizados. Para obtener más información, consulte  [Creación de diseños](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) y [Personalización de diseños](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Cuadro de diálogo Seleccionar diseño](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   En cada diseño se muestra una representación gráfica del aspecto que tendrá, y los iconos muestran en cuántas actividades publicadas e inactivas se usa ese diseño.

   * Para seleccionar uno o varios diseños existentes, haga clic en los diseños y elija **[!UICONTROL Siguiente]**.

      Si ha seleccionado varios criterios, solo puede seleccionar un diseño.

   * Para crear un diseño personalizado, haga clic en **[!UICONTROL Crear diseño]** y rellene el nombre y el código para el nuevo diseño. Haga clic en **[!UICONTROL Siguiente]**, seleccione o actualice una imagen y haga clic en **[!UICONTROL Hecho]** > **[!UICONTROL Hecho]**. Para obtener más información sobre cómo crear un diseño nuevo, consulte [Creación de diseños](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Haga clic en **[!UICONTROL Siguiente]**.

   Puede agregar promociones a sus recomendaciones. Para obtener más información sobre cómo agregar promociones principales y secundarias, consulte  [Añadir promociones](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Haga clic en **[!UICONTROL Guardar]**.

   La pantalla del compositor de experiencias visuales muestra el diseño de recomendaciones de su página.

1. (Opcional) Haga clic en **[!UICONTROL Vista previa]** para ver cómo aparecerá la actividad para los visitantes.

   El modo de [!UICONTROL Vista previa] permite interactuar con sus recomendaciones, como lo haría un visitante.

   Cuando termine con la vista previa de las recomendaciones, haga clic en **[!UICONTROL Componer]**.

1. Revise la recomendación en el VEC y, a continuación, haga clic en **[!UICONTROL Siguiente]**.

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
   * Cambie la colección (al lado de la etiqueta [!UICONTROL Criterios])
   * Cambiar el porcentaje de participantes que ven la experiencia de control
   * Ver el código del diseño
   * Cambiar o quitar un diseño

1. Haga clic en **[!UICONTROL Siguiente]** cuando termine.
1. Especifique la configuración de la actividad.

   Por ejemplo, escriba un nombre (obligatorio) y un objetivo (opcional) para la actividad. Para obtener información sobre la configuración, consulte [Configuración de actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Si especifica el nombre de una actividad de [!DNL Recommendation] existente para otra actividad de [!DNL Recommendations Classic], la nueva actividad se vuelve a sincronizar con un nombre nuevo. Este es el nombre original, al que se le agrega una marca de tiempo para que sea único. Ese nuevo nombre se muestra en [!DNL Target Standard/Premium] y en [!DNL Recommendations Classic].

1. Cuando termine, haga clic en **[!UICONTROL Guardar y cerrar]**.

   Se muestra la información general de la actividad.

   Desde la página [!UICONTROL Información general] puede:

   * Activar la actividad
   * Editar la actividad
   * Comparta la actividad en la fuente de su Experience Cloud
   * Control de calidad de la actividad
   * Ver las direcciones URL de la experiencia
   * Descargar datos
   * Cambiar el porcentaje de participantes en la actividad que ven la experiencia de control
   * Mostrar u ocultar detalles de criterios
   * Ver el código de los diseños

1. (Opcional) Abra la página [!UICONTROL Informes] para ver el informe que muestra el rendimiento de la actividad de [!DNL Recommendations].

1. (Opcional) Abra la página [!UICONTROL Conflictos] para ver cualquier [conflicto de actividades](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) que pueda producirse.

   Se produce un conflicto de actividades cuando existen varias actividades configuradas para publicar contenido en la misma página, lo cual puede hacer que se muestre contenido inesperado.

## Vídeo de formación: Crear una actividad de Recommendations (7:15) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)
