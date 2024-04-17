---
keywords: oferta de redireccionamiento;crear oferta de redireccionamientoa;añadir oferta de html;Pasar los parámetros de URL en el redireccionamiento;Pasar mboxSessionId en el redireccionamiento (solo cuando el redireccionamiento va a un dominio diferente)
description: Obtenga información sobre cómo crear ofertas de redireccionamiento en [!DNL Target] para hacer que un explorador redirija a una página nueva.
title: ¿Cómo Se Crean Ofertas De Redireccionamiento?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
source-git-commit: bd19686d2aa716af64f520fb0be798a300ed9fa3
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# Crear ofertas de redireccionamiento

Creación de ofertas de redireccionamiento en [!DNL Adobe Target] para hacer que un explorador redirija a una página nueva.

>[!NOTE]
>
>Este artículo contiene información sobre las actualizaciones de [!DNL Target] interfaz de usuario que actualmente forma parte de un programa beta. El [!DNL Adobe Target] A menudo, el equipo de habilita nuevas funciones para clientes seleccionados con fines de prueba y comentarios. Una vez completado el periodo de prueba, estas funciones se habilitarán para todos los clientes en el futuro [!DNL Target Standard/Premium] Versiones de y anunciadas en las notas de la versión.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la página B. Configure una [!UICONTROL A/B Test] actividad con dos experiencias: una que señala a la página predeterminada A y otra que redirige a la página B. La oferta está configurada para redirigir al visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en [!UICONTROL Offers] > [!UICONTROL Code Offers] o en la [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas de redireccionamiento en [!UICONTROL Visual Experience Composer] (VEC). El contenido se inserta en [!DNL Target] ubicaciones de solicitudes, por lo que es muy probable que estas ubicaciones no sean adecuadas para una [!DNL Target] solicitud.
>
>* AJAX No se pueden usar ofertas de redireccionamiento en mboxes de la (`mboxUpdate`).
>
>* Para redireccionar ofertas en actividades que utilizan Analytics como fuente de informes (A4T), su implementación debe cumplir ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Este proceso permite a los visitantes utilizar el botón Atrás en sus navegadores.

>[!NOTE]
>
>Si desea pasar el valor de referente de la página de aterrizaje, utilice una oferta de HTML en lugar de una oferta de redirección.

## Cree una oferta de redireccionamiento desde el [!UICONTROL Code Offers] página

1. Clic **[!UICONTROL Offers]**, luego seleccione la **[!UICONTROL Code Offers]** pestaña.

   ![Pestaña Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Clic **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la [!UICONTROL Assets] biblioteca.

1. (Condicional) Si tiene un [Cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Asegúrese de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** Deslice el botón de alternancia para activar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al activar esta opción, se modifica la oferta de redireccionamiento de la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ha introducido en el cuadro URL ha sido `https://www.mycompany.com/mensShirts.html`.

   * **Transferir ID de sesión de mbox:** Necesario para redirigir a un dominio diferente. Deslice el botón de alternancia para activar esta opción si desea que el `sessionId` para que se incluya automáticamente en el redireccionamiento. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Create]**.

>[!NOTE]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Cree una oferta de redireccionamiento utilizando [!UICONTROL Form-Based Experience Composer]

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar el **[!UICONTROL Content]** sección.

   ![Sección Contenido del Compositor de experiencias basadas en formularios](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Haga clic en **[!UICONTROL Default Content]** y haga clic en. **[!UICONTROL Change Redirect Offer]**.

   ![Cambiar opción de oferta de redirección](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Clic **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Cuadro de diálogo Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la [!UICONTROL Assets] biblioteca.

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Asegúrese de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **Incluir todos los parámetros de URL:** Deslice el botón de alternancia para activar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al activar esta opción, se modifica la oferta de redireccionamiento de la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ha introducido en el cuadro URL ha sido `https://www.mycompany.com/mensShirts.html`.

   * **Transferir ID de sesión de mbox:** Necesario para redirigir a un dominio diferente. Deslice el botón de alternancia para activar esta opción si desea que el `sessionId` para que se incluya automáticamente en el redireccionamiento. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Save]**.

>[!NOTE]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Usar ofertas de redireccionamiento en actividades

Debe aplicar ofertas de redireccionamiento utilizando [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). Actualmente no se pueden aplicar ofertas de redireccionamiento utilizando [!UICONTROL Visual Experience Composer] (VEC).

El [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual de creación de ofertas y experiencias que resulta útil para crear experiencias para utilizarlas en [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] actividades cuando el compositor de experiencias visuales no está disponible o su uso no es práctico. Por ejemplo, puede utilizar la variable [!UICONTROL Form-Based Experience Composer] para crear experiencias que utilicen ofertas de redireccionamiento.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable en la **[!UICONTROL Content]** y haga clic en **[!UICONTROL Change Redirect Offer]**.

   ![Cambiar opción de oferta de redirección](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Seleccione la oferta de redirección que desee en [!UICONTROL Select Remote Offer] y haga clic en **[!UICONTROL Done]**.

1. Termine de configurar la actividad.

## Vídeo de formación: Compositor basado en formularios ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo proporciona una demostración de la [!UICONTROL Form-Based Experience Composer], que puede utilizar para crear ofertas de redireccionamiento.

* Cree una actividad con la variable [!UICONTROL Form-Based Experience Composer]
* Comprender cuándo usar el [!UICONTROL Form-Based Experience Composer] frente al [!UICONTROL Visual Experience Composer]
* Usar refinamientos para segmentar una ubicación

>[!VIDEO](https://video.tv.adobe.com/v/17390)