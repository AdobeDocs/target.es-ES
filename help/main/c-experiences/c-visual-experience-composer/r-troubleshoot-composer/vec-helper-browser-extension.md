---
keywords: VEC;Compositor de experiencias visuales;VEC;iframe;extensión;explorador
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el [!UICONTROL Compositor de experiencias visuales] (VEC). La extensión del explorador VEC Helper le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión [!UICONTROL Compositor de experiencias visuales] (VEC) Helper?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: 'https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 5%
---
# Extensión de ayuda de [!UICONTROL Compositor de experiencias visuales] {#vec-helper-extension}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda cómo carga la extensión heredada del explorador VEC Helper sitios web en el **[!UICONTROL Compositor de experiencias visuales]** (VEC), y cómo instalarlo y utilizarlo.

>[!ENDSHADEBOX]

La extensión del explorador [!DNL Adobe Target] **[!UICONTROL Compositor de experiencias visuales]** (VEC) Helper de [!DNL Google Chrome] carga los sitios web de forma fiable en el VEC, lo que acelera la creación y comprobación de experiencias web. La extensión no es necesaria en [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* La extensión VEC Helper heredada [!DNL Target] documentada en este artículo se creó con Manifest V2. [!DNL Google] anunció que dejaría de permitir extensiones creadas con Manifest V2 a partir de junio de 2024. Para obtener más información, consulte el [Anuncio de la cronología de compatibilidad con Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} de [!DNL Google] en el sitio *Chrome para desarrolladores*.
>
>* A partir de junio de 2024, [!DNL Google] deshabilitará las extensiones creadas con Manifiesto V2, incluida la extensión documentada en este artículo. [!DNL Adobe] recomienda pasar a la nueva extensión [Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) lo antes posible.

## Por qué algunos sitios web no se abren de forma fiable en el VEC

Es posible que un sitio web no se abra de forma fiable en el VEC por los siguientes motivos:

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* Aún no se ha implementado la biblioteca at.js en el sitio web.
* El control de calidad o el sitio de ensayo del cliente son internos y no están disponibles fuera de la red.
* El sitio web usa [Service Workers](https://developer.mozilla.org/es/docs/Web/API/Service_Worker_API){target=_blank} (SW), que actualmente el VEC solo admite con limitaciones. Consulte la siguiente sección.
* El sitio web se abre en [!DNL Chrome] 80 o posterior, lo que aplica las directivas de cookies de SameSite. Para obtener más información, consulte [Políticas de cookies de Google Chrome SameSite](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

La extensión del explorador VEC Helper de [!DNL Chrome] resuelve los problemas de carga de sitios para los que los clientes dependen del [!DNL Target] [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o de extensiones de terceros como Requestly.

### Trabajadores de servicio

Un Service Worker (SW) es una tecnología web que instala una página web para interceptar las solicitudes de su dominio. El SW sobrevive a la visita de página y se activa en visitas posteriores. Decide qué solicitudes pasan y cuáles se interceptan y sirven desde una caché.

Un SW puede almacenar en caché la propia página web, los recursos estáticos como solicitudes JS, CSS, IMG y AJAX, su contenido y sus encabezados de respuesta. Estos encabezados incluyen los que la extensión [Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) intenta eliminar, como `X-Frame-Options: SAMEORIGIN`, CSP (`Content-Security-Policy`) y `Set-Cookie`.

Las API de extensión [!DNL Chrome] que interceptan solicitudes web no reciben las solicitudes interceptadas y administradas por un SW. Cuando un SW sirve la solicitud de página web desde una caché, la extensión no puede corregir los encabezados y las cookies y la página no se carga dentro del VEC debido a los encabezados en caché `X-Frame-Options` o CSP.

Como solución alternativa, deshabilite los Service Workers en la ficha [!DNL Chrome] Herramientas para desarrolladores > **Aplicación** y, a continuación, active la casilla &quot;Omitir para red&quot; en la sección Service Workers.

## Ventajas de la extensión VEC Helper

* **Encabezados de eliminación de iframes eliminados:** la extensión elimina implícitamente encabezados como `X-Frame-Options` y `Content-Security-Policy` del sitio web, por lo que no se necesitan reglas Requestly complicadas.
* **inyección de at.js:** cuando una página web aún no contiene la biblioteca JavaScript de at.js [!DNL Target], la extensión puede insertarla. A continuación, se pueden crear experiencias para el sitio web y las actividades se pueden crear y comprobar con vínculos de vista previa. Con el Compositor de experiencias mejorado (EEC), la extensión no inserta at.js, pero la funcionalidad de cookie SameSite permanece. Para insertar at.js en la página web, desactive el EEC.
* **Ventanillas móviles:** [Las ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el **[!UICONTROL Compositor de experiencias mejorado]** (EEC).
* **Nuevos clientes de [!DNL Target]:** la extensión permite experimentar con [!DNL Target] incluso cuando los desarrolladores de TI aún no han implementado [!DNL Target] en el sitio web.
* **Socios:** socios que brindan servicios a los sitios web y a las cuentas de [!DNL Target] de varios clientes obtienen un mecanismo para admitir la carga de VEC, en lugar de múltiples reglas en herramientas de terceros.

## Obtención e instalación de la extensión del explorador VEC Helper

La instalación de la extensión en [!DNL Chrome] permite cargar sitios web de forma fiable en el VEC, incluidos sitios web que bloquean iframes o que aún no tienen at.js implementado.

1. Vaya a la extensión de explorador [Adobe Target VEC Helper en Chrome Web Store](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca).
1. Haga clic en **[!UICONTROL Agregar a Chrome]** > **[!UICONTROL Agregar extensión]**.
1. Abra el VEC en [!DNL Target].
1. En el VEC o en [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), haga clic en el icono de la extensión del explorador VEC Helper ( ![icono de VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) en la barra de herramientas de [!DNL Chrome].
1. (Condicional) Si la página web aún no contiene la biblioteca JavaScript at.js [!DNL Target], active la opción **[!UICONTROL Inyectar bibliotecas de Target]**.

   La siguiente ilustración muestra el VEC Helper con la configuración **[!UICONTROL Inyectar bibliotecas de Target]** habilitada:

   ![Panel de extensión VEC Helper con la opción de inserción de bibliotecas de Target activada y la opción Cookies desactivada, que muestra que la configuración Cookies establece los indicadores SameSite=None y Secure en todas las cookies para las solicitudes dentro del VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   A continuación, el VEC Helper pregunta si debe insertar las bibliotecas de [!DNL Target] en la página para habilitar la creación:

   ![Inyectar bibliotecas de Target solicita que se indique que la extensión Target VEC Helper desea insertar bibliotecas de Target en la página para habilitar la creación, con los botones Cancelar y Permitir](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Active **[!UICONTROL Cookies]** para agregar automáticamente la corrección del explorador de atributos `SameSite=None`.

   ![Panel de extensión VEC Helper con la opción Cookies activada y resaltada, sobre el Compositor de experiencias visuales que muestra una página de muestra](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obtener más información sobre la corrección del atributo del explorador `SameSite=None`, consulte [Políticas de cookies de Google Chrome SameSite](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas de uso

* El indicador **[!UICONTROL Inyectar bibliotecas de Target]** de la extensión está desactivado de forma predeterminada. Actívelo para usar el VEC en un sitio en el que [!DNL Target] aún no se haya implementado.

  El indicador es una configuración global, por lo que está habilitado o deshabilitado para todos los sitios web abiertos en el VEC. Por ejemplo, con el indicador activado, al abrir un sitio web que ya ha implementado at.js se muestra un mensaje que indica que ya se ha cargado at.js. [!DNL Adobe] espera que la mayoría de los clientes ya tengan at.js implementado en sus páginas y usen la configuración predeterminada desactivada.

* La extensión carga la última versión de at.js disponible en la interfaz de usuario de [!DNL Target] en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.
* Para usar la extensión para insertar at.js en [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe estar abierta otra pestaña de Chrome. Esta ficha debe estar autenticada en la misma organización [!DNL Adobe Experience Cloud] en la que se creó la actividad.
* El VEC muestra mensajes en los siguientes casos:

  * Un sitio web no se puede cargar en el VEC. El mensaje sugiere instalar la extensión del explorador VEC Helper.
  * at.js aún no se ha implementado en el sitio web. El mensaje sugiere instalar la extensión.
  * La extensión se activa y enciende la carga. Los mensajes se muestran cuando la extensión inserta la biblioteca at.js, si es necesario, o ayuda a abrir el sitio web de forma fiable en el VEC.
