---
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.
keywords: Notas de la versión;versión preliminar
seo-description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
seo-title: Notas de la versión de Adobe Target (actual)
solution: Target
title: Notas de la versión de Target (actual)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51bf163881a651ce6ab92dcc6753a91f6d6cc4f8

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.

## Anuncios

Tenga en cuenta los siguientes avisos importantes:

* El 20 de febrero de 2019, la infraestructura de Adobe Target se actualizó en las regiones de EMEA, Japón y APAC para dejar de recopilar datos de usuarios finales con dispositivos antiguos o navegadores web que no son compatibles con TLS 1.1 o versiones posteriores. La misma actualización está planificada para la región de Norteamérica para **el 1 de abril de 2019**. Utilizar TLS 1.2 mejora la seguridad. Es importante que revise los detalles específicos y que planifique los cambios con su equipo informático para garantizar una transición sin contratiempos. Para obtener más información, consulte [Cambios en el cifrado de TLS (Seguridad de capa de transporte)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] y [!DNL Adobe Marketing Cloud] dejarán de ser compatibles con Microsoft Internet Explorer 11 a partir de marzo de 2019. Este cambio solo afecta a la creación de [!DNL Target]; este cambio no afecta al envío de la experiencia. Cambie a Microsoft Edge u otro explorador. Para obtener más información, consulte [Exploradores compatibles](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Target Standard/Premium 19.6.1 (26 de junio de 2019) 

Esta versión incorpora las siguientes nuevas funciones y mejoras:

| Función / Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales (VEC) | **Nuevas opciones de menú VEC**: Al hacer clic en un elemento de página del VEC, un menú muestra las opciones disponibles para ese tipo de elemento.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**Mejoras en el rastreo de clics**: Hemos mejorado el proceso para configurar el rastreo de clics dentro del VEC y el VEC de aplicación de una sola página (SPA).<ul><li>Al seleccionar elementos que se utilizan en el rastreo de clics, los nombres de todos los elementos disponibles se muestran en el panel Modificaciones del lado derecho, lo que facilita y simplifica la selección de los elementos deseados.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Puede pasar el ratón sobre este número para ver los nombres de todos los elementos seleccionados. (TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| Compositor de experiencias visuales para aplicaciones de una sola página  (SPA VEC) | **Flujo de trabajo guiado**: Un nuevo flujo de trabajo guiado ayuda a comprender cómo debe configurarse la configuración de las reglas de entrega de páginas para ejecutar y ejecutar una actividad correctamente en la aplicación de una sola página. (TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**Modificaciones en clonar**: Ahora puede definir una modificación utilizando el VEC de SPA y luego clonar esa modificación para usarla en otras vistas de la aplicación de una sola página. (TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Compositor de experiencias visuales (VEC) | **Varias versiones de la aplicación**: Ahora puede crear actividades para varias versiones de su aplicación móvil. Esto ahorra tiempo y esfuerzo cuando las versiones son similares y no es necesario cambiar de forma significativa la interfaz de usuario de la aplicación. (TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Insignia Premium](/help/assets/premium.png) Personalización automatizada (AP) y segmentación automática | **Experiencia específica como control**: Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de segmentación automática o de segmentación automática. Esta función permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado contra el tráfico de control a esa experiencia. La opción de control actual (experiencias servidas aleatoriamente) seguirá estando disponible. (TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**Informes de perspectivas de personalización**: La denominación fácil de utilizar para los atributos cuando un visitante ve un contenido específico en una ubicación específica proporciona información más significativa. (TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![Premium badge](/help/assets/premium.png) Recommendations | Puede utilizar la opción Recomendar elementos adquiridos anteriormente al crear la lógica de elementos visualizados recientemente. (TGT-34030)<br>Para obtener más información, consulte [Artículos vistos recientemente](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) en «Crear criterios». |
| Políticas de cookies de Google Chrome samesite | Google ha anunciado recientemente que a partir de Chrome 76, que se ha marcado para una versión del 30 de julio de 2019, los desarrolladores deben especificar explícitamente qué cookies pueden funcionar en distintos sitios web y qué cookies pueden rastrear a usuarios.<br>Dado que el sector realiza avances para crear una Web más segura para los consumidores, Target está absolutamente comprometido a ofrecer experiencias personalizadas durante la reunión y superar las expectativas de privacidad de los visitantes.<br>Consulte [las políticas de cookies de Google Chrome samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md). |

## Versión 2.1.0 de at. js (3 de junio de 2019)

Estamos encantados de anunciar las siguientes magníficas funciones en at. js 2.1.0:

| Función/Mejora | Descripción |
| --- | --- |
| Compatibilidad con Adobe Opt-in | Adobe Opt-In es una forma de simplificar las integraciones de soluciones de Adobe con plataformas de administración de consentimiento.<br>Para obtener más información sobre Adobe Opt-in, consulte [Privacidad y Reglamento General de Protección de Datos (RGPD)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Compatible con CSP estándar del sector | at. js ya no utiliza eval () para ejecutar JavaScript. |
| Registro de análisis de cliente | Proporciona a los clientes control total sobre cómo desean enviar datos de análisis a Adobe Analytics, ya sea en el lado del cliente o en el servidor.<br>Para obtener más información, consulte [Inicio de sesión en el lado del cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) Antes *de implementar*. |
| Enviar notificaciones | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>Para obtener más información, consulte [adobe. target. sendnotifications (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md). |
| Tamaño reducido de archivo | El tamaño de at. js se reduce en ~ 24%. El menor tamaño de archivo mejora el rendimiento de carga de página y reduce el tiempo para descargar at. js en la página. |
| Actualizaciones de documentación de at. js | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

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