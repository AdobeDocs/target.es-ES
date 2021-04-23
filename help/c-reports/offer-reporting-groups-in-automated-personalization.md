---
keywords: personalización automatizada;oferta;informes;grupo;grupo de informes
description: Aprenda a utilizar grupos de informes de ofertas en Adobe [!DNL Target] Automated Personalization activities. Using reporting groups, [!DNL Target] crea solo un modelo de personalización para cada grupo de informes.
title: ¿Puedo usar grupos de informes de ofertas en actividades de Automated Personalization?
feature: Informes
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 63%

---

# ![PREMIUM](/help/assets/premium.png) Grupos de informes de ofertas en Personalización automatizada

Información sobre el uso de grupos de informes en actividades [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Los grupos de informes realizan dos funciones clave:

* Permiten ver las ofertas agrupadas en informes de actividad de AP.
* Juegan un papel clave con el funcionamiento de los modelos de personalización [!DNL Target].

Cuando se utilizan grupos de informes, [!DNL Target] crea solo un modelo de personalización para cada grupo de informes en lugar de cada oferta en su actividad AP utilizando los datos de todas las ofertas de ese grupo.

Si la configuración de su actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes pueden ayudar a reducir los requisitos de datos para el uso de la personalización automatizada. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para aquellas actividades de AP en las que se introducen nuevas ofertas con regularidad.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Agrupar todas las ofertas o agrupar ofertas con tasas de conversión muy diferentes probablemente reduzca la eficacia de los modelos de personalización [!DNL Target].

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

1. (Condicional) Para asignar la oferta seleccionada a un grupo de informes existente, seleccione **[!UICONTROL Existente]**, seleccione el grupo de informes deseado en la lista desplegable y haga clic en **[!UICONTROL Aplicar]**.

   O

   Para crear un nuevo grupo de informes al que asignar la oferta seleccionada, elija **[!UICONTROL Nuevo]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Aplicar]**.

   ![](assets/ap_reporting_groups.png)
