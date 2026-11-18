---
keywords: público;seleccionar público;elegir público;selectores
description: Defina los visitantes del sitio que se unirán a su actividad de Adobe [!DNL Target] según los criterios de audiencia.
title: ¿Cómo selecciono una audiencia en una actividad A/B de [!DNL Target]?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: 'https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# Seleccionar el público {#select-audience}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a seleccionar, crear, combinar, ver, editar y copiar la audiencia de una actividad A/B, y a configurar el porcentaje de visitantes que se va a incluir.

>[!ENDSHADEBOX]

La audiencia determina qué visitantes calificadores se ingresan en su actividad [!DNL Adobe Target].

El paso **[!UICONTROL Segmentación]** del flujo de trabajo guiado de tres partes al [crear una actividad](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) muestra un diagrama de flujo que le guía a través de los pasos para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

![Paso de Segmentación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Para obtener más información acerca de todas las opciones del diagrama de flujo, vea [Crear una actividad de prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Seleccione una audiencia para la actividad

La audiencia controla quién ve la actividad. Solo pueden entrar en él los visitantes que coincidan con la audiencia y usted decide qué parte de esos visitantes participan. De forma predeterminada, la actividad se dirige a todos los visitantes.

1. Haga clic en el control **[!UICONTROL Todos los visitantes]** para seleccionar otra audiencia para la actividad.

   **[!UICONTROL Todos los visitantes]** es la audiencia predeterminada. Para una prueba A/B sin segmentación de audiencia específica, mantenga el valor predeterminado. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda.

1. Haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ).

   ![](../../assets/audience_activity.png)

1. En el cuadro de diálogo **[!UICONTROL Agregar audiencia]**, examine las audiencias seleccionadas en la **[!UICONTROL Biblioteca de audiencias]** o puede crear una audiencia solo de actividad.

   La **[!UICONTROL Biblioteca de audiencias]** contiene audiencias que se han definido anteriormente, incluidas algunas audiencias comunes predefinidas como parte de [!DNL Target].

   ![](../../assets/audience_activity_2.png)

1. Haga clic en el icono **[!UICONTROL Información]** ( ![icono de información](/help/main/assets/icons/InfoOutline.svg) ) junto a una audiencia para ver detalles sobre esa audiencia, incluidos su origen y atributos.

   ![](../../assets/audience_activity_3.png)

   También puede hacer clic en **[!UICONTROL Ver detalles completos]** para ver detalles adicionales sobre la audiencia.

1. (Condicional) Haga clic en **[!UICONTROL Combinar audiencias]** para [crear una audiencia que combine varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

   +++ Pasos para crear una audiencia nueva

   Para crear una audiencia nueva que no esté ya en la **[!UICONTROL Biblioteca de audiencias]**, haga clic en **[!UICONTROL Crear audiencia]**, defina la audiencia y haga clic en **[!UICONTROL Listo]**.

   Durante el [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), puede elegir entre las siguientes opciones:

   * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la **[!UICONTROL Biblioteca de audiencias]** y pueda reutilizarse en otras actividades.
   * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la **[!UICONTROL Biblioteca de audiencias]** y que solo se puede usar en la actividad actual.

   +++

1. Puede editar o copiar una audiencia haciendo clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/More.svg) ) junto a la audiencia deseada.

1. Después de seleccionar la audiencia, haga clic en **[!UICONTROL Asignar audiencia]**.

1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el panel derecho y, a continuación, especifique el porcentaje de visitantes correspondiente que desea incluir en la actividad.

1. Cuando esté satisfecho con la audiencia, haga clic en **[!UICONTROL Siguiente]** para pasar al tercer paso del flujo de trabajo guiado de tres pasos.

>[!NOTE]
>
>Las audiencias se importan automáticamente en segundo plano cuando abre la lista **[!UICONTROL Audiencia]** y las audiencias importadas tienen más de 10 minutos de antigüedad.
