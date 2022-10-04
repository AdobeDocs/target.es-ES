---
keywords: personalización automatizada;oferta;informes;grupo;grupo de informes
description: Aprenda a utilizar grupos de informes de ofertas en Adobe [!DNL Target] Actividades de Automated Personalization. Uso de grupos de informes, [!DNL Target] crea solo un modelo de personalización para cada grupo de informes.
title: ¿Puedo usar grupos de informes de ofertas en actividades de Automated Personalization?
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) Grupos de informes de ofertas en Personalización automatizada

Información sobre el uso de grupos de informes en [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Los grupos de informes realizan dos funciones clave:

* Permiten ver las ofertas agrupadas en informes de actividad de AP.
* Tienen un papel clave en la forma en que [!DNL Target] función de los modelos de personalización.

Cuando se usan grupos de informes, [!DNL Target] crea solo un modelo de personalización para cada grupo de informes en lugar de cada oferta en su actividad AP utilizando los datos de todas las ofertas de ese grupo.

Si la configuración de su actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes pueden ayudar a reducir los requisitos de datos para el uso de la personalización automatizada. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para aquellas actividades de AP en las que se introducen nuevas ofertas con regularidad.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Agrupar todas las ofertas o agrupar ofertas con tasas de conversión muy diferentes probablemente reduzca la eficacia del [!DNL Target] modelos de personalización.

>[!NOTE]
>
>Si se remplaza o elimina una oferta de un grupo de modelado particular, el tráfico histórico de la oferta también se elimina del grupo de modelado. En otras palabras, las ofertas eliminadas no contribuyen a los datos que se utilizan para la variable [!DNL Target] modelos de personalización para aprender.

**Para configurar grupos de informes:**

1. En el [!UICONTROL Experiencias] de una actividad AP, haga clic en el botón **[!UICONTROL Administrar contenido]** icono.

   ![](/help/main/c-reports/assets/ap_manage_content.png)

1. Haga clic en la pestaña **[!UICONTROL Ofertas]** en la parte superior del cuadro de diálogo [!UICONTROL Administrar contenido].
1. (Condicional) Agregue experiencias específicas a un grupo de informes pasando el puntero sobre la oferta deseada y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes]**.

   ![](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Condicional) Incluya experiencias en lote en un grupo de informes seleccionando la casilla de las experiencias relevantes y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes]**, en la esquina superior derecha del cuadro de diálogo.

   ![](/help/main/c-reports/assets/ap_manage_content_3.png)

1. (Condicional) Para asignar la oferta seleccionada a un grupo de informes existente, seleccione **[!UICONTROL Existente]**, seleccione el grupo de informes que desee en la lista desplegable y haga clic en **[!UICONTROL Aplicar]**.

   O

   Para crear un nuevo grupo de informes al que asignar la oferta seleccionada, elija **[!UICONTROL Nuevo]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Aplicar]**.

   ![](/help/main/c-reports/assets/ap_reporting_groups.png)
