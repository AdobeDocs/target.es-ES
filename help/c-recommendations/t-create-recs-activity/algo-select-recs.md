---
description: Seleccione los criterios que usará en su actividad de Recommendations.
keywords: recomendaciones;actividad de recomendaciones;criterios
seo-description: Seleccione los criterios que usará en su actividad de Recommendations.
seo-title: Seleccionar criterios
solution: Target
title: Seleccionar criterios
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Seleccionar criterios{#select-criteria}

Seleccione los criterios que usará en su actividad de Recommendations.

Puede probar distintos tipos de recomendaciones entre sí si agrega más de un criterio.

Si selecciona varios criterios, el tráfico se distribuye uniformemente entre los criterios seleccionados. Por ejemplo, si ha seleccionado dos criterios y la actividad está diseñada para mostrar contenido predeterminado al 20 % de participantes de la actividad, el 40 % de los participantes de la actividad verá las recomendaciones controladas por cada criterio. No hay posibilidad de cambiar los porcentajes para cada criterio.

* Para buscar un criterio existente (por ejemplo, si se muestran muchas tarjetas de criterios), escriba el campo de búsqueda hasta que aparezca el criterio deseado y, después, seleccione el criterio y haga clic en **[!UICONTROL Finalizado]**.

   Algunos criterios se proporcionan con [!DNL Recommendations]. También puede crear sus propios criterios personalizados.

* Para crear un nuevo criterio, haga clic en **[!UICONTROL Crear nuevo]** y rellene la información del nuevo criterio. Para obtener información sobre la creación de nuevos criterios, consulte [Crear nuevos criterios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

1. [Cree una nueva recomendación](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F) o localice la recomendación cuyos criterios quiera configurar y haga clic en **[!UICONTROL Editar]**.
1. Seleccione un tipo de sector y un tipo de página.

* **Tipo de sector:** el tipo de sector se usa para categorizar los criterios de [!DNL Recommendations]. Para cambiar el sector predeterminado, haga clic en **[!UICONTROL Configuración]** y seleccione la opción de **[!UICONTROL Sector]** predeterminada.
* **Tipo de página:** el tipo de página sirve para categorizar las recomendaciones. También hay criterios integrados que se pueden elegir para cada tipo de página.
* **Compatible:** muestra solo aquellos criterios en los que la página seleccionada pasa los datos necesarios. No todos los criterios se ejecutarán correctamente en cada página. La página o el mbox necesitan pasar `entity.id` o [!DNL entity.categoryId] para que las recomendaciones de la categoría actual o el elemento actual sean compatibles. En general, se recomienda mostrar solamente criterios compatibles. Sin embargo, si desea que haya disponibles criterios incompatibles para la actividad, desmarque la casilla de verificación **[!UICONTROL Compatible]**. Esta opción se puede activar o desactivar en las [!DNL Target] [!UICONTROL Preferencias de].

1. Haga clic en **[!UICONTROL Agregar]**.
