---
keywords: contenido mixto;seguro;inseguro;chrome;solución de problemas;vec;compositor de experiencias visuales;no seguro;http;https;firefox;internet explorer
description: Obtenga información sobre cómo habilitar contenido mixto en [!DNL Chrome], [!DNL Firefox] y [!DNL Edge].
title: Cómo se habilita el contenido mixto en mi explorador
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
TQID: 'https://experienceleague.adobe.com/6Q1UvNmU-vSr9sp3pe2JN-wkjFUMWFxtPkgQegArrVw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 11%
---
# Habilitar contenido mixto en el explorador {#mixed-content}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a habilitar el contenido mixto en [!DNL Google Chrome], [!DNL Mozilla Firefox] y [!DNL Microsoft Edge] para que el **[!UICONTROL Compositor de experiencias visuales]** (VEC) pueda abrir sitios HTTP y sitios que contengan contenido mixto.

>[!ENDSHADEBOX]

Una página contiene contenido mixto cuando se solicita de forma segura a través de HTTPS, pero carga contenido HTTPS y HTTP. El contenido HTTPS es seguro, mientras que el contenido HTTP no lo es, por lo que los exploradores modernos pueden bloquear una página de este tipo o mostrar un mensaje de advertencia.

Cuando el **[!UICONTROL Compositor de experiencias visuales]** (VEC) de [!DNL Adobe Target] intenta abrir una página con contenido mixto, aparece un mensaje de advertencia con instrucciones para deshabilitar el bloqueo en el explorador. Deshabilitar el bloqueo permite abrir un sitio HTTP o un sitio con contenido mixto (HTTPS y HTTP).

![Página de creación de actividad con el mensaje que indica que se debe permitir la carga de scripts de explorador para crear actividades, junto a una ilustración del mensaje de recarga del explorador](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Anteriormente, algunas acciones del paso 1 del flujo de trabajo guiado de tres pasos permanecían disponibles cuando no se permitía el contenido mixto. [!DNL Target] ahora bloquea todas las acciones del paso 1, por lo que el contenido mixto debe habilitarse para que la creación de la actividad pueda continuar.

La configuración de seguridad del explorador puede bloquear el contenido no seguro (HTTP) que se carga en una página o marco seguro (HTTPS), como el VEC. La alternativa a cambiar esta configuración es un sitio web HTTPS. Si el sitio web se ejecuta en un dominio no seguro (HTTP), se debe permitir al VEC cargar contenido mixto activo.

>[!IMPORTANT]
>
>Permitir el contenido mixto afecta únicamente al VEC y no al sitio web activo.

Para obtener más información, consulte [Contenido mixto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) en el sitio web *Mozilla Developer Network* (MDN).

## Habilitar contenido mixto en [!DNL Google Chrome]

[!DNL Chrome] comprueba que el contenido de una página solicitada a través de una conexión segura se haya transmitido correctamente. Consulte &quot;[Administrar advertencias sobre sitios no seguros](https://support.google.com/chrome/answer/99020?hl=es)&quot; en la Ayuda de Google Chrome.

Para usar el VEC con la última versión de [!DNL Chrome] (versión 79.0.3945.117 o posterior), actualice la configuración del sitio de la siguiente manera. Los visitantes del sitio no necesitan completar estos pasos.

1. Haga clic en el icono de bloqueo (precaución) y, a continuación, haga clic en **[!UICONTROL Configuración del sitio]**.

   ![Barra de direcciones de Chrome con el menú de conexión abierto y la configuración del sitio resaltada](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. En **[!UICONTROL Contenido no seguro]**, cambie &quot;Bloquear (predeterminado)&quot; a &quot;Permitir&quot; en la lista desplegable.

   ![Configuración del sitio de Chrome con la lista desplegable de Contenido no seguro abierta y Permitir seleccionados](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Vuelva a cargar la página del VEC.

## Habilitar contenido mixto en [!DNL Mozilla Firefox]

De manera predeterminada, [!DNL Firefox] bloquea las páginas que mezclan contenido seguro con contenido no seguro, por lo que esta configuración debe cambiarse permanentemente para usar [!DNL Target]. Los visitantes del sitio no necesitan completar estos pasos.

1. En [!DNL Firefox], escriba `about:config` en la barra de direcciones.
1. Reconozca el mensaje de advertencia que muestra [!DNL Firefox].

   ![Firefox Continúe con la página de advertencia de precaución para aproximadamente:config con el botón Aceptar el riesgo y continuar](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. En la barra de búsqueda, escriba `block_active`.

   ![Firefox about:config busca block_active mostrando security.mixed_content.block_active_content establecido en true](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Haga doble clic en `security.mixed_content.block_active_content`.

   El valor cambiará de &quot;Verdadero&quot; a &quot;Falso&quot;. Cuando el valor muestra &quot;False&quot;, el cambio se completa.

   ![Firefox sobre:config muestra security.mixed_content.block_active_content establecido en false](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. Reinicie el equipo después de cambiar esta configuración.

## Habilitar contenido mixto en [!DNL Microsoft Edge]

[!DNL Edge] comprueba que el contenido de una página solicitada a través de una conexión segura se haya transmitido correctamente. Para usar el VEC con la última versión de [!DNL Edge], actualice la configuración del sitio de la siguiente manera. Los visitantes del sitio no necesitan completar estos pasos.

1. En [!DNL Edge], haga clic en **[!DNL Microsoft Edge]** en la barra de menús, haga clic en **[!UICONTROL Configuración]** y, a continuación, haga clic en **Cookies y permisos del sitio**.
1. Desplácese hasta **[!UICONTROL Contenido no seguro]** y haga clic en él.
1. Junto a **[!UICONTROL Permitir]**, haz clic en **[!UICONTROL Agregar]**, ingresa el sitio en el que deseas permitir contenido no seguro y luego haz clic en **[!UICONTROL Agregar]**.
1. Vuelva a cargar la página del VEC.
