---
keywords: VEC;Compositor de experiencias visuales;visual experience composer;VEC;iframe;extensión;explorador
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en la variable [!UICONTROL Compositor de experiencias visuales] (VEC). La variable [!UICONTROL Ayuda de edición visual] la extensión del explorador permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la variable [!UICONTROL Ayuda de edición visual] ¿Extensión?
feature: Visual Experience Composer (VEC)
source-git-commit: 6fd90da68bfe9a78202e9289dc639d41e3daa48f
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 26%

---

# [!UICONTROL Ayuda de edición visual] Extensión

La variable [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] la extensión del explorador para Google Chrome permite cargar sitios web de forma fiable dentro de [!UICONTROL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) para crear y realizar controles de calidad de experiencias rápidamente.

>[!IMPORTANT]
>
>Esta nueva extensión sustituye a la anterior [Extensión de explorador de VEC Helper de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* El control de calidad o el sitio del cliente no están disponibles para el mundo exterior (el sitio es interno).

La variable [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] la extensión del explorador para Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen de la variable [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o extensiones de terceros, como Requestly.

## Ventajas de usar la variable [!UICONTROL Ayuda de edición visual] Extensión

* Todos los encabezados con eliminación de iframes, como `X-Frame-Options` y `Content-Security-Policy`, se eliminan implícitamente del sitio web. No hay necesidad de crear complicadas reglas Requestly.
* Si una página web todavía no contiene la biblioteca at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

Al usar la variable [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), la extensión no inyecta at.js, pero la funcionalidad Cookie SameSite sigue presente. Para insertar at.js en la página web, desactive el EEC.

* [Ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin [!UICONTROL Compositor de experiencias mejorado] (CEE)
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtenga e instale el [!UICONTROL Ayuda de edición visual] extensión del explorador

1. Vaya a la [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensión del explorador en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Haga clic en **[!UICONTROL Añadir a Chrome]** > **[!UICONTROL Agregar extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión de , haga clic en el botón [!UICONTROL Ayuda de edición visual] icono de extensión del explorador ( ![Icono de extensión de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) en la barra de herramientas del explorador Chrome mientras está en el modo VEC o QA.

   La variable [!UICONTROL Ayuda de edición visual] se activa automáticamente cuando se abre un sitio web en la variable [!UICONTROL Target] VEC para la creación de contenido. La extensión no tiene ninguna configuración condicional. La extensión gestiona todas las configuraciones automáticamente, incluida la configuración de cookies de SameSite.

   Para obtener más información sobre `SameSite=None` corrección del navegador de atributos, consulte &quot;¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?&quot; en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], la extensión carga la última versión de at.js disponible en la [!DNL Target] IU en [!UICONTROL Administración] > [!UICONTROL Implementación] y at.js descarga las bibliotecas de creación.
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en el mismo [!DNL Adobe Experience Cloud] organización en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale el [!UICONTROL Ayuda de edición visual] extensión del explorador.
   * Si at.js o alloy.js aún no están implementados en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
* Si intenta utilizar la nueva extensión y vuelve a la [Extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) y [!DNL Target] no se puede cargar el sitio web, borrar todos los datos del explorador y desactivar la nueva extensión.




