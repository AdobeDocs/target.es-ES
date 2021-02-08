---
keywords: Segmentación;compositor de experiencias visuales;vec;resolución de problemas del compositor de experiencias visuales;resolución de problemas;tls;tls 1.2
description: Obtenga información sobre cómo solucionar problemas que a veces se producen en el Compositor de experiencias visuales (VEC) de Adobe Target en determinadas condiciones.
title: ¿Cómo puedo solucionar problemas relacionados con el Compositor de experiencias visuales?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 89%

---


# Solución de problemas relacionados con el Compositor de experiencias visuales

A veces se producen problemas de visualización en el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) bajo ciertas condiciones.

## Cuando abro mi sitio web en el Compositor de experiencias visuales, las bibliotecas de Target no se cargan. (Solo VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

Target añade dos parámetros (`mboxEdit=1` y `mboxDisable=1`) al abrir el sitio web en el Compositor de experiencias visuales.

Si su sitio web (especialmente las aplicaciones de una sola página) recorta nuestros parámetros o los llega a eliminar al pasar de una página a otra (sin volver a cargar la página), la funcionalidad de Target se rompe y las bibliotecas de Target no se cargan. 
Para evitar este problema, asegúrese de que no recorta ni elimina estos dos parámetros.

## Mi página no se abre en el EEC. O bien, la carga de la página es lenta. Las actividades o experiencias ser cargan lentamente en el VEC. (Solo VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Varios problemas pueden afectar al rendimiento de la página en los compositores de experiencias de Target. Algunos problemas comunes son:

* Usted no tiene un mbox en la página.
* El sitio usa bloqueo de proxy, lo que no permite que la página se abra en ningún compositor de experiencias.
* El sitio no permite ser abierto en un iFrame.

Si ocurren problemas en el Compositor de experiencias mejorado, pruebe desactivar el Compositor de experiencias mejorado y use en cambio el Compositor de experiencias visuales.

Para deshabilitar el Compositor de experiencias mejorado, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y desactive la opción **[!UICONTROL Habilitar el Compositor de experiencias mejorado]**.

Algunos usuarios ven el siguiente mensaje de error en la consola:

![Mensaje de error de la consola](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Si ni el Compositor de experiencias visuales ni el Compositor de experiencias mejorado funcionan, use una extensión del navegador como Requestly (Chrome o Firefox) o Modify Response Headers (Firefox) que pueda sobrescribir las opciones de encabezados de X-Frames en su sitio y permita que se carguen en iFrames, habilitando el VEC. Si no puede usar extensiones del navegador, use el Compositor de formularios.

>[!NOTE]
>
>Además de la siguiente información, puede utilizar la [extensión del explorador Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.


>[!NOTE]
>
>Estos complementos deben usarse solo en el contexto de la edición de VEC.
>
>Para la extensión de Requestly, siempre que sea necesario eliminar encabezados, debe hacer lo siguiente:
>
>* Agregar reglas de URL para la URL que desea abrir en el VEC para que los encabezados se eliminen solo para esas URL.
   >
   >
* Habilitar la regla cuando esté editando en el VEC y deshabilitarla cuando no esté usando el VEC.
>
>
Para la extensión del encabezado de respuesta de modificación (Firefox), ya que no puede agregar una regla de URL, debe hacer lo siguiente:
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

      ![](assets/chrome_extension.png)


1. Haga clic en **[!UICONTROL Guardar]**.

   ![](assets/requestly.png)

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

![](assets/firefox_extension.png)

Después de configurar una extensión, abra Target. Sus páginas ahora deberían cargarse en el Compositor de experiencias visuales, incluso si está deshabilitado el Compositor de experiencias visuales.

## Mi página no se muestra en el VEC (solo VEC)    {#section_87B3BEA4B6174CFDA6C9A69A1A051FA1}

* El navegador no es compatible.
* El navegador bloquea una página no segura en un sitio seguro.

   Haga clic en el icono de la izquierda de la dirección URL en la barra de direcciones del navegador y seleccione **[!UICONTROL Deshabilitar protección en esta página]**.
* Ha escrito una dirección URL no válida.
* La dirección URL que ha indicado no es la predeterminada en la página de configuración de cuenta.

Asegúrese de que esta opción de configuración esté habilitada y luego descargue y actualice mbox.js en su sitio web.

## El VEC parece roto cuando utilizo el modo Examinar. (Solo VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Cuando se usa el modo Examinar, si accede a una dirección URL que no tiene target.js o contiene un encabezado con eliminación de iframes, parece que el Compositor de experiencias visuales no funciona. Debido a problemas de seguridad del navegador, Target no puede acceder a la dirección URL a la que navegó.
