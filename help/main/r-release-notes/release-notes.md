---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 15%

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

* **30 de junio de 2025**: la [interfaz de usuario actualizada [!DNL Target] 4} se convirtió en la experiencia predeterminada para todas las organizaciones de IMS que han habilitado la opción de versión de interfaz de usuario.](/help/main/c-intro/understand-the-target-ui.md)

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

## [!DNL Target Standard/Premium] 25.8.1 (7 de agosto de 2025)

Esta versión incluye las siguientes mejoras y correcciones:

**Actividades**

+++Ver detalles
* Se han corregido varios problemas con la interfaz de usuario actualizada, incluidos errores al eliminar tipos de página debido al espaciado en los valores de entrada, la copia de actividades no fiable entre espacios de trabajo y las reglas de entrega de páginas con error en entornos de control de calidad. (TGT-52703)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual los usuarios con el rol [!UICONTROL Editor] podían acceder e intentar editar actividades activas, que deberían restringirse. Las pantallas de lista de actividades y de información general mostraban incorrectamente las opciones de edición para actividades en directo, lo que producía posibles cambios no deseados. (TGT-53055)
* Se ha corregido un problema en la interfaz de usuario de [!UICONTROL Advanced Search] por el cual al seleccionar los operadores &quot;el valor está presente&quot; o &quot;el valor no está presente&quot; se pedía a los usuarios que escribieran un operando, que no debería ser necesario para estas condiciones. (TGT-51961)
* Se ha corregido un problema en la IU actualizada por el que los intentos de copiar actividades del espacio de trabajo de ensayo al de producción fallaban de forma consistente, incluso en entornos de zona protegida. Los clientes han encontrado varios mensajes de error, incluidas &quot;Audiencia anónima ya utilizada por la actividad&quot; e &quot;ID de audiencia no válido&quot;, a pesar de usar configuraciones válidas y tener los permisos de espacio de trabajo adecuados. (TGT-52394)

+++

**Fragmentos de experiencias (XF)**

+++Ver detalles
* Se ha corregido un problema en el cual el contenido de Fragmento de experiencia (XF) no se podía procesar en la vista previa de [!UICONTROL Visual Experience Composer] (VEC) a pesar de funcionar correctamente en la entrega de contenido. (TGT-53318)

+++

**Localización**

+++Ver detalles
* Se ha corregido un problema de localización en el que el botón Añadir promoción de la sección Promociones aparecía sin localizar en varios entornos de idioma en el inquilino de control de calidad. (TGT-53263)

+++

**Ofertas**

+++Ver detalles
* Se ha corregido un problema en el cual la edición de una oferta de HTML existente a través del Compositor de experiencias visuales (VEC) provocaba que todas las modificaciones se eliminaran de la entrega de contenido. Los cambios aparecen atenuados en la pestaña de modificación y no se reflejan en las vistas previas de control de calidad, a pesar de que se aplican correctamente en la interfaz de usuario heredada. (TGT-52863)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual las modificaciones de ofertas de HTML realizadas en [!UICONTROL Visual Experience Composer] (VEC) no persistían después de volver de la pestaña [!UICONTROL Targeting] a [!UICONTROL Experiences]. (TGT-52874)
* Se ha corregido un problema en la IU actualizada de [!DNL Target] por el cual la inserción de una oferta de HTML antes y otra después del mismo selector provocaba una generación de ubicación incorrecta. Cuando los clientes regresaron de la ficha [!UICONTROL Targeting] a la ficha [!UICONTROL Experience], solo se retuvo un selector, lo que resultó en la pérdida de modificaciones y la entrega de contenido interrumpida. Este comportamiento difería de la interfaz de usuario heredada, que conservaba correctamente ambas modificaciones con identificadores de ubicación distintos. (TGT-52891)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada por el cual al hacer clic en una oferta agregada dentro del carril [!UICONTROL Modifications], el panel derecho [!UICONTROL Configuration] aparecía y desaparecía intermitentemente, lo que dificultaba la interacción con la configuración de la oferta. (TGT-53288)
* Se ha corregido un problema por el cual las ofertas de HTML agregadas a variaciones específicas de audiencia dentro de una actividad no se guardaban ni aparecían de forma coherente en la sección de modificación. Después de cambiar entre audiencias durante la edición, las ofertas aplicadas anteriormente a veces desaparecían o no se procesaban, lo que interrumpía la validación y retrasaba la preparación de la actividad. (TGT-53440)
* Se ha corregido un problema que causaba que, al copiar una actividad que incluía ofertas, se crearan ofertas duplicadas en la nueva actividad. Este comportamiento causaba un desorden y una confusión innecesarios, especialmente al mover actividades entre espacios de trabajo. La corrección garantiza que las ofertas de [!DNL Target] ahora se copien correctamente en el espacio de trabajo de destino sin duplicación, lo que optimiza la administración de actividades y mejora la eficacia del flujo de trabajo. (TGT-53454)

+++

**Aplicaciones de una sola página (SPA)**

