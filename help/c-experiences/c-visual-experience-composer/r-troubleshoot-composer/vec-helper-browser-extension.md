---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Información para utilizar la extensión de explorador VEC (Visual Experience Composer) Helper de Adobe Target, para cargar sitios web de forma fiable dentro de VEC y crear y realizar controles de calidad de experiencias rápidamente.
title: Extensión del Compositor de experiencias visuales (VEC) Helper de Adobe Target
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 94%

---


# Extensión del Helper del Compositor de experiencias visuales

La extensión [!DNL Adobe Target]de explorador Compositor de experiencias visuales (VEC) Helper para Google Chrome permite cargar sitios web de forma fiable dentro del VEC para crear y realizar controles de calidad de experiencias rápidamente.

Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC:

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o el sitio del cliente no están disponibles para el mundo exterior (el sitio es interno).

La extensión del explorador VEC Helper de Chrome resuelve los problemas de carga de sitios para los que los clientes ahora dependen del [!DNL Target] [!UICONTROL Compositor de experiencias mejorado] o de extensiones de terceros, como Requestly.

Beneficios del uso de la extensión VEC Helper:

* Todos los encabezados de eliminación de iframes, como X-Frame-Options y Content-Security-Policy, se eliminan implícitamente del sitio web. No hay más necesidad de crear complicadas reglas Requestly para ello.
* Si una página web todavía no contiene la biblioteca JavaScript at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.
* Las Ventanillas móviles son compatibles incluso sin el [!UICONTROL Compositor de experiencias mejorado] (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Haga clic en [!UICONTROL Añadir a Chrome > Añadir extensión].
1. Para utilizar la extensión, haga clic en el icono de la extensión del explorador VEC Helper (![icono de VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo [control de calidad](/help/c-activities/c-activity-qa/activity-qa.md).

La siguiente ilustración muestra el VEC Helper con la configuración de [!UICONTROL Inserción de bibliotecas de Target] habilitada:

![VEC Helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

La siguiente ilustración muestra cómo el VEC Helper pregunta si desea que inserte bibliotecas [!DNL Target] en la página para habilitar la creación:

![VEC Helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## Notas

* Su implementación debe utilizar la biblioteca at.js de [!DNL Target]. No puede utilizar una implementación mbox.js con la extensión.
* El indicador de [!UICONTROL inserción de bibliotecas de Target] en la extensión está desactivado de forma predeterminada. Puede habilitar este indicador si desea utilizar el VEC en un sitio que aún no se haya implementado para [!DNL Target].

   Tenga en cuenta que este indicador es una configuración global. El indicador está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por lo tanto, si establece este indicador en activo y abre un sitio web que ya ha sido implementado con at.js, recibirá un mensaje que le informará de que ya se ha cargado at.js. Prevemos que la mayoría de los clientes ya tendrán at.js implementado en sus páginas y usaremos la configuración predeterminada desactivada.

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma Organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web mediante el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión del explorador VEC Helper.
   * Si at.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
   * Si la extensión está activada y es útil para la carga, los mensajes se muestran cuando la extensión inserte la biblioteca at.js (si es necesario) o ayude a abrir el sitio web de forma fiable dentro del VEC.