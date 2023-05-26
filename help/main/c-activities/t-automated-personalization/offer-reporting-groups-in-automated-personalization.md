---
keywords: personalización automatizada;oferta;informes;grupo;grupo de informes;ap
description: Aprenda a utilizar los grupos de informes de ofertas en Adobe [!DNL Target] [!UICONTROL Automated Personalization] actividades.
title: ¿Puedo utilizar los grupos de informes de ofertas en actividades de Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 30%

---

# Grupos de creación de informes de ofertas en [!UICONTROL Automated Personalization]

Información sobre el uso de grupos de informes en [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) Actividades de (AP).

Los grupos de informes realizan dos funciones clave:

* Los grupos de informes permiten ver las ofertas agrupadas en informes de actividad de AP.
* Los grupos de informes desempeñan un papel clave en la [!DNL Target] función de modelos de personalización.

Cuando se usan grupos de informes, [!DNL Target] crea un modelo de personalización para cada grupo de informes con los datos de todas las ofertas de ese grupo. Sin grupos de informes, [!DNL Target] crea un modelo de personalización para cada oferta en su actividad AP.

Si la configuración de la actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes pueden ayudar a reducir los requisitos de datos que se deben usar [!UICONTROL Automated Personalization]. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para actividades en las que las nuevas ofertas se introducen regularmente en la actividad de AP.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Agrupar todas las ofertas u ofertas con diferentes tasas de conversión probablemente reduce la eficacia de la variable [!DNL Target] modelos de personalización.

>[!NOTE]
>
>Si se remplaza o elimina una oferta de un grupo de modelado particular, el tráfico histórico de la oferta también se elimina del grupo de modelado. En otras palabras, las ofertas eliminadas no contribuyen a los datos que se utilizan para [!DNL Target] modelos de personalización para aprender.

## Configuración de grupos de informes

1. En el **[!UICONTROL Experiencias]** de una actividad AP, haga clic en el botón **[!UICONTROL Administrar contenido]** icono.

   ![Icono Administrar contenido](/help/main/c-reports/assets/ap_manage_content.png)

1. Haga clic en la pestaña **[!UICONTROL Ofertas]** en la parte superior del cuadro de diálogo [!UICONTROL Administrar contenido].
1. (Condicional) Agregue experiencias específicas a un grupo de informes pasando el puntero sobre la oferta deseada y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes]**.

   ![Icono de Grupo de informes](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Condicional) Incluya experiencias en lote en un grupo de informes seleccionando la casilla de las experiencias relevantes y haciendo clic en **[!UICONTROL Grupo de informes]** en la esquina superior derecha del cuadro de diálogo.

   ![Icono de Grupo de informes](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Para asignar la oferta seleccionada a un grupo de informes existente, seleccione **[!UICONTROL Existente]**, elija un grupo de informes en la lista desplegable y luego haga clic en **[!UICONTROL Aplicar]**.

   O

   Para crear un grupo de informes al que asignar la oferta seleccionada, seleccione **[!UICONTROL Nuevo]**, nombre el nuevo grupo de informes y haga clic en **[!UICONTROL Aplicar]**.

   ![Nuevo icono para crear un nuevo grupo de informes](/help/main/c-reports/assets/ap_reporting_groups.png)

Puede usar el complemento [!UICONTROL Ubicación] para filtrar ofertas por ubicación. Utilice la lista [!UICONTROL Grupo de informes] para filtrar ofertas por grupos de informes. Ahora también puede usar la lista [!UICONTROL Grupo de informes] para filtrar por [!UICONTROL Ofertas no asignadas], de modo que puede asignar un grupo de informes a una oferta que no está actualmente asignada a ningún grupo de informes.

Para obtener información sobre la segmentación de una oferta para audiencias específicas, consulte [Ofertas PA de Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Advertencias 

* Es importante comprender que los grupos de informes afectan a cómo [!DNL Target] crea sus modelos. Como resultado, [!DNL Adobe] recomienda usar grupos de informes solo si planea reemplazar o agregar nuevas ofertas mientras una actividad está activa. Si se introduce una nueva oferta en una actividad activa, poner la nueva oferta en un grupo con ofertas similares existentes permite al equipo utilizar los datos ya recopilados para las demás ofertas de su grupo para conocer la nueva oferta. Nunca debe colocar todas las ofertas en un solo grupo de informes.

* Las actividades AP tienen combinaciones de ubicación+oferta (modelables). Cuándo [!DNL Target] registra datos en informes, [!DNL Target] considera estas combinaciones para que quede claro de qué evento (visualización, clic, etc.) provino la oferta.

   Por ejemplo, una actividad puede tener varias ubicaciones y varias ofertas, que pueden superponerse. Si un visitante ve más de una de estas ofertas en diferentes ubicaciones, [!DNL Target] registra solo los datos de esas ofertas. Si el mismo visitante hace clic posteriormente en una oferta, [!DNL Target] registra solo un evento de esa combinación (no para todas las combinaciones).

   Del mismo modo, si el clic proviene de una ubicación diferente, que está presente en una métrica, pero no muestra una oferta, este evento se registra en la actividad, pero no para cualquier combinación de oferta + ubicación. Como resultado, esta oferta no aparece en el grupo de informes de ofertas.

   Este comportamiento se debe a que el clic puede realizarse desde un mbox diferente y no desde el mbox que sirvió a la oferta. Debido a esto, la métrica está asociada con la actividad, pero no con la oferta.

## Visualización de ofertas en un grupo de informes

1. Clic **[!UICONTROL Actividades]**, haga clic en el [!UICONTROL Automated Personalization] actividad de la lista y haga clic en **[!UICONTROL Informes]** para mostrar la pestaña [Nivel de oferta](/help/main/c-reports/personalization-reports/reports-ap.md) informe.

   Si tiene muchas actividades, puede filtrar la lista seleccionando [!UICONTROL Personalización automatizada] en la lista desplegable [!UICONTROL Tipo].

1. Clic **[!UICONTROL Control]** o **[!UICONTROL Objetivos]** en la tabla para mostrar las ofertas desagrupadas y las ofertas dentro de los grupos de informes.

   ![Grupos de ofertas: Control y segmentaciones](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Para obtener información sobre el uso de [!UICONTROL Automated Personalization] informes (incluido el [!UICONTROL Nivel de oferta] report), consulte [Informes de resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