+++Ver detalles
* Se ha corregido un problema en el VEC actualizado que impedía que los clientes aplicaran modificaciones a las vistas de [!UICONTROL Single Page Application] (SPA). Mientras que las actividades creadas en la IU antigua admitían la segmentación específica de la vista, la nueva IU no detectaba ni permitía las ediciones en esas vistas, con los controles de cambio de vista apareciendo deshabilitados. (TGT-52556)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* Se corrigió un problema en el cual las modificaciones realizadas en las experiencias dentro de [!UICONTROL Visual Experience Composer] no eran visibles o aparecían de forma incoherente en la interfaz de usuario. (TGT-TGT-53381)
* Se ha corregido un problema en el VEC actualizado en el cual la sección [!UICONTROL Manage Content] no mostraba texto alternativo para miniaturas de experiencias. Este problema dificultaba a los usuarios la identificación de documentos, especialmente cuando los nombres de archivo eran largos o estaban truncados. (TGT-52291)
* Se corrigió un error en el cual los clientes encontraban errores de validación incorrectos al configurar las reglas de [!UICONTROL page delivery] en las actividades VEC. En concreto, operadores como &quot;es igual a cualquiera de&quot; y &quot;no es igual a ninguno de&quot; activaron &quot;Entrada no válida para el tipo de operador&quot; al introducir valores de texto, aunque se debería admitir texto. (TGT-52629)
* Se han corregido varios problemas que provocaban un comportamiento incoherente en el panel [!UICONTROL Modifications] de la interfaz de usuario actualizada al seleccionar ofertas con el botón &quot;Seleccionar una oferta&quot;. En lugar de reemplazar la oferta existente, la interfaz de usuario agregó un duplicado e intentó interactuar con cualquiera de las ofertas, lo que resultó en errores de consola como `selectorNotFound`. Además, algunas ofertas no muestran el botón &quot;Seleccionar una oferta&quot;, que solo muestra propiedades editables. (TGT-53321)
* Se ha corregido un problema en la interfaz de usuario actualizada de [!DNL Target] por el cual los cambios de código de HTML realizados durante la configuración de la actividad no persistían en las páginas de variación, aunque se guardaban correctamente para los grupos de control. A pesar de varios intentos y de volver a crear pruebas sin agrupaciones de páginas, las páginas de variación no conservaban las modificaciones, lo que afectaba a la entrega de contenido y a la validación del control de calidad. (TGT-53436)
* Se ha corregido un problema en el VEC actualizado en el cual el operador &quot;es igual a cualquiera de&quot; en las reglas de entrega de página no acepta valores de entrada. Al configurar los parámetros del cliente en todos los mboxes, seleccionar este operador daba como resultado un error de &quot;Entrada no válida&quot;, lo que impedía la creación de reglas. (TGT-52623)

+++

**Espacios de trabajo**

+++Ver detalles
* Mejora del flujo de trabajo al copiar actividades entre espacios de trabajo. Anteriormente, la copia de actividades entre espacios de trabajo provocaba errores de sincronización debido a la falta de audiencias y a propiedades sin asignar. Esta actualización presenta un flujo de trabajo más inteligente e intuitivo que garantiza que las actividades copiadas estén correctamente configuradas y listas para su publicación. (TGT-47094)
* Se ha corregido un problema en el cual los clientes no podían copiar actividades entre espacios de trabajo debido a un error en la mutación `copyActivityBatchOperations`. Los intentos de duplicar actividades dieron como resultado un error de servidor (500) y una carga de respuesta nula. (TGT-52405)
* Se ha corregido un problema en el cual las actividades no se sincronizaban cuando las ofertas a las que se hace referencia en la configuración no eran accesibles en el espacio de trabajo seleccionado. Esto provocaba errores de publicación y dejaba las actividades en un estado fallido. (TGT-52535)
* Se corrigieron varios problemas al copiar actividades entre espacios de trabajo en la interfaz de usuario [!DNL Target] actualizada. Los clientes encontraron errores relacionados con el acceso a la audiencia, especialmente con las actividades activas y la validación incorrecta de privilegios, incluso cuando el usuario tenía funciones &quot;[!UICONTROL Approver]&quot; en los espacios de trabajo de origen y destino. (TGT-53002)
* Se ha corregido un problema en la IU actualizada por el cual la copia de actividades dentro del mismo espacio de trabajo duplicaba de forma innecesaria ofertas y audiencias asociadas. (TGT-53457)
* Se ha corregido un problema que se producía al tratar casos en los que las audiencias ad hoc (anónimas) no se copiaban correctamente entre espacios de trabajo no predeterminados o de espacios de trabajo no predeterminados a predeterminados. Aunque las actualizaciones anteriores garantizaban la duplicación adecuada en los escenarios predeterminados, no predeterminados y del mismo espacio de trabajo, esta mejora se centraba en preservar las configuraciones de audiencia combinadas que abarcan varios espacios de trabajo. La corrección garantiza un comportamiento de audiencia coherente y una segmentación precisa en todas las transiciones del espacio de trabajo. (TGT-53268)

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
