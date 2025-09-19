---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 14%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe]proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

+++Ver detalles
El equipo [!DNL Target] ofrece una característica temporal que le permite cambiar entre la interfaz de usuario [!DNL Target] actualizada y la versión heredada con un botón de alternancia. Esta opción solo está disponible durante la fase final del despliegue de la interfaz de usuario.

![Alternar versión de IU de Target](/help/main/r-release-notes/assets/toggle.png)

Una vez completado el despliegue, se eliminará la opción y todos los usuarios harán la transición de forma permanente a la interfaz de usuario actualizada. [!DNL Adobe] recomienda planificar con anticipación, ya que esta función se eliminará gradualmente en breve.

#### Cronología de desuso

Debido a problemas identificados recientemente, relacionados principalmente con personalizaciones complejas de clientes, el equipo [!DNL Target] ha ajustado la cronología de desuso:

* **17 de junio de 2025**: todas las organizaciones de IMS se han habilitado para la interfaz de usuario [!DNL Target] actualizada, ya sea para usuarios específicos o para toda la organización, para comenzar a probar la nueva experiencia.

* **30 de junio de 2025**: la [interfaz de usuario actualizada [!DNL Target] 4&rbrace; se convirtió en la experiencia predeterminada para todas las organizaciones de IMS que han habilitado la opción de versión de interfaz de usuario.](/help/main/c-intro/understand-the-target-ui.md)

   * Los clientes que actualmente ven la IU heredada de forma predeterminada ahora ven la IU actualizada al iniciar sesión.
   * El conmutador Versión de la interfaz de usuario permanece disponible hasta finales de julio, lo que permite a los usuarios volver si es necesario.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recomienda encarecidamente usar la interfaz de usuario [!DNL Target] actualizada. Cambie a la interfaz de usuario heredada solo si se produce un problema de bloqueo debido a las [limitaciones del comportamiento del conmutador de alternancia](#limitations).

* **Del 15 de julio al 30 de julio de 2025**: la opción de versión de la interfaz de usuario se deshabilitará de forma permanente por fases. Las organizaciones de IMS afectadas ya no pueden volver a la IU heredada.

   * Las excepciones se examinan caso por caso.
   * Los retrasos en la desaprobación de la alternancia solo se conceden brevemente (unos días) mientras se resuelven los problemas del bloqueador.

Póngase en contacto con el servicio de atención al cliente de [Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) si tiene dudas o si prevé problemas durante esta transición.

#### Limitaciones del comportamiento de alternancia de IU {#limitations}

La siguiente información describe las limitaciones que debe tener en cuenta al elegir utilizar la opción de versión:

* **Visibilidad de nuevas actividades**: las actividades creadas en la interfaz de usuario actualizada no serán visibles si vuelve a la interfaz de usuario heredada.
* **Edición de actividades existentes**: los cambios realizados en las actividades existentes (creadas originalmente en la interfaz de usuario heredada) al utilizar la interfaz de usuario actualizada se publican en el sitio web. Sin embargo, estas actualizaciones no están visibles en la interfaz de usuario heredada si vuelve; solo aparecen allí las últimas actualizaciones realizadas desde la interfaz de usuario heredada.
* **Consistencia de los detalles de la actividad**: los cambios más recientes, independientemente de la interfaz de usuario que utilice, se reflejarán en el sitio web activo. Sin embargo, la IU heredada solo muestra los cambios más recientes realizados desde esa versión. Esta situación puede causar confusión si las actividades editadas en la interfaz de usuario actualizada tienen un aspecto diferente al que se ve en la interfaz de usuario heredada.

#### Recursos adicionales para obtener más información sobre la IU actualizada

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.
* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).
* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].
* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.
* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.
* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

+++

## Actualizaciones del flujo de datos (19 de septiembre de 2025)

La combinación de ID de flujo de datos y zona protegida debe ser única para [!DNL Adobe Target] conexiones de destino.

Se ha actualizado la lógica de validación de [!DNL Target] conexiones de destino para exigir que la combinación del ID de secuencia de datos y el nombre de la zona protegida sea única dentro de una organización de IMS. Esto significa que:

* El mismo par ID + nombre de zona protegida de secuencia de datos no se puede reutilizar en varias conexiones de destino [!DNL Target].
* El mismo ID de flujo de datos solo se puede utilizar para conexiones diferentes si están configuradas en entornos limitados diferentes.
* Esta regla se aplica a todas las selecciones de flujos de datos, incluso cuando se selecciona &quot;Ninguno&quot;.

