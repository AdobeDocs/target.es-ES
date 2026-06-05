---
keywords: colección;Segmentación
description: Aprenda a utilizar colecciones de productos o elementos en  [!DNL Target Recommendations].
title: ¿Cómo utilizo las colecciones en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 755
ht-degree: 27%

---

# Colecciones

Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación. Una colección se define especificando las condiciones que deben cumplir los elementos para formar parte de ella.

Normalmente, una colección es un conjunto de artículos similares o relacionados, como una única colección de productos. Sin embargo, puede agrupar cualquier artículo en una categoría que tenga sentido para su negocio, como los productos de un determinado rango de precios o color o los artículos que pueden ser interesantes en una determinada área geográfica.

Utilice las colecciones para organizar sus productos en bloques lógicos. Por ejemplo, si algunos elementos están disponibles en una región pero no en otra, puede crear una colección que excluya los elementos que no están disponibles en la región del visitante. También puede usar las colecciones para organizar los artículos por temporadas, o cualquier otro parámetro de organización que sea útil para su negocio.

Las [recomendaciones de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md) generadas para cada criterio dentro de la recomendación también usan esta colección, por lo que en la recomendación de copia de seguridad solo se incluyen los elementos de la colección. Con las colecciones, tendrá la garantía de que solo se mostrarán aquellos productos que tenga sentido mostrar en una ubicación.

Las colecciones se vuelven a generar o se actualizan cada vez que se ejecuta un criterio.

Los artículos se pueden agrupar en catálogos y después crear recomendaciones independientes para cada colección.

Los criterios de inclusión permiten realizar cosas parecidas a las de una colección, pero deben configurarse cada vez que crea una actividad. Las colecciones permiten crear un conjunto de elementos una vez y, a continuación, utilizarlo siempre que sea adecuado sin tener que volver a configurarlo.

Al crear o editar una actividad [!DNL Recommendations], el nombre de la colección aparece junto a la etiqueta [!UICONTROL Criterios] en el diagrama de actividades.

>[!NOTE]
>
>* Las reglas de recopilación se aplican a los artículos de recomendación generados después de ejecutar los criterios. Solo afectan a las recomendaciones de entidad (ER) en la salida, no a la clave.
>
>* Las colecciones no se aplican al usar la clave de recomendación [!UICONTROL Artículos vistos recientemente].

## Crear una colección {#task_1256DFF6842141FCAADD9E1428EF7F08}

Cree una colección para organizar los productos o el contenido que desea mostrar en las recomendaciones.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Colecciones]** para mostrar la lista de colecciones existentes.

   La página [!UICONTROL Colecciones] muestra una lista de las colecciones existentes. Para crear colecciones nuevas, haga clic en el botón [!UICONTROL Crear colección]. También puede editar, copiar y eliminar colecciones existentes si hace clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) que se encuentra junto a la colección deseada y, a continuación, hace clic en la opción que desee.

   El &quot;Número de elementos&quot; registrado para cada colección en la vista de lista de [!UICONTROL Colecciones] es el número de productos que coinciden con las reglas para esa colección en el grupo de hosts [configurado como predeterminado en Recommendations](/help/main/administrating-target/hosts.md) (entorno). Para cambiar el grupo de hosts predeterminado, consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

1. Haga clic en **[!UICONTROL Crear colección]**.

1. Escriba un **[!UICONTROL Nombre]** para la colección.

   También puede escribir una **[!UICONTROL Descripción]** opcional.

1. (Condicional) Elija un [entorno](/help/main/administrating-target/environments.md) del filtro **[!UICONTROL Entorno]** mientras crea (o actualiza) una colección para obtener una vista previa del contenido de la colección en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

1. Defina las reglas que se usarán para compilar la colección.

   Por ejemplo, la colección se puede crear en función de un ID de producto, una categoría, un margen o cualquier otro parámetro de la lista.

   Puede añadir reglas para usar varios parámetros para definir una colección. Las reglas múltiples se unen con un operador AND. Todas las reglas especificadas deben coincidir con la colección que se va a aplicar.

1. Haga clic en **[!UICONTROL Crear]**.

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## Editar, copiar o eliminar una colección

Haga clic en el ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a la colección deseada en la lista y, a continuación, haga clic en el icono apropiado: [!UICONTROL Editar], [!UICONTROL Copiar] o [!DNL Delete].

Puede copiar una colección existente para crear una colección duplicada que luego puede modificar. Esto permite crear una colección similar con menos esfuerzo.

Tenga en cuenta que las colecciones están disponibles en toda la cuenta. Asegúrese de tenerlo en cuenta antes de eliminar una colección. Las colecciones eliminadas no se pueden recuperar.

## Usar una colección en una actividad [!DNL Recommendations]

1. Cree una colección utilizando uno de los métodos mencionados anteriormente.

1. Haga clic en **[!UICONTROL Actividades]** y [cree una nueva actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) o edite una actividad existente.

1. Después de seleccionar un criterio y un diseño, se muestra la página [!UICONTROL Opciones] en la que se selecciona la colección deseada.

1. (Condicional) Para cambiar una configuración de colección existente, en la página **[!UICONTROL Experiencias]** (paso 1 del flujo de trabajo guiado de tres partes), haga clic en una ubicación en la que haya colocado recomendaciones, haga clic en **[!UICONTROL Cambiar colección]** y, a continuación, seleccione la colección que desee.
