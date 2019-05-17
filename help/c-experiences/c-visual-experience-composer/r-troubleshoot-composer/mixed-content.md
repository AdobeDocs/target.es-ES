---
description: Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro.
keywords: contenido mixto;seguro;inseguro;chrome;solución de problemas;vec;compositor de experiencias visuales;no garantizado
seo-description: Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro.
seo-title: Habilitar contenido mixto en el navegador
solution: Target
title: Habilitar contenido mixto en el navegador
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Habilitar contenido mixto en el navegador{#enabling-mixed-content-in-your-browser} 

Algunos navegadores no permiten visualizar las páginas donde se combina contenido seguro con contenido no seguro.

## Habilitar contenido mixto en el navegador{#concept_46D022D50280468C9EF6D5DF6EFC911C} 

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

## Habilitar contenido mixto en Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

De manera predeterminada, Firefox bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar [!DNL Target].

<!-- 

target/t_mixed_content_firefox.xml

 -->

1. En Firefox, escriba `about:config` en la barra de direcciones.
1. Reconozca el mensaje de advertencia que muestra Firefox.
1. En la barra de búsqueda, escriba `block_active`.
1. Haga doble clic en ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   El valor cambiará de “Verdadero” a “Falso”. Cuando el valor cambie a “Falso”, habrá terminado.  Se recomienda reiniciar el equipo después de cambiar esta opción.

## Habilitar contenido mixto en Internet Explorer {#task_59E7D13C04DF486C92CD78D0C63DDDE8}

De manera predeterminada, Internet Explorer bloquea las páginas con contenido seguro y no seguro. Se recomienda cambiar esta opción de forma permanente para poder usar Target Standard.

<!-- 

target/t_mixed_content_ie.xml

 -->

1. En Internet Explorer, haga clic en el icono de configuración &gt; **[!UICONTROL Opciones de Internet]**.
1. Abra la pestaña [!UICONTROL Seguridad.]
1. Seleccione **[!UICONTROL Internet]** y, a continuación, **[!UICONTROL Nivel personalizado]**.
1. Seleccione **[!UICONTROL Miscelánea]**.
1. En [!UICONTROL Miscelánea]**, habilite la opción[!UICONTROL Mostrar contenido mixto]**.
1. Haga clic en **[!UICONTROL Aceptar]** &gt; **[!UICONTROL Sí]** &gt; **[!UICONTROL Aplicar]**.

Se recomienda reiniciar el equipo después de cambiar esta opción.

## Habilitar contenido mixto en Chrome   {#task_FF297A08F66E47A588C14FD67C037B3A}

Si va a visitar un sitio a través de una conexión segura, Google Chrome verificará que el contenido de la página web se haya transmitido correctamente.

<!-- 

target/t_mixed_content_chrome.xml

 -->

Consulte [Esta página tiene contenido no seguro](https://support.google.com/chrome/answer/1342714?hl=en) en la Ayuda de Google Chrome.
