---
keywords: búsqueda en el catálogo;catálogo;búsqueda;exclusión;colección;filtro
description: Aprenda a utilizar la búsqueda en el catálogo de Recommendations para localizar productos o contenido, crear colecciones o exclusiones, eliminar elementos del catálogo y mucho más.
title: ¿Cómo utilizo la búsqueda en el catálogo de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# Buscar en el catálogo

El [!UICONTROL Búsqueda en catálogo] página en [!DNL Adobe Recommendations] le ayuda a localizar los productos o el contenido en su catálogo. La tarea más básica que puede realizar en esta página es buscar un elemento. Además, puede cambiar el entorno, guardar los resultados de búsqueda en colecciones o exclusiones, agregar facetas de filtro, modificar columnas en la tabla, agregar nuevas facetas de búsqueda y mucho más.

Los catálogos hacen referencia a todo el conjunto de productos (entidades). El catálogo puede contener muchas colecciones, una forma de organizar los productos en bloques lógicos.

## Búsqueda en el catálogo de acceso

Para acceder a [!UICONTROL Búsqueda en catálogo] página, haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Búsqueda en catálogo]**.

![Página Buscar en el catálogo](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Buscar un elemento

Puede utilizar una búsqueda simple o una búsqueda avanzada para localizar elementos en su catálogo.

### Realice una búsqueda sencilla

1. Escriba un término de búsqueda en **[!UICONTROL Buscar productos]** field.

1. (Opcional) Puede restringir la búsqueda seleccionando una opción de búsqueda en el menú de opciones que se muestra al hacer clic en la flecha hacia abajo del campo de búsqueda.

   ![imagen searchproductsmenu](assets/searchproductsmenu.png)

   Las opciones de búsqueda son las siguientes:

   * TODOS - Busca en todos los demás criterios de búsqueda, usando la lógica OR.
   * Nombre
   * Marca
   * Categoría
   * ID
   * Mensaje

1. Ahora puede desplazarse por los elementos de los resultados de búsqueda para ver miniaturas y otra información del producto.

   La siguiente ilustración muestra los resultados de &quot;bicicleta&quot; con la opción Todos.

   ![Catálogo Búsqueda de bicicletas](/help/main/c-recommendations/c-products/assets/bike-results.png)

   El número que se muestra junto a “Productos” es el número de productos que coincide con el término de búsqueda, con respecto al total disponible en el entorno especificado.

   Tenga en cuenta que puede utilizar la funcionalidad de búsqueda autocompletada. En la siguiente ilustración, al escribir &quot;bicicleta&quot; se devuelven todos los productos que contienen la palabra &quot;bicicleta&quot;.

   ![Buscar autocompletar](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Cuando se realiza una búsqueda en el catálogo de un atributo personalizado con un valor numérico, los resultados tratan al atributo personalizado como un tipo de cadena en lugar de un valor numérico.
   >
   >Actualmente, no hay ninguna funcionalidad disponible que permita cambiar el tipo de un atributo. Para realizar un cambio, [abra un problema con el cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que haga referencia a los atributos cuyo tipo necesitan que cambie de cadena a numérico.

1. También puede utilizar filtros para encontrar el producto deseado. En el ejemplo siguiente, expandiendo el [!UICONTROL Colecciones] y seleccionando &quot;Bike Tools&quot;, se muestran todas las herramientas de su catálogo.

   ![Herramientas para bicicleta](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Puede buscar más en la lista de resultados introduciendo un término de búsqueda, por ejemplo &quot;cadena&quot;.

   ![Buscar cadena](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Realizar una búsqueda avanzada {#advanced-search}

Puede utilizar [!UICONTROL Búsqueda avanzada] para restringir aún más los resultados de búsqueda o para guardar los resultados de búsqueda como [colección](/help/main/c-recommendations/c-products/collections.md) o [exclusión](/help/main/c-recommendations/c-products/exclusions.md).

1. Haga clic en **[!UICONTROL Búsqueda avanzada]** vínculo.

   ![Página Búsqueda avanzada](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Utilice las listas desplegables para especificar el parámetro, el operador y los valores para la búsqueda.

1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** para agregar una regla de búsqueda adicional.

   Cada regla de búsqueda adicional se une con el operador AND.

1. Haga clic en **[!UICONTROL Buscar]**.

1. (Opcional) Haga clic en **[!UICONTROL Guardar como]**, luego haga clic en **[!UICONTROL Colección]** o **[!UICONTROL Exclusión]**.

   ![Guardar como opciones](/help/main/c-recommendations/c-products/assets/save-as.png)

   Para obtener más información, consulte [Crear una colección o exclusión basada en la búsqueda avanzada](#save-as) más abajo.

## Ver los detalles de un elemento

Puede ver los detalles de un elemento individual, incluidos el ID, el nombre, el mensaje, la categoría, etc., consultando sus detalles.

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

   ![Detalles del producto](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Eliminar un elemento del catálogo

1. Haga clic en un elemento de los resultados de búsqueda para ver sus detalles.

1. Clic **[!UICONTROL Eliminar del catálogo]**.

1. Confirme que desea quitar el elemento.

Toda la información sobre ese elemento se elimina del índice del catálogo. El elemento se incluirá en el catálogo solo si se vuelve a añadir en una fuente de datos. Un elemento eliminado debe eliminarse por separado de las fuentes.

## Actualizar el catálogo

El índice del catálogo se crea automáticamente al cargar la primera fuente y se actualiza según las [programación especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

El catálogo se actualiza automáticamente cuando se reciben actualizaciones mediante archivos de fuentes, API o actualizaciones de mbox. Las actualizaciones se suelen completar en una hora. Si las actualizaciones están en curso, se muestra la hora en la que se inició la más reciente. Si no hay actualizaciones en curso, se muestra la hora de inicio y finalización de la más reciente.

## Crear una colección o exclusión basada en la Búsqueda avanzada {#save-as}

Puede crear [colecciones](/help/main/c-recommendations/c-products/collections.md) o [exclusiones](/help/main/c-recommendations/c-products/exclusions.md) con Búsqueda avanzada en la página Búsqueda en el catálogo ([!UICONTROL Recommendations] > [!UICONTROL Búsqueda en el catálogo] > [!UICONTROL Búsqueda avanzada]).

1. Realización de una [búsqueda avanzada](#advanced-search).

1. Clic **[!UICONTROL Guardar como]**, luego haga clic en **[!UICONTROL Colección]** o **[!UICONTROL Exclusión]**.

   ![Guardar como opciones](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >El [!UICONTROL Búsqueda avanzada] no distingue entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que distingue entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta la distinción entre mayúsculas y minúsculas al crear colecciones o exclusiones basadas en resultados mediante [!UICONTROL Búsqueda avanzada] funcionalidad. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”. Las exclusiones se gestionan de forma similar.

## Cambiar el entorno

[Entornos](/help/main/administrating-target/environments.md) le permite organizar sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

1. Haga clic en el vínculo Entorno.

   ![Vínculo de entorno](/help/main/c-recommendations/c-products/assets/environment.png)

1. Seleccione el entorno que desee.

## Modificación de la página Buscar en el catálogo (filtros y columnas)

Puede modificar temporalmente los filtros y las columnas disponibles en la [!UICONTROL Búsqueda en catálogo] para la sesión actual.

### Modificación de filtros

Puede añadir facetas de filtro adicionales a la variable [!UICONTROL Búsqueda en catálogo] página.

1. En el **[!UICONTROL Filtros]** , haga clic en **[!UICONTROL Modificar]**.

   ![Modificar vínculo de filtros](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Seleccione las facetas de búsqueda que desee (ID, nombre, mensaje, etc.) y haga clic en **[!UICONTROL Guardar]**.

   ![Añadir filtros](/help/main/c-recommendations/c-products/assets/add-filters.png)

Tenga en cuenta que las facetas de filtro adicionales solo están disponibles en la sesión actual.

### Modificar columnas

Puede modificar temporalmente las columnas activas en [!UICONTROL Búsqueda en catálogo] página.

1. Haga clic en **[!UICONTROL Columnas]** vínculo.

   ![Opciones de columnas](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Condicional) Para reordenar el orden de las columnas activas, arrastre y suelte las columnas en la **[!UICONTROL Columnas activas]** en el orden deseado.

1. (Condicional) Arrastre y suelte elementos del **[!UICONTROL Columnas activas]** a la **[!UICONTROL Columnas inactivas]** (y viceversa), como se desee.

   También puede hacer clic en el icono Eliminar ( x ) junto a la columna que desea mover de la sección activa a inactiva.

Tenga en cuenta que cualquier cambio que realice se aplicará únicamente a la sesión actual.
