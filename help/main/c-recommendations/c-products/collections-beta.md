---
keywords: colección;Segmentación
description: Aprenda a utilizar colecciones de productos o artículos en [!DNL Target Recommendations].
title: ¿Cómo utilizo las colecciones en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 29%

---

# Colecciones

Una colección es un conjunto de productos o artículos que cumplen los requisitos para ser mostrados como recomendación. Una colección se define especificando las condiciones que deben cumplir los elementos para formar parte de ella.

Normalmente, una colección es un conjunto de artículos similares o relacionados, como una única colección de productos. Sin embargo, puede agrupar cualquier artículo en una categoría que tenga sentido para su negocio, como los productos de un determinado rango de precios o color o los artículos que pueden ser interesantes en una determinada área geográfica.

Utilice las colecciones para organizar sus productos en bloques lógicos. Por ejemplo, si algunos elementos están disponibles en una región pero no en otra, puede crear una colección que excluya los elementos que no están disponibles en la región del visitante. También puede usar las colecciones para organizar los artículos por temporadas, o cualquier otro parámetro de organización que sea útil para su negocio.

[Recomendaciones de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md) los artículos generados para cada criterio dentro de la recomendación también utilizan esta colección, por lo que solo los artículos de la recomendación de copia de seguridad se incluyen en ella. Con las colecciones, tendrá la garantía de que solo se mostrarán aquellos productos que tenga sentido mostrar en una ubicación.

Las colecciones se vuelven a generar o se actualizan cada vez que se ejecuta un criterio.

Los artículos se pueden agrupar en catálogos y después crear recomendaciones independientes para cada colección.

Los criterios de inclusión permiten realizar cosas parecidas a las de una colección, pero deben configurarse cada vez que crea una actividad. Las colecciones permiten crear un conjunto de elementos una vez y, a continuación, utilizarlo siempre que sea adecuado sin tener que volver a configurarlo.

Al crear o editar un [!DNL Recommendations] actividad, el nombre de la colección aparece junto a la variable [!UICONTROL Criteria] en el diagrama de actividad.

>[!NOTE]
>
>Las colecciones no se aplican al utilizar [!UICONTROL Recently Viewed Items] clave de recomendación.

## Crear una colección {#task_1256DFF6842141FCAADD9E1428EF7F08}

Cree una colección para organizar los productos o el contenido que desea mostrar en las recomendaciones.

1. Clic **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** para mostrar la lista de colecciones existentes.

   ![Lista de colecciones](assets/collections-list.png)

   El [!UICONTROL Collections] Esta página muestra una lista de las colecciones existentes. Para crear colecciones nuevas, haga clic en [!UICONTROL Create Collection] botón. También puede editar, copiar y eliminar colecciones existentes haciendo clic en el icono de puntos suspensivos situado junto a la colección deseada y, a continuación, haciendo clic en la opción deseada.

   El &quot;Número de elementos&quot; registrado para cada colección en la [!UICONTROL Collections] la vista de lista es el número de productos que coinciden con las reglas para esa colección en el Recommendations predeterminado configurado [grupo de hosts](/help/main/administrating-target/hosts.md) (entorno). Consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} para cambiar el grupo de hosts predeterminado.

1. Haga clic en **[!UICONTROL Create Collection]**.

   ![Crear una colección](/help/main/c-recommendations/c-products/assets/create-collection.png)

1. Escriba un **[!UICONTROL Name]** para la colección.

   También puede introducir un **[!UICONTROL Description]**.

1. (Condicional) Elija un [entorno](/help/main/administrating-target/environments.md) desde el **[!UICONTROL Environment]** filtre mientras crea (o actualiza) una colección para obtener una vista previa del contenido de la colección en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

1. Defina las reglas que se usarán para compilar la colección.

   Por ejemplo, la colección se puede crear en función de un ID de producto, una categoría, un margen o cualquier otro parámetro de la lista.

   Puede añadir reglas para usar varios parámetros para definir una colección. Las reglas múltiples se unen con un operador AND. Todas las reglas especificadas deben coincidir con la colección que se va a aplicar.

1. Haga clic en **[!UICONTROL Create]**.

## Crear una colección utilizando [!UICONTROL Advanced Search]

También puede crear colecciones utilizando [!UICONTROL Advanced Search] en el [Búsqueda en catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) página ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Guardar como cuadro de diálogo](/help/main/c-recommendations/c-products/assets/save-as.png)

Después de crear una búsqueda utilizando &quot;id > contiene&quot;, por ejemplo, puede hacer clic en [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>El [!UICONTROL Advanced Search] no distingue entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que distingue entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta la distinción entre mayúsculas y minúsculas al crear colecciones basadas en resultados mediante [!UICONTROL Advanced Search] funcionalidad. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea un catálogo con la intención de obtener productos que contengan “vacaciones”, solo se devolverán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”.

## Editar, copiar o eliminar una colección

Haga clic en **elipsis** junto a la colección que desee en la lista y, a continuación, haga clic en el icono correspondiente: editar, copiar o eliminar.

![Iconos de desplazamiento: editar, copiar y eliminar](/help/main/c-recommendations/c-products/assets/hover-icons-new.png)

Puede copiar una colección existente para crear una colección duplicada que luego puede modificar. Esto permite crear una exclusión similar con menos esfuerzo.

Tenga en cuenta que las colecciones están disponibles en toda la cuenta. Asegúrese de tenerlo en cuenta antes de eliminar una colección. Las colecciones eliminadas no se pueden recuperar.

## Uso de una colección en una [!DNL Recommendations] actividad

1. Cree una colección utilizando uno de los métodos mencionados anteriormente.

1. Clic **[!UICONTROL Activities]** y [crear un nuevo Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) actividad o editar una actividad existente.

1. Después de seleccionar un criterio y un diseño, la variable [!UICONTROL Options] La página se muestra donde se selecciona la colección deseada.

   ![Elegir opción de colección](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Condicional) Para cambiar una configuración de colección existente, en la variable **[!UICONTROL Experiences]** página (paso 2 del flujo de trabajo guiado de tres partes), haga clic en una ubicación donde haya colocado recomendaciones y haga clic en **[!UICONTROL Change Collection]** y, a continuación, seleccione la colección deseada.

   ![Opción Cambiar colección](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vídeo de formación: Creación de colecciones y exclusiones en Recommendations (7:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/27689)