Esta actualización garantiza una configuración coherente y evita conflictos entre entornos de varias zonas protegidas. Para obtener más información, consulte [Conexión de Adobe Target](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} en la guía *Destinos de Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 de septiembre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Experience Fragments]**

+++Ver detalles
* **Se mejoró la atribución de usuarios para [!UICONTROL AEM Experience Fragment] ofertas.** ha resuelto un problema en el VEC en el cual el campo &quot;[!UICONTROL Last updated]&quot; para [!UICONTROL AEM Experience Fragment] (XF) ofertas mostraba incorrectamente un ID de código en lugar del nombre de usuario. Esta discrepancia se producía durante la selección de la oferta en la interfaz de usuario actualizada, lo que crea incoherencia con la interfaz de usuario heredada y las ofertas de HTML, que muestran correctamente el nombre del último editor. Esta corrección garantiza una atribución de usuario coherente entre los tipos de oferta, lo que mejora la transparencia y la alineación con el comportamiento esperado. (TGT-52880 y TGT-52898)

+++

**Offer Decisioning**

+++Ver detalles
* **Error de decisión de oferta resuelto para ofertas ODE.** ha resuelto un problema en el cual las ofertas del Motor de decisión de ofertas (ODE) insertadas a través de [!DNL Target] devolvían un error 400 debido a la falta de metadatos de formato. El mensaje de error indicaba que el tipo MIME era nulo, lo que impedía el procesamiento correcto de las decisiones de oferta. Esta corrección garantiza la administración adecuada de los metadatos de la oferta, restaura la funcionalidad para la entrega de contenido personalizado y permite la ejecución ininterrumpida de campañas de marketing. (TGT-53635)
* **Problema de procesamiento de ofertas de ODS resuelto.** ha resuelto un problema en el cual las ofertas [!DNL Offer Decision Service] (ODS) creadas mediante [!DNL Adobe Journey Optimizer] (AJO) no se representaban cuando las actividades se creaban mediante el VEC en la interfaz de usuario actualizada. La misma configuración funcionaba correctamente en la interfaz de usuario heredada, lo que producía confusión y bloqueaba la ejecución de campañas. Esta corrección garantiza una entrega de ofertas coherente en ambas versiones de la interfaz de usuario, lo que restaura el comportamiento esperado para la personalización basada en AJO.

+++

**Informes**

+++Ver detalles
* **Opción de descarga restaurada en la sección de informes de la IU actualizada de Información general de informes.** ha resuelto un problema en la nueva interfaz de usuario de información general en el que el botón [!UICONTROL Download] no aparecía en la sección Informes, lo que impedía a los usuarios exportar puntuaciones de importancia de atributos. Esta actualización restaura la funcionalidad completa de exportación, lo que permite un acceso optimizado a los datos descargables para su análisis y sistema de informes. (TGT-53222)
* Botón **[!UICONTROL Download full CSV report]restaurado en la vista [!UICONTROL Important attributes].** ha resuelto un problema en la interfaz de usuario de creación de actividades actualizada en el que faltaba el botón [!UICONTROL Download full CSV report] en la sección [!UICONTROL Important Attributes] de la vista Informes. Esta corrección restaura el acceso a las perspectivas descargables, lo que garantiza una funcionalidad coherente en las IU actualizadas y heredadas. (TGT-53238)
* **Problemas resueltos de la interfaz de usuario que afectan a la creación de informes de [!UICONTROL Auto Target] en la IU de descripción general actualizada.** Se han corregido varios problemas de interfaz de usuario en la interfaz de información general actualizada que afectaban a los informes de actividad [!UICONTROL Auto Target]. Estas correcciones incluyen:

   * Faltan métricas de alza y confianza en los informes de resumen
   * Indicador de color incorrecto para la casilla de verificación &quot;modelos creados&quot;
   * Informe de gráfico no funcional a pesar de la variación de datos en [!DNL Analytics]
   * Falta el vínculo de descarga para los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes]
   * Visualización del informe [!UICONTROL Automated Segments] interrumpida

  Estas correcciones restauran el comportamiento esperado de los informes y mejoran la visibilidad del rendimiento de [!UICONTROL Auto Target] en la interfaz de usuario actualizada. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Ver detalles
