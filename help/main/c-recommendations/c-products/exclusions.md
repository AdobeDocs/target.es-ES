---
keywords: exclusiones
description: Obtenga información sobre cómo crear exclusiones en Adobe [!DNL Target] Recommendations para evitar que los productos o el contenido se recomienden a los visitantes.
title: ¿Cómo utilizo las exclusiones en las actividades de Recommendations?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 34%

---

# Exclusiones

Creación de una exclusión en [!DNL Adobe Target Recommendations] para evitar que se recomienden productos o contenido a los visitantes. Una exclusión es un subconjunto de productos o contenido que no debe recomendarse a los visitantes.

Las exclusiones están disponibles en toda la cuenta. A diferencia de las colecciones, donde especifica una colección específica para cada experiencia al crear una [!UICONTROL Recommendations] actividad, las exclusiones se aplican a todas las actividades de la cuenta. No hay ninguna opción para asignar un grupo de exclusión durante la creación de la actividad.

A continuación, mostramos algunos ejemplos de uso de exclusiones:

* Productos que se han suspendido
* El catálogo de otoño/invierno es ahora el único catálogo que debería estar presente en línea. Cualquier artículo del catálogo de verano ya no está disponible para adquirir.
* Artículos que pueden ser inadecuados para recomendar en la mayoría de las páginas o pantallas (productos para adultos, películas NC-17, etc.)
* Productos con campos de metadatos incompletos (faltan miniaturas, precios u otros metadatos importantes)
* Productos que nunca se deben recomendar (puede que exista un SKU en el sistema para algo, pero no es un artículo que se pueda comprar, o puede que sea un SKU falso para que el equipo de control de calidad simule una compra sin realmente pedir algo, etc.)

>[!IMPORTANT]
>
>Las reglas de exclusión se aplican globalmente a todos los entornos.
>
>Las reglas de exclusión estáticas y dinámicas son funciones potentes que pueden ayudarle en sus estrategias de marketing. Para obtener información detallada, ejemplos y casos de uso, consulte [Uso de reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Creación de una exclusión

1. Clic **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusiones]** para mostrar la lista de exclusiones existentes.

   ![imagen exclusions_list](assets/exclusions_list.png)

   El “Número de elementos” registrado para cada exclusión en la vista de la lista [!UICONTROL Exclusiones] es el número de productos que coinciden con las reglas para esa exclusión en el [grupo de hosts](/help/main/administrating-target/hosts.md) (entorno) configurado como predeterminado en Recommendations. Consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} para cambiar el grupo de hosts predeterminado.

1. Clic **[!UICONTROL Crear exclusión]**.

1. (Condicional) Elija un entorno de la **[!UICONTROL Entorno]** filtre al crear (o actualizar) una exclusión para previsualizar el contenido de la exclusión en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Crear exclusión](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. Escriba una exclusión **[!UICONTROL Nombre]** e introduzca una descripción opcional.

1. Utilice el generador de reglas para crear las exclusiones.

   Seleccione un parámetro en la lista reglas, elija un operador y luego escriba uno o varios valores para identificar los productos. Separe los distintos valores con comas.

1. Haga clic en **[!UICONTROL Guardar]**.

## Cree una exclusión con Búsqueda avanzada

También puede crear exclusiones utilizando [!UICONTROL Búsqueda avanzada] en el [Búsqueda en catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) página ( [!UICONTROL Recommendations] > [!UICONTROL Búsqueda en catálogo] > [!UICONTROL Búsqueda avanzada]).

![Guardar como cuadro de diálogo](/help/main/c-recommendations/c-products/assets/save-as.png)

Después de crear una búsqueda utilizando “id > contiene”, por ejemplo, puede hacer clic en [!UICONTROL Guardar como] > [!UICONTROL Exclusión].

>[!IMPORTANT]
>
>El [!UICONTROL Búsqueda avanzada] no distingue entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que distingue entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear exclusiones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea una exclusión con la intención de excluir productos que contengan “vacaciones”, solo se excluirán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”.

## Editar, copiar o eliminar una exclusión

Pase el ratón sobre la exclusión que quiera en la lista y luego haga clic en el icono correspondiente: editar, copiar o eliminar.

![Iconos de desplazamiento de una exclusión](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

Puede copiar una exclusión existente para crear una exclusión duplicada que luego puede modificar. Esto permite crear una exclusión similar con menos esfuerzo.

Tenga en cuenta que las exclusiones están disponibles en toda la cuenta. Asegúrese de tener esto en cuenta antes de eliminar una exclusión. Las exclusiones eliminadas no se pueden recuperar.

## Vídeo de formación: Creación de colecciones y exclusiones en Recommendations (7:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/27689)
