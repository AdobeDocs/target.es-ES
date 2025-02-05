---
keywords: personalización automatizada;oferta;informes;grupo;grupo de informes;ap
description: Aprenda a utilizar los grupos de informes de ofertas en  [!DNL Adobe Target] [!UICONTROL Automated Personalization] actividades.
title: ¿Puedo usar los grupos de informes de ofertas en [!UICONTROL Automated Personalization] actividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 15%

---

# Grupos de informes de ofertas en [!UICONTROL Automated Personalization]

Información sobre el uso de grupos de informes en [!DNL Adobe Target] actividades [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Los grupos de informes realizan dos funciones clave:

* Los grupos de informes permiten ver las ofertas agrupadas en informes de actividad de AP.
* Los grupos de informes desempeñan un papel clave en el funcionamiento de los modelos de personalización de [!DNL Target].

Cuando usa grupos de informes, [!DNL Target] crea un modelo de personalización para cada grupo de informes usando los datos de todas las ofertas de ese grupo. Sin grupos de informes, [!DNL Target] crea un modelo de personalización para cada oferta en su actividad AP.

Si la configuración de su actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes ayudan a reducir los requisitos de datos para usar [!UICONTROL Automated Personalization]. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para actividades en las que las nuevas ofertas se introducen regularmente en la actividad de AP.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Agrupar todas las ofertas u ofertas con diferentes tasas de conversión probablemente reduzca la eficacia de los modelos de personalización de [!DNL Target].

>[!NOTE]
>
>Si se remplaza o elimina una oferta de un grupo de modelado particular, el tráfico histórico de la oferta también se elimina del grupo de modelado. En otras palabras, las ofertas eliminadas no contribuyen a los datos que se utilizan para que los modelos de personalización [!DNL Target] aprendan.

## Configuración de grupos de informes

1. En la página **[!UICONTROL Experiences]** de una actividad AP, haga clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) )
1. Haga clic en la ficha **[!UICONTROL Offers]** en la parte superior del cuadro de diálogo [!UICONTROL Manage Content].
1. (Condicional) Agregue experiencias específicas a un grupo de informes haciendo clic en el icono [!UICONTROL More Actions] ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) de la oferta deseada y, a continuación, haciendo clic en **[!UICONTROL Reporting Group]**.

1. (Condicional) Incluya experiencias en lote en un grupo de informes seleccionando las casillas de las experiencias relevantes y luego haciendo clic en **[!UICONTROL Reporting Group]** en la parte inferior del cuadro de diálogo.

1. Para asignar la oferta seleccionada a un grupo de informes existente, seleccione **[!UICONTROL Existing]**, elija el grupo de informes deseado en la lista desplegable y luego haga clic en **[!UICONTROL Confirm]**.

   O

   Para crear un grupo de informes al que asignar la oferta seleccionada, seleccione **[!UICONTROL New]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Confirm]**.

Puede usar la lista [!UICONTROL Location] para filtrar ofertas por ubicación. Utilice la lista [!UICONTROL Report Group] para filtrar ofertas por grupos de informes. También puede usar la lista [!UICONTROL Report Group] para filtrar [!UICONTROL Unassigned Offers] y asignar un grupo de informes a una oferta que no esté actualmente asignada a ningún grupo de informes.

Para obtener información sobre cómo dirigir una oferta a audiencias específicas, consulte [Ofertas de Target [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Advertencias 

* Es importante comprender que los grupos de informes afectan la forma en que [!DNL Target] crea sus modelos. Como resultado, [!DNL Adobe] recomienda usar grupos de informes solamente si planea reemplazar o agregar nuevas ofertas mientras una actividad esté activa. Si se introduce una nueva oferta en una actividad activa, poner la nueva oferta en un grupo con ofertas similares existentes permite al equipo utilizar los datos ya recopilados para las demás ofertas de su grupo para conocer la nueva oferta. Nunca debe colocar todas las ofertas en un solo grupo de informes.

* Las actividades AP tienen combinaciones de ubicación+oferta (modelables). Cuando [!DNL Target] registra datos en los informes, [!DNL Target] considera dichas combinaciones de modo que queda claro de qué evento (mostrar, hacer clic, etc.) provino la oferta.

  Por ejemplo, una actividad puede tener varias ubicaciones y varias ofertas, que pueden superponerse. Si un visitante ve más de una de estas ofertas en diferentes ubicaciones, [!DNL Target] registra datos solo para esas ofertas. Si posteriormente el mismo visitante hace clic en una oferta, [!DNL Target] registra un evento solo a partir de esa combinación (no para todas las combinaciones).

  Del mismo modo, si el clic proviene de una ubicación diferente, que está presente en una métrica, pero no muestra una oferta, este evento se registra en la actividad, pero no para cualquier combinación de oferta + ubicación. Como resultado, esta oferta no aparece en el grupo de informes de ofertas.

  Este comportamiento se debe a que el clic puede realizarse desde un mbox diferente y no desde el mbox que sirvió a la oferta. Debido a esto, la métrica está asociada con la actividad, pero no con la oferta.

## Visualización de ofertas en un grupo de informes

1. Haga clic en **[!UICONTROL Activities]**, en la actividad [!UICONTROL Automated Personalization] que quiera de la lista y luego haga clic en la ficha **[!UICONTROL Reports]** para mostrar el informe [Nivel de oferta](/help/main/c-reports/personalization-reports/reports-ap.md).

   Si tiene muchas actividades, haga clic en el icono [!UICONTROL Show Filters] (canal) y, a continuación, seleccione la casilla de verificación [!UICONTROL Automated Personalization] para filtrar la lista y mostrar solo [!UICONTROL Automated Personalization] actividades.

1. Haga clic en **[!UICONTROL Control]** o **[!UICONTROL Targeted]** en la tabla para mostrar las ofertas y ofertas desagrupadas dentro de los grupos de informes.

   ![Grupos de ofertas: Control y segmentado](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Para obtener información sobre el uso de [!UICONTROL Automated Personalization] informes (incluido el informe [!UICONTROL Offer Level]), consulte [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
