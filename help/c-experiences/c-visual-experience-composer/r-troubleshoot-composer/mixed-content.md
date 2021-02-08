---
keywords: contenido mixto;seguro;inseguro;cromado;solución de problemas;vec;compositor de experiencias visuales;no seguro;http;https;firefox;internet explorer
description: Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro. Obtenga información sobre cómo activar contenido mixto en Chrome, Firefox y Edge.
title: ¿Cómo se habilita el contenido mixto en mi explorador?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 34%

---


# Activación de contenido mixto en el navegador

El contenido mixto se produce si se carga contenido HTTPS (seguro) *y* HTTP (no seguro) para mostrar la misma página web y la solicitud inicial era segura a través de HTTPS.

Los navegadores modernos pueden bloquear la visualización de una página o mostrar mensajes de advertencia si el contenido seguro se combina con contenido no seguro.

Si el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Target] intenta abrir una página con contenido mixto, se muestra un mensaje que muestra cómo deshabilitar el bloqueo en el explorador para que pueda abrir un sitio HTTP o un sitio con llamadas mixtas (HTTPS y HTTP).

![advertencia de contenido mixto](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Anteriormente, cuando el contenido mixto no estaba permitido, al crear actividades se podían realizar algunas acciones en el paso 1 del flujo de trabajo guiado de tres pasos. [!DNL Target]Ahora,  bloquea las acciones en el paso 1. Cuando se muestra este mensaje, debe activar el contenido mixto antes de continuar con la creación de la actividad.

La configuración de seguridad del navegador podría bloquear el contenido mixto o no seguro (HTTP) que se carga en una página o marco seguro (HTTPS), como VEC. Si no desea deshabilitar la configuración de seguridad del navegador, necesita disponer de un sitio web HTTPS.

Si su sitio web se ejecuta en un dominio no seguro (HTTP), debe permitir que el VEC cargue el contenido mixto activo.

>[!NOTE]
>
>Permitir el contenido mixto afecta únicamente al VEC y no al sitio web publicado.

Para obtener más información, consulte [Contenido mixto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) en el sitio web *Mozilla Developer Network* (MDN).

## Habilitar contenido mixto en Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si visita un sitio a través de una conexión segura, Chrome comprueba que el contenido de la página web se haya transmitido de forma segura.

Consulte [Esta página tiene contenido no seguro](https://support.google.com/chrome/answer/1342714?hl=en) en la Ayuda de Google Chrome.

Si utiliza el VEC con la versión más reciente de Chrome (versión 79.0.3945.117 o posterior), debe actualizar la configuración del sitio. Los visitantes al sitio no necesitan completar estos pasos.

1. Haga clic en el icono de bloqueo o precaución y, a continuación, haga clic en **[!UICONTROL Configuración del sitio]**.

   ![Configuración del sitio](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Desplácese hasta **[!UICONTROL Contenido no seguro]** y, a continuación, utilice la lista desplegable para cambiar &quot;Bloquear (predeterminado)&quot; a &quot;Permitir&quot;.

   ![Contenido no seguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Vuelva a cargar la página VEC.

## Habilitar contenido mixto en Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

De manera predeterminada, Firefox bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar [!DNL Target]. Los visitantes al sitio no necesitan completar estos pasos.

1. En Firefox, escriba `about:config` en la barra de direcciones.
1. Reconozca el mensaje de advertencia que muestra Firefox.

   ![Advertencia de Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. En la barra de búsqueda, escriba `block_active`.

   ![Configuración activa del bloque Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Haga doble clic en ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   El valor cambiará de “Verdadero” a “Falso”. Cuando el valor cambie a “Falso”, habrá terminado.

   ![Seguridad de Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Le recomendamos que reinicie el equipo después de cambiar esta configuración.

## Activación de contenido mixto en Microsoft Edge

Si está visitando un sitio a través de una conexión segura, Edge comprueba que el contenido de la página web se haya transmitido de forma segura.

Si utiliza el VEC con la versión más reciente de Edge, debe actualizar la configuración del sitio. Los visitantes al sitio no necesitan completar estos pasos.

1. Haga clic en el icono de bloqueo o precaución y, a continuación, haga clic en **[!UICONTROL Permisos del sitio]**.

   ![Permisos del sitio en Microsoft Edge](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Desplácese hasta **[!UICONTROL Contenido no seguro]** y, a continuación, utilice la lista desplegable para cambiar &quot;Bloquear (predeterminado)&quot; a &quot;Permitir&quot;.

   ![Contenido no seguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Vuelva a cargar la página VEC.