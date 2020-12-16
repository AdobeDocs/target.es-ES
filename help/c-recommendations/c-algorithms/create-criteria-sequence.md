---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;limit number of items returned;slot level control;slot
description: Utilice secuencias de hasta cinco criterios para ejercer el bueno control de los elementos que aparecen en las actividades de Adobe Target Recommendations.
title: Crear secuencias de criterios
feature: criteria
translation-type: tm+mt
source-git-commit: 4b9ff10ff01ea3bf4fc1be165b220d4975e1f948
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 35%

---


# ![PREMIUM](/help/assets/premium.png) Creación de secuencias de criterios

Utilice secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de [!UICONTROL Recomendaciones. ] También puede limitar el número de elementos devueltos (a veces denominado &quot;control de nivel de ranura&quot;).

>[!NOTE]
>
>Las secuencias de criterios no se pueden usar con las actividades de [!UICONTROL Recommendations] creadas antes de la versión de octubre de 2016 de [!DNL Target Premium].

Para crear una secuencia de criterios, debe crear primero los criterios que desea incluir en la secuencia. Consulte [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) para obtener más información.

Si utiliza una secuencia de criterios, puede ofrecer recomendaciones personalizadas adicionales, en lugar de utilizar más recomendaciones secundarias genéricas, cuando un criterio no obtenga suficientes resultados para llenar el diseño. Normalmente, una secuencia de criterios pasa de un objetivo más específico, que puede devolver menos resultados, a un objetivo más general, que generalmente devuelve más resultados.

Las secuencias de criterios pueden variar según el tipo de página, como se muestra en los siguientes ejemplos:

| Tipo de página | Posible orden de secuencia |
| --- | --- |
| Página de productos | <ol><li>Basado en el elemento actual, para la misma marca</li><li>Basado en el elemento actual, para todas las marcas</li><li>Basado en similitudes de contenido</li><li>Basado en los productos más vendidos</li><li>Basado en los elementos más visitados en todo el sitio</li></ol> |
| Página de inicio | <ol><li>Basado en la última compra del visitante </li><li>Basado en el elemento favorito del visitante</li><li>Basado en la categoría favorita del visitante</li><li>Basado en los productos más vendidos</li><li>Basado en lo más visitado en todo el sitio</li></ol> |

## Creación de una secuencia de criterios

Puede crear secuencias de criterios desde la pantalla [!UICONTROL Crear secuencia de criterios].

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear secuencia de criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recomendaciones]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear secuencia de criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!UICONTROL Recommendations].
* Cuando esté creando una actividad [!UICONTROL Recommendations], en la pantalla Seleccionar criterios, haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Tendrá la opción de guardar la nueva secuencia de criterios para usarla con otras actividades de [!UICONTROL Recommendations].
* Cuando esté editando una actividad [!UICONTROL Recommendations], haga clic en un cuadro [!UICONTROL Ubicación de Recommendations] de la página y, a continuación, seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!UICONTROL Recommendations].

Los pasos siguientes suponen que accede a la pantalla [!UICONTROL Crear secuencia de criterios] mediante el primer método: la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear secuencia de criterios]**.

   ![](assets/CreateCriteriaSequence.png)

1. Rellene la información de la sección [Información básica](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección **[!UICONTROL Secuencia de criterios]**, haga clic en **[!UICONTROL Añadir criterios]**.

   El orden de secuencia define el orden en que se rellena un diseño. Si el criterio 1 no tiene suficientes recomendaciones para completar el diseño, las ranuras restantes se rellenarán con el criterio 2, etc.

   ![Añadir criterios](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. En la pantalla [!UICONTROL Seleccionar criterios], seleccione un criterio y haga clic en **[!UICONTROL Añadir]**.

   Puede utilizar el cuadro de búsqueda y las listas desplegables de filtros para encontrar los criterios deseados.

   ![Seleccionar criterios](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Opcional) Deslice el **[!UICONTROL Limitar el número de elementos devueltos]** para cambiar a la posición &quot;on&quot; y luego especifique el número de elementos (entre 1 y 50).

   ![Limitar el número de elementos devueltos al alternador](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Para ayudarle a comprender el valor de la opción [!UICONTROL Limitar el número de elementos devueltos] (a veces denominada &quot;control de nivel de ranura&quot;), considere los siguientes casos de uso:

   * **Caso de uso 1**: Desea tener una mezcla de diferentes tipos de artículos en una única bandeja de recomendaciones. Por ejemplo, desea mostrar una combinación de ropa exterior (chaquetas) y camisetas (camisas, camisetas). Para conseguirlo, utilice una colección para la actividad que incluya todos los tipos de productos potenciales que desee en cualquier espacio del diseño. A continuación, configure su primer criterio con un filtro estático que limite los criterios para incluir solo el uso externo y configure su segundo criterio con un filtro estático que limite los criterios para incluir únicamente los elementos superiores. Finalmente, agregue ambos criterios a una secuencia de criterios y limite los primeros criterios a 2 ranuras.

      Es posible que la bandeja de recomendaciones tenga este aspecto en el sitio:

      ![Bandeja de recomendaciones de productos destacados](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: Desea una combinación de elementos alternativos y complementarios. Configure un criterio para utilizar un algoritmo visualizado/visualizado y un filtro dinámico que limite los elementos recomendados a la categoría del elemento actual. Configure el segundo criterio para utilizar un algoritmo visto/comprado y un filtro dinámico que incluya solo los artículos recomendados que no coincidan con la categoría del artículo actual. Finalmente, agregue ambos criterios a una secuencia y limite los primeros criterios a 2 ranuras.

1. Continúe agregando criterios adicionales a la secuencia. Puede agregar hasta cinco criterios en una secuencia.

1. Habilite [opciones de Contenido de copia de seguridad](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Haga clic en **[!UICONTROL Guardar]**.

   La secuencia de criterios se mostrará en la lista de criterios.

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](/help/c-recommendations/c-algorithms/algorithms.md).

## Vídeo de formación: Crear criterios en Recommendations (12:33)  ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
