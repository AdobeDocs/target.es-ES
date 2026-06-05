---
keywords: vec;compositor de experiencias visuales; vec;iframe;extensión;explorador;faq
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el [!UICONTROL Compositor de experiencias visuales] (VEC). La extensión de explorador [!UICONTROL Ayuda de edición visual] le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión [!UICONTROL Ayuda de edición visual]?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: e9001ce2-5245-4a8e-8601-dd958009072fid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 837
ht-degree: 52%

---

# Extensión [!UICONTROL Ayuda de edición visual]

La extensión de explorador [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] para [!DNL Google Chrome] le permite cargar sitios web de forma fiable dentro del [!UICONTROL Compositor de experiencias visuales] de [!UICONTROL Adobe Target] (VEC) para crear y realizar controles de calidad de experiencias rápidamente.

>[!IMPORTANT]
>
>* Esta nueva extensión sustituye a la [extensión de explorador de VEC Helper de Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) anterior. Consulte la nota importante que aparece al principio de ese artículo. Debido a las mejoras de seguridad en Manifest v3, [!DNL Adobe] requiere la descarga de esta nueva extensión para continuar creando de forma visual sus sitios web en [!DNL Target].

## Cambios en la extensión [!UICONTROL Ayuda de edición visual] (17 de enero de 2026)

### **Se ha corregido un problema al agregar la nueva característica experimental de limpieza de cookies de inicio en el VEC Helper.**

* Se ha corregido un problema al añadir una nueva función experimental de limpieza de cookies de inicio en el VEC Helper.
* Esta mejora mejora mejora el rendimiento y la fiabilidad al limpiar las cookies no particionadas una vez por pestaña cuando comienza la creación en lugar de continuamente.
* La función realiza un seguimiento del historial de pestañas para evitar limpiezas redundantes y borra el historial de cierre de pestañas para que la limpieza se comporte correctamente cuando se vuelva a abrir una pestaña.
* Se han añadido pruebas unitarias completas para garantizar un comportamiento coherente.

![Nuevas opciones de VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## Razones por las que algunos sitios web podrían no abrirse de forma fiable en el VEC

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* El control de calidad o la fase del cliente no están disponibles para el mundo exterior (el sitio es interno).

La extensión de explorador [!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] para resuelve los problemas de carga de sitios para los que los clientes ahora dependen del [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o de extensiones de terceros, como Requestly.

## Ventajas de usar la extensión [!UICONTROL Ayuda de edición visual]

* Todos los encabezados de eliminación de iframes, como `X-Frame-Options` y `Content-Security-Policy`, se eliminan implícitamente del sitio web. No hay necesidad de crear reglas Requestly complicadas.
* Si una página web todavía no contiene la biblioteca at.js de [!DNL Target], puede utilizar la extensión para insertar la biblioteca y así poder crear experiencias para el sitio web. A continuación, puede crear actividades y realizar controles de calidad mediante vínculos de vista previa.

  Al usar el [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite sigue presente. Para insertar at.js en el sitio web, desactive el EEC.

* Las [ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el [!UICONTROL Compositor de experiencias mejorado] (EEC).
* Los clientes nuevos de [!DNL Target] pueden utilizar la extensión para experimentar con [!DNL Target] incluso si los desarrolladores de TI todavía no han implementado [!DNL Target] en sus sitios web.
* Los socios que brindan servicios de múltiples páginas web de clientes y cuentas de [!DNL Target] ahora tienen un mecanismo sencillo para admitir la carga de VEC, en lugar de administrar varias reglas en herramientas de terceros.

## Obtenga e instale la extensión de explorador [!UICONTROL Ayuda de edición visual]

1. Vaya a la extensión de explorador [[!DNL Adobe Experience Cloud] [!UICONTROL Ayuda de edición visual] en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Haga clic en **[!UICONTROL Agregar a Chrome]** > **[!UICONTROL Agregar extensión]**.
1. Abra el VEC en [!DNL Target].
1. Para usar la extensión, haga clic en el icono de la extensión del explorador [!UICONTROL Ayuda de edición visual] ( ![icono de Extensión de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) en la barra de herramientas del explorador Chrome mientras está en VEC o en modo control de calidad.

   [!UICONTROL Ayuda de edición visual] se habilita automáticamente cuando se abre un sitio web en el VEC de [!UICONTROL Target] para la creación de contenido. La extensión no tiene ninguna configuración condicional. La extensión gestiona todas las configuraciones automáticamente, incluida la configuración de cookies de SameSite.

   Para obtener más información sobre la `SameSite=None` corrección del atributo de explorador, consulte “¿Cómo afectan las políticas de aplicación de cookies de Google Chrome SameSite a los VEC y EEC?” en [Resolución de problemas relacionados con el Compositor de experiencias visuales y el Compositor de experiencias mejorado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], la extensión carga la última versión de at.js disponible en la interfaz de usuario de [!DNL Target] en [!UICONTROL Administración] > [!UICONTROL Implementación] y at.js descarga las bibliotecas de creación.
* Cuando utilice la extensión para insertar at.js mientras está en [modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe tener otra pestaña de Chrome abierta. Esta pestaña de Chrome debe estar autenticada en la misma organización de [!DNL Adobe Experience Cloud] en la que creó la actividad.
* Los mensajes siguientes ayudan a mantenerle informado:

   * Si intenta cargar un sitio web usando el VEC que falla al cargar, aparece un mensaje sugiriendo que instale la extensión de explorador [!UICONTROL Ayuda de edición visual].
   * Si at.js o alloy.js aún no se ha implementado en el sitio web, aparece un mensaje en el VEC sugiriendo que instale la extensión.
* Si intenta utilizar la nueva extensión y después vuelve a la [extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) y [!DNL Target] no se puede cargar el sitio web, borre todos los datos del explorador y desactive la nueva extensión.

## Preguntas frecuentes

### ¿La extensión, cuando está activa, hace algo cuando se usa fuera de [!DNL Adobe Target] o [!UICONTROL Adobe Journey Optimizer] (AJO)?

La extensión solo se activa cuando el sitio web en cuestión se carga dentro de un iFrame en productos de [!DNL Adobe] ([!DNL Target], [!DNL AJO]). Fuera de este flujo, la extensión no intenta añadir, quitar ni modificar ningún encabezado, ni intenta insertar ningún código dentro del sitio web.

### ¿Qué hace la extensión cuando está activa en el VEC de [!DNL Adobe Target]?

Cuando un sitio web se carga dentro de un iFrame en productos de [!DNL Adobe] ([!DNL Target], [!DNL AJO]), la extensión inserta código (empaquetado con la extensión) en el sitio web y descarga los archivos de ayuda desde el CDN de [!DNL Adobe] para habilitar la creación visual.
