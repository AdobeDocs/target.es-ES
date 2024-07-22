---
keywords: búsqueda en el catálogo;catálogo;búsqueda;exclusión;colección;filtro
description: Aprenda a utilizar la búsqueda en el catálogo de Recommendations para localizar productos o contenido, crear colecciones o exclusiones, eliminar elementos del catálogo y mucho más.
title: ¿Cómo utilizo la búsqueda en el catálogo de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 22%

---

# Buscar en el catálogo

La página [!UICONTROL Catalog Search] de [!DNL Adobe Recommendations] le ayuda a localizar los productos o el contenido en su catálogo. La tarea más básica que puede realizar en esta página es buscar un elemento. Además, puede cambiar el entorno, guardar los resultados de búsqueda en colecciones o exclusiones, agregar facetas de filtro, modificar columnas en la tabla, agregar nuevas facetas de búsqueda y mucho más.

Los catálogos hacen referencia a todo el conjunto de productos (entidades). El catálogo puede contener muchas colecciones, una forma de organizar los productos en bloques lógicos.

## Búsqueda en el catálogo de acceso

Para tener acceso a la página [!UICONTROL Catalog Search], haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Página de búsqueda en el catálogo](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Buscar un elemento

Puede utilizar una búsqueda simple o una búsqueda avanzada para localizar elementos en su catálogo.

### Realice una búsqueda sencilla

1. Escriba un término de búsqueda en el campo **[!UICONTROL Search Products]**.

1. (Opcional) Puede restringir la búsqueda seleccionando una opción de búsqueda en el menú de opciones que se muestra al hacer clic en la flecha hacia abajo del campo de búsqueda.

   ![imagen searchproductsmenu](assets/searchproductsmenu.png)

   Las opciones de búsqueda son las siguientes:

   * ALL: busca en todos los demás criterios de búsqueda mediante la lógica OR.
   * Nombre
   * Marca
   * Categoría
   * ID
   * Mensaje

1. Ahora puede desplazarse por los elementos de los resultados de búsqueda para ver miniaturas y otra información del producto.

   La siguiente ilustración muestra los resultados de &quot;bicicleta&quot; con la opción Todos.

   ![Buscar en el catálogo la bicicleta](/help/main/c-recommendations/c-products/assets/bike-results.png)

   El número que se muestra junto a “Productos” es el número de productos que coincide con el término de búsqueda, con respecto al total disponible en el entorno especificado.

   Tenga en cuenta que puede utilizar la funcionalidad de búsqueda autocompletada. En la siguiente ilustración, al escribir &quot;bicicleta&quot; se devuelven todos los productos que contienen la palabra &quot;bicicleta&quot;.

   ![Autocompletar búsqueda](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Cuando se realiza una búsqueda en el catálogo de un atributo personalizado con un valor numérico, los resultados tratan al atributo personalizado como un tipo de cadena en lugar de un valor numérico.
   >
   >Actualmente, no hay ninguna funcionalidad disponible que permita cambiar el tipo de un atributo. Para realizar un cambio, [abra un problema con el cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que haga referencia a los atributos cuyo tipo necesitan que cambie de cadena a numérico.

1. También puede utilizar filtros para encontrar el producto deseado. En el ejemplo siguiente, expandiendo la faceta [!UICONTROL Collections] y seleccionando &quot;Herramientas para bicicletas&quot;, se muestran todas las herramientas para bicicletas del catálogo.

   ![Herramientas para bicicletas](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Puede buscar más en la lista de resultados introduciendo un término de búsqueda, por ejemplo &quot;cadena&quot;.

   ![Buscar cadena](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Realizar una búsqueda avanzada {#advanced-search}

Puede usar [!UICONTROL Advanced Search] para restringir aún más los resultados de búsqueda o para guardar los resultados de búsqueda como [colección](/help/main/c-recommendations/c-products/collections.md) o [exclusión](/help/main/c-recommendations/c-products/exclusions.md).

1. Haga clic en el vínculo **[!UICONTROL Advanced Search]**.

   ![Página de búsqueda avanzada](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Utilice las listas desplegables para especificar el parámetro, el operador y los valores para la búsqueda.

1. (Opcional) Haga clic en **[!UICONTROL Add Rule]** para agregar una regla de búsqueda adicional.

   Cada regla de búsqueda adicional se une con el operador AND.

1. Haga clic en **[!UICONTROL Search]**.

1. (Opcional) Haga clic en **[!UICONTROL Save As]** y luego haga clic en **[!UICONTROL Collection]** o **[!UICONTROL Exclusion]**.

   ![Guardar como opciones](/help/main/c-recommendations/c-products/assets/save-as.png)

   Para obtener más información, consulte [Crear una colección o exclusión basada en la búsqueda avanzada](#save-as) a continuación.

## Ver los detalles de un elemento

Puede ver los detalles de un elemento individual, incluidos el ID, el nombre, el mensaje, la categoría, etc., consultando sus detalles.

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

   ![Detalles del producto](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Eliminar un elemento del catálogo

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

1. Haga clic en **[!UICONTROL Remove from Catalog]**.

1. Confirme que desea quitar el elemento.

Toda la información sobre ese elemento se elimina del índice del catálogo. El elemento se incluirá en el catálogo solo si se vuelve a añadir en una fuente de datos. Un elemento eliminado debe eliminarse por separado de las fuentes.

## Actualizar el catálogo

El índice del catálogo se crea automáticamente al cargar la primera fuente y se actualiza según la [programación especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

El catálogo se actualiza automáticamente cuando se reciben actualizaciones mediante archivos de fuentes, API o actualizaciones de mbox. Las actualizaciones se suelen completar en una hora. Si las actualizaciones están en curso, se muestra la hora en la que se inició la más reciente. Si no hay actualizaciones en curso, se muestra la hora de inicio y finalización de la más reciente.

## Crear una colección o exclusión basada en la Búsqueda avanzada {#save-as}

Puede crear [colecciones](/help/main/c-recommendations/c-products/collections.md) o [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) utilizando [!UICONTROL Advanced Search] en la página [!UICONTROL Catalog Search] ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Realice una [búsqueda avanzada](#advanced-search).

1. Haga clic en **[!UICONTROL Save As]** y luego en **[!UICONTROL Collection]** o **[!UICONTROL Exclusion]**.

   ![Guardar como opciones](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >La funcionalidad [!UICONTROL Advanced Search] no distingue entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que distingue entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta la distinción entre mayúsculas y minúsculas al crear colecciones o exclusiones basadas en resultados que utilicen la funcionalidad [!UICONTROL Advanced Search]. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”. Las exclusiones se gestionan de forma similar.

## Cambiar el entorno

Los [entornos](/help/main/administrating-target/environments.md) le permiten organizar sus sitios y entornos de preproducción para facilitar la administración y la generación de informes individuales.

1. Haga clic en el vínculo Entorno.

   ![Vínculo de entorno](/help/main/c-recommendations/c-products/assets/environment.png)

1. Seleccione el entorno que desee.

## Modificación de la página Buscar en el catálogo (filtros y columnas)

Puede modificar temporalmente los filtros y las columnas disponibles en la página [!UICONTROL Catalog Search] para la sesión actual.

### Modificación de filtros

Puede agregar facetas de filtro adicionales a la página [!UICONTROL Catalog Search].

1. En el panel **[!UICONTROL Filters]**, haga clic en **[!UICONTROL Modify]**.

   ![Modificar vínculo de filtros](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Seleccione las facetas de búsqueda que desee (ID, nombre, mensaje, etc.) y haga clic en **[!UICONTROL Save]**.

   ![Agregar filtros](/help/main/c-recommendations/c-products/assets/add-filters.png)

Tenga en cuenta que las facetas de filtro adicionales solo están disponibles en la sesión actual.

### Modificar columnas

Puede modificar temporalmente las columnas activas en la página [!UICONTROL Catalog Search].

1. Haga clic en el vínculo **[!UICONTROL Columns]**.

   ![Opciones de columnas](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Condicional) Para reordenar el orden de las columnas activas, arrastre y suelte las columnas de la sección **[!UICONTROL Active Columns]** en el orden deseado.

1. (Condicional) Arrastre y suelte los elementos de **[!UICONTROL Active Columns]** en **[!UICONTROL Inactive Columns]** (y viceversa) según sus preferencias.

   También puede hacer clic en el icono Eliminar ( x ) junto a la columna que desea mover de la sección activa a inactiva.

Tenga en cuenta que cualquier cambio que realice se aplicará únicamente a la sesión actual.
