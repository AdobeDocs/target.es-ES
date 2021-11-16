---
keywords: VEC;Compositor de experiencias visuales;visual experience composer;VEC;iframe;extensión;explorador
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el Compositor de experiencias visuales (VEC). La extensión del explorador VEC Helper permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión de ayuda del Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: cf8bb1a438681ccb5bf9e825503f9f929fbcfdbf
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 54%

---

# Extensión del Helper del Compositor de experiencias visuales

La variable [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) La extensión del explorador Helper para Google Chrome permite cargar sitios web de forma fiable dentro del VEC para crear y realizar controles de calidad de experiencias rápidamente.

>[!NOTE]
>
>El explorador VEC Helper es una extensión de Chrome. Esta extensión no es necesaria cuando se utiliza Mozilla Firefox.

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o el sitio del cliente no están disponibles para el mundo exterior (el sitio es interno).
* Utiliza Google Chrome 80+ con directivas de aplicación de cookies SameSite mejoradas. Para obtener más información, consulte [¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite recientemente anunciadas al VEC y EEC?](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

La extensión del explorador VEC Helper para Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen de [!DNL Target] [Compositor de experiencias mejorado](/help/administrating-target/visual-experience-composer-set-up.md#eec) o extensiones de terceros, como Requestly.

## Beneficios del uso de la extensión VEC Helper

* Todos los encabezados de eliminación de iframes, como X-Frame-Options y Content-Security-Policy, se eliminan implícitamente del sitio web. No hay más necesidad de crear complicadas reglas Requestly.
* Si una página web todavía no contiene la biblioteca JavaScript at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

   Tenga en cuenta que, con el Compositor de experiencias mejorado (EEC), la extensión no inyecta at.js, pero la funcionalidad Cookie SameSite sigue presente. Para insertar at.js en la página web, desactive el EEC.

* [Ventanillas móviles](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin [!UICONTROL Compositor de experiencias mejorado] (CEE)
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

1. Vaya a la [Extensión del explorador Adobe Target VEC Helper en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Haga clic en **[!UICONTROL Añadir a Chrome > Añadir extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador VEC Helper (![icono de VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo [control de calidad](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslice el **[!UICONTROL Inserción de bibliotecas de Target]** cambie a la posición &quot;activado&quot; si la página web aún no contiene la variable [!DNL Target] Biblioteca JavaScript at.js.

   La siguiente ilustración muestra el VEC Helper con la configuración de [!UICONTROL Inserción de bibliotecas de Target] habilitada:

   ![VEC Helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   La siguiente ilustración muestra cómo el VEC Helper pregunta si desea que inserte bibliotecas [!DNL Target] en la página para habilitar la creación:

   ![VEC Helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslice el **[!UICONTROL Cookies]** cambie a la posición &quot;activado&quot; para agregar automáticamente la variable `SameSite=None` corrección del navegador de atributos.

   ![Alternar cookies en la extensión del asistente de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obtener más información sobre `SameSite=None` corrección del navegador de atributos, consulte &quot;¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?&quot; en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas

* El indicador de [!UICONTROL inserción de bibliotecas de Target] en la extensión está desactivado de forma predeterminada. Puede habilitar este indicador si desea utilizar el VEC en un sitio que aún no se haya implementado para [!DNL Target].

   Este indicador es una configuración global. El indicador está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por lo tanto, si establece este indicador en &quot;activo&quot; y abre un sitio web que ya se ha implementado con at.js, recibirá un mensaje que le informará de que at.js ya se ha cargado. El Adobe anticipa que la mayoría de los clientes ya tienen at.js implementado en sus páginas y utilizan la configuración predeterminada &quot;desactivado&quot;.

* La extensión carga la última versión de at.js disponible en la [!DNL Target UI] en [!UICONTROL Administración > Implementación].
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma Organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión del explorador VEC Helper.
   * Si at.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
   * Si la extensión está activada y es útil para la carga, los mensajes se muestran cuando la extensión inserte la biblioteca at.js (si es necesario) o ayude a abrir el sitio web de forma fiable dentro del VEC.
