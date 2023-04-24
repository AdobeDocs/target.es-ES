---
keywords: Segmentación;compositor de experiencias visuales;vec;resolución de problemas del compositor de experiencias visuales;resolución de problemas;tls;tls 1.2
description: Obtenga información sobre cómo solucionar problemas que a veces ocurren en el Adobe [!DNL Target] Compositor de experiencias visuales (VEC) bajo determinadas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias visuales?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 67%

---

# Resolución de problemas relacionados con el Compositor de experiencias visuales

Los problemas de visualización a veces ocurren en la variable [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) en determinadas condiciones.

## Cuando abro mi sitio web en el Compositor de experiencias visuales, la variable [!DNL Target] las bibliotecas no se cargan. (Solo VEC)   {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Target añade dos parámetros (`mboxEdit=1` y `mboxDisable=1`) al abrir el sitio web en el Compositor de experiencias visuales.

Si su sitio web (especialmente las aplicaciones de una sola página) recorta nuestros parámetros o los llega a eliminar al pasar de una página a otra (sin volver a cargar la página), la funcionalidad de Target se rompe y las bibliotecas de Target no se cargan. 
Para evitar este problema, asegúrese de que no recorta ni elimina estos dos parámetros.

## Mi página no se abre en el EEC. O bien, la carga de la página es lenta. Las actividades o experiencias ser cargan lentamente en el VEC. (Solo VEC)   {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Varios problemas pueden afectar al rendimiento de la página en los compositores de experiencias de Target. Algunos problemas comunes son:

* Usted no tiene un mbox en la página.
* El sitio usa bloqueo de proxy, lo que no permite que la página se abra en ningún compositor de experiencias.
* El sitio no permite ser abierto en un iFrame.

Si ocurren problemas en el Compositor de experiencias mejorado, pruebe desactivar el Compositor de experiencias mejorado y use en cambio el Compositor de experiencias visuales.

Para deshabilitar el Compositor de experiencias mejorado, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y apague la variable **[!UICONTROL Habilitar el Compositor de experiencias mejorado]** .

Algunos usuarios ven el siguiente mensaje de error en la consola:

![Mensaje de error de la consola](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Si ni el Compositor de experiencias visuales ni el Compositor de experiencias mejorado funcionan, use una extensión del navegador como Requestly (Chrome o Firefox) o Modify Response Headers (Firefox) que pueda sobrescribir las opciones de encabezados de X-Frames en su sitio y permita que se carguen en iFrames, habilitando el VEC. Si no puede usar extensiones del navegador, use el Compositor de formularios.

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la [extensión del explorador Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.


>[!NOTE]
>
>Estos complementos deben usarse solo en el contexto de la edición de VEC.
>
>Para la extensión de Requestly, siempre que sea necesario eliminar encabezados, debe hacer lo siguiente:
>
>* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
>
>* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.
>
>Para la extensión del encabezado de respuesta de modificación (Firefox), ya que no puede agregar una regla de URL, debe hacer lo siguiente:
>
>* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.


**Para usar la extensión Requestly en Chrome o Firefox:**

1. Desactive el Compositor de experiencias mejorado.
1. Instale la extensión Requestly del navegador en Chrome o Firefox.
1. Abra la extensión y configúrela de la siguiente manera:
1. Seleccione **[!UICONTROL Modificar encabezados]**.
1. Introduzca lo siguiente:

   * Nombre de la regla
   * Reglas de modificación

      * Cambie de **[!UICONTROL Agregar]** a **[!UICONTROL Eliminar]**.
      * Cambie de **[!UICONTROL Solicitud]** a **[!UICONTROL Respuesta]**.
      * Introduzca “X-Frame-Options” como nombre del encabezado.
      * Repita los pasos anteriores e introduzca “x-frame-options” como nombre del encabezado.

         >[!NOTE]
         >
         >Los encabezados manipulados mediante Requestly distinguen entre mayúsculas y minúsculas.

      * Cambie **[!UICONTROL Es igual a]** por **[!UICONTROL Contiene]** como condición para la dirección URL de origen e introduzca la URL de la actividad que está intentando cargar en el VEC.

      ![imagen chrome_extension](assets/chrome_extension.png)


1. Haga clic en **[!UICONTROL Guardar]**.

   ![imagen requestly](assets/requestly.png)

   Ahora debería poder cargar la página rápidamente con el Compositor de experiencias visuales.

**Para usar la extensión Modify Response Headers en Firefox:**

1. Instale Modify Response Headers en Firefox y reinicie el navegador.
1. Desde las extensiones de Firefox, seleccione la extensión Modify Response Headers.
1. Haga clic en **[!UICONTROL Preferencias]**.
1. Seleccione **[!UICONTROL Filtrar]** en el menú desplegable Acción.
1. En el campo Nombre del encabezado, introduzca: **[!UICONTROL X-Frame-Options]**.
1. Repita los pasos 4 y 5 para añadir un filtro con **[!UICONTROL x-frame-options]**.
1. Haga clic en **[!UICONTROL Agregar]**.
1. Haga clic en **[!UICONTROL Inicio]**.

![imagen firefox_extension](assets/firefox_extension.png)

Después de configurar una extensión, abra Target. Sus páginas ahora deberían cargarse en el Compositor de experiencias visuales, incluso si está deshabilitado el Compositor de experiencias visuales.

## Mi página no se muestra en el VEC (solo VEC)   {#does-not-load}

* El navegador no es compatible.
* El navegador bloquea una página no segura en un sitio seguro.

   Haga clic en el icono de la izquierda de la dirección URL en la barra de direcciones del navegador y seleccione **[!UICONTROL Deshabilitar protección en esta página]**.
* Ha escrito una dirección URL no válida.
* La dirección URL que ha indicado no es la predeterminada en la página de configuración de cuenta.

   Asegúrese de que esta configuración esté habilitada y luego descargue y actualice at.js en su sitio web.

* Si intenta usar la variable [new [!UICONTROL Ayuda de edición visual] Extensión](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) y vuelva a la [Extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) y [!DNL Target] no se puede cargar el sitio web, borrar todos los datos del explorador y desactivar la nueva extensión.

* Si el sitio web no se carga en el VEC o se comporta de forma inesperada, una posible corrección es aceptar cookies en el sitio web del explorador antes de intentar cargar el sitio web en [!DNL Target].

## El VEC parece roto cuando utilizo el modo Examinar. (Solo VEC)   {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Mientras utiliza el modo Examinar, si accede a una dirección URL que no tiene [!DNL Target] bibliotecas implementadas ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}) o contiene un encabezado de trama-buster, el VEC parece roto. Debido a problemas de seguridad del explorador, [!DNL Target] no puede acceder correctamente a la dirección URL a la que navegó o la dirección URL del VEC no se actualiza de forma coherente si la página se carga.

Este problema se produce porque el VEC carga la página web en una `<iframe>`. Los mecanismos de seguridad actuales de los navegadores impiden que [!DNL Target] La interfaz de usuario no puede acceder a los elementos del marco dado debido a la política del mismo origen. Los navegadores bloquean los scripts que intentan acceder a un marco con un origen diferente y que incluyen información como el `location.href`.

Debe usar el nuevo [Extensión de Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (recomendado) o [Extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para inyectar el [!DNL Target] dentro de las páginas para explorarlas de forma óptima.
