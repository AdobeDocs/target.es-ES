---
keywords: personalización automatizada;oferta;informes;grupo;grupo de informes;ap
description: Aprenda a utilizar los grupos de informes de ofertas en [!DNL Adobe Target] actividades de [!UICONTROL Automated Personalization].
title: ¿Puedo usar los grupos de informes de ofertas en las actividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: 'https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# Grupos de informes de ofertas en [!UICONTROL Automated Personalization] {#offer-reporting-groups}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda cómo funcionan los grupos de informes de ofertas en las actividades de **[!UICONTROL Automated Personalization]**, cómo configurarlas y cómo verlas en los informes.

>[!ENDSHADEBOX]

Los grupos de informes permiten organizar las ofertas de una actividad [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) en grupos. Los grupos de informes realizan dos funciones clave:

* Permiten ver las ofertas agrupadas en informes de actividad de AP.
* Desempeñan un papel clave en el funcionamiento de los modelos de personalización de [!DNL Target].

Cuando usa grupos de informes, [!DNL Target] crea un modelo de personalización para cada grupo de informes usando los datos de todas las ofertas de ese grupo. Sin grupos de informes, [!DNL Target] crea un modelo de personalización para cada oferta en su actividad AP.

Los grupos de informes también reducen los requisitos de datos para usar **[!UICONTROL Automated Personalization]** cuando la configuración de la actividad no tiene datos suficientes para crear un modelo de personalización por oferta. Ayudan con el problema de &quot;inicio en frío&quot; de las nuevas ofertas, que se agrupan con ofertas similares para que cada modelo tenga más datos sobre los que entrenar.

Este método funciona bien cuando los visitantes responden de la misma manera a todas las ofertas de un grupo, por lo que agrupa las ofertas con tasas de conversión similares. Nunca incluya todas las ofertas en un único grupo de informes ni las agrupe con distintas tasas de conversión, ya que ambas opciones probablemente reduzcan la eficacia de los modelos de personalización de [!DNL Target].

>[!NOTE]
>
>Si una oferta se elimina de un grupo de informes o se reemplaza en él, el tráfico histórico que vio esa oferta también se elimina del grupo, por lo que las ofertas eliminadas no contribuyen a los datos que los modelos de personalización de [!DNL Target] utilizan para aprender.


## Consideraciones

### Uso de grupos de informes para actividades activas

Los grupos de informes afectan la forma en que [!DNL Target] crea sus modelos. Como resultado, [!DNL Adobe] recomienda usar grupos de informes solamente si planea reemplazar o agregar ofertas mientras una actividad esté activa. Si se introduce una nueva oferta en una actividad activa, poner la nueva oferta en un grupo con ofertas similares existentes permite que [!DNL Target] use los datos ya recopilados para las demás ofertas del grupo para obtener información sobre la nueva oferta.

### Registro de datos de ofertas y ubicaciones

Las actividades AP tienen combinaciones de ubicación y oferta (modelables). Cuando [!DNL Target] registra datos en los informes, tiene en cuenta estas combinaciones, por lo que queda claro de qué evento (mostrar, hacer clic, etc.) provino la oferta.

Por ejemplo, una actividad puede tener varias ubicaciones y varias ofertas, que pueden superponerse. Si un visitante ve más de una de estas ofertas en diferentes ubicaciones, [!DNL Target] registra datos solo para esas ofertas. Si posteriormente el mismo visitante hace clic en una oferta, [!DNL Target] registra un evento solo a partir de esa combinación (no para todas las combinaciones).

Del mismo modo, si el clic proviene de una ubicación diferente que está presente en una métrica pero no muestra una oferta, el evento se registra en la actividad, pero no para cualquier combinación de oferta y ubicación. Como resultado, esta oferta no aparece en el grupo de informes de ofertas. Este comportamiento se produce porque el clic puede realizarse desde un mbox diferente al que sirvió a la oferta. En ese caso, la métrica se asocia con la actividad, pero no con la oferta.

## Configuración de grupos de informes

La asignación de ofertas a grupos de informes determina cómo [!DNL Target] crea sus modelos de personalización y cómo se muestran las ofertas en los informes de actividad. Configure los grupos mientras crea la actividad o más tarde, si agrega nuevas ofertas a una actividad activa.

1. En la página **[!UICONTROL Experiencias]** de una actividad AP, haga clic en el icono **[!UICONTROL Administrar contenido]** ( ![Icono Administrar contenido](/help/main/assets/icons/Experience.svg) ).

1. Haga clic en la pestaña **[!UICONTROL Ofertas]** en la parte superior del cuadro de diálogo **[!UICONTROL Administrar contenido]**.

   ![Icono de configuración](../assets/ap-offers-2.png)

1. (Condicional) Elija las ofertas que desea agregar a un grupo de informes.

   * Para agregar una sola oferta, haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) de la oferta y, a continuación, haga clic en **[!UICONTROL Grupo de informes]**.
   * Para agregar varias ofertas a la vez, seleccione las casillas de verificación de las ofertas y haga clic en **[!UICONTROL Grupo de informes]** en la parte inferior del cuadro de diálogo.

1. Asigne las ofertas seleccionadas a un grupo de informes.

   * Para asignar las ofertas a un grupo de informes existente, seleccione **[!UICONTROL Existente]**, seleccione el grupo de informes en la lista desplegable y haga clic en **[!UICONTROL Confirmar]**.
   * Para crear un grupo de informes para las ofertas, seleccione **[!UICONTROL Nuevo]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Confirmar]**.

Para reducir la lista de ofertas, filtra por ubicación con la lista **[!UICONTROL Ubicación]** o por grupo de informes con la lista **[!UICONTROL Grupo de informes]**. La lista **[!UICONTROL Grupo de informes]** también ofrece la opción **[!UICONTROL Ofertas sin asignar]**, que muestra las ofertas que aún no pertenecen a ningún grupo de informes, de modo que puede asignarlas a una.

Para obtener información sobre cómo dirigir una oferta a audiencias específicas, consulte [Ofertas de Target **[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#set-up-targeting-rules).

## Visualización de ofertas en un grupo de informes

El informe **[!UICONTROL Nivel de oferta]** muestra el rendimiento de las ofertas de una actividad, agrupadas por grupo de informes, para que pueda comparar los grupos y las ofertas individuales.

1. Haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad **[!UICONTROL Automated Personalization]** de la lista y, a continuación, haga clic en la pestaña **[!UICONTROL Informes]** para mostrar el informe [Nivel de oferta](/help/main/c-reports/personalization-reports/reports-ap.md).

   Si tiene muchas actividades, haga clic en el icono **[!UICONTROL Mostrar filtros]** (funnel) y, a continuación, seleccione la casilla de verificación **[!UICONTROL Automated Personalization]** para mostrar solo las actividades de **[!UICONTROL Automated Personalization]**.

1. Haga clic en **[!UICONTROL Control]** o **[!UICONTROL Segmentado]** en la tabla para mostrar las ofertas desagrupadas y las ofertas dentro de los grupos de informes.

   ![Grupos de ofertas: Control y segmentado](/help/main/c-reports/assets/offer-groups.png)

Para obtener información sobre el uso de los informes de **[!UICONTROL Automated Personalization]** (incluido el informe de **[!UICONTROL Nivel de oferta]**), consulte [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
