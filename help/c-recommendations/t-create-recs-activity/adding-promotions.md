---
keywords: promotions;front promotions;back promotions;promotions type
description: Añada elementos promocionados y controle su ubicación en sus diseños de Recommendations de Adobe Target. Puede añadir promociones estáticas y dinámicas.
title: Agregue promociones en diseños de Recommendations de Adobe Target.
feature: recs creation
translation-type: tm+mt
source-git-commit: e07a457339509d1019cdd241ef3adfbb17ffafaa
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 60%

---


# ![PREMIUM](/help/assets/premium.png) Añadir promociones

Añada elementos promocionados y controle su ubicación en sus diseños de Recommendations. Puede añadir promociones estáticas y dinámicas.

>[!IMPORTANT]
>
>Las reglas de exclusión estáticas y dinámicas son funciones potentes que pueden ayudarle en sus estrategias de marketing. Para obtener información detallada, ejemplos y casos de uso, consulte [Uso de reglas de inclusión dinámicas y estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Al crear una actividad de [!DNL Recommendations], tiene la opción de incluir elementos promocionados en el diseño de [!DNL Recommendations]. Las promociones se ubican en los espacios libres del diseño y tienen prioridad sobre los resultados de criterios y las recomendaciones de copia de seguridad. Por ejemplo, si su diseño tiene seis espacios y utiliza dos para las promociones, quedarán cuatro espacios disponibles para los elementos recomendados a partir de los criterios.

Las promociones se eliminan de la duplicación de elementos recomendados por los criterios de la actividad, por lo que un elemento dado no aparecerá dos veces en una sola bandeja de recomendaciones.

Puede promocionar elementos concretos del modo habitual o de forma dinámica, así como elementos basados en atributos o colecciones.

![](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Si utiliza promociones, se cambiarán la estructura y los resultados del CSV. Estos cambios no afectan a ningún proceso externo que utilice el CSV, como el correo electrónico.

1. En la página **[!UICONTROL Opciones]**, haga clic en la opción **[!UICONTROL Promoción principal]** o **[!UICONTROL Promoción secundaria]**.

   La siguiente ilustración muestra la opción de [!UICONTROL Promoción principal] en la posición “Activada”.

   ![Agregar opciones de promoción principal](/help/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Puede introducir promociones antes *o* después de los resultados de criterios.
1. Defina el número de espacios del diseño que se utilizarán para los elementos promocionados.

   Puede utilizar hasta 20 espacios en función de su diseño de [!DNL Recommendations]. Todos los espacios que utilice dejarán de estar disponibles para las recomendaciones ofrecidas a partir de sus criterios.

1. Defina una fecha de inicio y una fecha de finalización para los elementos promocionados.

   Si no define una fecha de inicio, la promoción se inicia inmediatamente. Si no define una fecha de finalización, la promoción se ejecuta indefinidamente.

1. Seleccione un **[!UICONTROL Tipo de promoción]**.

   * Seleccione **[!UICONTROL Lista de elementos]** e introduzca los valores `entity.id`, separados por comas, de los elementos específicos que desea promocionar.

   * Seleccione **[!UICONTROL Promocionar por atributo]** y agregue reglas para definir los atributos de los elementos que desea promocionar.

      Si selecciona Promocionar por atributo, puede crear coincidencias dinámicas. Para obtener más información, consulte [Uso de reglas de inclusión dinámicas y estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Seleccione **[!UICONTROL Promocionar una colección]** y elija la colección de elementos que desea promocionar.

      Puede crear nuevas colecciones para utilizarlas en las promociones. Consulte [Crear una colección](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obtener más información.
   Si ha seleccionado **[!UICONTROL Lista de elementos]** como tipo **[!UICONTROL de]** promoción, active la casilla de verificación Orden **** aleatorio del elemento, si lo desea.

   El orden de clasificación predeterminado para la [!UICONTROL Lista de elementos] se basa en el orden especificado en la IU o API de Destinatario.

   If your list includes more items than the number of slots you set for promotions, the [!UICONTROL Randomize Item Order] option randomizes the promoted items that are displayed in your design. Choosing this option results in [!DNL Target] randomly selecting the items enabled for promotions in the template from the entire promotion set on each hit.

   Si las entidades no tienen un `entity.value` atributo (por ejemplo, no vende productos), puede pasar un valor numérico al `entity.value` atributo, como la fecha de publicación. En este caso, los elementos promocionados se pueden promocionar en función de la fecha de publicación más reciente, en orden descendente. El `entity.value` atributo es de tipo doble; no acepta cadenas.

   Si ha seleccionado la opción [!UICONTROL Promocionar por atributo] o [!UICONTROL Promocionar una colección] , la opción para aleatorizar el pedido no es aplicable.

   Al promocionar elementos específicos mediante las opciones [!UICONTROL Promocionar por atributo] o [!UICONTROL Promocionar una colección] , el orden predeterminado en el que se presentan los elementos se basa en el `entity.value` atributo, en orden numérico descendente.

   La siguiente tabla ilustra las diferencias entre estas opciones:

   | Tipo de promoción | Orden predeterminado | Orden de copia de seguridad | Opción de filtrado dinámico |
   | --- | --- | --- | --- |
   | Lista de elementos | Orden introducido en la interfaz de usuario/API de Destinatario | Aleatorio (cuando se selecciona mediante la interfaz de usuario/API) | No |
   | Promocionar por atributo | entity.value (orden descendente) | Se aleatorizan en cada solicitud (cuando no hay ningún atributo entity.value presente) | No |
   | Promocionar una colección | entity.value (orden descendente) | Se aleatorizan en cada solicitud (cuando no hay ningún atributo entity.value presente) | No |

1. Haga clic en **[!UICONTROL Guardar.]**.

Las promociones se aplican a todas las experiencias de la actividad.
