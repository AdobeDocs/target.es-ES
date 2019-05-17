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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium.

## Anuncios

Tenga en cuenta los siguientes avisos importantes:

* El 20 de febrero de 2019, la infraestructura de Adobe Target se actualizó en las regiones de EMEA, Japón y APAC para dejar de recopilar datos de usuarios finales con dispositivos antiguos o exploradores Web que no admiten TLS 1.1 o posterior. La misma actualización está planificada para la región de Norteamérica para **el 1 de abril de 2019**. Utilizar TLS 1.2 mejora la seguridad. Es importante que avance por los específicos y planifique los cambios con su equipo de TI para lograr una transición suave. Para obtener más información, consulte [Cambios de codificación de TLS (Transporte Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] y [!DNL Adobe Marketing Cloud] dejarán de ser compatibles con Microsoft Internet Explorer 11 a partir de marzo de 2019. Este cambio solo afecta a la creación de [!DNL Target]; este cambio no afecta al envío de la experiencia. Cambie a Microsoft Edge u otro explorador. Para obtener más información, consulte [Exploradores compatibles](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Compositor de experiencias visuales de aplicaciones móviles (14 de mayo de 2019) {mobile-vec}

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales de aplicaciones móviles (VEC) | El VEC de aplicación móvil le permite crear actividades y personalizar contenido en aplicaciones móviles nativas de forma práctica sin dependencias de desarrollo continuas y ciclos de lanzamiento de aplicaciones.<br>Para obtener más información, consulte:<ul><li>[Compositor de experiencias visuales para aplicaciones móviles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS: configuración de la aplicación móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar el rastreo de clics en el VEC móvil](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium 19.4.2 (30 de abril de 2019) {#release-19-4-2}

Esta versión incorpora las siguientes funciones, cambios y mejoras:

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

### Actualizaciones de funciones

| Función/Mejora | Descripción |
| --- | --- |
| [!UICONTROL Compositor de experiencias visuales] | El [!UICONTROL Compositor] de experiencias visuales (VEC) incluye las siguientes mejoras para que su trabajo sea más rápido y eficiente:<ul><li>La función de ruta DOM ahora está disponible al configurar el rastreo de clics.<br>Para obtener más información, consulte [Rastreo de clics](/help/c-activities/r-success-metrics/click-tracking.md#considerations).</li><li>Utilice el panel Estilos para ver o editar el valor de los estilos existentes para el elemento seleccionado. También puede añadir estilo adicional.<br>Para acceder al panel Estilos, haga clic en un elemento de página desde el VEC y, a continuación, haga clic [!UICONTROL en Editar] &gt; [!UICONTROL Estilos].<br>El panel Estilos aparece a la derecha del VEC. El panel contiene una lista de estilos que le permite editar o agregar al elemento seleccionado. Un editor CSS en tiempo real permite ver cambios y agregar estilos si se siente cómodo utilizando hojas de estilo en cascada (CSS) o si recibe código de su desarrollador.<br>Para obtener más información, consulte [Estilos](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) en *opciones del Compositor de experiencias visuales*.</li><li>El Editor de texto enriquecido ahora admite elementos anidados HTML 5.<br>Las especificaciones HTML 5 permiten nuevas combinaciones de etiquetas para anidar. La versión anterior del editor de texto enriquecido no permitía el anidamiento nuevo de etiquetas como lo permitía la especificación HTML 5. Como resultado, los elementos anidados seleccionados en el VEC no se gestionaban correctamente, lo que producía cambios HTML no deseados. (TGT -33618)<br>Para obtener más información, consulte [Editar texto/HTML](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html) en *las opciones del Compositor de experiencias visuales*.</li> |

### Mejoras, correcciones y cambios

* Hemos mejorado el flujo de trabajo de eliminación de recursos con el VEC. Los recursos eliminados ahora se eliminan de la biblioteca [!UICONTROL Ofertas] y del [!DNL Scene7] (si procede). Los recursos eliminados ya no se muestran en los resultados de la búsqueda. (TGT-31981)
* Ahora puede eliminar carpetas de recursos incluso si contienen imágenes (carpetas que no estén vacías). (TGT-33265)

   Anteriormente, no se podía eliminar una carpeta que no estaba vacía de la biblioteca de ofertas de imágenes de Target ([!UICONTROL Ofertas] &gt; [!UICONTROL Ofertas de imágenes]). Obtendría una «Carpeta no está vacía». al intentar eliminar la carpeta de la interfaz de usuario. Con esta función, hemos añadido la capacidad de permitir la eliminación de carpetas para eliminar una carpeta entera que contenga cualquier número de recursos y subcarpetas dentro de. Esta función está disponible en la interfaz de usuario de Target también en la interfaz de usuario de Recursos de Adobe Experience Cloud.

   * Las carpetas que no estén vacías en la biblioteca de ofertas de imágenes se pueden eliminar. Si no se hace referencia a todas las imágenes de la carpeta en ninguna actividad, se eliminará toda la carpeta y su contenido. Si se hace referencia a algunas imágenes dentro de la carpeta en cualquier actividad, se eliminan todas las imágenes sin referencia, pero se conservan las imágenes y carpetas que contienen esas imágenes.
   * La representación de ofertas de imágenes en el selector de recursos de imagen se hace más rápida y eficaz.
   Para obtener más información, consulte [Trabajo con contenido en la biblioteca](/help/c-experiences/c-manage-content/assets-working.md). (TGT-32897)

* Hemos mejorado la representación de ofertas de imagen en el Selector de recursos. Ahora, mostrar y seleccionar ofertas de imagen es más rápido y eficaz. (TGT-32897)
* Se ha mejorado la gestión de las redirecciones a las URL cuando se cancela la carga de una página dentro del VEC. (TGT-33815)
* Después de seleccionar una [!UICONTROL colección de Recomendaciones] en el selector Colecciones, ahora debe hacer clic en [!UICONTROL el] botón Guardar. Este flujo de trabajo es coherente respecto a otros flujos de trabajo dentro de [!DNL Target]. (TGT-33205)
* Se ha corregido un problema que provocaba que un pequeño conjunto de informes de Insight devolviera tasas de conversión del 0% en lugar de las tasas de conversión reales. (TNT-32125)

## [!DNL Target] Standard/Premium 19.4.1 (15 de abril de 2019) {#release-19-4-1}

Esta es una versión de mantenimiento e incluye el siguiente cambio:

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

* Se ha actualizado [!DNL Adobe Experience Cloud] la interfaz de usuario para reflejar los cambios de marca y productos. (TGT-33546, TGT-33272 y TGT-33331)

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios en la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte [Notas de la versión de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |