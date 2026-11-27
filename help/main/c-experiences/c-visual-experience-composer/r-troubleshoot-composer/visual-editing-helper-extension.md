---
keywords: vec;compositor de experiencias visuales; vec;iframe;extensión;explorador;faq
description: Descubra por qué algunos sitios web podrían no abrirse de forma fiable en el [!UICONTROL Compositor de experiencias visuales] (VEC). La extensión de explorador [!UICONTROL Ayuda de edición visual] le permite cargar sitios web de forma fiable dentro del VEC.
title: ¿Cómo utilizo la extensión [!UICONTROL Ayuda de edición visual]?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: 'https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus'
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
source-wordcount: '829'
ht-degree: 4%
---
# Extensión [!UICONTROL Ayuda de edición visual] {#visual-editing-helper}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda cómo la extensión de explorador **[!UICONTROL Ayuda de edición visual]** carga los sitios web de forma fiable en el **[!UICONTROL Compositor de experiencias visuales]** (VEC), y cómo instalarlos y utilizarlos.

>[!ENDSHADEBOX]

La extensión de explorador [!DNL Adobe Experience Cloud] **[!UICONTROL Ayuda de edición visual]** para [!DNL Google Chrome] carga los sitios web de forma fiable en el [!DNL Adobe Target] **[!UICONTROL Compositor de experiencias visuales]** (VEC), lo que hace que sea más rápido crear y comprobar experiencias web.

>[!IMPORTANT]
>
>Esta extensión reemplaza la extensión de explorador [Target VEC Helper anterior](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), tal como se describe en la nota importante de la parte superior de ese artículo. Manifiesto V3 introduce mejoras de seguridad, por lo que [!DNL Adobe] requiere la descarga de esta nueva extensión para seguir creando sitios web de forma visual en [!DNL Target].

## Por qué algunos sitios web no se abren de forma fiable en el VEC

Es posible que un sitio web no se abra de forma fiable en el VEC por los siguientes motivos:

* El sitio web tiene normas estrictas de seguridad.
* El sitio web se encuentra en un iframe.
* El control de calidad o el sitio de ensayo del cliente son internos y no están disponibles fuera de la red.

La extensión soluciona estos problemas de carga de sitios, para los que los clientes dependen del [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) o de extensiones de terceros como Requestly.

## Ventajas de la extensión

* **Encabezados de eliminación de iframes eliminados:** la extensión elimina implícitamente encabezados como `X-Frame-Options` y `Content-Security-Policy` del sitio web, por lo que no se necesitan reglas Requestly complicadas.
* **inyección de at.js:** cuando una página web aún no contiene la biblioteca de at.js [!DNL Target], la extensión puede insertarla. A continuación, se pueden crear experiencias para el sitio web y las actividades se pueden crear y comprobar con vínculos de vista previa. Con el [Compositor de experiencias mejorado](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) (EEC), la extensión no inserta at.js, pero la funcionalidad de la cookie SameSite permanece. Para insertar at.js en la página web, desactive el EEC.
* **Ventanillas móviles:** [Las ventanillas móviles](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) son compatibles incluso sin el **[!UICONTROL Compositor de experiencias mejorado]** (EEC).
* **Nuevos clientes de [!DNL Target]:** la extensión permite experimentar con [!DNL Target] incluso cuando los desarrolladores de TI aún no han implementado [!DNL Target] en el sitio web.
* **Socios:** socios que brindan servicios a los sitios web y a las cuentas de [!DNL Target] de varios clientes obtienen un mecanismo para admitir la carga de VEC, en lugar de múltiples reglas en herramientas de terceros.

## Obtención e instalación de la extensión

La instalación de la extensión en [!DNL Chrome] permite cargar sitios web de forma fiable en el VEC, incluidos sitios web que bloquean iframes o que aún no tienen at.js implementado.

1. Vaya a la extensión de explorador [[!DNL Adobe Experience Cloud] **[!UICONTROL Ayuda de edición visual &#x200B;]**&#x200B;en Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Haga clic en **[!UICONTROL Agregar a Chrome]** > **[!UICONTROL Agregar extensión]**.
1. Abra el VEC en [!DNL Target].
1. En el VEC o en modo control de calidad, haga clic en el icono de la extensión del explorador **[!UICONTROL Ayuda de edición visual]** ( ![icono de Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) en la barra de herramientas de [!DNL Chrome].

   La extensión se habilita automáticamente cuando se abre un sitio web en el VEC [!DNL Target] para la creación de contenido. No tiene configuración condicional y administra todas las configuraciones automáticamente, incluida la configuración de la cookie SameSite. Para obtener más información sobre la corrección del atributo del explorador `SameSite=None`, consulte [Políticas de cookies de Google Chrome SameSite](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas de uso

* La extensión carga la última versión de at.js disponible en la interfaz de usuario de [!DNL Target] en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**, y at.js descarga las bibliotecas de creación.
* Para usar la extensión para insertar at.js en [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md), debe estar abierta otra pestaña de Chrome. Esta ficha debe estar autenticada en la misma organización [!DNL Adobe Experience Cloud] en la que se creó la actividad.
* El VEC muestra mensajes que sugieren la instalación de la extensión en los siguientes casos:

  * Un sitio web no se puede cargar en el VEC.
  * at.js o alloy.js aún no se ha implementado en el sitio web.

* Si se intentó usar la nueva extensión y se vuelve a usar la [extensión antigua](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), pero [!DNL Target] no pudo cargar el sitio web, borre todos los datos del explorador y deshabilite la nueva extensión.

## Últimos cambios en la extensión de (17 de enero de 2026)

La extensión agrega una función experimental de limpieza de cookies de inicio al VEC Helper. La función limpia las cookies sin particiones una vez por pestaña cuando comienza la creación, en lugar de hacerlo de forma continua, lo que mejora el rendimiento y la fiabilidad. Realiza un seguimiento del historial de cada ficha para evitar una limpieza redundante y borra ese historial cuando se cierra la ficha, de modo que la limpieza se comporta correctamente cuando se vuelve a abrir la ficha. Las pruebas unitarias garantizan un comportamiento coherente.

![Opciones de la extensión VEC Helper, incluidos los modos de procesamiento de cookies, la opción de registro avanzado y las características experimentales Retrasar la carga de la página web, Limpiar cookies y Limpiar cookies de inicio](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## Preguntas más frecuentes

+++ ¿Hace algo la extensión cuando se usa fuera de [!DNL Adobe Target] o [!UICONTROL Adobe Journey Optimizer] (AJO)?

La extensión solo se activa cuando el sitio web se carga dentro de un iFrame en [!DNL Adobe] productos ([!DNL Target], [!DNL AJO]). Fuera de este flujo, la extensión no intenta agregar, quitar ni modificar encabezados y no intenta insertar ningún código dentro del sitio web.

+++

+++ ¿Qué hace la extensión cuando está activa en el VEC de [!DNL Adobe Target]?

Cuando se carga un sitio web dentro de un iFrame en [!DNL Adobe] productos ([!DNL Target], [!DNL AJO]), la extensión inserta código que está empaquetado con la extensión en el sitio web y descarga archivos de ayuda de la CDN [!DNL Adobe] para habilitar la creación visual.

+++
