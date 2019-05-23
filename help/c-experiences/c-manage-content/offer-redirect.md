---
description: La oferta de redireccionamiento hace que un navegador redirija a una página nueva.
keywords: oferta de redireccionamiento;crear oferta de redireccionamientoa;añadir oferta de html;Pasar los parámetros de URL en el redireccionamiento;Pasar mboxSessionId en el redireccionamiento (solo cuando el redireccionamiento va a un dominio diferente)
seo-description: La oferta de redireccionamiento hace que un navegador redirija a una página nueva.
seo-title: Crear ofertas de redireccionamiento
solution: Target
title: Crear ofertas de redireccionamiento
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# Crear ofertas de redireccionamiento{#create-redirect-offers}

La oferta de redireccionamiento hace que un navegador redirija a una página nueva.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En ese caso, la prueba A/B compara la página A con la B. Configure una campaña de prueba A/B con dos experiencias: una que apunte a la página A predeterminada y otra que redirija a la página B. La oferta se configura para redirigir al visitante a una página distinta.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>No se pueden usar las ofertas de redireccionamiento en los mboxes de Ajax ( `mboxUpdate`).

>[!NOTE]
>
>Para redireccionar ofertas en actividades que utilizan A4T, su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

Para obtener información sobre la configuración de una experiencia de redireccionamiento, consulte [Redireccionar a una URL](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el método `window.location.replace();`, de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Esto permite que el visitante siga usando el botón de retorno del navegador.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Si se desea pasar el valor de referente de la página de aterrizaje, se recomienda usar una oferta HTML en lugar de una oferta de redireccionamiento.

**Para crear una oferta de redireccionamiento:**

1. Haga clic en **[!UICONTROL Ofertas]** y seleccione la pestaña **Ofertas de código[!UICONTROL .]**
1. Haga clic en **[!UICONTROL Crear]** &gt; **[!UICONTROL Oferta de redireccionamiento]**.
1. Escriba el nombre de una oferta.
1. Escriba la dirección URL del contenido único o del destino al que quiera dirigir el redireccionamiento. Debe ser una dirección URL absoluta.

   >[!NOTE]
   >
   >Las ofertas de redireccionamiento generan un bucle infinito si la URL de redireccionamiento también califica al usuario para la misma actividad. Debe asegurarse de que el usuario no vuelva a ser calificado para la actividad después de ser redirigido.

1. Seleccione las opciones que quiera para personalizar la oferta de redireccionamiento:

* **Incluir todos los parámetros de URL:** marque esta casilla si quiere que todos los parámetros de URL presentes en la página anterior se propaguen en la página a la que se redirige.

   Por ejemplo, imagine que quiere redirigir a las personas que están en una página para hombres directamente a una página de categoría de camisetas para hombres. También quiere que los parámetros dinámicos de la dirección URL se transmitan porque es su manera de hacer un seguimiento de si las personas han llegado al sitio web a través del correo electrónico, de publicidad tipo titular, de un anuncio de búsqueda o de forma orgánica. Al marcar esta casilla, su oferta de redireccionamiento de la página [!DNL `https://www.mycompany.com/mens.html?emailId=123`] se convertirá automáticamente en [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] si todo lo que insertó en el cuadro de URL fue [!DNL `https://www.mycompany.com/mensShirts.html`].

* **Pasar ID de sesión mbox (requerido para redirigir a un dominio diferente):** marque esta casilla si quiere que el identificador `sessionId` se incluya automáticamente en el redireccionamiento. Solo es necesario si está realizando una prueba de los clics desde un correo electrónico o de los clics de un dominio u otro. El parámetro `sessionId` coincide con la cookie del visitante para que pueda realizarse un seguimiento del visitante y mostrar el contenido adecuado.

   Si usa la configuración de cookie de origen y de terceros, no tiene que pasar ID de sesión mbox al cruzar dominios. Este identificador se conserva en la cookie de terceros, por lo que no es necesario en la dirección URL.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Consulte con su asesor de implementación antes de iniciar estas pruebas.

## Vídeo de capacitación: El repositorio de contenido (4:56)

Este vídeo incluye información sobre la administración de contenido.

* Conexión entre la [biblioteca de activos de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/creative_cloud.html) y la biblioteca de contenido de Target
* Ofertas HTML personalizadas
* Oferta HTML personalizada en el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/17387)
