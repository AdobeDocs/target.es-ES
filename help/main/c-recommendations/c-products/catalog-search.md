---
keywords: búsqueda en el catálogo;catálogo;búsqueda;exclusión;colección;filtro;recomendaciones
description: Aprenda a usar [!DNL Recommendations] [!UICONTROL Búsqueda en el catálogo] para localizar productos o contenido, quitar elementos del catálogo y mucho más.
title: ¿Cómo se usa la [!DNL Recommendations] [!UICONTROL búsqueda en el catálogo]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
TQID: 'https://experienceleague.adobe.com/en3hkFsDjEE86Tc-3vPSiZFy0K47SftZMN6RW0INNic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 7%
---
# [!UICONTROL Buscar en el catálogo] {#catalog-search}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a buscar en el catálogo de [!DNL Adobe Recommendations] para encontrar productos o contenido, y a filtrar, ver y quitar elementos.

>[!ENDSHADEBOX]

La página **[!UICONTROL Búsqueda en el catálogo]** de [!DNL Adobe Recommendations] se usa para encontrar los productos o el contenido en el catálogo. La tarea más básica de esta página es buscar un elemento. La página también permite cambiar el entorno, filtrar las facetas, modificar las columnas de la tabla, etc.

El catálogo es todo el conjunto de productos (entidades). Puede contener muchas colecciones, que organizan los productos en grupos lógicos.

El índice del catálogo se crea automáticamente cuando se carga la primera fuente y se actualiza según la [programación especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

El catálogo se actualiza automáticamente cuando se reciben actualizaciones mediante archivos de fuentes, la API o actualizaciones de mbox. Las actualizaciones se suelen completar en una hora. Si las actualizaciones están en curso, se muestra la hora en la que se inició la más reciente. Si no hay actualizaciones en curso, se muestra la hora de inicio y finalización de la más reciente.

## Buscar en el catálogo

Utilice los resultados de búsqueda para revisar los elementos del catálogo y, si es necesario, eliminarlos.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Búsqueda en el catálogo]**.

1. (Opcional) Para filtrar los resultados, haga clic en el icono **[!UICONTROL Mostrar filtros]** ( ![Mostrar filtros](/help/main/assets/icons/Filter.svg) ) y, a continuación, seleccione los filtros que desee aplicar. Los filtros disponibles son **[!UICONTROL Entorno]**, **[!UICONTROL Colecciones]**, **[!UICONTROL Categoría]**, **[!UICONTROL Marca]**, **[!UICONTROL Inventario]** y **[!UICONTROL Valor]**.

   [Los entornos](/help/main/administrating-target/environments.md) organizan los sitios y entornos de preproducción para la administración y la creación de informes separados. Para cambiar el entorno, seleccione el entorno que desee en la lista desplegable **[!UICONTROL Entorno]**.

   ![Página de búsqueda en el catálogo con el panel de filtros resaltado: colecciones, categoría, marca, inventario, valor y búsqueda avanzada](../assets/catalog_search.png)

1. Escriba un término de búsqueda en el campo **[!UICONTROL Buscar en]**.

1. (Opcional) Refine la búsqueda seleccionando una opción de búsqueda en el menú de opciones, que se abre desde la flecha hacia abajo en el campo **[!UICONTROL Buscar en]**.

   Las opciones de búsqueda son las siguientes:

   * ID
   * Nombre
   * Mensaje

1. Haga clic en el icono **[!UICONTROL Personalizar tabla]** ( ![Personalizar icono de tabla](/help/main/assets/icons/ColumnSetting.svg) ) para modificar las columnas activas en la página **[!UICONTROL Búsqueda en el catálogo]**.

   ![Página de búsqueda en el catálogo con el icono Personalizar tabla resaltado](../assets/catalog_search_4.png)

1. Desplácese por los elementos de los resultados de búsqueda para ver miniaturas y otra información del producto.

   >[!NOTE]
   >
   >En una búsqueda en el catálogo de un atributo personalizado con un valor numérico, los resultados tratan el atributo personalizado como un tipo de cadena en lugar de un valor numérico.
   >
   >El tipo de un atributo no se puede cambiar en este momento. Para solicitar un cambio, [abra un problema con el cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que haga referencia a los atributos cuyo tipo debe cambiar de cadena a numérico.

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles, incluidos el ID, el nombre, el mensaje, la categoría, etc.

   ![Detalles de un elemento de catálogo que muestra su identificador, categorías, margen y otros atributos](../assets/catalog_search_2.png)

1. Para quitar el elemento del catálogo, haga clic en **[!UICONTROL Quitar del catálogo]**.

   Toda la información sobre ese elemento se elimina del índice del catálogo. El elemento se vuelve a incluir en el catálogo solo si se vuelve a añadir en una fuente de datos. Un elemento eliminado también debe eliminarse de forma independiente de las fuentes.

   ![Detalles de un elemento de catálogo con el botón Quitar del catálogo resaltado](../assets/catalog_search_3.png)

<!--
### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.
-->

<!--
## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.
-->



<!--
## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.
-->
