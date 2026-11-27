---
keywords: promociones;promociones principales;promociones secundarias;tipo de promociones;lista de elementos;promocionar por atributo;promocionar una colección
description: Aprenda a agregar elementos promocionados y controlar su ubicación en sus diseños de Recommendations de Adobe [!DNL Target]. Puede añadir promociones estáticas y dinámicas.
title: ¿Cómo puedo añadir promociones en diseños de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: 'https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E'
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
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%
---
# Agregar promociones {#add-promotions}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a agregar elementos promocionados a un diseño de [!DNL Recommendations] y a determinar su criterio de ordenación.

>[!ENDSHADEBOX]

Las promociones colocan elementos específicos en un diseño de [!DNL Recommendations], además de los elementos recomendados según los criterios. Utilizan espacios disponibles en el diseño y tienen prioridad sobre los resultados de criterios y las recomendaciones de copia de seguridad. Por ejemplo, si un diseño tiene seis espacios y dos de ellos se utilizan para promociones, quedan cuatro espacios para los artículos recomendados en función de criterios.

Las promociones se eliminan de la duplicación de elementos recomendados por los criterios de la actividad, por lo que un elemento determinado no aparece dos veces en una sola bandeja de recomendaciones.

![Cambiar cuadro de diálogo de promoción con las opciones Promoción principal y Promoción secundaria desactivadas](assets/add_promotion_toggles.png)

>[!NOTE]
>
>El uso de promociones cambia la estructura y la salida CSV. Estos cambios pueden afectar a cualquier proceso externo que incluya CSV, como el correo electrónico.

## Añadir una promoción {#add-promotion}

Una promoción define qué elementos se promocionan, cuántos espacios de diseño utilizan y el periodo durante el cual se muestran.

1. En la página **[!UICONTROL Opciones]**, haga clic en la opción **[!UICONTROL Promoción principal]** o **[!UICONTROL Promoción secundaria]**.

   La siguiente ilustración muestra la opción **[!UICONTROL Promoción principal]** en la posición &quot;Activada&quot;. Las promociones se pueden insertar antes y después de los resultados de criterios.

   ![Cambiar cuadro de diálogo de promoción con la opción Promoción principal activada, que muestra el número de espacios de diseño, la programación y las opciones de tipo de promoción](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

1. Establezca el **[!UICONTROL número de espacios de diseño]** que se utilizarán para los elementos promocionados.

   Se pueden usar hasta 20 espacios, según el diseño de [!DNL Recommendations]. Cada ranura utilizada no está disponible para las recomendaciones devueltas según los criterios.

1. Establezca una fecha de **inicio** y una fecha de **fin** para los elementos promocionados.

   Si no se establece ninguna fecha de inicio, la promoción se inicia inmediatamente. Si no se establece ninguna fecha de finalización, la promoción se ejecuta indefinidamente.

1. Seleccionar un **[!UICONTROL tipo de promoción]**:

   * **[!UICONTROL Lista de elementos]**: escriba los valores `entity.id` de los elementos que desea promocionar, separados por comas.
   * **[!UICONTROL Promocionar por atributo]**: agregue reglas para definir los atributos de los elementos que se promocionarán. Esta opción permite coincidencias dinámicas mediante reglas de inclusión estáticas y dinámicas. Para obtener información detallada, ejemplos y casos de uso, consulte [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).
   * **[!UICONTROL Promocionar una colección]**: elija la colección de elementos que desea promocionar. Se pueden crear nuevas colecciones para las promociones. Ver [Crear una colección](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08).

   El tipo de promoción también determina el orden de los elementos promocionados. Consulte [Tipos de promociones y criterio de ordenación](#promotion-sort-order).

   ![Cambiar cuadro de diálogo de promoción con las opciones Tipo de promoción resaltadas: Lista de elementos, Promocionar por atributo y Promocionar una colección](/help/main/c-recommendations/t-create-recs-activity/assets/promotion_type.png)

1. Haga clic en **[!UICONTROL Guardar]**.

Las promociones se aplican a todas las experiencias de la actividad.

## Tipos de promociones y criterio de ordenación {#promotion-sort-order}

El orden de los elementos promocionados depende del tipo de promoción, como se muestra en la tabla siguiente.

| Tipo de promoción | Orden predeterminado | Orden de copia | Opción de filtrado dinámico |
| --- | --- | --- | --- |
| **[!UICONTROL Lista de elementos]** | Orden ingresado en la interfaz de usuario o API de [!DNL Target] | Aleatorio (cuando se selecciona mediante la interfaz de usuario o la API) | No |
| **[!UICONTROL Promocionar por atributo]** | `entity.value` (orden descendente) | Sin aleatorización | Sí |
| **[!UICONTROL Promocionar una colección]** | `entity.value` (orden descendente) | Sin aleatorización | No |

* **[!UICONTROL Lista de elementos]**: el criterio de ordenación predeterminado es el orden introducido en la interfaz de usuario o la API de [!DNL Target]. La casilla de verificación **[!UICONTROL Ordenar elementos de forma aleatoria]** está disponible para este tipo. Cuando la lista incluye más elementos que el número de espacios definido para las promociones, esta opción aleatoriza qué elementos promocionados se muestran en el diseño. En cada visita, [!DNL Target] selecciona aleatoriamente los elementos habilitados para las promociones en la plantilla de todo el conjunto de promociones.
* **[!UICONTROL Promocionar por atributo]** y **[!UICONTROL Promocionar una colección]**: El orden predeterminado se basa en el atributo `entity.value`, en orden numérico descendente. No es aplicable el orden aleatorio.

Si las entidades no tienen un atributo `entity.value` (por ejemplo, la empresa no vende productos), se puede pasar un valor numérico como la fecha de publicación al atributo `entity.value`. A continuación, los elementos promocionados se ordenan por la fecha de publicación más reciente, en orden descendente. El atributo `entity.value` es del tipo double y no acepta cadenas.
