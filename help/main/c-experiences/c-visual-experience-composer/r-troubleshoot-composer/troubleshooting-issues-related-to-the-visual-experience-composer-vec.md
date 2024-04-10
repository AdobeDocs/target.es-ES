---
keywords: Segmentación;compositor de experiencias visuales;vec;solución de problemas del compositor de experiencias visuales;resolución de problemas;tls;tls 1.2
description: Obtenga información sobre cómo solucionar problemas en [!UICONTROL Visual Experience Composer] (VEC).
title: ¿Cómo puedo solucionar problemas relacionados con la [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 24%

---

# Resolución de problemas relacionados con [!UICONTROL Visual Experience Composer]

Los problemas de visualización a veces ocurren en [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) bajo ciertas condiciones.

## Cuando abro mi sitio web en [!UICONTROL Visual Experience Composer], el [!DNL Target] Las bibliotecas de no se cargan. (Solo VEC)   {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] añade dos parámetros (`mboxEdit=1` y `mboxDisable=1`) al abrir el sitio web en [!UICONTROL Visual Experience Composer].

Si su sitio web (especialmente las aplicaciones de una sola página) recorta parámetros o los elimina al pasar de una página a otra (sin volver a cargar la página), la variable [!DNL Target] se interrumpe la funcionalidad y [!DNL Target] Las bibliotecas de no se cargan.

Para evitar este problema, asegúrese de que no recorta ni elimina estos dos parámetros.

## Mi página no se abre en el EEC. O bien, la carga de la página es lenta. Las actividades o experiencias ser cargan lentamente en el VEC. (Solo VEC)   {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Varios problemas pueden afectar al rendimiento de la página en [!UICONTROL Target] compositores de experiencias. Algunos problemas comunes son:

* Usted no tiene un mbox en la página.
* El sitio usa bloqueo de proxy, lo que no permite que la página se abra en ningún compositor de experiencias.
* El sitio no permite ser abierto en un iFrame.

Si se producen problemas en [!UICONTROL Enhanced Experience Composer], intente desactivar la [!UICONTROL Enhanced Experience Composer] y utilice el [!UICONTROL Visual Experience Composer] en su lugar.

Para deshabilitar la variable [!UICONTROL Enhanced Experience Composer], vaya a **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** y apague el **[!UICONTROL Enable Enhanced Experience Composer]** opción.

Algunos usuarios ven el siguiente mensaje de error en la consola:

![Mensaje de error de la consola](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Si ninguno de los [!UICONTROL Visual Experience Composer] ni el [!UICONTROL Enhanced Experience Composer] funciona, utilice una extensión de explorador como [!DNL Requestly] ([!DNL Chrome] o [!DNL Firefox]) o Modifique los encabezados de respuesta (Firefox) que pueden sobrescribir las opciones de encabezado de X-Frames de su sitio y permitir que se carguen en iFrames, lo que habilita el VEC. Si no puede utilizar las extensiones del explorador, utilice el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la variable [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] extensión](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) para [!DNL Google Chrome].


>[!NOTE]
>
>Estos complementos deben usarse solo en el contexto de la edición de VEC.
>
>Para el [!DNL Requestly] , siempre que sea necesario eliminar encabezados, debe hacer una de las siguientes acciones:
>
>* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
>
>* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.
>
>Para el [!UICONTROL Modify Response Header] extensión ([!DNL Firefox]), ya que no puede agregar una regla de URL, debe hacer lo siguiente:
>
>* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.

**Para usar la variable [!DNL Requestly] extensión el [!DNL Chrome] o [!DNL Firefox]:**

1. Desactive la [!UICONTROL Enhanced Experienced Composer].
1. Instale el [!DNL Requestly] extensión de explorador activada [!DNL Chrome] o [!DNL Firefox].
1. Abra la extensión y configúrela de la siguiente manera:
1. Seleccionar **[!UICONTROL Modify headers]**.
1. Introduzca lo siguiente:

   * Nombre de la regla
   * Reglas de modificación

      * Alternar **[!UICONTROL Add]** hasta **[!UICONTROL Remove]**.
      * Alternar **[!UICONTROL Request]** hasta **[!UICONTROL Response]**.
      * Introduzca “X-Frame-Options” como nombre del encabezado.
      * Repita los pasos anteriores e introduzca “x-frame-options” como nombre del encabezado.

        >[!NOTE]
        >
        >Encabezados manipulados mediante [!DNL Requestly] distinguen entre mayúsculas y minúsculas.

      * Cambiar **[!UICONTROL Equals]** hasta **[!UICONTROL Contains]** como condición para la URL de origen e introduzca la URL de la actividad que está intentando cargar en el VEC.

     ![imagen chrome_extension](assets/chrome_extension.png)

1. Haga clic en **[!UICONTROL Save]**.

   ![imagen solicitada](assets/requestly.png)

   Ahora debería poder cargar la página rápidamente con el [!UICONTROL Visual Experience Composer].

**Para usar la variable [!DNL Modify Response Headers] extensión el [!UICONTROL Firefox]:**

1. Instale el [!UICONTROL Modify Response Headers] el [!DNL Firefox] y reinicie el explorador.
1. De su [!DNL Firefox] , seleccione la extensión Modify Response Headers.
1. Haga clic en **[!UICONTROL Preferences]**.
1. Seleccionar **[!UICONTROL Filter]** desde el [!UICONTROL Action] desplegable.
1. En el [!UICONTROL Header Name] , introduzca: **[!UICONTROL X-Frame-Options]**.
1. Repita los pasos 4 y 5 para añadir un filtro con **[!UICONTROL x-frame-options]**.
1. Haga clic en **[!UICONTROL Add]**.
1. Haga clic en **[!UICONTROL Start]**.

![Extensión de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Después de configurar una extensión, abra [!DNL Target]. Las páginas deben cargarse en el [!UICONTROL Visual Experience Composer], incluso si la variable [!UICONTROL Enhanced Experience Composer] está deshabilitada.

## Mi página no se muestra en el VEC (solo VEC)   {#does-not-load}

* La mejor compatibilidad con el VEC está garantizada por la versión más reciente de la extensión: [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Para comprobar si utiliza la versión más reciente, vaya a [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] luego haga clic en [!UICONTROL Details].

* El [!UICONTROL Visual Experience Composer] requiere la creación de bibliotecas para poder realizar modificaciones en la página web. Estas bibliotecas están incrustadas en la biblioteca at.js de y la extensión las descarga desde [!DNL Adobe] cada vez que se utiliza VEC.

  La extensión descarga la biblioteca at.js independientemente de si at.js o [!DNL Adobe Experience Platform Web SDK] ya se incluyen en la página.

  Asegúrese de que no se hayan añadido cambios no válidos a los encabezados at.js configurados en la [!UICONTROL Administration] > [!UICONTROL Implementation] sección.

* Asegúrese de que la página web no bloquee las solicitudes de carga obligatorias cuando estén incrustadas en un iFrame. Esto incluye el uso de directivas CSP de antecesores de marco o código JS personalizado incrustado en el sitio web del cliente, etiquetas meta de HTML o el encabezado x-frame-options.

* Asegúrese de que el Javascript de la página web no interfiera con las bibliotecas de creación. No utilice ni incluya archivos con los siguientes nombres reservados:

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     Además, la anulación accidental de variables o eventos definidos dentro de estos archivos podría provocar problemas con VEC.

* El navegador bloquea una página no segura en un sitio seguro.

  Haga clic en el icono a la izquierda de la dirección URL en la barra de direcciones del explorador y haga clic en **[!UICONTROL Disable protection on this page]**

* Ha escrito una dirección URL no válida.
* Si el sitio web no se carga en el VEC o se comporta de forma inesperada, una posible corrección es aceptar cookies en el sitio web en el explorador antes de intentar cargar el sitio web en [!DNL Target].

## El VEC parece roto cuando utilizo el modo Examinar. (Solo VEC)   {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Al utilizar el modo Examinar, si accede a una dirección URL que no tiene [!DNL Target] bibliotecas implementadas ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=es){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}) o contiene un encabezado de eliminación de fotogramas, el VEC parece roto. Debido a problemas de seguridad del explorador, [!DNL Target] no puede acceder correctamente a la URL a la que ha navegado o la URL del VEC no se actualiza de forma coherente si se carga la página.

Este problema se produce porque VEC carga la página web en un `<iframe>`. Los mecanismos de seguridad actuales de los exploradores impiden que [!DNL Target] La interfaz de usuario no puede acceder a los elementos del marco determinado debido a la política del mismo origen. Los navegadores bloquean los scripts que intentan acceder a un marco con un origen diferente y que incluye información como la `location.href`.

Debe utilizar el nuevo [Extensión de Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (recomendado) o el [extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para inyectar el [!DNL Target] en las páginas para explorarlas de forma óptima.

## Problemas causados por conflictos de CSS en [!UICONTROL Visual Experience Composer]

Compruebe si hay algún archivo CSS que pueda afectar a la visibilidad al cargar la página web en el editor. Por ejemplo, usar la variable `overflow: hidden` La propiedad de en el cuerpo de la página podría provocar problemas de desplazamiento o eventos de clic en el déclencheur que podrían interferir con el menú de creación.