* **Validación de formulario corregida para las condiciones de presencia de parámetros en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual al seleccionar &quot;[!UICONTROL Custom mbox parameter value is present]&quot; o &quot;[!UICONTROL Parameter is present]&quot; se requería incorrectamente que los clientes especificaran un valor. Este comportamiento entra en conflicto con la lógica deseada, que simplemente comprueba la existencia de un parámetro independientemente de su valor. La corrección alinea la validación del formulario con el comportamiento esperado, lo que permite una configuración de la actividad más suave y admite la adopción completa de la IU actualizada. (TGT-53638)
* **Se ha corregido la lógica del formulario para las reglas de presencia de parámetros en la entrega de páginas.&quot;** ha resuelto un problema en la interfaz de usuario actualizada que hacía que, al seleccionar reglas de entrega de páginas como &quot;[!UICONTROL Parameter is present]&quot;, &quot;[!UICONTROL Parameter is not present]&quot;, &quot;[!UICONTROL Parameter value is present]&quot; o &quot;[!UICONTROL Parameter value is not present]&quot;, se exigiera incorrectamente a los usuarios que especificaran un valor de parámetro adicional. Este comportamiento era incoherente con la interfaz de usuario heredada y contradecía la lógica pretendida de detectar la presencia de parámetros sin especificar un valor. Esta corrección restaura el comportamiento esperado de la configuración de reglas, optimiza la configuración de actividades y mejora la facilidad de uso. (TGT-53640)
* **Se ha mejorado la lógica de validación para el generador de reglas de varias páginas en la IU actualizada.** ha resuelto varios problemas de validación en el generador de reglas de varias páginas dentro de la interfaz de usuario actualizada. Estas correcciones incluyen:

   * Impedir la creación de reglas cuando el parámetro de mbox está vacío
   * Visualización de mensajes de error adecuados para estados de regla no válidos
   * Corrección de la lógica de validación para operadores unarios y basados en parámetros que no requieren valores de operando
   * Activación de las reglas de fragmento hash con operadores unarios mediante la restauración de la funcionalidad de guardado

  Estas actualizaciones garantizan una configuración de reglas precisa y mejoran la facilidad de uso en escenarios de entrega de páginas complejos. (TGT-53722)
* **Problema de cambio de nombre de ubicación resuelto en las actividades A/B y MVT.** Se ha corregido un error en la interfaz de usuario actualizada que hacía que el cambio de nombre de una ubicación en una actividad [!UICONTROL A/B Test] o [!UICONTROL Multivariate Test] (MVT) no persistiera después de navegar entre la lista de ubicaciones, el direccionamiento y atrás. Esta actualización garantiza que los cambios en el nombre de la ubicación se guarden y se reflejen de forma coherente en todo el flujo de trabajo de la actividad. (TGT-52367)
* **Se ha corregido la persistencia de nombre de ubicación para actividades MVT y AP en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual los nombres de ubicación editados en las actividades [!UICONTROL Multivariate Test] (MVT) y [!UICONTROL Automated Personalization] (AP) no se guardaban correctamente. Después de cambiar el nombre de una ubicación, al desplazarse entre las fichas, como [!UICONTROL Targeting] y [!UICONTROL Experiences], los nombres volvieron a su estado anterior. Esta corrección garantiza una nomenclatura de ubicación coherente en todas las pestañas y mejora la fiabilidad durante la configuración de la actividad. (TGT-52927)
* Se ha corregido el etiquetado de ubicación **en el panel Administrar experiencias para actividades MVT.** ha resuelto un problema en la interfaz de usuario actualizada en el que el panel [!UICONTROL Manage Experiences] de las actividades [!UICONTROL Multivariate Test] (MVT) mostraba una numeración de ubicación incoherente. Esta corrección garantiza que las etiquetas de ubicación sean secuenciales y estén correctamente alineadas con las modificaciones definidas por el usuario, lo que mejora la claridad y la facilidad de uso durante la configuración de la experiencia. (TGT-52929)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| [Cambios de la documentación](/help/main/r-release-notes/doc-change.md) | Vea información detallada sobre las actualizaciones que se realizaron en esta guía y que no se incluyen en estas notas de la versión. |
| [Notas de la versión para versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium. |
| [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es){target=_blank} | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud. |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
