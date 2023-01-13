---
keywords: VEC;Compositor de experiencias visuales;VEC;iframe;extensión;explorador;faq
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el [!UICONTROL Compositor de experiencias visuales] (VEC). La extensión del explorador [!UICONTROL Ayuda de edición visual] le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión [!UICONTROL Ayuda de edición visual]?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 30ad6712d9722854384721ca20d38a605930c4d7
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 83%

---

# Extensión [!UICONTROL Ayuda de edición visual]

La extensión del explorador [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] para Google Chrome permite cargar sitios web de forma fiable dentro del [!UICONTROL Compositor de experiencias visuales] (VEC) de [!UICONTROL Adobe Target] para crear y realizar controles de calidad de experiencias web rápidamente.

>[!IMPORTANT]
>
>Esta nueva extensión sustituye a la [extensión de explorador de VEC Helper de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) anterior. Consulte la nota importante que aparece en la parte superior de ese artículo.

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* El control de calidad o la fase del cliente no están disponibles para el mundo exterior (el sitio es interno).

La extensión de explorador [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] para Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen del [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o de extensiones de terceros, como Requestly.

## Ventajas de usar la extensión [!UICONTROL Ayuda de edición visual]

* Todos los encabezados de eliminación de iframes, como `X-Frame-Options` y `Content-Security-Policy`, se eliminan implícitamente del sitio web. No hay necesidad de crear reglas Requestly complicadas.
* Si una página web todavía no contiene la biblioteca at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

   Al usar el [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite sigue presente. Para insertar at.js en el sitio web, desactive el EEC.

* Las [Ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el [!UICONTROL Compositor de experiencias mejorado] (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtenga e instale la extensión de explorador [!UICONTROL Ayuda de edición visual]

1. Vaya a la [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensión de explorador en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Haga clic en **[!UICONTROL Añadir a Chrome]** > **[!UICONTROL Añadir extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador [!UICONTROL Ayuda de edición visual] (![icono de Extensión de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo control de calidad.

   La [!UICONTROL Ayuda de edición visual] se activa automáticamente cuando se abre un sitio web en el VEC de [!UICONTROL Target] para la creación de contenido. La extensión no tiene ninguna configuración condicional. La extensión gestiona todas las configuraciones automáticamente, incluida la configuración de cookies de SameSite.

   Para obtener más información sobre la `SameSite=None` corrección del atributo de explorador, consulte “¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?” en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], la extensión carga la última versión de at.js disponible en la [!DNL Target] IU en [!UICONTROL Administración] > [!UICONTROL Implementación] y at.js descarga las bibliotecas de creación.
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web usando el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión de explorador [!UICONTROL Ayuda de edición visual].
   * Si at.js o alloy.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
* Si intenta utilizar la nueva extensión y después vuelve a la [extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) y [!DNL Target] no se puede cargar el sitio web, borre todos los datos del explorador y desactive la nueva extensión.

## Preguntas frecuentes

### ¿Hace la extensión, cuando está activa, algo cuando se utiliza fuera de [!DNL Adobe Target] o [!UICONTROL Adobe Journey Optimizer] (AJO)?

La extensión solo se activa cuando el sitio web en cuestión se carga dentro de un iFrame en [!DNL Adobe] products ([!DNL Target], [!DNL AJO]). Fuera de este flujo, la extensión no intenta añadir, quitar ni modificar ningún encabezado y la extensión no intenta insertar ningún código dentro del sitio web.

### ¿Qué hace la extensión cuando está activa en la [!DNL Adobe Target] ¿VEC?

Cuando un sitio web se carga dentro de un iFrame en [!DNL Adobe] products ([!DNL Target], [!DNL AJO]), la extensión inserta código (empaquetado con la extensión) en el sitio web y descarga los archivos de ayuda desde el [!DNL Adobe] CDN para habilitar la creación visual.
