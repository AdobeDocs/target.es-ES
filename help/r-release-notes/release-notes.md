---
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.
keywords: Notas de la versión;versión preliminar
seo-description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
seo-title: Notas de la versión de Target (actual)
solution: Target
title: Notas de la versión de Target (actual)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.

## Anuncios

Tenga en cuenta los siguientes avisos importantes:

* El 20 de febrero de 2019, la infraestructura de Adobe Target se actualizó en las regiones de EMEA, Japón y APAC para dejar de recopilar datos de usuarios finales con dispositivos antiguos o navegadores web que no son compatibles con TLS 1.1 o versiones posteriores. La misma actualización está planificada para la región de Norteamérica para **el 1 de abril de 2019**. Utilizar TLS 1.2 mejora la seguridad. Es importante que revise los detalles específicos y que planifique los cambios con su equipo informático para garantizar una transición sin contratiempos. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] y [!DNL Adobe Marketing Cloud] dejarán de ser compatibles con Microsoft Internet Explorer 11 a partir de marzo de 2019. Este cambio solo afecta a la creación de [!DNL Target]; este cambio no afecta al envío de la experiencia. Cambie a Microsoft Edge u otro explorador. Para obtener más información, consulte [Exploradores compatibles](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Versión 2.1.0 de at. js (3 de junio de 2019)

Estamos encantados de anunciar las siguientes magníficas funciones en at. js 2.1.0:

| Función/Mejora | Descripción |
| --- | --- |
| Compatibilidad con Adobe Opt-in | Adobe Opt-In es una forma de simplificar las integraciones de soluciones de Adobe con plataformas de administración de consentimiento.<br>Para obtener más información sobre Adobe Opt-in, consulte [Privacidad y Reglamento General de Protección de Datos (RGPD)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Compatible con CSP estándar del sector | at. js ya no utiliza eval () para ejecutar JavaScript. |
| Registro de análisis de cliente | Proporciona a los clientes control total sobre cómo desean enviar datos de análisis a Adobe Analytics, ya sea en el lado del cliente o en el servidor.<br>Para obtener más información, consulte [Inicio de sesión en el lado del cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) Antes *de implementar*. |
| Enviar notificaciones | Permite a los desarrolladores enviar notificaciones cuando su código procesa una experiencia en lugar de utilizar `applyOffer()` o `applyOffers()`.<br>Para obtener más información, consulte [adobe. target. sendnotifications (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md). |
| Tamaño reducido de archivo | El tamaño de at. js se reduce en ~ 24%. El menor tamaño de archivo mejora el rendimiento de carga de página y reduce el tiempo para descargar at. js en la página. |
| Actualizaciones de documentación de at. js | Para obtener una lista completa de todos los artículos actualizados debido a la versión de at. js 2.1.0, consulte las entradas del 3 de junio de 2019 en [los cambios de documentación](/help/r-release-notes/doc-change.md). |

## [!DNL Target] Standard/Premium 19.5.1 (21 de mayo de 2019) {#tgt-19-5-1}

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

### Actualizaciones de funciones

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales para aplicaciones de una sola página  (SPA VEC) | El SPA VEC incluye las siguientes mejoras para que su trabajo sea más fácil y eficiente:<ul><li>Al hacer clic en una acción en el SPA se resalta el elemento del sitio donde se aplicará esta acción. Cada acción del VEC creada en una Vista tiene cuatro iconos correspondientes: Información, Editar, Mover y Eliminar. La nueva funcionalidad “Mover” de esta versión permite mover la acción a un evento de Carga de página o a cualquier otra Vista que ya exista en el panel de modificaciones. (TGT-33746)</li><li>Puede realizar muchas acciones antes de que la página se cargue en VEC o incluso si la página no se carga completamente (por ejemplo, si el código personalizado ya no funciona). Las acciones que no se pueden editar antes de que el sitio web cargue no aparecerán en la IU de Target. (TGT-33851 y TGT-34149)</li></ul>Para obtener más información, consulte [Compositor de experiencias visuales de la aplicación de una sola página (SPA)](/help/c-experiences/spa-visual-experience-composer.md). |

### Mejoras, correcciones y cambios

* Los iconos de la barra de herramientas se muestran correctamente después de cancelar la carga de una página dentro del VEC. Si no se pueden realizar acciones específicas hasta que la página se haya cargado por completo, los iconos de la barra de herramientas asociados se desactivan. (TGT-33811)

## Compositor de experiencias visuales para aplicaciones móviles (14 de mayo de 2019) {#mobile-vec-may14-2}

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales (VEC) para aplicaciones móviles | El Compositor de experiencias visuales (VEC) para aplicaciones móviles le permite crear actividades y personalizar contenido en aplicaciones móviles nativas por su cuenta, sin las continuas dependencias de desarrollo y los ciclos de lanzamiento de aplicaciones.<br>Para obtener más información, consulte:<ul><li>[Compositor de experiencias visuales para aplicaciones móviles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar el rastreo de clics en el VEC móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vídeo: Compositor de experiencias visuales de aplicaciones móviles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte [Notas de la versión de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en la Lista prioritaria de actualización de productos Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |