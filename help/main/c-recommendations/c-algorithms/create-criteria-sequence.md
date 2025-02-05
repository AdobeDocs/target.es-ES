---
keywords: secuencia de criterios;varios criterios;algoritmos;criterios;criterios de recomendaciones;secuencia;número límite de elementos devueltos;control de nivel de ranura;ranura
description: Aprenda a definir secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de Recommendations.
title: ¿Cómo se crean secuencias de criterios en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 18%

---

# Crear secuencias de criterios

Utilice secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de [!DNL Adobe Target] [!UICONTROL Recommendations]. También puede limitar el número de elementos devueltos (a veces denominado &quot;control de nivel de ranura&quot;).

>[!NOTE]
>
>Las secuencias de criterios no se pueden usar con [!UICONTROL Recommendations] actividades creadas antes de la versión de octubre de 2016 de [!DNL Target Premium].

Para crear una secuencia de criterios, debe crear primero los criterios que desea incluir en la secuencia. Consulte [Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) para obtener más información.

Si utiliza una secuencia de criterios, puede ofrecer recomendaciones personalizadas adicionales, en lugar de utilizar más recomendaciones secundarias genéricas, cuando un criterio no obtenga suficientes resultados para llenar el diseño. Normalmente, una secuencia de criterios pasa de un objetivo más específico, que podría devolver menos resultados, a un objetivo más general, que generalmente devuelve más resultados.

Las secuencias de criterios pueden variar en orden según el tipo de página, como se muestra en los ejemplos siguientes:

| Tipo de página | Orden de secuencia posible |
| --- | --- |
| Página de productos | <ol><li>En función del artículo actual, de la misma marca</li><li>Basado en el elemento actual, para todas las marcas</li><li>Basado en similitudes de contenido</li><li>Basado en los productos más vendidos</li><li>Basado en los elementos más visitados en todo el sitio</li></ol> |
| Página de inicio | <ol><li>Basado en la última compra del visitante </li><li>Basado en el elemento favorito del visitante</li><li>Basado en la categoría favorita del visitante</li><li>Basado en los productos más vendidos</li><li>Basado en lo más visitado en todo el sitio</li></ol> |

## Crear una secuencia de criterios

Puede crear secuencias de criterios desde la pantalla [!UICONTROL Create Criteria Sequence].

Existen varias formas de llegar a la pantalla [!UICONTROL Create Criteria Sequence]. Algunas opciones de pantalla dependen de cómo llega a la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Los criterios que crea aquí quedan disponibles automáticamente para todas las actividades de [!UICONTROL Recommendations].
* Cuando esté creando una actividad [!UICONTROL Recommendations], en la pantalla [!UICONTROL Select Criteria], haga clic en **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Tiene la opción de guardar la nueva secuencia de criterios para usarla con otras [!UICONTROL Recommendations] actividades.
* Cuando esté editando una actividad [!UICONTROL Recommendations], haga clic en un cuadro [!UICONTROL Recommendations Location] de la página y seleccione **[!UICONTROL Change Criteria]**. En la pantalla [!UICONTROL Select Criteria], haga clic en **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Tiene la opción de guardar los nuevos criterios para usarlos con otras [!UICONTROL Recommendations] actividades.

Los siguientes pasos dan por sentado que tiene acceso a la pantalla de [!UICONTROL Create Criteria Sequence] mediante el primer método: la pantalla de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Haga clic en **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

1. Rellene la información de la sección [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección **[!UICONTROL Criteria Sequence]**, haga clic en el signo Más ( + ) para agregar una o más secuencias de criterios.

   El orden de secuencia define el orden en el que se rellena un diseño. Si Criterios 1 no tiene suficientes recomendaciones para llenar su diseño, las ranuras restantes se llenan con Criterios 2, y así sucesivamente.

1. En la pantalla [!UICONTROL Select Criteria], seleccione un criterio y luego haga clic en **[!UICONTROL Save]**.

   Puede utilizar el cuadro [!UICONTROL Search] y la opción de filtro para encontrar los criterios deseados.

1. (Opcional) Deslice el conmutador **[!UICONTROL Limit the number of items returned]** a la posición &quot;Activado&quot; y, a continuación, especifique el número de elementos (entre 1 y 50).

   Para ayudarle a comprender el valor de la opción [!UICONTROL Limit the number of items returned] (a veces denominada &quot;control de nivel de ranura&quot;), considere los siguientes casos de uso:

   * **Caso de uso 1**: desea tener una combinación de diferentes tipos de elementos en una sola bandeja de recomendaciones. Por ejemplo, desea mostrar una mezcla de ropa exterior (chaquetas) y tops (camisas, camisetas). Para conseguirlo, utilice una colección para la actividad que incluya todos los tipos de productos potenciales que desee en cualquier ranura del diseño. A continuación, configure el primer criterio con un filtro estático que limite los criterios para incluir solo ropa exterior y configure el segundo criterio con un filtro estático que limite los criterios para incluir solo tops. Finalmente, agregue ambos criterios a una secuencia de criterios y limite los primeros criterios a 2 ranuras.

     La bandeja de recomendaciones puede tener este aspecto en el sitio:

     ![Bandeja de recomendaciones de productos destacados](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: desea una combinación de elementos alternativos y complementarios. Defina un criterio para utilizar un algoritmo de visualizado/visualizado y un filtro dinámico que limite los elementos recomendados a la categoría del elemento actual. Configure el segundo criterio para utilizar un algoritmo de artículos vistos o comprados y utilice un filtro dinámico que incluya solo artículos recomendados que no coincidan con la categoría del artículo actual. Finalmente, agregue ambos criterios a una secuencia y limite los primeros criterios a 2 ranuras.

1. Siga agregando criterios adicionales a la secuencia. Puede agregar hasta cinco criterios en una secuencia.

1. Habilitar [opciones de contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Haga clic en **[!UICONTROL Create]**.

   La secuencia de criterios se muestra en la lista [!UICONTROL Criteria].

   Para obtener más información sobre opciones de lógica de recomendación, consulte [Criterios](/help/main/c-recommendations/c-algorithms/algorithms.md).
