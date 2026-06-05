---
keywords: público;seleccionar público;elegir público;selectores
description: Defina los visitantes del sitio que se unirán a su actividad de Adobe [!DNL Target] según los criterios de audiencia.
title: ¿Cómo selecciono una audiencia en una actividad  [!DNL Target] A/B?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 575
ht-degree: 10%

---

# Seleccionar el público

La audiencia determina qué visitantes calificadores se ingresan en su actividad [!DNL Adobe Target].

El paso [!UICONTROL Segmentación] del flujo de trabajo guiado de tres partes al [crear una actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) muestra un diagrama de flujo que le guía a través de los pasos para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Para obtener más información acerca de todas las opciones del diagrama de flujo, vea [Crear una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Seleccione una audiencia para la actividad

1. Haga clic en el control **[!UICONTROL Todos los visitantes]** para seleccionar otra audiencia para la actividad.

   La audiencia [!UICONTROL Todos los visitantes] está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

   Para una prueba A/B sin segmentación de audiencia específica, elija el valor predeterminado [!UICONTROL Todos los visitantes].

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.

1. En el cuadro de diálogo [!UICONTROL Agregar audiencia], [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Asignar audiencia]**.

   De forma predeterminada, su audiencia son todos los visitantes. No obstante, puede modificar la audiencia. Las audiencias se seleccionan de la [!UICONTROL Biblioteca de audiencias] o puede crear una audiencia solo de actividad. La [!UICONTROL Biblioteca de audiencias] contiene audiencias que se han definido anteriormente, incluidas algunas audiencias comunes predefinidas como parte de [!DNL Target].

1. (Condicional) Haga clic en **Combinar audiencias** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

1. (Condicional) Para crear una audiencia nueva que no esté ya en la [!UICONTROL Biblioteca de audiencias], haga clic en **Crear audiencia**, defina la audiencia y haga clic en **[!UICONTROL Listo]**.

   Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

   * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la [!UICONTROL Biblioteca de audiencias] y que pueda reutilizarse en otras actividades.
   * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la [!UICONTROL Biblioteca de audiencias] y que solo se puede usar en la actividad actual.

1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el panel derecho y, a continuación, especifique el porcentaje de visitantes correspondiente que desea incluir en la actividad.

1. Cuando esté satisfecho con la audiencia, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

>[!NOTE]
>
>Las audiencias se importan automáticamente en segundo plano cuando abre la lista [!UICONTROL Audiencia] y las audiencias importadas tienen más de 10 minutos de antigüedad.

## Ver la información de una audiencia

1. En el cuadro de diálogo [!UICONTROL Agregar audiencias], haga clic en el icono de **[!UICONTROL Información]** ( ![icono de información](/help/main/assets/icons/InfoOutline.svg) ) junto a una audiencia para ver detalles sobre esa audiencia, incluidos su origen y atributos.

1. Haga clic en **[!UICONTROL Ver detalles completos]** para ver detalles adicionales sobre la audiencia. Los detalles incluyen los atributos de la audiencia, la descripción de la audiencia, el espacio de trabajo, el tipo y el origen, y una lista de actividades que hacen referencia a esta audiencia. Puede ver información sobre cada audiencia, incluido el nombre de la actividad, el estado, el espacio de trabajo, y cuándo se modificó la audiencia por última vez y quién la modificó.

## Editar o copiar una audiencia

Puede editar o copiar una audiencia haciendo clic en el icono [!UICONTROL Más acciones] ( ![Icono de más acciones](/help/main/assets/icons/More.svg) ) junto a la audiencia deseada en el cuadro de diálogo [!UICONTROL Agregar audiencia] y, a continuación, haciendo clic en [!UICONTROL Editar] o [!UICONTROL Copiar].

Copiar una audiencia es útil si quiere crear una audiencia similar a otra ya existente. Puede crear una copia de la audiencia, realizar sus modificaciones y después guardarla como una audiencia nueva.
