---
keywords: búsqueda en el catálogo;catálogo;búsqueda;exclusión;colección;filtro;recomendaciones
description: Aprenda a utilizar el [!DNL Recommendations] [!UICONTROL Catalog Search] para localizar productos o contenido, quitar artículos del catálogo y mucho más.
title: ¿Cómo utilizo el [!DNL Recommendations] [!UICONTROL Catalog Search]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 6b0175b1-0eee-498d-8a08-513cf6695114
source-git-commit: 16a7c11e8b9b1a08b1e467519f997d0b05e47529
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 21%

---

# [!UICONTROL Catalog Search]

El [!UICONTROL Catalog Search] página en [!DNL Adobe Recommendations] le ayuda a localizar los productos o el contenido en su catálogo. La tarea más básica que puede realizar en esta página es buscar un elemento. Además, puede cambiar el entorno, filtrar facetas, modificar columnas de la tabla, agregar nuevas facetas de búsqueda y más.

Los catálogos hacen referencia a todo el conjunto de productos (entidades). El catálogo puede contener muchas colecciones, una forma de organizar los productos en bloques lógicos.

## Acceso [!UICONTROL Catalog Search]

Para acceder a [!UICONTROL Catalog Search] página, haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Página Buscar en el catálogo](/help/main/c-recommendations/c-products/assets/catalog-search-new.png)

## Realice una búsqueda sencilla

1. Escriba un término de búsqueda en **[!UICONTROL Search In]** field.

1. (Opcional) Puede restringir la búsqueda seleccionando una opción de búsqueda en el menú de opciones que se muestra al hacer clic en la flecha hacia abajo en el [!UICONTROL Search In] field.

   Las opciones de búsqueda son las siguientes:

   * ID
   * Nombre
   * Mensaje

1. Desplácese por los elementos de los resultados de búsqueda para ver miniaturas y otra información del producto.

   >[!NOTE]
   >
   > Cuando se realiza una búsqueda en el catálogo de un atributo personalizado con un valor numérico, los resultados tratan al atributo personalizado como un tipo de cadena en lugar de un valor numérico.
   >
   >Actualmente no hay ninguna funcionalidad disponible que permita cambiar el tipo de un atributo. Para realizar un cambio, [abra un problema con el cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que haga referencia a los atributos cuyo tipo necesitan que cambie de cadena a numérico.

   También puede utilizar filtros para encontrar los productos deseados. Por ejemplo, haciendo clic en el botón **[!UICONTROL Show Filters]** icono ( ![Mostrar icono de filtros](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ), expandiendo el [!UICONTROL Collections] faceta, si selecciona una o varias colecciones, se muestran todos los productos que pertenecen a las colecciones seleccionadas en el catálogo.

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## Ver los detalles de un elemento

Puede ver los detalles de un elemento individual, incluidos el ID, el nombre, el mensaje, la categoría, etc., consultando sus detalles.

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

## Eliminar un elemento del catálogo

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

1. Haga clic en **[!UICONTROL Remove from Catalog]**.

1. Confirme que desea quitar el elemento.

Toda la información sobre ese elemento se elimina del índice del catálogo. El elemento se incluirá en el catálogo solo si se vuelve a añadir en una fuente de datos. Un elemento eliminado debe eliminarse por separado de las fuentes.

## Actualizar el catálogo

El índice del catálogo se crea automáticamente al cargar la primera fuente y se actualiza según las [programación especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

El catálogo se actualiza automáticamente cuando se reciben actualizaciones mediante archivos de fuentes, API o actualizaciones de mbox. Las actualizaciones se suelen completar en una hora. Si las actualizaciones están en curso, se muestra la hora en la que se inició la más reciente. Si no hay actualizaciones en curso, se muestra la hora de inicio y finalización de la más reciente.

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## Cambiar el entorno

[Entornos](/help/main/administrating-target/environments.md) le permite organizar sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

1. Haga clic en el icono Mostrar filtros ( ![Mostrar icono de filtros](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ).

1. Seleccione el entorno que desee en **[!UICONTROL Environment]** lista desplegable.

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## Modificar columnas

Puede modificar temporalmente las columnas activas en [!UICONTROL Catalog Search] página.

1. Haga clic en **[!UICONTROL Customize Table]** icono (  ![Icono Personalizar tabla](/help/main/c-recommendations/c-products/assets/icon-customize-table.png) ).

1. Seleccione o anule la selección de las columnas que desee mostrar u ocultar.

Tenga en cuenta que cualquier cambio que realice se aplicará únicamente a la sesión actual.
