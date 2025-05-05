---
keywords: exclusiones
description: Aprenda a crear exclusiones en el Adobe  [!DNL Target] Recommendations para evitar que se recomienden productos o contenido a los visitantes.
title: ¿Cómo utilizo las exclusiones en las actividades de Recommendations?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 28%

---

# Exclusiones

Cree una exclusión en [!DNL Adobe Target Recommendations] para evitar que los productos o el contenido se recomienden a los visitantes. Una exclusión es un subconjunto de productos o contenido que no debe recomendarse a los visitantes.

Las exclusiones están disponibles en toda la cuenta. A diferencia de las colecciones, donde especifica una colección específica para cada experiencia al crear una actividad [!UICONTROL Recommendations], las exclusiones se aplican a todas las actividades de la cuenta. No hay ninguna opción para asignar un grupo de exclusión durante la creación de la actividad.

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

1. Haga clic en **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** para mostrar la lista de exclusiones existentes.

   ![imagen exclusions_list](assets/exclusions_list.png)

   El &quot;Número de elementos&quot; registrado para cada exclusión en la vista de lista [!UICONTROL Exclusions] es el número de productos que coinciden con las reglas para esa exclusión en el grupo de hosts [2&rbrace; (entorno) de Recommendations predeterminado configurado. ](/help/main/administrating-target/hosts.md) Consulte [Configuración](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=es){target=_blank} para cambiar el grupo de hosts predeterminado.

1. Haga clic en **[!UICONTROL Create Exclusion]**.

1. (Condicional) Elija un entorno del filtro **[!UICONTROL Environment]** mientras crea (o actualiza) una exclusión para obtener una vista previa del contenido de la exclusión en ese entorno. De forma predeterminada, se muestran los resultados del grupo de hosts predeterminado.

   ![Crear exclusión](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. Escriba una exclusión **[!UICONTROL Name]** e introduzca una descripción opcional.

1. Utilice el generador de reglas para crear las exclusiones.

   Seleccione un parámetro en la lista reglas, elija un operador y luego escriba uno o varios valores para identificar los productos. Separe los distintos valores con comas.

1. Haga clic en **[!UICONTROL Save]**.

## Cree una exclusión con Búsqueda avanzada

También puede crear exclusiones usando [!UICONTROL Advanced Search] en la página [Búsqueda en el catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Guardar como cuadro de diálogo](/help/main/c-recommendations/c-products/assets/save-as.png)

Después de crear una búsqueda utilizando &quot;id > contiene&quot;, por ejemplo, puede hacer clic en [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>La funcionalidad [!UICONTROL Advanced Search] no distingue entre mayúsculas y minúsculas; sin embargo, los productos devueltos en el momento de la entrega se basan en la búsqueda que distingue entre mayúsculas y minúsculas. Esta diferencia puede llevar a confusiones. Asegúrese de tener en cuenta las mayúsculas y minúsculas al crear exclusiones basadas en resultados que utilizan la funcionalidad Búsqueda avanzada. Por ejemplo, si busca “Vacaciones”, obtendrá resultados que contienen “Vacaciones” y “vacaciones”. Si a continuación crea una exclusión con la intención de excluir productos que contengan “vacaciones”, solo se excluirán los productos que contienen “vacaciones”, pero no los productos que contengan “Vacaciones”.

## Editar, copiar o eliminar una exclusión

Pase el ratón sobre la exclusión que quiera en la lista y luego haga clic en el icono correspondiente: editar, copiar o eliminar.

![Iconos de desplazamiento para una exclusión](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

Puede copiar una exclusión existente para crear una exclusión duplicada que luego puede modificar. Esto permite crear una exclusión similar con menos esfuerzo.

Tenga en cuenta que las exclusiones están disponibles en toda la cuenta. Asegúrese de tener esto en cuenta antes de eliminar una exclusión. Las exclusiones eliminadas no se pueden recuperar.

## Vídeo de formación: Creación de colecciones y exclusiones en Recommendations (7:05) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene la información siguiente:

* Creación de una colección
* Creación de una exclusión

>[!VIDEO](https://video.tv.adobe.com/v/35463?captions=spa)
