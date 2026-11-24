---
keywords: exclusiones
description: Aprenda a crear exclusiones en [!DNL Target Recommendations] para evitar que los productos o el contenido se recomienden a los visitantes.
title: ¿Cómo utilizo exclusiones en actividades de [!UICONTROL Recommendations]?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: 'https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o'
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%
---
# Exclusiones {#exclusions}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear y administrar exclusiones en [!DNL Adobe Target Recommendations] para evitar que los productos o el contenido se recomienden a los visitantes.

>[!ENDSHADEBOX]

Una exclusión es un subconjunto de productos o contenido que no debe recomendarse a los visitantes. Las exclusiones están disponibles en toda la cuenta. A diferencia de las colecciones, que se seleccionan para cada experiencia cuando se crea una actividad [!DNL Recommendations], las exclusiones se aplican a todas las actividades de la cuenta y no se puede asignar ningún grupo de exclusión durante la creación de la actividad.

Las exclusiones se utilizan generalmente para:

* Productos que se han suspendido.
* Elementos de un catálogo que ya no está disponible. Por ejemplo, cuando solo el catálogo de otoño e invierno debe estar presente en línea, cualquier artículo del catálogo de verano no se puede comprar.
* Artículos que pueden ser inadecuados para recomendar en la mayoría de las páginas o pantallas (productos para adultos, películas NC-17, etc.).
* Productos con campos de metadatos incompletos (faltan miniaturas, precios u otros metadatos importantes).
* Productos que nunca se deben recomendar, como un SKU que existe en el sistema pero que no se puede comprar, o un SKU falso que el equipo de control de calidad utiliza para simular una compra sin pedir nada.

>[!IMPORTANT]
>
>Las reglas de exclusión se aplican globalmente a todos los [entornos](/help/main/administrating-target/environments.md).
>
>Para obtener información detallada, ejemplos y casos de uso sobre las reglas de exclusión estáticas y dinámicas, consulte [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).

## Creación de una exclusión

Las reglas de exclusión se definen una vez y luego se aplican a cada actividad [!DNL Recommendations] de la cuenta.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusiones]** para mostrar la lista de exclusiones existentes.

   >[!NOTE]
   >
   >El &quot;Número de elementos&quot; registrado para cada exclusión en la vista de lista de **[!UICONTROL Exclusiones]** es el número de productos que coinciden con las reglas para esa exclusión en el grupo de hosts [configurado como predeterminado en Recommendations](/help/main/administrating-target/hosts.md) (entorno). Consulte [Planificar e implementar [!DNL Recommendations]](https://experienceleague.adobe.com/es/docs/target-dev/developer/recommendations){target=_blank} en la *Guía para desarrolladores de Adobe Target* para obtener información sobre cómo cambiar el grupo de hosts predeterminado.


1. Haga clic en el icono **[!UICONTROL Mostrar filtros]** ( ![Mostrar filtros](/help/main/assets/icons/Filter.svg) ) y, a continuación, elija el [entorno](/help/main/administrating-target/environments.md) que desee en la lista desplegable **[!UICONTROL Entorno]** para obtener una vista previa del contenido de la exclusión en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Página de exclusiones con el panel de filtros abierto y la lista de entornos](../assets/exclusions_2.png)

1. Haga clic en **[!UICONTROL Crear exclusión]**.

   ![Página de exclusiones con el botón Crear exclusión](../assets/exclusions_1.png)

1. Escriba una exclusión **[!UICONTROL Name]**. También se puede introducir una descripción opcional.

1. Utilice el generador de reglas para definir la exclusión.

   Seleccione un parámetro en la lista **[!UICONTROL Reglas]**, seleccione un operador y, a continuación, introduzca uno o varios valores para identificar los productos. Separe los distintos valores con comas.

1. Haga clic en **[!UICONTROL Crear]**.

1. Haga clic en el icono Más acciones ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a la exclusión deseada en la lista y, a continuación, haga clic en la opción adecuada: **[!UICONTROL Editar]**, **[!UICONTROL Copiar]** o **[!UICONTROL Eliminar]**.

   ![Lista de exclusiones con el menú Más acciones abierto, que muestra Editar, Copiar y Eliminar](../assets/exclusions_3.png)

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->


## Vídeo de formación: Crear colecciones y exclusiones en Recommendations (7:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/27689)
