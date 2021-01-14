---
keywords: automated personalization;offer;reporting;group;reporting group
description: Información sobre el uso de grupos de sistemas de informes en actividades de Automated Personalization (AP) en Adobe Target.
title: Grupos de sistemas de informes de oferta en actividades Automated Personalization (AP) en Adobe Target
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 64%

---


# ![PREMIUM](/help/assets/premium.png) Grupos de informes de ofertas en Personalización automatizada{#offer-reporting-groups-in-automated-personalization}

Información sobre el uso de grupos de sistemas de informes en actividades [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Los grupos de informes realizan dos funciones clave:

* Permiten ver las ofertas agrupadas en informes de actividad de AP.
* Desempeñan un papel clave en el funcionamiento de los modelos de personalización [!DNL Target].

Cuando se utilizan grupos de sistemas de informes, [!DNL Target] crea sólo un modelo de personalización para cada grupo de sistemas de informes en lugar de cada oferta de la actividad AP utilizando los datos de todas las ofertas de ese grupo.

Si la configuración de su actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes pueden ayudar a reducir los requisitos de datos para el uso de la personalización automatizada. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para aquellas actividades de AP en las que se introducen nuevas ofertas con regularidad.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Agrupar todas las ofertas o agrupar ofertas con tasas de conversión muy diferentes probablemente reduzca la efectividad de los modelos de personalización [!DNL Target].

>[!NOTE]
>
>Si se remplaza o elimina una oferta de un grupo de modelado particular, el tráfico histórico de la oferta también se elimina del grupo de modelado. En otras palabras, las ofertas eliminadas no contribuyen a los datos que se utilizan para que los modelos de personalización [!DNL Target] aprendan.

**Para configurar grupos de informes:**

1. En la página [!UICONTROL Experiencias] de una actividad AP, haga clic en el icono **[!UICONTROL Administrar contenido]**.

   ![](assets/ap_manage_content.png)

1. Haga clic en la pestaña **[!UICONTROL Ofertas]** en la parte superior del cuadro de diálogo [!UICONTROL Administrar contenido].
1. (Condicional) Agregue experiencias específicas a un grupo de informes pasando el puntero sobre la oferta deseada y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes]**.

   ![](assets/ap_manage_content_2.png)

1. (Condicional) Incluya experiencias en lote en un grupo de informes seleccionando la casilla de las experiencias relevantes y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes]**, en la esquina superior derecha del cuadro de diálogo.

   ![](assets/ap_manage_content_3.png)

1. (Condicional) Para asignar la oferta seleccionada a un grupo de sistemas de informes existente, seleccione **[!UICONTROL Existente]**, seleccione el grupo de sistemas de informes que desee en la lista desplegable y haga clic en **[!UICONTROL Aplicar]**.

   O

   Para crear un nuevo grupo de informes al que asignar la oferta seleccionada, elija **[!UICONTROL Nuevo]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Aplicar]**.

   ![](assets/ap_reporting_groups.png)

