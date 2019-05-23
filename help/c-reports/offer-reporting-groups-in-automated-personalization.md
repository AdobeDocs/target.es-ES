---
description: Información sobre el uso de grupos de informes en actividades de Personalización automatizada (AP).
keywords: personalización automatizada;oferta;informes;grupo
seo-description: Información sobre el uso de grupos de informes en actividades de Personalización automatizada (AP).
seo-title: Grupos de informes de ofertas en Personalización automatizada
solution: Target
title: Grupos de informes de ofertas en Personalización automatizada
title-outputclass: premium
topic: Advanced
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
badge: premium
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# ![PREMIUM](/help/assets/premium.png) Grupos de informes de ofertas en Personalización automatizada{#offer-reporting-groups-in-automated-personalization}

Información sobre el uso de grupos de informes en actividades de Personalización automatizada (AP).

Los grupos de informes realizan dos funciones clave:

* Permiten ver las ofertas agrupadas en informes de actividad de AP.
* Tienen un papel esencial en el funcionamiento de los modelos de personalización de Target.

Cuando se utilizan grupos de informes, Target crea en su actividad de AP un único modelo de personalización para cada grupo de informes en vez de para cada oferta, utilizando para ello los datos de todas las ofertas de ese grupo.

Si la configuración de su actividad no tiene datos suficientes para crear un modelo de personalización para cada oferta, los grupos de informes pueden ayudar a reducir los requisitos de datos para el uso de la personalización automatizada. Los grupos de informes también pueden ayudar a resolver el problema de “inicio en frío” de las nuevas ofertas. Lo hacen agrupando ofertas similares, de modo que cada modelo disponga de más datos con los que trabajar. Los grupos de modelado también se pueden utilizar para aquellas actividades de AP en las que se introducen nuevas ofertas con regularidad.

Este enfoque funciona bien si los visitantes responden de la misma manera a todas las ofertas de un grupo. Una práctica recomendada es agrupar aquellas ofertas a las que grupos de visitantes similares responden de forma similar. En otras palabras, agrupe las ofertas con tasas de conversión similares. Nunca debe colocar todas las ofertas en un solo grupo de informes. Si agrupa todas las ofertas, o si agrupa ofertas con tasas de conversión muy diversas, es probable que la efectividad de los modelos de personalización de Target se reduzca.

>[!NOTE]
>
>Si se remplaza o elimina una oferta de un grupo de modelado particular, el tráfico histórico de la oferta también se elimina del grupo de modelado. En otras palabras, las ofertas eliminadas no contribuyen a los datos que los modelos de personalización de Target utilizan para aprender.

**Para configurar grupos de informes:**

1. En la página Experiencias de una actividad de AP, haga clic en el icono **[!UICONTROL Gestionar contenido].**

   ![](assets/ap_manage_content.png)

1. Haga clic en la pestaña **[!UICONTROL Ofertas]** en la parte superior del cuadro de diálogo [!UICONTROL Administrar contenido].
1. (Condicional) Agregue experiencias específicas a un grupo de informes pasando el puntero sobre la oferta deseada y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes].**

   ![](assets/ap_manage_content_2.png)

1. (Condicional) Incluya experiencias en lote en un grupo de informes seleccionando la casilla de las experiencias relevantes y haciendo clic en el icono de la carpeta **[!UICONTROL Grupo de informes], en la esquina superior derecha del cuadro de diálogo.**

   ![](assets/ap_reporting_groups.png)

1. Para asignar la oferta seleccionada a un grupo de informes existente, seleccione **[!UICONTROL Existente]**, elija un grupo de informes en la lista desplegable y luego haga clic en **[!UICONTROL Aplicar]**.

   O

   Para crear un nuevo grupo de informes al que asignar la oferta seleccionada, elija **[!UICONTROL Nuevo]**, asigne un nombre al nuevo grupo de informes y haga clic en **[!UICONTROL Aplicar]**.

   ![](assets/ap_manage_content_3.png)

