---
keywords: VEC;Compositor de experiencias visuales;VEC;iframe;extensión;explorador
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el [!UICONTROL Visual Experience Composer] (VEC). La extensión del explorador VEC Helper le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión [!UICONTROL Visual Experience Composer] (VEC) Helper?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: c41580bcbecf2eb2c14f13ce8e66e854c655d059
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 50%

---

# [!UICONTROL Visual Experience Composer] extensión de ayudante

La extensión de explorador [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper para [!DNL Google Chrome] le permite cargar sitios web de forma fiable dentro del VEC para crear y realizar controles de calidad de experiencias rápidamente.

El explorador VEC Helper es una extensión [!DNL Chrome]. Esta extensión no es necesaria cuando se usa [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* La extensión VEC Helper heredada [!DNL Target] documentada en este artículo se creó con Manifest V2. [!DNL Google] anunció que ya no permitirá extensiones creadas con Manifest V2 a partir de junio de 2024. Para obtener más información, consulte el [Anuncio de la cronología de compatibilidad con Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} de [!DNL Google] en el sitio de *Chrome para desarrolladores*.
>
>* A partir de junio de 2024, [!DNL Google] empezará a deshabilitar las extensiones creadas con Manifest V2, incluida la extensión documentada en este tema. [!DNL Adobe] recomienda que los clientes cambien a la nueva extensión [Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) lo antes posible.

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o la fase del cliente no están disponibles para el mundo exterior (el sitio es interno).
* Existen algunas limitaciones actuales al intentar usar el VEC para abrir un sitio web que esté usando [Service Workers](https://developer.mozilla.org/es/docs/Web/API/Service_Worker_API){target=_blank} (SW).

Un SW es una tecnología web que se puede utilizar para interceptar solicitudes del dominio en el que están instalados en una página web. El SW sobrevive a la visita de página y se activa en visitas posteriores. El SW decide qué solicitudes pasan y cuáles se interceptan y sirven desde una caché en su lugar.

El SW puede controlar el almacenamiento en caché; puede almacenar en caché la página web en sí, los recursos estáticos como JS, CSS, IMG, las solicitudes de AJAX, su contenido y sus encabezados de respuesta, incluidos los que la [Extensión de Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) intenta quitar, como X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) o Set-Cookie.

Desafortunadamente, las API de extensión de Chrome que interceptan solicitudes web no reciben las solicitudes interceptadas y gestionadas por un SW. Por lo tanto, la extensión no puede corregir los encabezados y las cookies si la solicitud de página web la proporcionó un SW desde una caché porque la página web no se cargará dentro del VEC debido a los encabezados X-Frame-Options o CSP que también se almacenaron en caché.

Como solución alternativa, puede deshabilitar los Service Workers desde la pestaña Herramientas para desarrolladores de Chrome > Aplicación y, a continuación, activar la casilla Saltar para acceder a red en la sección Service Workers.

* Utiliza Google Chrome 80+ con políticas mejoradas de aplicación de cookies de SameSite. Para obtener más información, consulte [¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

La extensión del explorador VEC Helper de Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen de [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o de extensiones de terceros, como Requestly.

## Ventajas de utilizar la extensión VEC Helper

* Todos los encabezados de eliminación de iframes, como X-Frame-Options y Content-Security-Policy, se eliminan implícitamente del sitio web. No hay más necesidad de crear complicadas reglas Requestly.
* Si una página web todavía no contiene la biblioteca JavaScript at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

  Tenga en cuenta que al usar el Compositor de experiencias mejorado (EEC), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite sigue presente. Para insertar at.js en el sitio web, desactive el EEC.

* [Las ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el [!UICONTROL Enhanced Experience Composer] (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

1. Vaya a la extensión de explorador [Adobe Target VEC Helper en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Haga clic en **[!UICONTROL Add to Chrome > Add Extension]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador VEC Helper (![icono de VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo [control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslice el conmutador **[!UICONTROL Inject Target Libraries]** a la posición &quot;activado&quot; si la página web aún no contiene la biblioteca JavaScript at.js [!DNL Target].

   La siguiente ilustración muestra el VEC Helper con la configuración [!UICONTROL Inject Target Libraries] habilitada:

   ![VEC Helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   La siguiente ilustración muestra cómo el VEC Helper pregunta si desea que inserte bibliotecas [!DNL Target] en la página para habilitar la creación:

   ![VEC Helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslice el conmutador **[!UICONTROL Cookies]** a la posición &quot;Activado&quot; para agregar automáticamente la corrección del explorador de atributos `SameSite=None`.

   ![Alternan las cookies en la extensión del ayudante del VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obtener más información sobre la `SameSite=None` corrección del atributo de explorador, consulte “¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?” en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas

* El indicador [!UICONTROL Inject Target libraries] de la extensión está desactivado de forma predeterminada. Puede habilitar este indicador si desea utilizar el VEC en un sitio que aún no se haya implementado para [!DNL Target].

  Este indicador es una configuración global. El indicador está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por lo tanto, si establece este indicador en &quot;activado&quot; y abre un sitio web que ya ha sido implementado con at.js, recibirá un mensaje que le informará de que ya se ha cargado at.js. Adobe prevé que la mayoría de los clientes ya tengan at.js implementado en sus páginas y usen la configuración predeterminada desactivada.

* La extensión carga la última versión de at.js disponible de [!DNL Target UI] en [!UICONTROL Administration > Implementation].
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma Organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión del explorador VEC Helper.
   * Si at.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
   * Si la extensión está activada y es útil para la carga, los mensajes se muestran cuando la extensión inserte la biblioteca at.js (si es necesario) o ayude a abrir el sitio web de forma fiable dentro del VEC.
