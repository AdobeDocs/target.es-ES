---
keywords: VEC;Compositor de experiencias visuales;VEC;iframe;extensión;explorador
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el Compositor de experiencias visuales (VEC). La extensión del explorador VEC Helper le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión de ayuda del Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 3456da329e25f3d8e8f591fce0b851580d385455
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 57%

---

# Extensión del Helper del Compositor de experiencias visuales

El [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) La extensión de explorador Helper para Google Chrome permite cargar sitios web de forma fiable dentro del VEC para crear y realizar controles de calidad de experiencias rápidamente.

El explorador VEC Helper es una extensión de Chrome. Esta extensión no es necesaria cuando se utiliza Mozilla Firefox.

>[!IMPORTANT]
>
>El actual [!DNL Target] La extensión VEC Helper documentada en este artículo se creó con Manifest v2. Google ha anunciado recientemente que ya no permitirá nuevas extensiones creadas con Manifest v2.
>
>La extensión existente aún funciona en Google Chrome. En el futuro, [!DNL Adobe] dejará de utilizar la extensión del ayudante documentada en este tema y requerirá que los clientes se pasen a la versión más reciente de [Extensión de Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). Se le notificará mediante las notas de la versión y el texto de este artículo cuando esta extensión deje de funcionar. Sin embargo, debido a las mejoras de seguridad de Manifest v3, [!DNL Adobe] recomienda descargar la nueva extensión para seguir creando visualmente sus sitios web en [!DNL Target].

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o la fase del cliente no están disponibles para el mundo exterior (el sitio es interno).
* Existen algunas limitaciones actuales al intentar usar el VEC para abrir un sitio web que esté usando [Trabajadores de servicio](https://developer.mozilla.org/es/docs/Web/API/Service_Worker_API){target=_blank} (SW).

Un SW es una tecnología web que se puede utilizar para interceptar solicitudes del dominio en el que están instalados en una página web. El SW sobrevive a la visita de página y se activa en visitas posteriores. El SW decide qué solicitudes pasan y cuáles se interceptan y sirven desde una caché en su lugar.

El SW puede controlar el almacenamiento en caché; puede almacenar en caché la página web en sí, los recursos estáticos como JS, CSS, IMG, las solicitudes de AJAX, su contenido y sus encabezados de respuesta, incluidos los que la [Extensión de Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) intenta quitar, como X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) o Set-Cookie.

Lamentablemente, las API de extensión de Chrome que interceptan solicitudes web no reciben las solicitudes interceptadas y gestionadas por un SW. Por lo tanto, la extensión no puede corregir los encabezados y las cookies si la solicitud de página web la proporcionó un SW desde una caché porque la página web no se cargará dentro del VEC debido a los encabezados X-Frame-Options o CSP que también se almacenaron en caché.

Como solución, puede deshabilitar los Service Workers desde la pestaña Herramientas para desarrolladores de Chrome > Aplicación y, a continuación, activar la casilla Saltar para acceder a red en la sección Service Workers.

* Utiliza Google Chrome 80 y versiones posteriores con políticas mejoradas de aplicación de cookies de SameSite. Para obtener más información, consulte [¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

La extensión del explorador VEC Helper de Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen del [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o extensiones de terceros, como Requestly.

## Beneficios del uso de la extensión VEC Helper

* Todos los encabezados de eliminación de iframes, como X-Frame-Options y Content-Security-Policy, se eliminan implícitamente del sitio web. No hay más necesidad de crear complicadas reglas Requestly.
* Si una página web todavía no contiene la biblioteca JavaScript at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

   Tenga en cuenta que al usar el Compositor de experiencias mejorado (EEC), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite sigue presente. Para insertar at.js en el sitio web, desactive el EEC.

* Las [Ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el [!UICONTROL Compositor de experiencias mejorado] (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

1. Vaya a [Extensión del explorador Adobe Target VEC Helper en la Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Haga clic en **[!UICONTROL Añadir a Chrome > Añadir extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador VEC Helper (![icono de VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo [control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslice el **[!UICONTROL Inserción de bibliotecas de Target]** cambiar a la posición &quot;on&quot; si la página web aún no contiene el [!DNL Target] Biblioteca JavaScript de at.js.

   La siguiente ilustración muestra el VEC Helper con la configuración de [!UICONTROL Inserción de bibliotecas de Target] habilitada:

   ![VEC Helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   La siguiente ilustración muestra cómo el VEC Helper pregunta si desea que inserte bibliotecas [!DNL Target] en la página para habilitar la creación:

   ![VEC Helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslice el **[!UICONTROL Cookies]** cambiar a la posición &quot;on&quot; para añadir automáticamente el `SameSite=None` corrección del atributo del explorador.

   ![Alternar cookies en la extensión del ayudante del VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obtener más información sobre la `SameSite=None` corrección del atributo de explorador, consulte “¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?” en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas

* El indicador de [!UICONTROL inserción de bibliotecas de Target] en la extensión está desactivado de forma predeterminada. Puede habilitar este indicador si desea utilizar el VEC en un sitio que aún no se haya implementado para [!DNL Target].

   Este indicador es una configuración global. El indicador está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por lo tanto, si establece este indicador en &quot;activado&quot; y abre un sitio web que ya ha sido implementado con at.js, recibirá un mensaje que le informará de que ya se ha cargado at.js. Adobe prevé que la mayoría de los clientes ya tengan at.js implementado en sus páginas y usen la configuración predeterminada desactivada.

* La extensión carga la última versión de at.js disponible en el [!DNL Target UI] in [!UICONTROL Administración > Implementación].
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma Organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión del explorador VEC Helper.
   * Si at.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
   * Si la extensión está activada y es útil para la carga, los mensajes se muestran cuando la extensión inserte la biblioteca at.js (si es necesario) o ayude a abrir el sitio web de forma fiable dentro del VEC.
