---
description: En estas notas de la versión se proporciona información acerca de las características, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Target.
keywords: notas de la versión
seo-description: En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Adobe Target
seo-title: Notas de la versión de Target (versión previa)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3a36b900ac3d24e515be5028ddee3d8f250023c7

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 28 de mayo de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios. Para ver la información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.

## Versión 2.1.0 de at. js (3 de junio de 2019)

Estamos encantados de anunciar las siguientes magníficas funciones en at. js 2.1.0:

| Función/Mejora | Descripción |
| --- | --- |
| Compatibilidad con Adobe Opt-in | Adobe Opt-In es una forma de simplificar las integraciones de soluciones de Adobe con plataformas de administración de consentimiento.<br>Para obtener más información sobre Adobe Opt-in, consulte [Privacidad y Reglamento General de Protección de Datos (RGPD)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Compatible con CSP estándar del sector | at. js ya no utiliza eval () para ejecutar JavaScript. |
| Registro de análisis de cliente | Proporciona a los clientes control total sobre cómo desean enviar datos de análisis a Adobe Analytics, ya sea en el lado del cliente o en el servidor. |
| Enviar notificaciones | Permite a los desarrolladores enviar notificaciones cuando su código procesa una experiencia en lugar de utilizar `applyOffer()` o `applyOffers()`. |
| Tamaño reducido de archivo | El tamaño de at. js se reduce en ~ 24%. El menor tamaño de archivo mejora el rendimiento de carga de página y reduce el tiempo para descargar at. js en la página. |

## [!DNL Target] Standard/Premium 19.5.1 (21 de mayo de 2019) {#release-19-5-1-prerelease}

Esta versión incluye las funciones, cambios y mejoras siguientes:

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

### Actualizaciones de funciones

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales para aplicaciones de una sola página (SPA VEC) | El SPA VEC incluye las siguientes mejoras para que su trabajo sea más fácil y eficiente:<ul><li>Al hacer clic en una acción en el SPA, se resalta el elemento del sitio donde se aplicará esta acción. Cada acción del VEC creada en una Vista tiene cuatro iconos correspondientes: Información, Editar, Mover y Eliminar. La nueva funcionalidad «Mover» de esta versión permite mover la acción a un evento de carga de página o a cualquier otra vista que ya exista en el panel de modificaciones. (TGT-33746)</li><li>Puede realizar muchas acciones antes de que la página se cargue en VEC o incluso si la página no se carga completamente (por ejemplo, si el código personalizado ya no funciona). Las acciones que no se pueden editar antes de que el sitio web cargue no aparecerán en la IU de Target. (TGT-33851 y TGT-34149)</li></ul>Para obtener más información, consulte [Compositor de experiencias visuales de la aplicación de una sola página (SPA)](/help/c-experiences/spa-visual-experience-composer.md). |

### Mejoras, correcciones y cambios

* Los iconos de la barra de herramientas se muestran correctamente después de cancelar la carga de una página dentro del VEC. Si no se pueden realizar acciones específicas hasta que la página se haya cargado por completo, los iconos de la barra de herramientas asociados se desactivan. (TGT-33811)

## Compositor de experiencias visuales de aplicaciones móviles (14 de mayo de 2019) {#mobile-vec-may14}

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales de aplicaciones móviles (VEC) | El VEC de aplicación móvil le permite crear actividades y personalizar contenido en aplicaciones móviles nativas de forma práctica sin dependencias de desarrollo continuas y ciclos de lanzamiento de aplicaciones.<br>Para obtener más información, consulte:<ul><li>[Compositor de experiencias visuales para aplicaciones móviles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar el rastreo de clics en el VEC móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vídeo: Compositor de experiencias visuales de aplicaciones móviles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
