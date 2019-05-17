---
description: Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación.
keywords: colección;Segmentación
seo-description: Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación.
seo-title: Colecciones
solution: Target
title: Colecciones
title-outputclass: premium
topic: Premium
uuid: aa1afdcf-e51c-4e44-a229-3c21fc9d0514
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Colecciones{#collections}

Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación.

## Colecciones {#concept_671BEFFB997D4F1282665BF3CAC00AC5}

Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación.

Normalmente, una colección es un conjunto de artículos similares o relacionados, como una única colección de productos. Sin embargo, puede agrupar cualquier artículo en una categoría que tenga sentido para su negocio, como los productos de un determinado color o rango de precios, o los artículos que pueden resultar interesantes en una determinada área geográfica. 

Utilice las colecciones para organizar sus productos en bloques lógicos. Por ejemplo, si algunos artículos están disponibles en una región pero no en otra, puede crear una colección que excluya los artículos que no están disponibles en la región del visitante. También puede usar las colecciones para organizar los artículos por temporadas, o cualquier otro parámetro de organización que sea útil para su negocio.

Las recomendaciones de copia de seguridad generadas para cada criterio dentro de la recomendación también utilizan esta colección. Por eso, en la recomendación de copia de seguridad solo se incluyen los artículos de la recomendación. Con las colecciones, tendrá la garantía de que solo se mostrarán aquellos productos que tenga sentido mostrar en una ubicación.

Las colecciones se vuelven a generar o se actualizan cada vez que se ejecuta un criterio.

Los artículos se pueden agrupar en catálogos y después crear recomendaciones independientes para cada colección.

Los criterios de inclusión permiten realizar cosas parecidas a las de una colección, pero deben configurarse cada vez que crea una actividad. Las colecciones permiten crear un conjunto de artículos de una sola vez, y luego usarla cada vez que resulte apropiado, sin tener que volver a configurarlas.

Al crear o editar una actividad de [!DNL Recommendations], el nombre de la colección aparece junto a la etiqueta [!UICONTROL Criterios] en el diagrama de actividades.

>[!NOTE]
>
>Las colecciones no se aplican al utilizar la clave de recomendación [!UICONTROL Artículos vistos recientemente].

## Creación de una colección {#task_1256DFF6842141FCAADD9E1428EF7F08}

Puede crear una colección para organizar los productos que quiere mostrar en sus recomendaciones.

1. Haga clic en **[!UICONTROL Recommendations]** &gt; **[!UICONTROL Colecciones]** para visualizar la lista de colecciones existentes.

   El “Número de elementos” registrado para cada colección en la vista de la lista [!UICONTROL Colecciones] es el número de productos que coinciden con las reglas para esa colección en el [grupo de hosts](/help/administrating-target/hosts.md) (entorno) configurado como predeterminado en Recommendations. Para cambiar el grupo de hosts predeterminado, consulte [Configuración](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

   ![](assets/collections_list.png)

1. Haga clic en **[!UICONTROL Crear colección]**.

1. (Condicional) Elija un entorno del filtro **[!UICONTROL Entorno]** mientras crea (o actualiza) una colección para obtener una vista previa del contenido de dicha colección en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Crear una colección](/help/c-recommendations/c-products/assets/CreateCollection.png)

1. Introduzca un **[!UICONTROL Nombre]** para la colección.

   También puede escribir una **[!UICONTROL Descripción opcional]**.

1. Defina las reglas que se usarán para compilar la colección. 

   Por ejemplo, la colección se puede crear en función de un ID de producto, una categoría, un margen o cualquier otro parámetro de la lista.

   Puede añadir reglas para usar varios parámetros para definir una colección. Si hay varias reglas, debe unirlas mediante AND. Todas las reglas especificadas deben coincidir con la colección que se va a aplicar.

1. Haga clic en **[!UICONTROL Guardar]**.
También puede crear colecciones utilizando Búsqueda avanzada en la página Buscar en el catálogo ([!UICONTROL Recommendations] &gt; [!UICONTROL Buscar en el catálogo] &gt; [!UICONTROL Búsqueda avanzada]). Después de crear una búsqueda utilizando “id &gt; contiene”, por ejemplo, puede hacer clic en [!UICONTROL Guardar como] &gt; [!UICONTROL Colección].

>[!IMPORTANT]
>
>La función Búsqueda avanzada diferencia entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que diferencia entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear colecciones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”. 