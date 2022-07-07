---
keywords: contenido mixto;seguro;inseguro;chrome;solución de problemas;vec;compositor de experiencias visuales;no seguro;http;https;firefox;internet explorer
description: Aprenda a habilitar contenido mixto en Chrome, Firefox y Edge. Puede habilitar el contenido mixto cuando un explorador bloquee la visualización de una página porque el contenido seguro se mezcla con no seguro.
title: Cómo se habilita el contenido mixto en mi explorador
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 5e6bb16ad752b85e9a7dad088d15f5f6d3897ee9
workflow-type: ht
source-wordcount: '593'
ht-degree: 100%

---

# Habilitación del contenido mixto en el navegador

El contenido mixto se produce si la solicitud inicial es segura a través de HTTPS, pero el contenido HTTPS *y* HTTP se carga para mostrar la página web. El contenido HTTPS es seguro. El contenido HTTP no es seguro.

Los exploradores modernos pueden bloquear la visualización de una página o mostrar mensajes de advertencia si el contenido seguro se mezcla con contenido no seguro.

Si el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] intenta abrir una página con contenido mixto. Este mensaje le informa sobre cómo deshabilitar el bloqueo en su explorador. Deshabilitar el bloqueo le permite abrir un sitio HTTP o un sitio que tenga llamadas mixtas (HTTPS y HTTP).

![Advertencia de contenido mixto](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Anteriormente, cuando el contenido mixto no estaba permitido, al crear actividades se podían realizar algunas acciones en el paso 1 del flujo de trabajo guiado de tres pasos. [!DNL Target] Ahora, bloquea las acciones en el paso 1. Cuando se muestra este mensaje, debe habilitar el contenido mixto antes de seguir creando la actividad.

La configuración de seguridad del navegador podría bloquear el contenido mixto o no seguro (HTTP) que se carga en una página o marco seguro (HTTPS), como VEC. Si no desea deshabilitar la configuración de seguridad del navegador, debe disponer de un sitio web HTTPS.

Si su sitio web se ejecuta en un dominio no seguro (HTTP), debe permitir que el VEC cargue el contenido mixto activo.

>[!NOTE]
>
>Permitir el contenido mixto afecta únicamente al VEC y no al sitio web publicado.

Para obtener más información, consulte [Contenido mixto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) en el sitio web *Mozilla Developer Network* (MDN).

## Habilitar contenido mixto en Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si va a visitar un sitio a través de una conexión segura, Chrome verificará que el contenido de la página web se haya transmitido correctamente.

Consulte “[Esta página tiene contenido no seguro](https://support.google.com/chrome/answer/1342714?hl=es)” en la Ayuda de Google Chrome.

Si utiliza el VEC con la última versión de Chrome (versión 79.0.3945.117 o posterior), debe actualizar la configuración del sitio. Los visitantes del sitio no necesitan completar estos pasos.

1. Haga clic en el icono de bloqueo (precaución) y, a continuación, haga clic en **[!UICONTROL Configuración del sitio]**.

   ![Configuración del sitio](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Desplácese hasta **[!UICONTROL Contenido no seguro]** y, a continuación, utilice la lista desplegable para cambiar “Bloquear (predeterminado)” por “Permitir”.

   ![Contenido no seguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Vuelva a cargar la página del VEC.

## Habilitar contenido mixto en Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

De manera predeterminada, Firefox bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar [!DNL Target]. Los visitantes del sitio no necesitan completar estos pasos.

1. En Firefox, escriba `about:config` en la barra de direcciones.
1. Reconozca el mensaje de advertencia que muestra Firefox.

   ![Advertencia de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. En la barra de búsqueda, escriba `block_active`.

   ![Configuración de Firefox block_active](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Haga doble clic en ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   El valor cambiará de “Verdadero” a “Falso”. Cuando el valor cambie a “Falso”, habrá terminado.

   ![Seguridad de Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Reinicie el equipo después de cambiar esta configuración.

## Habilitar contenido mixto en Microsoft Edge

Si va a visitar un sitio a través de una conexión segura, Edge verificará que el contenido de la página web se haya transmitido correctamente.

Si utiliza el VEC con la última versión de Edge, debe actualizar la configuración del sitio. Los visitantes del sitio no necesitan completar estos pasos.

1. Haga clic en el icono de bloqueo (precaución) y, a continuación, haga clic en **[!UICONTROL Permisos del sitio]**.

   ![Permisos del sitio en Microsoft Edge](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Desplácese hasta **[!UICONTROL Contenido no seguro]** y, a continuación, utilice la lista desplegable para cambiar “Bloquear (predeterminado)” por “Permitir”.

   ![Contenido no seguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Vuelva a cargar la página del VEC.
