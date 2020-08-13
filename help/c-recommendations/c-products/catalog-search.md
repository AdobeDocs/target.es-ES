---
keywords: catalog;search
description: La búsqueda de catálogo en Adobe Target permite encontrar los productos o el contenido en su catálogo.
title: Buscar en el catálogo en Adobe Target
feature: catalog
uuid: e0876963-5905-4850-a615-953e435f26e9
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 96%

---


# ![PREMIUM](/help/assets/premium.png) Búsqueda en el catálogo{#catalog-search}

La búsqueda en el catálogo permite encontrar los productos o el contenido en su catálogo.

To access catalog search, click **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

Puede restringir la búsqueda: seleccione una opción de búsqueda en el menú de opciones que se muestra al hacer clic en la flecha abajo del campo de búsqueda.

![](assets/searchproductsmenu.png)

Las opciones de búsqueda son las siguientes:

* TODOS
* Nombre
* Marca
* Categoría
* ID
* Mensaje

**[!UICONTROL TODO]** indica todas las búsquedas en todos los demás criterios de búsqueda usando la lógica OR.

En los resultados de búsqueda, haga clic en **[!UICONTROL Entorno]** para especificar el entorno del grupo de hosts de producción cuyo catálogo se está mostrando. [](/help/administrating-target/hosts.md) También puede desplazarse por los artículos en los resultados de búsqueda para ver las miniaturas y otra información del producto.

El número que se muestra junto a “Productos” es el número de productos que coincide con el término de búsqueda, con respecto al total disponible en el entorno especificado.

El catálogo se actualiza automáticamente cuando se reciben actualizaciones mediante archivos de fuentes, API o actualizaciones de mbox. Las actualizaciones se suelen completar en una hora. Si las actualizaciones están en curso, se muestra la hora en la que se inició la más reciente. Si no hay actualizaciones en curso, se muestra la hora de inicio y finalización de la más reciente.

## Crear una colección o exclusión basada en la Búsqueda avanzada

Puede crear [colecciones](/help/c-recommendations/c-products/collections.md) o [exclusiones](/help/c-recommendations/c-products/exclusions.md) con Búsqueda avanzada en la página Búsqueda en el catálogo ([!UICONTROL Recommendations] > [!UICONTROL Búsqueda en el catálogo] > [!UICONTROL Búsqueda avanzada]).

![Guardar como cuadro de diálogo](/help/c-recommendations/c-products/assets/save-as-dialog.png)

Después de crear una búsqueda utilizando “id > contiene”, por ejemplo, puede hacer clic en [!UICONTROL Guardar como] > [!UICONTROL Colección o Exclusión].

>[!IMPORTANT]
>
>La función Búsqueda avanzada diferencia entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que diferencia entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear colecciones o exclusiones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”. Las exclusiones se gestionan de forma similar.
