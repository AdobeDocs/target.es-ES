---
keywords: oferta de redireccionamiento;crear oferta de redireccionamiento;añadir oferta de html;Pasar todos los parámetros de URL en el redireccionamiento
description: Aprenda a crear ofertas de redireccionamiento para guiar fácilmente a los navegadores a nuevas páginas.
title: ¿Cómo Se Crean Ofertas De Redireccionamiento?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: 751a8d97-2e35-4527-99f3-d7a42c104fcb
source-git-commit: 4b57712b838906611702db521b51af84077501e6
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 24%

---

# Crear ofertas de redireccionamiento

Aprenda a crear ofertas de redireccionamiento para guiar fácilmente a los navegadores a nuevas páginas.

>[!NOTE]
>
>Este artículo contiene información sobre las actualizaciones realizadas en la interfaz de usuario [!DNL Target] que actualmente forma parte de un programa de Beta. El equipo [!DNL Adobe Target] a menudo habilita nuevas características para clientes seleccionados con fines de prueba y comentarios. Una vez completado el período de prueba, estas características se habilitarán para todos los clientes en futuras versiones de [!DNL Target] y se anunciarán en [notas de la versión](/help/main/r-release-notes/release-notes.md).

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la B. Configure una actividad [!UICONTROL A/B Test] con dos experiencias: una que apunte a la página A predeterminada y otra que redirija a la página B. La oferta está configurada para redirigir al visitante a una página diferente.

>[!NOTE]
>
> * Las ofertas de redireccionamiento se pueden crear en la página [!UICONTROL Offers] > [!UICONTROL Code Offers] o en el [Compositor de experiencias basadas en Forms](/help/main/c-experiences/form-experience-composer.md). No puede crear ni aplicar ofertas de redireccionamiento en [!UICONTROL Visual Experience Composer] (VEC). El contenido se inserta en las ubicaciones de solicitud [!DNL Target], por lo que es muy probable que estas ubicaciones no sean apropiadas para una solicitud [!DNL Target] global.
>
>* AJAX No se pueden usar ofertas de redireccionamiento en mboxes de (`mboxUpdate`).
>
>* Para redireccionar ofertas en actividades que utilizan [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Ver [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Este proceso permite a los visitantes utilizar el botón Atrás en sus navegadores.

>[!NOTE]
>
>Si desea pasar el valor de referente de la página de aterrizaje, utilice una oferta de HTML en lugar de una oferta de redirección.

## Crear una oferta de redireccionamiento desde la página [!UICONTROL Code Offers]

1. Haga clic en **[!UICONTROL Offers]** y luego seleccione la ficha **[!UICONTROL Code Offers]**.
1. Haga clic en **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Assets].

1. (Condicional) Si tiene una [cuenta de Target Premium](/help/main/c-intro/intro.md#premium), seleccione el [espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) que desee.

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Asegúrese de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **[!UICONTROL Include all URL parameters]:** Active esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También desea que se pasen los parámetros dinámicos en la dirección URL, ya que este método es la forma de rastrear si las personas llegaron al sitio por correo electrónico, anuncio de banner, anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro URL fue `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Necesario para redirigir a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Crear una oferta de redireccionamiento usando [!UICONTROL Form-Based Experience Composer]

1. Al crear una actividad con [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md), seleccione la ubicación para mostrar la sección **[!UICONTROL Content]**.
1. Haga clic en la lista desplegable **[!UICONTROL Content]**, luego en el icono **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, por último, en **[!UICONTROL Change Redirect Offer]**.
1. Haga clic en **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Escriba un nombre descriptivo para la oferta.

   Un nombre descriptivo le ayuda a usted y a otros a encontrar rápidamente la oferta en la biblioteca [!UICONTROL Assets].

1. Especifique la dirección URL del contenido único o del destino al que desea redirigir. Esta URL debe ser una URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Asegúrese de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

   * **[!UICONTROL Include all URL parameters]:** Deslice el conmutador para habilitar esta opción si desea que todos los parámetros de URL presentes en la página anterior se propaguen a la página a la que se redirige.

     Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También desea que se pasen los parámetros dinámicos en la dirección URL, ya que este método es la forma de rastrear si las personas llegaron al sitio por correo electrónico, anuncio de banner, anuncio de búsqueda o de forma orgánica. Al habilitar esta opción, su oferta de redireccionamiento en la página `https://www.mycompany.com/mens.html?emailId=123` se convierte automáticamente en `https://www.mycompany.com/mensShirts.html?emailId=123` cuando todo lo que ingresó en el cuadro URL fue `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Necesario para redirigir a un dominio diferente. Deslice el botón de alternancia para habilitar esta opción si desea que `sessionId` se incluya automáticamente en la redirección. Esta opción solo es necesaria cuando está probando los clics de un correo electrónico o los clics de un dominio a otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

     Si utiliza la configuración de cookies de origen y de terceros, no necesita pasar el ID de sesión de mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

1. Haga clic en **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Consulte con su consultor de implementación antes de iniciar estas pruebas.

## Usar ofertas de redireccionamiento en actividades

Aplicar ofertas de redireccionamiento utilizando [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). Actualmente no puede aplicar ofertas de redireccionamiento usando el [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] es una interfaz no visual y de creación de ofertas que resulta útil para crear experiencias para utilizarlas en las actividades [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Recommendations] cuando [!UICONTROL Visual Experience Composer] no está disponible o su uso no es práctico. Por ejemplo, podría usar [!UICONTROL Form-Based Experience Composer] para crear experiencias que usen ofertas de redireccionamiento.

1. Cree o edite una actividad en [!UICONTROL Form-Based Experience Composer].

   Consulte [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) para obtener instrucciones detalladas paso a paso.

1. Especifique la ubicación deseada y añada los refinamientos de audiencia que sean necesarios.

1. Haga clic en la lista desplegable **[!UICONTROL Content]**, luego en el icono **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) y, por último, en **[!UICONTROL Change Redirect Offer]**.
1. Seleccione la oferta de redirección que desee en el cuadro de diálogo [!UICONTROL Select Redirect Offer] y haga clic en **[!UICONTROL Add]**.
1. Termine de configurar la actividad.
