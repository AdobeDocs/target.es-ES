---
keywords: optimización;personalización;adobe recorrido optimizer;ajo;casos de uso;escenarios;cambio de contenido/prueba ab;atributo de perfil;cambiar imagen;intercambiar imagen
description: Libere los secretos para aplicar pruebas A/B a los cambios de contenido en Adobe Journey Optimizer
title: Cambios de contenido mediante pruebas A/B en  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: bbf56b2d041ea6537116d900278242a7a679dedd
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---

# Cambios de contenido mediante pruebas A/B en [!DNL Adobe Journey Optimizer]

Este caso de uso le ayuda a desbloquear los secretos para aplicar cambios efectivos en el contenido de las pruebas A/B en [!DNL Adobe Journey Optimizer].

## Escenario

Una compañía de ropa aumentó las conversiones probando varias imágenes y personalizando las páginas de aterrizaje de la campaña con los nombres de los usuarios a partir de sus atributos de perfil.

## Ventajas y valor

* **Optimizar la eficacia del contenido**: descubra qué elementos y variaciones de contenido interesan más a sus clientes, lo que aumenta la participación y las conversiones.
* **Decisiones basadas en datos**: Aproveche los datos para tomar decisiones informadas en su estrategia de contenido, lo que garantiza el máximo impacto.
* **Experiencia del usuario personalizada**: Adapte el contenido para satisfacer las preferencias y necesidades únicas de todos los segmentos de audiencia.

## Instrucciones paso a paso

Siga estos pasos para optimizar una página web probando varias imágenes y personalizando los mensajes con los nombres de los usuarios:

1. En [!DNL Adobe Journey Optimizer], haga clic en **Campañas** en el carril izquierdo para mostrar la página [!UICONTROL Campaigns].

   ![Página de aterrizaje de Adobe Journey Optimizer con la pestaña Campañas resaltada.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Haga clic en **[!UICONTROL Create Campaign]** en la esquina superior derecha de la página [!UICONTROL Campaigns].

1. Seleccione **[!UICONTROL Scheduled - Marketing]** (el valor predeterminado) y luego haga clic en **Crear** para mostrar la página de detalles de [!UICONTROL Campaign].

   ![Página de detalles de la campaña en Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. Proporcione un nombre descriptivo y una descripción opcional para la campaña.

1. (Condicional) Haga clic en **[!UICONTROL Select Audience]** y elija las audiencias que desee.

   Para este caso de uso, elegimos activar la campaña para todos los visitantes (opción predeterminada).

1. Elija **[!UICONTROL Web]** de la lista desplegable **[!UICONTROL Action]** y, a continuación, seleccione o cree una nueva configuración web.

   Una configuración web, o superficie de canal, es una configuración que ha definido un administrador del sistema. La configuración web contiene todos los parámetros técnicos para enviar el mensaje, como el parámetro de encabezado, subdominio, aplicaciones móviles, etc.

   Para obtener más información, consulte [Configurar superficies de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} en la *documentación de Journey Optimizer*.

1. Haga clic en **[!UICONTROL Edit Content]** para abrir el sitio web en el diseñador web [!DNL Journey Optimizer].

   ![Página de aterrizaje de yoga en el sitio web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Haga clic en **[!UICONTROL Edit Web Page]** en el carril derecho.

   ![Editar página de contenido en la página de aterrizaje de Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Para cambiar la imagen a pantalla completa, haga clic en la imagen que desee cambiar y, a continuación, haga clic en el botón **[!UICONTROL Choose Image]**.

   ![Elegir botón de imagen](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Busque y seleccione la imagen que desee y luego haga clic en **[!UICONTROL Use This Image]**.

   ![Nueva imagen en la página de Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Para personalizar el mensaje con los nombres de los usuarios mediante atributos de perfil, haga clic en el texto que desee personalizar y, a continuación, haga clic en **[!UICONTROL Add Personalization]** para mostrar la página [!UICONTROL Add Personalization].

   ![Botón Agregar Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

1. Busque y seleccione el atributo de perfil &quot;nombre&quot;, ajuste el texto como desee y haga clic en **[!UICONTROL Save]**.

   ![Agregar atributo de perfil para el nombre](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Para obtener más información, consulte [Introducción al editor de personalización](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} en la *documentación de Journey Optimizer*.

1. Haga clic en la flecha hacia atrás de la esquina superior izquierda para volver al diseñador web.

   ![Flecha atrás](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Haz clic en **[!UICONTROL Review to Activate]**, asegúrate de que todo se ve según lo esperado y luego haz clic en **Activar**.

>[!MORELIKETHIS]
>
>[Editar contenido web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} en la *documentación de Journey Optimizer*
>[Vídeo explicativo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/web-spa#video){target=_blank} en la *documentación de Journey Optimizer*
>[Crear una campaña](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} en *Tutorials de Journey Optimizer*

