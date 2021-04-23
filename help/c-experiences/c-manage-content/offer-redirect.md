---
keywords: oferta de redireccionamiento;crear oferta de redireccionamientoa;añadir oferta de html;Pasar los parámetros de URL en el redireccionamiento;Pasar mboxSessionId en el redireccionamiento (solo cuando el redireccionamiento va a un dominio diferente)
description: 'Aprenda a crear ofertas de redireccionamiento en Adobe [!DNL Target] para hacer que un navegador redirija a una nueva página. '
title: ¿Cómo Se Crean Ofertas De Redireccionamiento?
feature: Experiencias y ofertas
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 48%

---

# Crear ofertas de redireccionamiento

Las ofertas de redireccionamiento en [!DNL Adobe Target] hacen que un explorador redirija a una nueva página.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la B. Configure una prueba A/B con dos experiencias: una que señala a la página predeterminada A y otra que redirige a la página B. La oferta está configurada para redirigir al visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en la página [!UICONTROL Ofertas] > [!UICONTROL Ofertas de código] o en el [Compositor de experiencias basadas en Forms](/help/c-experiences/form-experience-composer.md). No se pueden crear ni aplicar ofertas de redireccionamiento en el Compositor de experiencias visuales (VEC). El contenido se insertará en las ubicaciones de solicitud [!DNL Target], por lo que lo más probable es que no sean apropiadas para una solicitud global [!DNL Target].
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

## Cree una oferta de redireccionamiento desde la página Ofertas de código

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **[!UICONTROL Ofertas de código]**.

   ![Pestaña Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta de redireccionamiento]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca Activos.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** deslice la opción para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen en la página a la que se redirige.

      Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, la oferta de redireccionamiento de la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que haya introducido en el cuadro URL sea `https://www.mycompany.com/mensShirts.html`.

   * **Pasar ID de sesión de mbox:**  obligatorio para redirigir a un dominio diferente. Deslice la opción para habilitar esta opción si desea que el `sessionId` se incluya automáticamente en el redireccionamiento. Esto solo es necesario si está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

      Si utiliza la configuración de cookies de origen y de terceros, no es necesario que pase el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Crear una oferta de redireccionamiento con el Compositor de experiencias basadas en formularios

1. Al crear una actividad con el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Contenido]**.

   ![Sección Contenido del Compositor de experiencias basadas en formularios](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en la lista desplegable **[!UICONTROL Contenido predeterminado]** y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de redireccionamiento]**.

   ![Opción Cambiar oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Haga clic en **[!UICONTROL Crear]** > **[!UICONTROL Oferta de redireccionamiento]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo permite encontrar la oferta rápidamente en la biblioteca Activos.

1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** deslice la opción para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen en la página a la que se redirige.

      Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, la oferta de redireccionamiento de la página `https://www.mycompany.com/mens.html?emailId=123` se convertirá automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que haya introducido en el cuadro URL sea `https://www.mycompany.com/mensShirts.html`.

   * **Pasar ID de sesión de mbox:**  obligatorio para redirigir a un dominio diferente. Deslice la opción para habilitar esta opción si desea que el `sessionId` se incluya automáticamente en el redireccionamiento. Esto solo es necesario si está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

      Si utiliza la configuración de cookies de origen y de terceros, no es necesario que pase el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Uso de ofertas de redireccionamiento en actividades

Debe aplicar ofertas de redireccionamiento utilizando el [!UICONTROL Compositor de experiencias basadas en formularios]. Actualmente no puede aplicar ofertas de redireccionamiento utilizando el VEC.

El [!DNL Adobe Target] [!UICONTROL Compositor de experiencias basadas en formularios] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en [!UICONTROL Pruebas A/B], [!UICONTROL Segmentación de experiencias] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] actividades 10/> cuando el Compositor de experiencias visuales no está disponible o su uso no es práctico. Por ejemplo, puede usar el [!UICONTROL Compositor de experiencias basadas en formularios] para crear experiencias que usen ofertas de redireccionamiento.

1. Cree o edite una actividad en el [!UICONTROL Compositor de experiencias basadas en formularios].

   Consulte [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada cualquier refinamiento de audiencia según sea necesario.

1. Haga clic en la lista desplegable de la sección **[!UICONTROL Content]** y, a continuación, haga clic en **[!UICONTROL Cambiar oferta de redireccionamiento]**.

   ![Opción Cambiar oferta de redireccionamiento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Seleccione la oferta de redireccionamiento que desee en el cuadro de diálogo [!UICONTROL Seleccionar oferta remota] y haga clic en **[!UICONTROL Listo]**.

1. Termine de configurar la actividad.

## Vídeo de formación: Compositor basado en formularios ![Distintivo tutorial](/help/assets/tutorial.png)

Este vídeo proporciona una demostración del compositor basado en formularios, que puede utilizar para crear ofertas de redireccionamiento.

* Crear una actividad con el Compositor de experiencias basadas en formularios
* Entender cuándo usar el Compositor de experiencias basadas en formularios o el Compositor de experiencias visuales
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)
