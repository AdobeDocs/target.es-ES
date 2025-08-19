---
keywords: audiencia;seleccionar audiencia;elegir audiencia;selectores
description: Defina los visitantes del sitio que se unirán a su actividad de Adobe [!DNL Target] según los criterios de audiencia.
title: ¿Cómo selecciono una audiencia en una actividad  [!DNL Target] A/B?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: f6845756f9d4220214b0d9131cd5f27db2ae94a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# Seleccionar la audiencia

La audiencia determina qué visitantes calificadores se ingresan en su actividad [!DNL Adobe Target].

El paso [!UICONTROL Targeting] del flujo de trabajo guiado de tres partes al [crear una actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) muestra un diagrama de flujo que lo lleva a través de los pasos para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Para obtener más información acerca de todas las opciones del diagrama de flujo, vea [Crear una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Seleccione una audiencia para la actividad

1. Haga clic en el control **[!UICONTROL All Visitors]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL All Visitors] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Para una prueba A/B sin segmentación de audiencia específica, elija el valor predeterminado [!UICONTROL All Visitors].

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Replace]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.

1. En el cuadro de diálogo [!UICONTROL Add Audience], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Assign Audience]**.

   De forma predeterminada, su audiencia son todos los visitantes. No obstante, puede modificar la audiencia. Las audiencias se seleccionan entre [!UICONTROL Audience Library] o puede crear una audiencia solo de actividad. [!UICONTROL Audience Library] contiene audiencias que se han definido anteriormente, entre las que se incluyen algunas audiencias comunes predefinidas como parte de [!DNL Target].

1. (Condicional) Haga clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

1. (Condicional) Para crear una audiencia nueva que no esté ya en [!UICONTROL Audience Library], haga clic en **Crear audiencia**, defina la audiencia y haga clic en **[!UICONTROL Done]**.

   Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

   * **[!UICONTROL Audience Library]**: cree una audiencia bajo demanda que se guarde en [!UICONTROL Audience Library] y que pueda reutilizarse en otras actividades.
   * **[!UICONTROL This activity only]**: cree una [audiencia específica de actividad](/help/main/c-target/creating-activity-only-audience.md) que no se haya guardado en [!UICONTROL Audience Library] y que solo se pueda usar en la actividad actual.

1. Haga clic en **[!UICONTROL Visitor Percentage]** en el panel derecho y, a continuación, especifique el porcentaje de visitantes correspondiente que desea incluir en la actividad.

1. Cuando esté satisfecho con la audiencia, haga clic en **[!UICONTROL Next]** para ir al tercer paso del flujo de trabajo guiado de tres pasos.

>[!NOTE]
>
>Las audiencias se importan automáticamente en segundo plano cuando abre la lista [!UICONTROL Audience] y las audiencias importadas tienen más de 10 minutos de antigüedad.

## Ver la información de una audiencia

1. En el cuadro de diálogo [!UICONTROL Add Audiences], haga clic en el icono **[!UICONTROL Information]** ( ![icono de información](/help/main/assets/icons/InfoOutline.svg) ) situado junto a una audiencia para ver detalles sobre la misma, incluido su origen y atributos.

1. Haga clic **[!UICONTROL View Full Details]** para ver detalles adicionales acerca de la audiencia. Los detalles incluyen los atributos de la audiencia, la descripción de la audiencia, el espacio de trabajo, el tipo y el origen, y una lista de actividades que hacen referencia a esta audiencia. Puede ver información sobre cada audiencia, incluido el nombre de la actividad, el estado, el espacio de trabajo, y cuándo se modificó la audiencia por última vez y quién la modificó.

## Editar o copiar una audiencia

Puede editar o copiar una audiencia haciendo clic en el icono [!UICONTROL More Actions] ( ![icono Más acciones](/help/main/assets/icons/More.svg) ) junto a la audiencia deseada en el cuadro de diálogo [!UICONTROL Add Audience] y luego haciendo clic en [!UICONTROL Edit] o [!UICONTROL Copy].

Copiar una audiencia es útil si quiere crear una audiencia similar a otra ya existente. Puede realizar una copia de la audiencia, realizar ediciones y guardarla como una audiencia nueva.
