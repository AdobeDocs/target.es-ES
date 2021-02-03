---
keywords: VEC;Compositor de experiencias visuales;visual experience composer;VEC;iframe;extensión;explorador
description: Información para utilizar la extensión de explorador VEC (Visual Experience Composer) Helper de Adobe Target, para cargar sitios web de forma fiable dentro de VEC y crear y realizar controles de calidad de experiencias rápidamente.
title: Extensión de ayuda del Compositor de experiencias visuales (VEC)
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 56%

---


# Extensión del Helper del Compositor de experiencias visuales

La extensión del explorador auxiliar [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC) para Google Chrome le permite cargar sitios web de forma fiable dentro del VEC para crear rápidamente experiencias web y realizar un control de calidad.

>[!NOTE]
>
>El explorador del asistente de VEC es una extensión de Chrome. Esta extensión no es necesaria cuando se utiliza Mozilla Firefox.

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o el sitio del cliente no están disponibles para el mundo exterior (el sitio es interno).
* Está utilizando Google Chrome 80+ con directivas de aplicación de cookies SameSite mejoradas. Para obtener más información, consulte [¿Cómo afectan las políticas de aplicación de cookies Google Chrome SameSite a los VEC y EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

La extensión del explorador del asistente de VEC para Chrome resuelve los problemas de carga del sitio para los que los clientes ahora confían en el [!DNL Target] [Compositor de experiencias mejorado](/help/administrating-target/visual-experience-composer-set-up.md#eec) o en extensiones de terceros, como Requestly.

## Beneficios del uso de la extensión VEC Helper

* Todos los encabezados de eliminación de iframes, como X-Frame-Options y Content-Security-Policy, se eliminan implícitamente del sitio web. No hay más necesidad de crear complicadas reglas Requestly para ello.
* Si una página web todavía no contiene la biblioteca JavaScript at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

   Tenga en cuenta que, al utilizar el Compositor de experiencias mejorado (EEC), la extensión no inyecta at.js, pero la funcionalidad de cookie SameSite aún está presente. Para inyectar at.js en la página web, apague EEC.

* [Los ](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) visores móviles son compatibles incluso sin el Compositor [!UICONTROL  de experiencias ] mejorado (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

1. Vaya a la extensión [del explorador auxiliar de Adobe Target VEC en el almacén web de Chrome](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Haga clic en **[!UICONTROL Añadir a Chrome > Añadir extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador VEC Helper (![icono de VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo [control de calidad](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslice el **[!UICONTROL botón Inyectar bibliotecas de Destinatario]** para cambiar a la posición &quot;on&quot; si la página web aún no contiene la biblioteca JavaScript [!DNL Target] at.js.

   La siguiente ilustración muestra el VEC Helper con la configuración de [!UICONTROL Inserción de bibliotecas de Target] habilitada:

   ![VEC Helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   La siguiente ilustración muestra cómo el VEC Helper pregunta si desea que inserte bibliotecas [!DNL Target] en la página para habilitar la creación:

   ![VEC Helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslice el conmutador **[!UICONTROL Cookies]** a la posición &quot;on&quot; para agregar automáticamente la corrección del explorador de atributos SameSite=None y, a continuación, especifique el nombre y el dominio de la cookie.

   ![Alternar las cookies en la extensión del asistente de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Los siguientes vínculos proporcionan información adicional:

   * Para obtener más información sobre la corrección del explorador de atributos SameSite=None, consulte &quot;¿Cómo afectan las políticas de aplicación de cookies Google Chrome SameSite recientemente anunciadas al VEC y EEC?&quot; en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * El nombre de la cookie es &quot;mbox&quot; y el dominio de la cookie es el segundo nivel y el nivel superior de los dominios desde los que se sirve el mbox. Dado que se proporciona desde el dominio de la compañía, se trata de una cookie de origen. Ejemplo: `mycompany.com`. Para obtener más información, consulte [Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) en la *Guía del usuario de la interfaz de Experience Cloud*.

## Notas

* Su implementación debe utilizar la biblioteca at.js de [!DNL Target]. No puede utilizar una implementación mbox.js con la extensión.
* El indicador de [!UICONTROL inserción de bibliotecas de Target] en la extensión está desactivado de forma predeterminada. Puede habilitar este indicador si desea utilizar el VEC en un sitio que aún no se haya implementado para [!DNL Target].

   Tenga en cuenta que este indicador es una configuración global. El indicador está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por ejemplo, si establece este indicador en &quot;on&quot; y abre un sitio web que ya está implementado con at.js, recibirá un mensaje que le informará de que at.js ya está cargado. Prevemos que la mayoría de los clientes ya tendrán at.js implementado en sus páginas y utilizará la configuración predeterminada &quot;off&quot;.

* La extensión carga la versión más reciente de at.js que está disponible en [!DNL Target UI] en [!UICONTROL Administración > Implementación].
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma Organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión del explorador VEC Helper.
   * Si at.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
   * Si la extensión está activada y es útil para la carga, los mensajes se muestran cuando la extensión inserte la biblioteca at.js (si es necesario) o ayude a abrir el sitio web de forma fiable dentro del VEC.

