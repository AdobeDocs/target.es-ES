---
keywords: promociones;promociones principales;promociones secundarias;tipo de promociones;lista de elementos;promocionar por atributo;promocionar una colección
description: Aprenda a agregar elementos promocionados y controlar su ubicación en sus diseños de Adobe [!DNL Target] Recommendations. Puede añadir promociones estáticas y dinámicas.
title: ¿Cómo puedo añadir promociones en diseños de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 709
ht-degree: 41%

---

# Agregar promociones

Agregue elementos promocionados y controle su ubicación en sus diseños de [!DNL Adobe Target Recommendations]. Puede añadir promociones estáticas y dinámicas.

>[!IMPORTANT]
>
>Las reglas de exclusión estáticas y dinámicas son funciones potentes que pueden ayudarle en sus estrategias de marketing. Para obtener información detallada, ejemplos y casos de uso, consulte [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Al crear una actividad de [!DNL Recommendations], tiene la opción de incluir elementos promocionados en el diseño de [!DNL Recommendations]. Las promociones se ubican en los espacios libres del diseño y tienen prioridad sobre los resultados de criterios y las recomendaciones de copia de seguridad. Por ejemplo, si su diseño tiene seis espacios y utiliza dos para las promociones, quedarán cuatro espacios disponibles para los elementos recomendados a partir de los criterios.

Las promociones se eliminan de la duplicación de elementos recomendados por los criterios de la actividad, por lo que un elemento dado no aparecerá dos veces en una sola bandeja de recomendaciones.

Puede promocionar elementos concretos del modo habitual o de forma dinámica, así como elementos basados en atributos o colecciones.

![[!UICONTROL Opciones de promoción principal] y [!UICONTROL promoción secundaria] en la interfaz de usuario de [!DNL Target]](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Si utiliza promociones, se cambiarán la estructura y los resultados del CSV. Estos cambios no afectan a ningún proceso externo que utilice el CSV, como el correo electrónico.

1. En la página **[!UICONTROL Opciones]**, haga clic en la opción **[!UICONTROL Promoción principal]** o **[!UICONTROL Promoción secundaria]**.

   La siguiente ilustración muestra la opción [!UICONTROL Promoción principal] en la posición &quot;Activada&quot;.

   ![Agregar opciones de promoción principal](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Puede introducir promociones antes *o* después de los resultados de criterios.

1. Defina el número de espacios del diseño que se utilizarán para los elementos promocionados.

   Puede utilizar hasta 20 espacios en función de su diseño de [!DNL Recommendations]. Todos los espacios que utilice dejarán de estar disponibles para las recomendaciones ofrecidas a partir de sus criterios.

1. Defina una fecha de inicio y una fecha de finalización para los elementos promocionados.

   Si no define una fecha de inicio, la promoción se inicia inmediatamente. Si no define una fecha de finalización, la promoción se ejecuta indefinidamente.

1. Seleccione un **[!UICONTROL tipo de promoción]**.

   * Seleccione **[!UICONTROL Lista de elementos]** e introduzca los valores de `entity.id`, separados por comas, de los elementos específicos que desea promocionar.

   * Seleccione **[!UICONTROL Promocionar por atributo]** y agregue reglas para definir los atributos de los elementos que desea promocionar.

     Si selecciona [!UICONTROL Promocionar por atributo], puede crear coincidencias dinámicas. Para obtener más información, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Seleccione **[!UICONTROL Promocionar una colección]** y elija la colección de elementos que desea promocionar.

     Puede crear nuevas colecciones para utilizarlas en las promociones. Consulte [Crear una colección](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obtener más información.

   Si elige **[!UICONTROL Lista de elementos]** como **[!UICONTROL Tipo de promoción]**, puede activar la casilla de verificación **[!UICONTROL Ordenar elementos de forma aleatoria]**, si lo desea.

   El criterio de ordenación predeterminado de [!UICONTROL Lista de elementos] se basa en el orden especificado en la interfaz de usuario o la API de [!DNL Target]. Si la lista incluye más elementos que el número de espacios establecido para las promociones, la opción [!UICONTROL Ordenar elementos de forma aleatoria] asignará al azar los elementos promocionados que se muestran en el diseño. Elegir esta opción hace que [!DNL Target] seleccione aleatoriamente los elementos habilitados para las promociones en la plantilla de todo el conjunto de promociones en cada visita.

   Si las entidades no tienen un atributo `entity.value` (por ejemplo, no vende productos), puede pasar un valor numérico al atributo `entity.value`, como la fecha de publicación. En este caso, los elementos promocionados se pueden promocionar en función de la fecha de publicación más reciente, en orden descendente. El atributo `entity.value` es de tipo double; no acepta cadenas.

   Si seleccionó la opción **[!UICONTROL Promocionar por atributo]** o **[!UICONTROL Promocionar una colección]**, la opción para asignar aleatoriamente el pedido no es aplicable.

   Al promocionar elementos específicos mediante las opciones [!UICONTROL Promocionar por atributo] o [!UICONTROL Promocionar una colección], el orden predeterminado en que se presentan los elementos se basa en el atributo `entity.value`, en orden numérico descendente.

   La siguiente tabla ilustra las diferencias entre estas opciones:

   | Tipo de promoción | Orden predeterminado | Orden de copia | Opción de filtrado dinámico |
   | --- | --- | --- | --- |
   | [!UICONTROL Lista de elementos] | Pedido introducido en la IU/API de Target | Aleatorio (cuando se selecciona mediante la interfaz de usuario/API) | No |
   | [!UICONTROL Promocionar por atributo] | `entity.value` (orden descendente) | Sin aleatorización | Sí |
   | [!UICONTROL Promocionar una colección] | `entity.value` (orden descendente) | Sin aleatorización | No |

1. Haga clic en **[!UICONTROL Guardar]**.

Las promociones se aplican a todas las experiencias de la actividad.
