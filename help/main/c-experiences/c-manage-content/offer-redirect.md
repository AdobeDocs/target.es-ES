---
keywords: oferta de redireccionamiento;crear oferta de redireccionamientoa;añadir oferta de html;Pasar los parámetros de URL en el redireccionamiento;Pasar mboxSessionId en el redireccionamiento (solo cuando el redireccionamiento va a un dominio diferente)
description: Aprenda a crear ofertas de redireccionamiento en el Adobe  [!DNL Target]  para que un explorador redirija a una página nueva.
title: ¿Cómo Se Crean Ofertas De Redireccionamiento?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 45%

---

# Crear ofertas de redireccionamiento

Las ofertas de redireccionamiento en [!DNL Adobe Target] hacen que un explorador redirija a una página nueva.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la B. Configure una actividad Prueba A/B con dos experiencias: una que apunte a la página A predeterminada y otra que redirija a la página B. La oferta está configurada para redirigir al visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en la página [!UICONTROL Offers] > [!UICONTROL Code Offers] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas de redireccionamiento en el Compositor de experiencias visuales (VEC). El contenido se insertará en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que no sean adecuadas para una solicitud [!DNL Target] global.
>
>* No puede usar ofertas de redireccionamiento en mboxes ajax (`mboxUpdate`).
>
>* Para redireccionar ofertas en actividades que utilizan A4T, su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Esto permite que el visitante siga usando el botón de retorno del navegador.

>[!NOTE]
>
>Si se desea pasar el valor de referente de la página de aterrizaje, se recomienda usar una oferta HTML en lugar de una oferta de redireccionamiento.

## Cree una oferta de redireccionamiento desde la página Ofertas de código

1. Haga clic en **[!UICONTROL Offers]** y luego seleccione la ficha **[!UICONTROL Code Offers]**.

   ![Ficha Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Haga clic en **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca de Assets.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** Deslice el botón de alternancia para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro de URL fuera `https://www.mycompany.com/mensShirts.html`.

   * **Se requiere el paso del id. de sesión de mbox:** para redirigir a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en el redireccionamiento. Esto solo es necesario cuando realiza una prueba de los clics desde un correo electrónico o de los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Save]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Creación de una oferta de redireccionamiento mediante el Compositor de experiencias basadas en formularios

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Content]**.

   ![Sección de contenido en el Compositor de experiencias basadas en formularios](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en la lista desplegable **[!UICONTROL Default Content]** y luego haga clic en **[!UICONTROL Change Redirect Offer]**.

   ![Cambiar opción de oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Haga clic en **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca de Assets.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** Deslice el botón de alternancia para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro de URL fuera `https://www.mycompany.com/mensShirts.html`.

   * **Se requiere el paso del id. de sesión de mbox:** para redirigir a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en el redireccionamiento. Esto solo es necesario cuando realiza una prueba de los clics desde un correo electrónico o de los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Save]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Usar ofertas de redireccionamiento en actividades

Debe aplicar ofertas de redireccionamiento usando [!UICONTROL Form-Based Experience Composer]. Actualmente, no puede aplicar ofertas de redireccionamiento utilizando el VEC.

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en las actividades [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] cuando Visual Experience Composer no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Form-Based Experience Composer] para crear experiencias que usen ofertas de redireccionamiento.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable de la sección **[!UICONTROL Content]** y, a continuación, haga clic en **[!UICONTROL Change Redirect Offer]**.

   ![Cambiar opción de oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Seleccione la oferta de redirección que desee en el cuadro de diálogo [!UICONTROL Select Remote Offer] y haga clic en **[!UICONTROL Done]**.

1. Termine de configurar la actividad.

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios, que puede utilizar para crear ofertas de redireccionamiento.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
