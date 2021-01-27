---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: ¿Puedo utilizar ofertas de redireccionamiento para hacer que un explorador redirija a una nueva página?
title: Crear ofertas de redireccionamiento
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 3456eb3844d37dcc8f2d8a4d0fe713c50e0c234c
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 47%

---


# Crear ofertas de redireccionamiento

Las ofertas de redireccionamiento en [!DNL Adobe Target] hacen que un explorador redirija a una nueva página.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la página B. Configure actividades de prueba A/B con dos experiencias: uno que señala a la página A predeterminada y el otro que redirige a la página B. La oferta está configurada para redirigir el visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en la página [!UICONTROL Ofertas] > [!UICONTROL Ofertas de código] o en el [Compositor de experiencias basado en Forms](/help/c-experiences/form-experience-composer.md). No se pueden crear ni aplicar ofertas de redireccionamiento en el Compositor de experiencias visuales (VEC). El contenido se insertará en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que no sean apropiadas para una solicitud global [!DNL Target].
   >
   >
* No se pueden usar las ofertas de redireccionamiento en los mboxes de Ajax (`mboxUpdate`).
   >
   >
* Para redireccionar ofertas en actividades que utilizan A4T, su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
   >
   >
* Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Esto permite que el visitante siga usando el botón de retorno del navegador.

>[!NOTE]
>
>Si se desea pasar el valor de referente de la página de aterrizaje, se recomienda usar una oferta HTML en lugar de una oferta de redireccionamiento.

## Crear una oferta de redireccionamiento desde la página Ofertas de código

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **[!UICONTROL Ofertas de código]**.

   ![Ficha Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta de redireccionamiento]**.

   ![Cuadro de diálogo Crear Oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca Activos.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** deslice el conmutador para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página redireccionada.

      Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, la oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que especificó en el cuadro de dirección URL sea `https://www.mycompany.com/mensShirts.html`.

   * **Transmitir ID de sesión de mbox:** obligatorio para redireccionar a un dominio diferente. Deslice el conmutador para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esto solo se requiere cuando se prueban clics desde un correo electrónico o clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

      Si utiliza la configuración de cookies individuales y de terceros, no es necesario que pase la ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Creación de una oferta de redirección mediante el Compositor de experiencias basadas en formularios

1. Al crear una actividad con el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), seleccione la ubicación en la que desea mostrar la sección **[!UICONTROL Contenido]**.

   ![Sección Contenido del Compositor de experiencias basadas en formularios](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en la lista desplegable **[!UICONTROL Contenido predeterminado]** y, a continuación, haga clic en **[!UICONTROL Cambiar Oferta de redirección]**.

   ![Cambiar la opción de Oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta de redireccionamiento]**.

   ![Cuadro de diálogo Crear Oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca Activos.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** deslice el conmutador para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página redireccionada.

      Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, la oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que especificó en el cuadro de dirección URL sea `https://www.mycompany.com/mensShirts.html`.

   * **Transmitir ID de sesión de mbox:** obligatorio para redireccionar a un dominio diferente. Deslice el conmutador para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esto solo se requiere cuando se prueban clics desde un correo electrónico o clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

      Si utiliza la configuración de cookies individuales y de terceros, no es necesario que pase la ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Usar ofertas de redireccionamiento en actividades

Debe aplicar ofertas de redireccionamiento mediante el [!UICONTROL Compositor de experiencias basadas en formularios]. Actualmente no puede aplicar ofertas de redireccionamiento mediante el VEC.

El [!DNL Adobe Target] [!UICONTROL Compositor de experiencias basadas en formularios] es una interfaz de creación de ofertas y experiencia no visual que resulta útil para crear experiencias que se pueden usar en [!UICONTROL Pruebas A/B], [!UICONTROL Segmentación de experiencias] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations a10/> actividades cuando el Compositor de experiencias visuales no está disponible o es práctico para su uso. ] Por ejemplo, puede utilizar el [!UICONTROL Compositor de experiencias basadas en formularios] para crear experiencias que utilicen ofertas de redireccionamiento.

1. Cree o edite una actividad en el [!UICONTROL Compositor de experiencias basadas en formularios].

   Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y agregue las refinaciones de audiencia necesarias.

1. Haga clic en la lista desplegable en la sección **[!UICONTROL Contenido]** y, a continuación, haga clic en **[!UICONTROL Cambiar Oferta de redirección]**.

   ![Cambiar la opción de Oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Seleccione la oferta de redireccionamiento que desee en el cuadro de diálogo [!UICONTROL Seleccionar Oferta remota] y haga clic en **[!UICONTROL Listo]**.

1. Termine de configurar la actividad.

## Vídeo de capacitación: Compositor basado en formularios ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios, que puede utilizar para crear ofertas de redireccionamiento.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
