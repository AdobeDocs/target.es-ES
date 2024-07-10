---
keywords: exclusiones
description: Obtenga información sobre cómo crear exclusiones en [!DNL Target Recommendations] para evitar que se recomienden productos o contenido a los visitantes.
title: ¿Cómo utilizo las exclusiones en? [!UICONTROL Recommendations] ¿Actividades?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 31cf23a52c331eabad0e5f6423eeeca84df87625
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 18%

---

# Exclusiones

Creación de una exclusión en [!DNL Adobe Target Recommendations] para evitar que se recomienden productos o contenido a los visitantes. Una exclusión es un subconjunto de productos o contenido que no debe recomendarse a los visitantes.

Las exclusiones están disponibles en toda la cuenta. A diferencia de las colecciones, donde especifica una colección específica para cada experiencia al crear una [!UICONTROL Recommendations] actividad, las exclusiones se aplican a todas las actividades de la cuenta. No hay ninguna opción para asignar un grupo de exclusión durante la creación de la actividad.

A continuación, mostramos algunos ejemplos de uso de exclusiones:

* Productos que se han suspendido.
* El catálogo de otoño e invierno es ahora el único catálogo que debería estar presente en línea. Cualquier artículo del catálogo de verano ya no está disponible para adquirir.
* Artículos que pueden ser inadecuados para recomendar en la mayoría de las páginas o pantallas (productos para adultos, películas NC-17, etc.).
* Productos con campos de metadatos incompletos (faltan miniaturas, precios u otros metadatos importantes).
* Productos que nunca deben recomendarse (puede que exista un SKU en el sistema para algo, pero no es un artículo que se pueda comprar). O tal vez sea un SKU falso para el equipo de control de calidad para simular una compra sin realmente ordenar algo, y así sucesivamente).

>[!IMPORTANT]
>
>Las reglas de exclusión se aplican globalmente a todos los [entornos](/help/main/administrating-target/environments.md).
>
>Las reglas de exclusión estáticas y dinámicas son funciones potentes que pueden ayudarle en sus estrategias de marketing. Para obtener información detallada, ejemplos y casos de uso, consulte [Uso de reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Creación de una exclusión

1. Clic **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** para mostrar la lista de exclusiones existentes.

   ![imagen exclusions_list](assets/exclusions-list.png)

   El &quot;Número de elementos&quot; registrado para cada exclusión en la [!UICONTROL Exclusions] la vista de lista es el número de productos que coinciden con las reglas para esa exclusión en la Recommendations predeterminada configurada [grupo de hosts](/help/main/administrating-target/hosts.md) (entorno). Consulte [Planificar e implementar [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} en el *Guía para desarrolladores de Adobe Target* para obtener información sobre cómo cambiar el grupo de hosts predeterminado.

1. (Condicional) Haga clic en [!UICONTROL Filter] y, a continuación, elija el [entorno](/help/main/administrating-target/environments.md) desde el **[!UICONTROL Environment]** lista desplegable al crear (o actualizar) una exclusión para obtener una vista previa del contenido de la exclusión en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Crear exclusión](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. Haga clic en **[!UICONTROL Create Exclusion]**.

   ![Cuadro de diálogo Crear exclusión](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. Escriba una exclusión **[!UICONTROL Name]** e introduzca una descripción opcional.

1. Utilice el generador de reglas para crear las exclusiones.

   Seleccione un parámetro en la lista reglas, elija un operador y luego escriba uno o varios valores para identificar los productos. Separe los distintos valores con comas.

1. Haga clic en **[!UICONTROL Create]**.

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## Editar, copiar o eliminar una exclusión

Haga clic en **elipsis** junto a la exclusión deseada en la lista y, a continuación, haga clic en el icono correspondiente: editar, copiar o eliminar.

![Opciones: editar, copiar y eliminar](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

Puede copiar una exclusión existente para crear una exclusión duplicada que luego puede modificar. Esta opción permite crear una exclusión similar con menos esfuerzo.

Tenga en cuenta que las exclusiones están disponibles en toda la cuenta. Asegúrese de tener en cuenta esta advertencia antes de eliminar una exclusión. Las exclusiones eliminadas no se pueden recuperar.

## Vídeo de formación: Creación de colecciones y exclusiones en Recommendations (7:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/27689)