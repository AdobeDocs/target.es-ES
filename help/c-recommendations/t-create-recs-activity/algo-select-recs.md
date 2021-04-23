---
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo
description: Obtenga información sobre cómo seleccionar los criterios (reglas que determinan qué productos o contenido se recomiendan) para usar en la actividad de Adobe [!DNL Target] Recommendations.
title: ¿Cómo se seleccionan los criterios de una actividad de Recommendations?
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 74%

---

# ![PREMIUM](/help/assets/premium.png) Seleccionar criterios

Seleccione los [criterios](/help/c-recommendations/c-algorithms/algorithms.md) que usará en su actividad de [!DNL Adobe Target Recommendations] Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.

Puede probar distintos tipos de recomendaciones entre sí si agrega más de un criterio.

Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

* Para buscar un criterio existente (por ejemplo, si se muestran muchas tarjetas de criterios), escriba el campo de búsqueda hasta que aparezca el criterio deseado y, después, seleccione el criterio y haga clic en **[!UICONTROL Finalizado]**.

   Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

* Para crear un nuevo criterio, haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear criterio]** y rellene la información del nuevo criterio. Para obtener información sobre la creación de nuevos criterios, consulte [Crear nuevos criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Para seleccionar criterios:**

1. Mientras [crea una nueva recomendación](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), en el cuadro de diálogo **[!UICONTROL Seleccionar criterios]**, busque y seleccione uno o más criterios.

   ![Cuadro de diálogo Seleccionar criterios](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   Puede utilizar el filtro [!UICONTROL Tipo de sector], el filtro [!UICONTROL Tipo de página] y la casilla [!UICONTROL Compatible] para filtrar la lista de criterios. Estas opciones le ayudan a encontrar los criterios deseados.

   * **Tipo de sector:** el tipo de sector se usa para categorizar los criterios de [!DNL Recommendations]. Para cambiar el sector predeterminado, haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Configuración]** y seleccione la configuración predeterminada **[!UICONTROL Sector]** que desee.
   * **Tipo de página:** el tipo de página sirve para categorizar las recomendaciones. También hay criterios integrados que se pueden elegir para cada tipo de página.
   * **Compatible:** muestra solo aquellos criterios en los que la página seleccionada pasa los datos necesarios. No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o `entity.categoryId` para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desmarque la casilla de verificación **[!UICONTROL Compatible]**. Esta opción se puede activar o desactivar en la configuración: **[!UICONTROL Recommendations]** > **[!UICONTROL Configuración]**.

1. Haga clic en **[!UICONTROL Siguiente]** para mostrar el cuadro de diálogo [Seleccionar diseño](/help/c-recommendations/c-design-overview/design-overview.md).
