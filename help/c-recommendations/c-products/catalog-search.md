---
description: La búsqueda en el catálogo permite encontrar los productos o el contenido en su catálogo.
keywords: catálogo;buscar
seo-description: La búsqueda de catálogos en Adobe Target le ayuda a localizar los productos o el contenido en el catálogo.
seo-title: Búsqueda de catálogos en Adobe Target
solution: Target
title: Búsqueda en el catálogo
title-outputclass: premium
topic: Premium
uuid: e0876963-5905-4850-a615-953e435f26e9
badge: premium
translation-type: tm+mt
source-git-commit: afb87e3e23b44133982e55fdc7650250e6bf8b3a

---


# ![PREMIUM](/help/assets/premium.png) Búsqueda en el catálogo{#catalog-search}

La búsqueda en el catálogo permite encontrar los productos o el contenido en su catálogo.

Para obtener acceso a la búsqueda de catálogos, haga clic en **[!UICONTROL Recomendaciones]** &gt; Búsqueda **[!UICONTROL de catálogos]**.

Puede restringir la búsqueda: seleccione una opción de búsqueda en el menú de opciones que se muestra al hacer clic en la flecha abajo del campo de búsqueda.

![](assets/searchproductsmenu.png)

Las opciones de búsqueda incluyen lo siguiente:

* ALL
* Nombre
* Marca
* Categoría
* ID
* Mensaje

**[!UICONTROL TODO]** indica todas las búsquedas en todos los demás criterios de búsqueda usando la lógica OR.

En los resultados de búsqueda, haga clic en **[!UICONTROL Entorno]** para especificar el entorno del grupo de hosts de producción cuyo catálogo se está mostrando. [](/help/administrating-target/hosts.md) También puede desplazarse por los artículos en los resultados de búsqueda para ver las miniaturas y otra información del producto.

El número que se muestra junto a “Productos” es el número de productos que coincide con el término de búsqueda, con respecto al total disponible en el entorno especificado.

El catálogo se actualiza automáticamente cuando se reciben actualizaciones a través de archivos de fuentes, API o actualizaciones de mbox. Las actualizaciones suelen completarse en una hora. Si las actualizaciones están en curso, se muestra el tiempo en que se inició la actualización más reciente. Si no hay actualizaciones en curso, se muestra el tiempo en que se inició y finalizó la actualización más reciente.

## Crear una colección o exclusión basada en la búsqueda avanzada

You can create [collections](/help/c-recommendations/c-products/collections.md) or [exclusions](/help/c-recommendations/c-products/exclusions.md) using Advanced Search on the Catalog Search page ([!UICONTROL Recommendations] &gt; [!UICONTROL Catalog Search] &gt; [!UICONTROL Advanced Search]).

![Guardar como](/help/c-recommendations/c-products/assets/save-as.png)

Después de crear una búsqueda utilizando “id &gt; contiene”, por ejemplo, puede hacer clic en [!UICONTROL Guardar como] &gt; [!UICONTROL Colección o Exclusión].

>[!IMPORTANT]
>
>La función Búsqueda avanzada diferencia entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que diferencia entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear colecciones o exclusiones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”. Las exclusiones se gestionan de forma similar.
