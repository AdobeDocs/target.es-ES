---
keywords: optimización;personalización;adobe recorrido optimizer;ajo;casos de uso;escenarios;cambio de contenido/prueba ab;atributo de perfil;cambiar imagen;intercambiar imagen
description: Libere los secretos para aplicar pruebas A/B a los cambios de contenido en Adobe Journey Optimizer
title: Cambios de contenido mediante pruebas A/B en  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: a8d1ad897972edd4263901d411f57b4d22fdd1eb
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 1%

---

# Cambios de contenido mediante pruebas A/B en [!DNL Adobe Journey Optimizer]

Este caso de uso le ayuda a desbloquear los secretos para aplicar cambios efectivos en el contenido de las pruebas A/B en [!DNL Adobe Journey Optimizer].

Este caso de uso muestra cómo realizar tareas familiares, como pruebas A/B con una [actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), utilizando [!DNL Journey Optimizer] en lugar de [!DNL Adobe Target].

Este caso de uso se ha diseñado para mostrar cómo realizar tareas familiares que podría haber realizado con [!DNL Adobe Target], pruebas A/B con una [actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), pero con [!DNL Journey Optimizer].

## Ventajas y valor

* **Optimizar la eficacia del contenido**: descubra qué elementos y variaciones de contenido interesan más a sus clientes, lo que aumenta la participación y las conversiones.
* **Decisiones basadas en datos**: Aproveche los datos para tomar decisiones informadas en su estrategia de contenido, lo que garantiza el máximo impacto.
* **Experiencia del usuario personalizada**: Adapte el contenido para satisfacer las preferencias y necesidades únicas de todos los segmentos de audiencia.

## Posibles escenarios

* Una compañía de ropa aumentó las conversiones probando varias imágenes y personalizando las páginas de aterrizaje de la campaña con los nombres de los usuarios en el texto de la llamada a la acción.

* Una empresa de comercio electrónico descubrió que sus miembros más fieles al oro tenían tasas de conversión más altas probando varias descripciones de productos e imágenes en una página de aterrizaje de campaña, lo que provocó un aumento de las ventas.

## Pasos

>[!NOTE]
>
>Las instrucciones de esta sección resaltan los pasos necesarios para cambiar una imagen y utilizar atributos de perfil para personalizar los mensajes de texto. Para obtener más información sobre las opciones disponibles en el diseñador web de [!DNL Journey Optimizer], consulte [Editar contenido web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} en la *documentación de Journey Optimizer*.
>
>El vídeo de la parte inferior de la página es especialmente útil.

Realice los siguientes pasos para optimizar una página web probando varias imágenes y personalizando los mensajes con los nombres de los usuarios mediante un script de perfil:

1. En [!DNL Adobe Journey Optimizer], haga clic en **Campañas** en el carril izquierdo para mostrar la página [!UICONTROL Campaigns].

   ![Página de aterrizaje de Adobe Journey Optimizer con la pestaña Campañas resaltada.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Haga clic en **[!UICONTROL Create Campaign]** en la esquina superior derecha de la página [!UICONTROL Campaigns].

1. Seleccione **[!UICONTROL Scheduled - Marketing]** (el valor predeterminado) y luego haga clic en **Crear** para mostrar la página de detalles de [!UICONTROL Campaign].

   ![Página de detalles de la campaña en Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. En la sección **[!UICONTROL Properties]**, proporcione un nombre descriptivo y una descripción opcional para la campaña.

1. (Condicional) En la sección **[!UICONTROL Audience]**, haga clic en **[!UICONTROL Select Audience]** y elija la audiencia que desee.

   En este caso de uso, puede activar la campaña de [!UICONTROL All Visitors] (valor predeterminado).

1. En la sección **[!UICONTROL Action]**, elija **[!UICONTROL Web]** en la lista desplegable **[!UICONTROL Action]** y, a continuación, seleccione o cree una nueva configuración web.

   Una configuración web, o superficie de canal, es una configuración definida por un administrador del sistema. La configuración web contiene todos los parámetros técnicos para enviar el mensaje, como el parámetro de encabezado, subdominio, aplicaciones móviles, etc.

   Para obtener más información, consulte [Configurar superficies de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} en la *documentación de Journey Optimizer*.

1. En la sección **[!UICONTROL Action]**, haga clic en **[!UICONTROL Edit Content]** para abrir el sitio web en el diseñador web [!DNL Journey Optimizer].

   Se necesitan dos o más experimentos para las pruebas A/B. Puede utilizar la página de inicio existente como el primer experimento. Los pasos siguientes explican cómo configurar un segundo experimento.

   ![Página de aterrizaje de yoga en el sitio web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Para crear un experimento con el fin de determinar qué contenido funciona mejor, haga clic en **[!UICONTROL Create Experiment]**.

   Los experimentos de contenido permiten variar el contenido, el asunto o el remitente del mensaje para definir varios tratamientos y determinar la mejor combinación para las audiencias. Para obtener más información, consulte [Crear un experimento de contenido](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} en la *documentación de Journey Optimizer*.

1. Seleccione una métrica de éxito y haga clic en Acción.

   Haga clic en los iconos de Ayuda para obtener más información y vínculos a artículos relevantes.

1. Haga clic en **[!UICONTROL Add Treatment]** y luego en **[!UICONTROL Create]**.

   En este caso de uso, puede dejar la distribución en el 50 % para cada experimento.

1. En la página de detalles de [!UICONTROL Campaign], en **[!UICONTROL Action]**, haga clic en **[!UICONTROL Edit Content]**.

1. Haga clic en Web en Tratamiento B

   En este caso de uso, mantenga [!UICONTROL Treatment A] sin cambios para usar la experiencia original como la primera experiencia en la prueba A/B.

1. Haga clic en **[!UICONTROL Edit Web Page]** en el carril derecho.

   ![Editar página de contenido en la página de aterrizaje de Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Para cambiar la imagen a pantalla completa, haga clic en la imagen que desee cambiar y, a continuación, haga clic en el botón **[!UICONTROL Choose Image]**.

   ![Elegir botón de imagen](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Busque y seleccione la imagen que desee y luego haga clic en **[!UICONTROL Use This Image]**.

   ![Nueva imagen en la página de Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Para personalizar el mensaje con los nombres de los usuarios mediante atributos de perfil, haga clic en el texto que desee personalizar y, a continuación, haga clic en **[!UICONTROL Add Personalization]** para mostrar la página [!UICONTROL Add Personalization].

   ![Botón Agregar Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Para obtener más información sobre los atributos de perfil, consulte [Introducción al editor de personalización](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} en la *documentación de Journey Optimizer*.

1. Busque y haga clic en el signo más para agregar el atributo de perfil &quot;nombre&quot;, ajuste el texto como desee y haga clic en **[!UICONTROL Save]**.

   ![Agregar atributo de perfil para el nombre](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Para obtener más información, consulte [Introducción al editor de personalización](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} en la *documentación de Journey Optimizer*.

1. Haga clic en la flecha hacia atrás de la esquina superior izquierda para volver al diseñador web.

   ![Flecha atrás](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Haz clic en **[!UICONTROL Review to Activate]**, asegúrate de que todo se ve según lo esperado y luego haz clic en **Activar**.

## Ver informes

Haga clic en el botón [!UICONTROL Reports] y luego haga clic en el período de informe deseado:

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

Para obtener más información, consulte [Introducción a la nueva interfaz de informes](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} en la *documentación de Journey Optimizer*.

>[!MORELIKETHIS]
>
>[Editar contenido web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} en la *documentación de Journey Optimizer*
>[Vídeo explicativo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content#video){target=_blank} en la *documentación de Journey Optimizer*
>[Crear una campaña](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} en *Tutorials de Journey Optimizer*

