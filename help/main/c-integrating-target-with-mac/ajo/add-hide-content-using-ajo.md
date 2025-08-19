---
keywords: optimización;personalización;adobe recorrido optimizer;ajo;casos de uso;escenarios;añadir contenido;ocultar contenido;añadir componentes;ocultar componentes
description: Aprenda a agregar u ocultar componentes en la página web mediante  [!DNL Adobe Journey Optimizer].
title: Agregar U Ocultar Componentes A Su Página Web En  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# Agregar u ocultar componentes a la página web

Este caso de uso le ayuda a desbloquear los secretos para aplicar cambios efectivos en el contenido de las pruebas A/B en [!DNL Adobe Journey Optimizer].

Este caso de uso muestra cómo realizar tareas familiares, como pruebas A/B con una [actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), utilizando [!DNL Journey Optimizer] en lugar de [!DNL Adobe Target].

Este caso de uso se ha diseñado para mostrar cómo realizar tareas familiares que podría haber realizado con [!DNL Adobe Target], pruebas A/B con una [actividad de prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md), pero con [!DNL Journey Optimizer].

## Ventajas y valor

* **Mejora la participación del usuario**: Capta la atención de los usuarios con un diseño de página optimizado que resalta la información relevante, como las promociones.
* **Mejore la capacidad de detección**: coloque estratégicamente nuevos componentes o contenido en aplicaciones web o móviles para optimizar las acciones y mejorar la navegación.
* **Aumente los puntos de contacto adicionales**: guíe a los usuarios de forma eficaz hacia los eventos de conversión y los objetivos para acelerar el impacto en la empresa.

## Posibles escenarios

* Una compañía de servicios financieros planea agregar un nuevo mosaico en su página de inicio para acceder rápidamente a la calculadora de préstamos, reducir el tiempo de búsqueda y aumentar las solicitudes de préstamos.

* Una compañía de ropa aumentó las conversiones al agregar un nuevo botón de call-to-action en su página web.

## Pasos

>[!NOTE]
>
>Las instrucciones de esta sección resaltan los pasos necesarios para cambiar una imagen y utilizar atributos de perfil para personalizar los mensajes de texto. Para obtener más información sobre las opciones disponibles en el diseñador web de [!DNL Journey Optimizer], consulte [Trabajar con el diseñador web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} en la *documentación de Journey Optimizer*.
>
>El vídeo de la parte inferior de la página es especialmente útil.

Siga estos pasos para agregar componentes u ocultarlos en la página web:

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

   ![Página de aterrizaje de yoga en el sitio web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Para agregar y ocultar un elemento, haga clic en **[!UICONTROL Edit Web Page]** en el carril derecho.

1. Haga clic en el elemento que desee ocultar y, a continuación, haga clic en el botón [!UICONTROL Hide] en el carril derecho.

   El carril derecho muestra la opción que puede realizar en el elemento seleccionado. Estas opciones varían en función del elemento seleccionado.

   ![Botón Ocultar elemento](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

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
>[Trabaje con el diseñador web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} en la *documentación de Journey Optimizer*
>>[Crear una campaña](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} en *Tutoriales de Journey Optimizer*
