---
keywords: vec;compositor de experiencias visuales; vec;iframe;extensión;explorador;faq
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en [!UICONTROL Visual Experience Composer] (VEC). El [!UICONTROL Visual Editing Helper] La extensión del explorador permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo el [!UICONTROL Visual Editing Helper] ¿Extensión?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 8edae6a197a3ac82b85fcce4d99c8b0d5f45c712
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 64%

---

# [!UICONTROL Visual Editing Helper] extensión

El [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensión del explorador para [!DNL Google Chrome] permite cargar sitios web de forma fiable dentro de [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para crear y realizar controles de calidad de experiencias web rápidamente.

>[!IMPORTANT]
>
>Esta nueva extensión sustituye a la [extensión de explorador de VEC Helper de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) anterior. Consulte la nota importante que aparece al principio de ese artículo. Debido a las mejoras de seguridad de Manifest v3, [!DNL Adobe] requiere la descarga de esta nueva extensión para seguir creando visualmente sus sitios web en [!DNL Target].

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* El control de calidad o la fase del cliente no están disponibles para el mundo exterior (el sitio es interno).

El [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] La extensión del explorador para resuelve los problemas de carga de sitios para los que los clientes ahora dependen de la variable [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o extensiones de terceros, como Requestly.

## Ventajas de utilizar [!UICONTROL Visual Editing Helper] extensión

* Todos los encabezados de eliminación de iframes, como `X-Frame-Options` y `Content-Security-Policy`, se eliminan implícitamente del sitio web. No hay necesidad de crear reglas Requestly complicadas.
* Si una página web todavía no contiene la biblioteca at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

  Al usar el [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite sigue presente. Para insertar at.js en el sitio web, desactive el EEC.

* [Ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el [!UICONTROL Enhanced Experience Composer] (CEE).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación del [!UICONTROL Visual Editing Helper] extensión del explorador

1. Vaya a [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensión de explorador en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Clic **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en [!UICONTROL Visual Editing Helper] icono de extensión del explorador ( ![Icono de extensión de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) en la barra de herramientas del navegador Chrome mientras está en VEC o en modo control de calidad.

   El [!UICONTROL Visual Editing Helper] se activa automáticamente cuando se abre un sitio web en [!UICONTROL Target] VEC para la creación de contenido. La extensión no tiene ninguna configuración condicional. La extensión gestiona todas las configuraciones automáticamente, incluida la configuración de cookies de SameSite.

   Para obtener más información sobre la `SameSite=None` corrección del atributo de explorador, consulte “¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?” en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], la extensión carga la última versión de at.js disponible en el [!DNL Target] IU en [!UICONTROL Administration] > [!UICONTROL Implementation] y at.js descarga las bibliotecas de creación.
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale el [!UICONTROL Visual Editing Helper] extensión del explorador.
   * Si at.js o alloy.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
* Si intenta utilizar la nueva extensión y después vuelve a la [extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) y [!DNL Target] no se puede cargar el sitio web, borre todos los datos del explorador y desactive la nueva extensión.

## Preguntas frecuentes

### ¿La extensión, cuando está activa, hace algo cuando se utiliza fuera de? [!DNL Adobe Target] o [!UICONTROL Adobe Journey Optimizer] (AJO)?

La extensión solo se activa cuando el sitio web en cuestión se carga dentro de un iFrame en productos de [!DNL Adobe] ([!DNL Target], [!DNL AJO]). Fuera de este flujo, la extensión no intenta añadir, quitar ni modificar ningún encabezado, ni intenta insertar ningún código dentro del sitio web.

### ¿Qué hace la extensión cuando está activa en el VEC de [!DNL Adobe Target]?

Cuando un sitio web se carga dentro de un iFrame en productos de [!DNL Adobe] ([!DNL Target], [!DNL AJO]), la extensión inserta código (empaquetado con la extensión) en el sitio web y descarga los archivos de ayuda desde el CDN de [!DNL Adobe] para habilitar la creación visual.
