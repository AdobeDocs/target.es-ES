---
keywords: secuencia de criterios;varios criterios;algoritmos;criterios;criterios de recomendaciones;secuencia;número límite de elementos devueltos;control de nivel de ranura;ranura
description: Aprenda a definir secuencias de hasta cinco criterios para ejercer un mayor control sobre los elementos que aparecen en las actividades de Recommendations.
title: ¿Cómo se crean secuencias de criterios en Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
TQID: 'https://experienceleague.adobe.com/dxO5cKxesTxgzZyfcvydQUlSq4TAgFN0ztT5VIe1WKU'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 8%
---
# Crear secuencias de criterios {#create-criteria-sequence}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear secuencias de criterios para controlar los elementos que aparecen en las actividades de [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Las secuencias de hasta cinco criterios proporcionan un mayor control sobre los elementos que aparecen en las actividades [!DNL Adobe Target] **[!UICONTROL Recommendations]**. El número de elementos devueltos también puede ser limitado (a veces denominado &quot;control de nivel de ranura&quot;).

Cuando un criterio no devuelve resultados suficientes para rellenar el diseño, una secuencia de criterios proporciona recomendaciones de objetivo adicionales en lugar de recomendaciones de copia de seguridad más genéricas. Normalmente, una secuencia de criterios pasa de un objetivo más específico, que podría devolver menos resultados, a un objetivo más general, que generalmente devuelve más resultados.

>[!NOTE]
>
>Las secuencias de criterios no se pueden usar con las actividades **[!UICONTROL Recommendations]** creadas antes de la versión de octubre de 2016 de [!DNL Target Premium].

Para crear una secuencia de criterios, primero cree los criterios que desea incluir en la secuencia. Consulte [Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) para obtener más información.

El orden de una secuencia de criterios puede variar según el tipo de página, como se muestra en los ejemplos siguientes:

| Tipo de página | Orden de secuencia posible |
| --- | --- |
| Página de productos | <ol><li>En función del artículo actual, de la misma marca</li><li>Basado en el elemento actual, para todas las marcas</li><li>Basado en similitudes de contenido</li><li>Basado en los productos más vendidos</li><li>Basado en los elementos más visitados en todo el sitio</li></ol> |
| Página de inicio | <ol><li>Basado en la última compra del visitante </li><li>Basado en el elemento favorito del visitante</li><li>Basado en la categoría favorita del visitante</li><li>Basado en los productos más vendidos</li><li>Basado en lo más visitado en todo el sitio</li></ol> |

## Crear una secuencia de criterios

Las secuencias de criterios se crean desde la pantalla **[!UICONTROL Crear secuencia de criterios]**. Hay varias formas de llegar a esta pantalla. Algunas opciones de pantalla varían según la forma en que se alcance la pantalla.

* En la pantalla de la biblioteca **[!UICONTROL Recomendaciones]** > **[!UICONTROL Criterios]**, haga clic en **[!UICONTROL Crear criterio]** > **[!UICONTROL Crear secuencia de criterios]**. Los criterios creados aquí quedan disponibles automáticamente para todas las actividades de **[!UICONTROL Recommendations]**.
* Al crear una actividad **[!UICONTROL Recommendations]**, en la pantalla **[!UICONTROL Seleccionar criterios]**, haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. La nueva secuencia de criterios se puede guardar para usarla con otras actividades de **[!UICONTROL Recommendations]**.
* Al editar una actividad de **[!UICONTROL Recommendations]**, haga clic en un cuadro de **[!UICONTROL Ubicación de Recommendations]** de la página y, a continuación, seleccione **[!UICONTROL Cambiar criterios]**. En la pantalla **[!UICONTROL Seleccionar criterios]**, haga clic en **[!UICONTROL Crear nuevo]** > **[!UICONTROL Crear secuencia de criterios]**. Los nuevos criterios se pueden guardar para usarlos con otras actividades de **[!UICONTROL Recommendations]**.

Los siguientes pasos suponen que se accede a la pantalla **[!UICONTROL Crear secuencia de criterios]** desde el menú **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Criterios]**.

1. Haga clic en **[!UICONTROL Crear criterios]** > **[!UICONTROL Crear secuencia de criterios]**.

   ![Página de criterios con la opción Crear secuencia de criterios seleccionada en el menú Crear criterios](../assets/criteria_create_6.png)

1. Rellene la información de la sección [Información básica](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. En la sección **[!UICONTROL Secuencia de criterios]**, haga clic en el signo Más ( + ) para agregar una o más secuencias de criterios.

   El orden de secuencia define el orden en el que se rellena un diseño. Si el criterio 1 no tiene suficientes recomendaciones para rellenar el diseño, las ranuras restantes se rellenan con el criterio 2, y así sucesivamente.

   ![Sección Secuencia de criterios del cuadro de diálogo Crear secuencia de criterios con cinco campos de criterios y el signo más de Criterios 1 seleccionado](../assets/criteria_create_7.png)

1. En la pantalla **[!UICONTROL Seleccionar criterios]**, seleccione un criterio y haga clic en **[!UICONTROL Guardar]**.

   El cuadro **[!UICONTROL Buscar]** y la opción de filtro se pueden usar para encontrar los criterios deseados.

1. (Opcional) Habilite **[!UICONTROL Limitar el número de elementos devueltos]** y después especifique el número de elementos (entre 1 y 50).

   ![Sección de secuencia de criterios con Recomendado para usted como criterio 1 y la opción Limitar el número de elementos devueltos activada](../assets/criteria_create_8.png)

   Los siguientes casos de uso ilustran el valor de la opción **[!UICONTROL Limit the number of items returned]** (a veces denominada &quot;control de nivel de ranura&quot;).

   +++ Casos de uso para limitar el número de elementos devueltos

   * **Caso de uso 1**: Una mezcla de diferentes tipos de artículos en una sola bandeja de recomendaciones, por ejemplo, una mezcla de ropa exterior (chaquetas) y tops (camisas, camisetas). Para conseguirlo, utilice una colección para la actividad que incluya todos los tipos de productos que pueden aparecer en cualquier ranura del diseño. A continuación, configure el primer criterio con un filtro estático que incluya solo ropa de abrigo y el segundo criterio con un filtro estático que incluya solo tops. Finalmente, agregue ambos criterios a una secuencia de criterios y limite los primeros criterios a 2 ranuras.

     La bandeja de recomendaciones puede tener este aspecto en un sitio:

     ![Bandeja de recomendaciones de productos destacados](assets/featured-products.png)

   * **Caso de uso 2**: una combinación de elementos alternativos y complementarios. Configure un criterio para utilizar un algoritmo visualizado/visualizado y un filtro dinámico que limite los elementos recomendados a la categoría del elemento actual. Configure el segundo criterio para utilizar un algoritmo visto/comprado y un filtro dinámico que incluya solo los artículos recomendados que no coincidan con la categoría del artículo actual. Finalmente, agregue ambos criterios a una secuencia y limite los primeros criterios a 2 ranuras.

   +++

1. Siga agregando criterios a la secuencia. Se pueden añadir hasta cinco criterios a una secuencia.

1. Habilitar [opciones de contenido de copia de seguridad](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Haga clic en **[!UICONTROL Crear]**.

La secuencia de criterios se muestra en la lista **[!UICONTROL Criterios]**.

Para obtener más información acerca de las opciones de lógica de recomendación, vea [Introducción a los criterios](/help/main/c-recommendations/c-algorithms/algorithms.md).
