---
keywords: secuencia de criterios;varios criterios;algoritmos;criterios;criterios de recomendaciones;secuencia;número límite de elementos devueltos;control de nivel de ranura;ranura
description: Aprenda a configurar secuencias de hasta cinco criterios para ejercer el bueno control sobre los elementos que aparecen en las actividades de Adobe [!DNL Target] Recommendations.
title: ¿Cómo creo secuencias de criterios en Recommendations?
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---

# ![PREMIUM](/help/assets/premium.png) Creación de secuencias de criterios

Utilice secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de [!UICONTROL Recomendaciones. ] También puede limitar el número de elementos devueltos (a veces denominados &quot;control de nivel de ranura&quot;).

>[!NOTE]
>
>Las secuencias de criterios no se pueden usar con las actividades de [!UICONTROL Recommendations] creadas antes de la versión de octubre de 2016 de [!DNL Target Premium].

Para crear una secuencia de criterios, debe crear primero los criterios que desea incluir en la secuencia. Consulte [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) para obtener más información.

Si utiliza una secuencia de criterios, puede ofrecer recomendaciones personalizadas adicionales, en lugar de utilizar más recomendaciones secundarias genéricas, cuando un criterio no obtenga suficientes resultados para llenar el diseño. Normalmente, una secuencia de criterios pasa de una segmentación más específica, que podría devolver menos resultados, a una segmentación más general, que generalmente devuelve más resultados.

Las secuencias de criterios pueden variar en orden dependiendo del tipo de página, como se muestra en los ejemplos siguientes:

| Tipo de página | Posible orden de secuencia |
| --- | --- |
| Página de producto | <ol><li>Basado en el elemento actual, para la misma marca</li><li>Basado en el elemento actual, para todas las marcas</li><li>Basado en similitudes de contenido</li><li>Basado en los productos más vendidos</li><li>Basado en los elementos más visitados en todo el sitio</li></ol> |
| Página principal | <ol><li>Basado en la última compra del visitante </li><li>Basado en el elemento favorito del visitante</li><li>Basado en la categoría favorita del visitante</li><li>Basado en los productos más vendidos</li><li>Basado en lo más visitado en todo el sitio</li></ol> |

## Crear una secuencia de criterios

Las secuencias de criterios se crean desde la pantalla [!UICONTROL Crear secuencia de criterios].

Existen varias maneras de llegar a la pantalla [!UICONTROL Crear secuencia de criterios]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recomendaciones]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear secuencia de criterios]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!UICONTROL Recommendations].
* Cuando esté creando una actividad [!UICONTROL Recommendations], en la pantalla Seleccionar criterios, haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Tendrá la opción de guardar la nueva secuencia de criterios para usarla con otras actividades de [!UICONTROL Recommendations].
* Cuando esté editando una actividad [!UICONTROL Recommendations], haga clic en un cuadro [!UICONTROL Ubicación de Recommendations] de la página y, a continuación, seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla [!UICONTROL Seleccionar criterios], haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Tendrá la opción de guardar los nuevos criterios para usarlos con otras actividades de [!UICONTROL Recommendations].

Los siguientes pasos suponen que accede a la pantalla [!UICONTROL Crear secuencia de criterios] mediante el primer método: la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear secuencia de criterios]**.

   ![](assets/CreateCriteriaSequence.png)

1. Rellene la información de la sección [Información básica](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección **[!UICONTROL Secuencia de criterios]**, haga clic en **[!UICONTROL Agregar criterios]**.

   El orden de la secuencia define el orden en que se rellena el diseño. Si el criterio 1 no tiene suficientes recomendaciones para rellenar el diseño, las ranuras restantes se rellenarán con el criterio 2, etc.

   ![Agregar criterios](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. En la pantalla [!UICONTROL Seleccionar criterios], seleccione un criterio y haga clic en **[!UICONTROL Agregar]**.

   Puede utilizar el cuadro Buscar y los desplegables de filtro para encontrar los criterios deseados.

   ![Seleccionar criterios](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Opcional) Deslice el botón **[!UICONTROL Limit the number of items return]** para colocarlo en la posición &quot;on&quot; y, a continuación, especifique el número de elementos (entre 1 y 50).

   ![Limite el número de elementos devueltos mediante la opción](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Para ayudarle a comprender el valor de la opción [!UICONTROL Limit the number of items return] (a veces denominada &quot;control de nivel de ranura&quot;), considere los siguientes casos de uso:

   * **Caso de uso 1**: Desea tener una mezcla de diferentes tipos de artículos en una sola bandeja de recomendaciones. Por ejemplo, desea mostrar una combinación de ropa exterior (chaquetas) y camisetas (camisas, camisetas). Para conseguirlo, utilice una colección para la actividad que incluya todos los tipos de productos potenciales que desee en cualquier espacio del diseño. A continuación, configure su primer criterio con un filtro estático que limite los criterios para incluir solo el uso externo y configure su segundo criterio con un filtro estático que limite los criterios para incluir solo los superiores. Finalmente, agregue ambos criterios a una secuencia de criterios y limite los primeros criterios a 2 espacios.

      La bandeja de recomendaciones puede tener este aspecto en el sitio:

      ![Bandeja de recomendaciones de productos destacados](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: Desea una combinación de elementos alternativos y complementarios. Configure un criterio para usar un algoritmo visto/visto y un filtro dinámico que limite los artículos recomendados a la categoría del artículo actual. Configure el segundo criterio para utilizar un algoritmo visto/comprado y utilice un filtro dinámico que incluya solo los artículos recomendados que no coincidan con la categoría del artículo actual. Finalmente, agregue ambos criterios a una secuencia y limite los primeros criterios a 2 espacios.

1. Siga agregando criterios adicionales a la secuencia. Puede agregar hasta cinco criterios en una secuencia.

1. Active [Opciones de contenido de copia de seguridad](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Haga clic en **[!UICONTROL Guardar]**.

   La secuencia de criterios se mostrará en la lista de criterios.

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](/help/c-recommendations/c-algorithms/algorithms.md).

## Vídeo de formación: Crear criterios en Recommendations (12:33)  ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Crear criterios
* Crear secuencias de criterios
* Cargar criterios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
