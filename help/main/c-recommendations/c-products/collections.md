---
keywords: colección;Segmentación
description: Aprenda a utilizar colecciones de productos o elementos en [!DNL Target Recommendations].
title: ¿Cómo utilizo las colecciones en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: 'https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o'
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
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 8%
---
# Colecciones {#collections}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear, administrar y usar colecciones de elementos en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Una colección es un conjunto de productos o artículos que cumplen los criterios para ser mostrados como recomendación. Una colección se define mediante las condiciones que deben cumplir los elementos para formar parte de ella. Los artículos pueden agruparse de cualquier manera que tenga sentido para el negocio, como artículos similares o relacionados, productos en un determinado rango de precios o color, o artículos que pueden ser interesantes en una zona geográfica en particular.

Las colecciones organizan los productos en bloques lógicos. Por ejemplo, si algunos elementos están disponibles en una región pero no en otra, una colección puede excluir los elementos que no están disponibles en la región del visitante. Las colecciones también pueden organizar artículos de temporada o cualquier otro parámetro de organización que se aplique al negocio. Los elementos se pueden agrupar en catálogos y, a continuación, se pueden crear recomendaciones independientes para cada colección.

Los siguientes puntos describen cómo interactúan las colecciones con el resto de [!DNL Recommendations]:

* Las [recomendaciones de copia de seguridad](/help/main/c-recommendations/c-algorithms/backup-recs.md) generadas para cada criterio también utilizan la colección, por lo que en la recomendación de copia de seguridad solo se incluyen los elementos de la colección. Como resultado, solo se muestran los productos que tienen sentido para una ubicación.
* Las colecciones se vuelven a generar o se actualizan cada vez que se ejecuta un criterio.
* Las reglas de recopilación se aplican a los artículos de recomendación generados después de ejecutar los criterios. Solo afectan a las recomendaciones de entidad (ER) en la salida, no a la clave.
* Las colecciones no se aplican al usar la clave de recomendación **[!UICONTROL Artículos vistos recientemente]**.
* Los criterios de inclusión pueden producir resultados similares, pero deben configurarse cada vez que se crea una actividad. Una colección se crea una vez y se puede reutilizar sin volver a configurarla.
* Cuando se crea o edita una actividad [!DNL Recommendations], el nombre de la colección aparece junto a la etiqueta **[!UICONTROL Criterios]** en el diagrama de actividad.

## Creación de una colección {#task_1256DFF6842141FCAADD9E1428EF7F08}

Las colecciones están disponibles en toda la cuenta, por lo que se puede seleccionar una colección que se cree una vez en cualquier actividad [!DNL Recommendations]. Las reglas se definen en la colección, por lo que no es necesario volver a configurarlas para cada actividad.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Colecciones]** para mostrar la lista de colecciones existentes.

   Para editar, copiar o eliminar una colección existente, haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a la colección y, a continuación, haga clic en la opción que desee.

   >[!NOTE]
   >
   >El &quot;Número de elementos&quot; registrado para cada colección en la vista de lista de **[!UICONTROL Colecciones]** es el número de productos que coinciden con las reglas para esa colección en el grupo de hosts [configurado como predeterminado en Recommendations](/help/main/administrating-target/hosts.md) (entorno). Para cambiar el grupo de hosts predeterminado, consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

1. Haga clic en **[!UICONTROL Crear colección]**.

   ![Página de colecciones con el botón Crear colección](../assets/collection_1.png)

1. Escriba un **[!UICONTROL Nombre]** para la colección. También se puede escribir una **[!UICONTROL descripción]** opcional.

1. (Condicional) Elija un [entorno](/help/main/administrating-target/environments.md) del filtro **[!UICONTROL Entorno]** para obtener una vista previa del contenido de la colección en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

1. Defina las reglas que se usarán para compilar la colección.

   Se puede crear una colección en torno a un ID de producto, categoría, margen o cualquier otro parámetro de la lista. Agregue reglas para utilizar varios parámetros para definir una colección. Las reglas múltiples se unen con un operador AND, por lo que todas las reglas especificadas deben coincidir para que se aplique la colección.

1. Haga clic en **[!UICONTROL Crear]**.

1. Una vez creada la colección, haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) y seleccione la opción adecuada: **[!UICONTROL Editar]**, **[!UICONTROL Copiar]** o **[!UICONTROL Eliminar]**.

   ![Lista de colecciones con el menú Más acciones abierto, que muestra Editar, Copiar y Eliminar](../assets/collection_2.png)

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## Uso de una colección en una actividad

Se selecciona una colección para cada experiencia de una actividad [!DNL Recommendations]. La colección determina qué artículos cumplen los requisitos para aparecer en las recomendaciones de esa experiencia.

1. [Crear una colección](#task_1256DFF6842141FCAADD9E1428EF7F08).

   ![Crear pantalla de colección con las secciones Detalles de colección y Reglas](../assets/collection_3.png)

1. Haga clic en **[!UICONTROL Actividades]** y [cree una nueva actividad de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) o edite una actividad existente.

   ![Página Todas las actividades con Recommendations seleccionado en el menú Crear actividad](../assets/collection_4.png)

1. Después de seleccionar un criterio y un diseño, seleccione la colección que desee en la página **[!UICONTROL Options]**.

1. (Condicional) Para cambiar la colección de una actividad existente, haga clic en una ubicación de Recommendations en las páginas de **[!UICONTROL Experiencias]**, haga clic en **[!UICONTROL Cambiar colección]** y seleccione la colección que desee.
