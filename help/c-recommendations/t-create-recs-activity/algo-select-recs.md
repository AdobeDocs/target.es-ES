---
keywords: recommendations;recommendations activity;criteria;algorithm
description: Seleccione los criterios que usará en su actividad de recomendaciones de Adobe Target.
title: Seleccionar criterios
feature: recs creation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 82%

---


# ![PREMIUM](/help/assets/premium.png) Seleccionar criterios{#select-criteria}

Seleccione los [criterios](/help/c-recommendations/c-algorithms/algorithms.md) que usará en su actividad de [!DNL Adobe Target Recommendations] Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.

Puede probar distintos tipos de recomendaciones entre sí si agrega más de un criterio.

Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

* Para buscar un criterio existente (por ejemplo, si se muestran muchas tarjetas de criterios), escriba el campo de búsqueda hasta que aparezca el criterio deseado y, después, seleccione el criterio y haga clic en **[!UICONTROL Finalizado]**.

   Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

* To create a new criteria, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. Para obtener información sobre la creación de nuevos criterios, consulte [Crear nuevos criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Para seleccionar criterios:**

1. While [creating a new recommendation](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Select Criteria]** dialog box, locate and select one or more criteria.

   ![Cuadro de diálogo Seleccionar criterios](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   Puede utilizar el filtro [!UICONTROL Tipo de sector], el filtro [!UICONTROL Tipo de página] y la casilla [!UICONTROL Compatible] para filtrar la lista de criterios. Estas opciones le ayudan a encontrar los criterios deseados.

   * **Tipo de sector:** el tipo de sector se usa para categorizar los criterios de [!DNL Recommendations]. To change your default industry vertical, click **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** and select your desired default **[!UICONTROL Industry Vertical]** setting.
   * **Tipo de página:** el tipo de página sirve para categorizar las recomendaciones. También hay criterios integrados que se pueden elegir para cada tipo de página.
   * **Compatible:** muestra solo aquellos criterios en los que la página seleccionada pasa los datos necesarios. No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desmarque la casilla de verificación **[!UICONTROL Compatible]**. This option can be disabled or enabled in your settings: **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar el cuadro de diálogo [Seleccionar diseño](/help/c-recommendations/c-design-overview/design-overview.md).
