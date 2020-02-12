---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure
description: Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro.
title: Activación de contenido mixto en el navegador
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro.

Si el Compositor de experiencias visuales (VEC) intenta abrir una página con contenido mixto (seguro y no seguro), se muestra un mensaje que indica cómo deshabilitar el bloqueo en el navegador, de modo que pueda abrir un sitio HTTP o un sitio con llamadas mixtas (HTTPS y HTTP).

![](assets/mixed_content_warning.gif)

Anteriormente, cuando el contenido mixto no estaba permitido, al crear actividades se podían realizar algunas acciones en el paso 1 del flujo de trabajo guiado de tres pasos. Ahora, Target bloquea las acciones en el paso 1. Cuando se muestra este mensaje, debe habilitar el contenido mixto antes de continuar.

La configuración de seguridad del navegador podría bloquear el contenido mixto o no seguro (HTTP) que se carga en una página o marco seguro (HTTPS), como VEC. Si no desea deshabilitar la configuración de seguridad del navegador, necesita disponer de un sitio web HTTPS.

Si su sitio web se ejecuta en un dominio no seguro (HTTP), debe permitir que el VEC cargue el contenido mixto activo.

>[!NOTE]
>
>Permitir el contenido mixto afecta únicamente al VEC y no al sitio web publicado.

Para obtener más información, consulte [Contenido mixto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) en el sitio web *Mozilla Developer Network* (MDN).

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Si va a visitar un sitio a través de una conexión segura, Google Chrome verificará que el contenido de la página web se haya transmitido correctamente.

Consulte [Esta página tiene contenido no seguro](https://support.google.com/chrome/answer/1342714?hl=en) en la Ayuda de Google Chrome.

### Vídeo de capacitación: Habilite el VEC en Chrome versión 79.0.3945.117 o posterior (enero de 2020) ![Indicador de información general](/help/assets/overview.png)

Si utiliza el VEC con la versión más reciente de Chrome (versión 79.0.3945.117 o posterior), debe actualizar la configuración del sitio. Los visitantes del sitio no necesitarán completar estos pasos.

>[!VIDEO](https://www.youtube.com/watch?v=6zGCi5Y8eVo)

El vídeo anterior describe los pasos necesarios:

1. Haga clic en el icono de bloqueo o precaución y, a continuación, haga clic en Configuración del sitio.

   ![Configuración del sitio](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Desplácese al contenido no seguro y, a continuación, utilice la lista desplegable para cambiar el valor de Bloque (predeterminado) a Permitir.

   ![Contenido no seguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Vuelva a cargar la página VEC.

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

De manera predeterminada, Firefox bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar [!DNL Target].

1. En Firefox, escriba `about:config` en la barra de direcciones.
1. Reconozca el mensaje de advertencia que muestra Firefox.
1. En la barra de búsqueda, escriba `block_active`.
1. Haga doble clic en ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   El valor cambiará de “Verdadero” a “Falso”. Cuando el valor cambie a “Falso”, habrá terminado.  Se recomienda reiniciar el equipo después de cambiar esta opción.

## Enabling mixed content in Microsoft Internet Explorer {#task_59E7D13C04DF486C92CD78D0C63DDDE8}

De manera predeterminada, Internet Explorer bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar Target.

1. En Internet Explorer, haga clic en el icono de configuración > **[!UICONTROL Opciones de Internet]**.
1. Abra la pestaña [!UICONTROL Seguridad.]
1. Seleccione **[!UICONTROL Internet]** y, a continuación, **[!UICONTROL Nivel personalizado]**.
1. Seleccione **[!UICONTROL Miscelánea]**.
1. En [!UICONTROL Miscelánea]**[!UICONTROL , habilite la opción Mostrar contenido mixto]**.
1. Haga clic en **[!UICONTROL Aceptar]** > **[!UICONTROL Sí]** > **[!UICONTROL Aplicar]**.

Le recomendamos que reinicie el equipo después de cambiar esta configuración.

