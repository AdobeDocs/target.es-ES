---
keywords: exclusions
description: Cree una lista de exclusión en Adobe Target para impedir que se recomienden determinados artículos.
title: Exclusiones en Adobe Target
feature: entities
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 421168f34bffe1f5f90d90f4af9b28940d0b8010
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 83%

---


# Exclusiones{#exclusions}

Cree una exclusión en [!DNL Adobe Target Recommendations] para evitar que los productos o el contenido se recomienden a los visitantes.

Una exclusión es un subconjunto de productos o contenido que no debe recomendarse a sus visitantes. Por ejemplo, puede utilizar exclusiones para evitar que los productos o el contenido se muestren en recomendaciones que se han interrumpido o que son de naturaleza delicada (como películas con una clasificación no adecuada para todas las edades).

>[!IMPORTANT]
>
>Las reglas de exclusión estáticas y dinámicas son funciones potentes que pueden ayudarle en sus estrategias de marketing. Para obtener información detallada, ejemplos y casos de uso, consulte [Uso de reglas de inclusión dinámicas y estáticas](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Creación de una exclusión

1. Haga clic en **[!UICONTROL Recomendaciones]** > **[!UICONTROL Exclusiones]** para visualizar la lista de exclusiones existentes.

   ![](assets/exclusions_list.png)

   El “Número de elementos” registrado para cada exclusión en la vista de la lista [!UICONTROL Exclusiones] es el número de productos que coinciden con las reglas para esa exclusión en el [grupo de hosts](/help/administrating-target/hosts.md) (entorno) configurado como predeterminado en Recommendations. Para cambiar el grupo de hosts predeterminado, consulte [Configuración](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

1. Haga clic en **[!UICONTROL Crear exclusión]**.

1. (Condicional) Elija un entorno del filtro **[!UICONTROL Entorno]** mientras crea (o actualiza) una exclusión para obtener una vista previa del contenido de la exclusión en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Crear exclusión](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Escriba un **[!UICONTROL Nombre]** de exclusión e introduzca una descripción opcional.

1. Utilice el generador de reglas para crear las exclusiones.

   Seleccione un parámetro en la lista reglas, elija un operador y luego escriba uno o varios valores para identificar los productos. Separe los distintos valores con comas.

1. Haga clic en **[!UICONTROL Guardar]**.

## Cree una exclusión con Búsqueda avanzada

También puede crear exclusiones utilizando Búsqueda avanzada en la página Buscar en el catálogo ([!UICONTROL Recommendations] > [!UICONTROL Buscar en el catálogo] > [!UICONTROL Búsqueda avanzada]).

![Guardar como](/help/c-recommendations/c-products/assets/save-as-dialog.png)

Después de crear una búsqueda utilizando “id > contiene”, por ejemplo, puede hacer clic en [!UICONTROL Guardar como] > [!UICONTROL Exclusión]. Para obtener más información, consulte [Búsqueda en catálogo](/help/c-recommendations/c-products/catalog-search.md#save-as).

>[!IMPORTANT]
>
>La función Búsqueda avanzada diferencia entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que diferencia entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear exclusiones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea una exclusión con la intención de excluir productos que contengan “vacaciones”, solo se excluirán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”.

## Vídeo de formación: Creación de colecciones y exclusiones en Recommendations (7:05) ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/27689)