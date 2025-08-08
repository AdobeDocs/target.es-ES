---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f00cec3194863bb7187d4cdc91c39a87b624e9bd
workflow-type: tm+mt
source-wordcount: '4816'
ht-degree: 11%

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

## [!DNL Target Standard/Premium] 25.7.4 (1 de agosto de 2025)

Esta versión resuelve problemas recientes, causados principalmente por las personalizaciones complejas de los clientes, e incluye las siguientes correcciones y mejoras:

**Actividades**

+++Ver detalles
* Se ha corregido un problema en el cual un cliente encontraba el error &quot;Entrada de usuario no válida&quot; al intentar guardar una actividad activa, incluso sin realizar cambios. La respuesta de GraphQL indica un problema de ID local duplicado. (TGT-53329 Y TGT-53373 Y TGT-53195)
* Se ha corregido un problema que impedía crear una experiencia de redireccionamiento en el VEC actualizado. Se ignoró la dirección URL de redireccionamiento y se mostró la página original en su lugar. (TGT-53306)

+++

**Localización**

+++Ver detalles
* Se corrigió un problema de localización en el modal [!UICONTROL Create Criteria], al seleccionar la opción &quot;entre los siguientes valores&quot; en la lista desplegable [!UICONTROL Choose Price Rule], se deslocalizó la cadena &quot;a&quot; en la sección [!UICONTROL Inclusion Rules]. (TGT-49754)
* Se ha corregido un problema de localización con la cadena &quot;[!UICONTROL All host groups]&quot; en la lista desplegable [!UICONTROL Environment] del Asistente para la creación de fuentes que no está localizada correctamente. (TGT-46737)

+++

**QA**

+++Ver detalles
* Se ha corregido un problema en el cual el entorno de control de calidad no podía cargar datos en varias pestañas, lo que inutilizaba la interfaz. (TGT-53377)
* Se ha corregido un problema que impedía crear una actividad en el entorno de control de calidad. El proceso se redirigió a la página [!UICONTROL Activities] en lugar de completarse correctamente. (TGT-53328)

+++

**Recommendations**

+++Ver detalles
* Se corrigió un problema en el cual al pasar el ratón por encima del operando &quot;aprendizaje profundo&quot; mientras se creaba una colección en [!DNL Recommendations], la página se bloqueaba. (TGT-53305)
* Se corrigió un problema en el cual las sugerencias de filtro en [!UICONTROL Catalog Search] en la interfaz de usuario actualizada eran inexactas. (TGT-52007)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el cual el filtro Operandos aparecía al usar los operadores &quot;el valor está presente&quot; o &quot;el valor no está presente&quot;, aunque debería estar oculto. (TGT-53012)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* Se corrigió un problema en el cual un usuario hacía clic en [!UICONTROL Manage Content] y luego en [!UICONTROL Done] mientras editaba una actividad de Automated Personalization (AP), la página se quedaba en blanco y dejaba de responder. (TGT-53047 y TGT-52993)
* Se corrigió un problema en el cual al seleccionar la métrica de conversión [!UICONTROL Viewed an mbox] en [!UICONTROL Goals & Settings] la página se bloqueaba. (TGT-53346, TGT-53343 y TGT-53348)
* Se ha corregido un problema en el cual la característica [!UICONTROL Redirect to URL] no funcionaba como se esperaba; no se produce ninguna redirección incluso con direcciones URL válidas. (TGT-53307)

+++

**Espacios de trabajo**

+++Ver detalles
* Se ha corregido un problema que se producía al copiar actividades entre espacios de trabajo y que provocaba entradas duplicadas de &quot;Audience Copy&quot; y conflictos de ID. Las audiencias ahora se copian con ID únicos, contexto de espacio de trabajo y control recursivo para audiencias combinadas (hasta 5 niveles). (TGT-53081)
* Se ha corregido un problema que se producía cuando el área de trabajo se establecía en &quot;[!UICONTROL All Workspaces]&quot; y al copiar una actividad que ya existe en el área de trabajo predeterminada se producía un error incorrecto:

  &quot;Se debe incluir al menos una propiedad para los espacios de trabajo no predeterminados&quot;.

  Dado que la copia se encuentra dentro del espacio de trabajo predeterminado, no se debe requerir ninguna propiedad. Al intentar agregar una propiedad y guardar, se produce un segundo error:

  &quot;Entrada de usuario no válida&quot;

+++

## [!DNL Target Standard/Premium] 25.7.3 (viernes, 24 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles
* Se corrigió un problema en el cual el método `buildViews` de la clase de generador establecía incorrectamente `viewMaxLocalId` en el recuento total de vistas, en lugar de en la asignación de `viewLocalId` más alta. (TGT-53207)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual las ofertas eliminadas en las actividades [!UICONTROL Automated Personalization] (AP) se mostraban como `Deleted option with ID: X` en lugar de sus nombres originales (por ejemplo, `Offer Name [Deleted]`, como se muestra en la interfaz de usuario heredada). Esta corrección restaura el etiquetado significativo de las ofertas eliminadas, lo que mejora la claridad y hace que la creación de informes sea más precisa y fácil de usar. (TGT-52921)
* Se corrigió un problema en el cual algunas actividades migraron del front-end [!DNL Target] a [!DNL Target] Central tenían configuraciones de métricas incoherentes debido a un error de sincronización corregido anteriormente. Específicamente, las actividades que originalmente usaron una métrica de conversión y luego se actualizaron a una métrica basada en análisis retuvieron valores obsoletos en los campos `primaryMetricType` y `successCriteria`. (TGT-52643)
* Se corrigió un problema en el cual todo el contenido de una página de vista previa de control de calidad se podía editar debido a la inclusión no deseada del atributo `contentEditable` en las modificaciones de HTML. Esto permitía a los usuarios hacer clic y editar cualquier texto de la página, lo que podía causar problemas de diseño y confusión durante el control de calidad. (TGT-53247)
* Se ha corregido un problema por el cual al mover una modificación de [!DNL Page Load] a [!UICONTROL View] se duplicaba la modificación, permaneciendo en [!UICONTROL Page Load] y apareciendo también en [!UICONTROL View]. Además, si se quita la modificación de [!UICONTROL View], también se quitaría incorrectamente de [!UICONTROL Page Load]. (TGT-53270)

+++

**API**

+++Ver detalles
* Se ha corregido un problema en la capa de persistencia del back-end por el cual las opciones eliminadas se almacenaban correctamente, pero no se podía acceder a ellas a través de puntos finales de API existentes. Como resultado, las aplicaciones de front-end no pudieron recuperar nombres significativos para las opciones eliminadas, lo que afectó a las vistas históricas de los informes. Esta corrección garantiza que los datos de opciones eliminados conservados ahora se puedan mostrar correctamente en la interfaz de usuario. (TGT-52973)
* Se implementó un nuevo extremo de migración para admitir la transferencia de opciones de actividad eliminadas de actividades basadas en JCR a [!DNL Target] actividades centrales. Esta funcionalidad permite un seguimiento y un sistema de informes coherentes entre sistemas. Esta característica garantiza que las opciones eliminadas se conserven y sincronicen en el front-end y back-end de [!DNL Target], lo que mejora la integridad de los datos y los informes históricos. (TGT-53217)
* Se ha introducido un nuevo extremo de API que permite a los usuarios restaurar las opciones de actividad eliminadas anteriormente desde una base de datos secundaria. Esta funcionalidad aprovecha la infraestructura existente proporcionada por las clases `RemovedCampaignElements` y `RemovedOptionInfo`, lo que garantiza la reintegración perfecta de las opciones eliminadas en las actividades activas. (TGT-52903)
* Se ha corregido un problema en el cual las actividades [!DNL Recommendations] que contenían nombres de métricas de más de 25 caracteres no se podían abrir ni editar debido a limitaciones de API. Esta corrección garantiza la compatibilidad con los nombres de métricas que superan el límite de caracteres y restaura el acceso completo a las actividades afectadas. (TGT-52839)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] que hacía que el editor se bloqueara después de hacer clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) ) al crear o editar una actividad [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalles
* Se ha corregido un problema que impedía que [!UICONTROL Catalog Search] cargara resultados adicionales al desplazarse hasta la parte inferior de la lista, restaurando un comportamiento coherente con la interfaz de usuario heredada. (TGT-53088)
* Se ha corregido un problema que bloqueaba la eliminación de elementos del cuadro de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Se ha corregido un problema que impedía abrir o interactuar con productos sin nombre. Este problema se producía al seleccionar entornos que devolvían resultados sin nombre, lo que impedía el acceso a los detalles del producto. (TGT-53007)
* Se ha corregido un problema que hacía que la página [!UICONTROL Catalog Search] se bloqueara y mostrara una pantalla en blanco al seleccionar ciertos productos. (TGT-53087)
* Se ha corregido un problema en el cual los usuarios no podían editar la actividad de site_cart_z1 [!DNL Recommendation] en la interfaz de usuario de [!DNL Target]. Al intentar abrir la actividad, se produjo un error en la página [!UICONTROL Overview] que bloqueó el acceso al editor. (TGT-53221)

+++

**Creación de informes**

+++Ver detalles
* Se corrigió un problema en el cual el campo de espacio aislado de la base de datos de actividad no se borraba al cambiar el origen de informes de [!DNL Customer Journey Analytics] o [!DNL Analytics] a [!DNL Target]. Anteriormente, la interfaz de usuario enviaba correctamente la zona protegida: null, pero el backend ignoraba este valor, lo que dejaba los datos obsoletos de la zona protegida en su lugar. El servidor ahora borra correctamente el campo de la zona protegida cuando se recibe un valor nulo. (TGT-52798)
* Se ha vuelto a implementar la capa de persistencia de opciones eliminadas en el backend de Target para admitir la creación de informes históricos precisos en actividades [!UICONTROL Automated Personalization] (AP). Anteriormente, cuando se eliminaba una opción, se perdía su nombre, lo que dificultaba la interpretación de los datos de rendimiento anteriores.

  **Mejoras de clave**:

   * Las opciones eliminadas ahora se rastrean usando la infraestructura existente de `RemovedCampaignElements` y `RemovedOptionInfo`.
   * Cuando se elimina una opción de una actividad AP, se conservan sus metadatos (por ejemplo, ID y nombre).
   * La interfaz de usuario de creación de informes ahora puede mostrar el nombre de opción original (por ejemplo, `Option Name [Deleted]`) junto con las métricas históricas, lo que mejora la claridad y la facilidad de uso.

  Esta actualización garantiza la creación de informes coherentes y significativos, incluso después de eliminar las opciones de una actividad. (TGT-52986)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* Se ha corregido un problema en el VEC por el cual la aplicación de una modificación a una vista provocaba duplicación y activaba un error de &quot;entrada de usuario no válida&quot;. (TGT-52886)
* Se corrigió un problema con la funcionalidad [!UICONTROL Undo] para las opciones [!UICONTROL Insert Before] y [!UICONTROL Insert After] al configurar ofertas de imagen en el VEC.

  Anteriormente, deshacer una acción de [!UICONTROL Insert Before] o [!UICONTROL Insert After] en ofertas de imagen resultaba en un comportamiento incoherente o en un error al revertir correctamente la modificación, especialmente en las actividades creadas en la interfaz de usuario de [!DNL Target] heredada. Este problema se ha resuelto para garantizar que las acciones de deshacer ahora funcionen de forma fiable para estas modificaciones. (TGT-52809)

* Se corrigió un problema en el cual el atributo `contentEditable` se establecía involuntariamente como verdadero y persistía en el contenido de HTML guardado. Esta actualización garantiza una salida de HTML más limpia y esperada sin un comportamiento de edición no deseado. (TGT-52319)
* Para evitar la pérdida permanente de opciones eliminadas y garantizar un comportamiento coherente entre servicios, se ha implementado la funcionalidad de eliminación suave para las opciones de la interfaz de usuario y los microservicios relacionados.

  **Cambios clave**:

   * Las opciones ya no se eliminan de forma permanente. En su lugar, se marcan con un nuevo indicador eliminado: true en el objeto XML de parámetros.
   * Solo la interfaz de usuario [!DNL Target] actualizada usa este indicador para excluir de la representación las opciones eliminadas y para evitar que se envíen a los servicios Edge.
   * Las opciones eliminadas siguen formando parte de la carga útil de la actividad durante las ediciones, lo que garantiza la trazabilidad y evita al mismo tiempo la entrega de opciones inexistentes a los clientes.

  Esta actualización mejora la integridad de los datos y se ajusta a las prácticas recomendadas para administrar eliminaciones en sistemas distribuidos. (TGT-52726)

+++

**Espacios de trabajo**

+++Ver detalles
* Se ha corregido un problema que se producía al copiar una actividad de un espacio de trabajo no predeterminado a predeterminado o entre espacios de trabajo no predeterminados. Las ofertas ahora se duplican con un seguimiento y un nombre mejorados para evitar conflictos.

  **Mejoras de clave**:
   * Las ofertas se vuelven a crear en el espacio de trabajo de destino con ID y metadatos actualizados.
   * Se cambia el nombre de las ofertas copiadas con el formato: &quot;Copia del nombre de la oferta&quot; más un número aleatorio o una marca de tiempo para garantizar su exclusividad.
   * El sistema actualiza los estados de oferta y actividad para reflejar los nuevos ID.
   * Esta funcionalidad evita errores causados por varios nombres de &quot;copia de oferta&quot; idénticos durante acciones de copia repetidas.
   * Es posible que las ofertas no aparezcan inmediatamente en la lista de ofertas del espacio de trabajo de destino, pero se procesen y se muestren correctamente.

  Esta actualización mejora la fiabilidad y la trazabilidad al administrar ofertas en varios espacios de trabajo. (TGT-53080)

+++

## [!DNL Target Standard/Premium] 25.7.2 (sábado, 18 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles
* Se ha añadido una advertencia de confirmación adicional al cancelar las ediciones de la actividad con cambios no guardados: ¿Seguro que desea guardar esta actividad? Si no guarda, se perderán todos los cambios.&quot; Este mensaje ayuda a evitar la pérdida accidental de datos. (TGT-52865)
* Se ha restaurado la funcionalidad heredada en el control deslizante [!UICONTROL Priority] de [!UICONTROL Goals & Settings], lo que permite a los clientes introducir un valor numérico directamente, tal como se admite en la interfaz de usuario heredada. (TGT-53185 y TGT-53219)

+++

**Audiencias**

+++Ver detalles
* Se ha corregido un problema que impedía guardar o editar actividades que contenían audiencias personalizadas. Los clientes han encontrado el mensaje de error &quot;No podemos completar su solicitud. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste.&quot; al intentar guardar cambios o incluso guardarlos sin cambios en determinadas actividades. (TGT-53189)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Ver detalles
* Se corrigió un problema en el cual los clientes veían informes de actividades específicas en la página [!UICONTROL Goals & Settings], el vínculo [!UICONTROL View in Analytics] señala incorrectamente al entorno de control de calidad en lugar del entorno de producción. (TGT-53163)

+++

**[!UICONTROL Experiences]y[!UICONTROL Offers]**

+++Ver detalles
* Se corrigió un problema en el cual invocar `triggerView` mediante código personalizado causaba un bucle infinito. (TGT-52885)
* Se corrigió un problema que ocasionaba discrepancias entre `LocalIds` definidos para actividades y los `LocalIds` utilizados en definiciones de experiencia. (TGT-52669)
* Se ha corregido un problema por el cual faltaban nombres de métricas en la página de la actividad [!UICONTROL Overview] que solo mostraban &quot;Oferta&quot; en lugar del nombre de métrica correcto. (TGT-53054)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] que impedía guardar la actividad y activaba el mensaje de error: &quot;No se pueden leer las propiedades de undefined (leyendo &#39;map&#39;)&quot;. (TGT-53145)

+++

**Recommendations**

+++Ver detalles
* Se corrigió un problema en el cual al hacer clic en un producto de [!UICONTROL Catalog Search] se mostraba el error &quot;No se pudieron recuperar los detalles del producto&quot; y se abría un modal sin una opción de cierre. (TGT-53082)
* Se corrigió un problema en el cual [recommendations como ofertas](/help/main/c-recommendations/recommendations-as-an-offer.md) en actividades [!UICONTROL A/B Test] no se actualizaban correctamente al cambiar colecciones o promociones. (TGT-52884)
* Se ha corregido un problema en el entorno de producción por el cual al hacer clic en una entidad en la IU actualizada se mostraba el error: &quot;No se pudieron recuperar los detalles del producto. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste.&quot; (TGT-53071)

+++

**Informes**

+++Ver detalles
* Se ha corregido un problema en el cual al guardar detalles de pedidos en un archivo CSV, se producía un archivo vacío. (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles
* Se ha resuelto un problema en la página [!UICONTROL Goals & Settings] en el cual los selectores utilizados en varias experiencias no se resaltaban de manera consistente como seleccionados. (TGT-53062)
* Se ha corregido un problema que impedía la edición de la actividad y activaba el mensaje de error: &quot;No se pueden leer las propiedades de undefined (leyendo &#39;mapa&#39;)&quot;. (TGT-53161)

+++

**Espacios de trabajo**

+++Ver detalles
* Se ha mejorado la administración de ofertas ad hoc al cambiar de espacio de trabajo.
   * Al cambiar del espacio de trabajo predeterminado a un espacio de trabajo no predeterminado (o entre espacios de trabajo no predeterminados), las ofertas ad hoc ahora se copian correctamente. Durante la inicialización, el contexto del espacio de trabajo se actualiza y se asigna un nuevo ID a la oferta para garantizar su exclusividad.
   * No se producen cambios al permanecer en el mismo espacio de trabajo. (TGT-53079)
* Se ha corregido un problema que impedía que los clientes [copiaran actividades entre diferentes espacios de trabajo](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6). (TGT-52753 y TGT-47094)
* Se corrigió un problema que se producía al cambiar propiedades entre espacios de trabajo.
   * Al cambiar entre el espacio de trabajo predeterminado y un espacio de trabajo no predeterminado, si la propiedad actual existe en el espacio de trabajo de destino, se conserva la propiedad.
   * Si la lista [!UICONTROL Properties] muestra una advertencia (probablemente para indicar que algunas propiedades pueden no ser compatibles) y el cliente hace clic en [!UICONTROL Add] o [!UICONTROL Remove] y, a continuación, hace clic en [!UICONTROL Save], se quitarán todas las propiedades que no estén en el área de trabajo de destino. Si el cliente hace clic en [!UICONTROL Cancel], todas las propiedades permanecerán, aunque no existan en el área de trabajo de destino. (TGT-47094)
   * Si permanece en el mismo espacio de trabajo o cambia de un espacio de trabajo no predeterminado al predeterminado u otro, todo permanece tal cual. (TGT-53078)
* Se ha actualizado la lógica de validación de entidad para respetar el contexto original del espacio de trabajo de la actividad. Las entidades como [!UICONTROL Experience Fragments] (XF) ahora se validan en función del espacio de trabajo en el que se creó originalmente la actividad. Por ejemplo, si existe un XF en el espacio de trabajo por defecto y la actividad se copia del espacio de trabajo X al espacio de trabajo Y, la validación seguirá pasando siempre que el XF sea válido en el espacio de trabajo original (por defecto). (TGT-53196)
* Compatibilidad mejorada para copiar audiencias específicas durante la duplicación de actividades.
   * Las audiencias específicas, incluidas las métricas, los informes, las páginas y los tipos solo de actividad, ahora se copian automáticamente en los siguientes casos:
      * Al copiar una actividad del espacio de trabajo predeterminado a un espacio de trabajo no predeterminado.
      * Al copiar una actividad en el mismo espacio de trabajo. (TGT-53197)

+++

## [!DNL Target Standard/Premium] 25.7.1 (sábado, 11 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles
* Se ha corregido un problema en el cual la dirección URL [!UICONTROL Activity QA] incluía un parámetro de consulta innecesario: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Se ha corregido un problema por el cual las direcciones URL de vista previa incluían incorrectamente audiencias adicionales más allá de la escrita explícitamente por el usuario. Este comportamiento se ha corregido para garantizar que solo se aplique la audiencia especificada al generar un control de calidad o un vínculo de vista previa. (TGT-52912)
* Se ha corregido un problema que impedía a los usuarios crear actividades [!UICONTROL Auto-Target] (AT) si [!UICONTROL Auto-Allocate] (AA) se seleccionaba primero durante la configuración de la asignación de tráfico. Este problema provocaba un error de validación del back-end e impedía guardar la actividad. (TGT-53096)

+++

**Audiencias**

+++Ver detalles
* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Approver] no podían agregar ni guardar refinamientos de audiencia solo de actividad. Al intentar hacerlo, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario tenía permisos suficientes para aprobar y administrar actividades. (TGT-52984)
* Se ha corregido un problema que se producía cuando se eliminaba una audiencia específica de actividad mediante la opción [!UICONTROL Remove Audience Refinement], de modo que la audiencia ya no aparecía en la lista de audiencias para volver a seleccionarse dentro de la misma actividad. Este comportamiento impedía a los usuarios volver a añadir la misma audiencia a menos que se volviera a crear desde cero. (TGT-52979)
* Se ha corregido un problema en el cual los refinamientos de audiencia solo de actividad desaparecían de la interfaz de usuario inmediatamente después de eliminarse de una ubicación, incluso antes de guardar la actividad. Este comportamiento contradecía la funcionalidad esperada y la guía de información del objeto, que indica: &quot;Todas las audiencias no utilizadas de esta biblioteca se eliminarán una vez guardada la actividad&quot;. (TGT-52982)
* Se corrigió un problema que se producía al intentar asignar una audiencia distinta de [!UICONTROL All Visitors] a una actividad. Al guardar, se muestra el siguiente mensaje de error: &quot;No podemos completar su solicitud. Póngase en contacto con [!UICONTROL Adobe Client Care] si el problema persiste.&quot; (TGT-53008)
* Se ha corregido un problema que bloqueaba el guardado de una actividad después de crear y asignar una nueva audiencia dentro del editor de actividades. El mensaje de error mostrado era: &quot;No podemos completar su solicitud. Póngase en contacto con [!UICONTROL Adobe Client Care] si el problema persiste.&quot; (TGT-52977)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Ver detalles
* Se corrigió un problema en el cual copiar una actividad existente y cambiar el origen de informes a [!DNL Adobe Analytics] (A4T) resultaría en un error de &quot;entrada de usuario no válida&quot;. El error se activó cuando ciertas acciones de métricas incompatibles con los informes de [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` y `restart_new_experience`, se retuvieron de la actividad original. (TGT-52900)
* Se ha corregido un problema que impedía que los clientes crearan o guardaran una actividad al seleccionar [!DNL Adobe Analytics] (A4T) como fuente de informes en el paso [!UICONTROL Goals & Settings]. El problema se produjo específicamente al seleccionar una métrica de [!UICONTROL Custom Event] (por ejemplo, &quot;Evento personalizado 16&quot;), dando como resultado el siguiente error: &quot;Entrada de usuario no válida&quot;. (TGT-52910)
* Se ha corregido un problema que causaba que, al hacer clic en el vínculo &quot;[!UICONTROL View in Analytics]&quot;, se redirigiera a los usuarios a la página principal en lugar del panel [!DNL Analytics] deseado. (TGT-53092 y TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Se ha corregido un problema que se producía al ver una actividad [!DNL Recommendations] en la interfaz de usuario [!UICONTROL Overview] actualizada, y que provocaba que la sección [!UICONTROL Goals & Settings] no se cargara cuando se seleccionaba [!DNL Adobe Analytics] (A4T) como origen de informes. Se muestra el siguiente mensaje de error: &quot;Se ha producido un error. No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste. (TGT-52999)

+++

**[!UICONTROL Experiences]y[!UICONTROL Offers]**

+++Ver detalles
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Se corrigió un problema en el cual la característica [!UICONTROL Manage Content] no validaba correctamente el estado de una ubicación después de quitar todas las opciones de contenido. Este problema podría provocar un comportamiento incoherente o errores al intentar guardar o continuar con la configuración de la actividad. (TGT-52801)
* Se ha corregido un problema en el cual los usuarios encontraban un error de &quot;entrada no válida&quot; al añadir una nueva página y eliminar elementos específicos dentro de diferentes experiencias. El error se desencadena cuando se genera un duplicado de `LocalIds` durante la manipulación de elementos, especialmente al cambiar entre experiencias y modificar estructuras de páginas compartidas. (TGT-52720)
* Se corrigió un problema en el cual al usar la característica [!UICONTROL Generate Adhoc Offer] aparecían ubicaciones indefinidas en el panel [!UICONTROL Manage Content]. (TGT-53076 y TGT-53070)
* Se ha aclarado el comportamiento con el cliente, donde las modificaciones realizadas mediante una oferta de HTML podrían no aparecer al navegar desde el paso [!UICONTROL Targeting] hacia atrás a [!UICONTROL Experiences]. Para este cliente, el sitio web afectado generaba dinámicamente varios selectores DOM que cambiaban con cada carga de página. Como resultado, el selector utilizado originalmente para la modificación no se puede encontrar cuando se vuelve a abrir el editor, lo que hace que la modificación parezca no estar presente o no ser válida. Este escenario funciona según lo diseñado. Para garantizar que las modificaciones persistan visualmente en el editor, se recomienda que los clientes utilicen selectores estables y coherentes que no cambien entre las recargas de la página. (TGT-52874)
* Se ha corregido un problema en el cual al intentar eliminar o desactivar una oferta que formaba parte de una experiencia excluida se activaba un error de &quot;entrada de usuario no válida&quot;. Este problema se producía aunque la oferta no se usaba de forma activa en las experiencias incluidas. (TGT-52917)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles
* Se ha corregido un problema en las actividades basadas en formularios en el cual duplicar una experiencia y editar el código personalizado en una de las experiencias duplicadas aplicaba involuntariamente esos cambios a todas las experiencias duplicadas. Cada experiencia ahora conserva su propio código personalizado de forma independiente después de la duplicación. (TGT-51600)

+++

**Localización**

+++Ver detalles
* Se han actualizado las cadenas de localización en la nueva IU para francés (fr_FR), alemán (de_DE), italiano (it_IT), coreano (ko_KO) y chino simplificado (zh_CN).

+++

**[!DNL Recommendations]**

+++Ver detalles
* Se agregó una nueva fuente [!DNL Recommendations] [estado](/help/main/c-recommendations/c-products/feeds.md#status): [!UICONTROL Partial Import Failed]. (KB-2215)
* Se corrigió un problema que afectaba el flujo de trabajo de creación de actividad al agregar [!DNL Recommendations] con [!UICONTROL promotions]. Cuando los usuarios seleccionaron &quot;[!UICONTROL Promote by Attribute]&quot; y agregaron una regla de filtrado (por ejemplo, [!UICONTROL Parameter Matching]), el tipo de regla y los valores de operando seleccionados no se retuvieron después de guardar y volver a editar la actividad. Al volver a abrir, el tipo de regla de filtrado cambiaba inesperadamente y faltaban los valores de operando. (TGT-53059)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el cual cualquier promoción creada con una sola regla se interpretaba y mostraba de forma incorrecta como un tipo de promoción &quot;Lista de elementos&quot;, independientemente de la lógica de la regla. (TGT-53063)
* Se corrigió un problema que se producía al usar la [!UICONTROL Overview]IU actualizada, el botón &quot;[!UICONTROL Download Recommendations Data]&quot; no estaba presente para las actividades [!UICONTROL Experience Targeting] (XT) que incluyen [!DNL Recommendations]. (TGT-52730 y TGT-52756)
* Anteriormente, la interfaz de usuario de Recommendations solo mostraba el número de entidades importadas correctamente desde una fuente. Sin embargo, el formato de mensaje back-end incluye tanto el número de entidades importadas como el número total de entidades con el formato: `# of entities imported / # of total entities`. Debido a esta discrepancia, los usuarios solo veían el primer valor (recuento importado) en la interfaz de usuario, lo que provocaba confusión. La interfaz de usuario ahora muestra ambos números. (TGT-53073)
* Se ha corregido un problema en el cual los clientes no podían guardar una regla de filtrado al configurar una promoción &quot;[!UICONTROL Promote by attribute]&quot; en una actividad A/B basada en formularios con recomendaciones. Después de guardar y volver a abrir la actividad, faltaba la regla de filtrado y la actividad no se pudo guardar correctamente. (TGT-53057)

+++

**Informes**

+++Ver detalles
* Se corrigió un problema en el cual al seleccionar &quot;[!UICONTROL Export order details to CSV]&quot; de la página [!UICONTROL Reports] se descargaba un archivo vacío. Este problema ocurría incluso cuando había datos de pedido válidos en la actividad. (TGT-52225)
* Se ha corregido un problema que se producía al intentar guardar una actividad después de crear y asignar una nueva audiencia de informes. El mensaje de error devuelto fue: &quot;Acceso denegado. Para realizar esta operación, se requieren todos los privilegios siguientes: [editor].&quot; Este problema se producía a pesar de que el usuario tenía acceso de nivel de aprobador. (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles
* Se ha resuelto un problema en el cual la aplicación de una modificación a una vista resultaba en la duplicación de la vista y la actividad devolvía un error de &quot;entrada de usuario no válida&quot;. Esta corrección garantiza que las modificaciones de la vista se apliquen correctamente sin activar errores de duplicación o validación. (TGT-52886)
* Se ha corregido un problema por el cual las modificaciones de código personalizado se mostraban incorrectamente para la experiencia incorrecta. En concreto, los cambios destinados a una experiencia se mostraron en una experiencia diferente, lo que provocó confusión y posibles errores de configuración en las actividades activas. (TGT-52776)
* Se ha corregido un problema que impedía editar o guardar modificaciones de código personalizado en la nueva interfaz de usuario de VEC. Específicamente:

   * Después de editar un bloque de código personalizado y guardar, los cambios no se reflejaron en la interfaz de usuario ni en la previsualización de control de calidad.
   * En algunos casos, las modificaciones no se podían eliminar a menos que se cerrara y se volviera a abrir la actividad.
   * Como solución alternativa, los usuarios tenían que copiar el código, eliminar la modificación y volver a crearlo manualmente con el contenido actualizado. (TGT-53072)

* Se ha corregido un problema por el cual al editar y guardar código personalizado el panel [!UICONTROL Modifications] dejaba de responder. (TGT-53075)
* Se ha corregido un problema por el cual las modificaciones realizadas en el código personalizado en experiencias de variante se reflejaban de forma involuntaria en la experiencia [!UICONTROL Control]. Esto provocaba cambios no deseados en el comportamiento de entrega. La experiencia [!UICONTROL Control] ahora permanece aislada de las ediciones de código personalizado realizadas en otras experiencias. (TGT-52413)
* Se ha corregido un problema en el cual las modificaciones realizadas en una experiencia (por ejemplo, la Experiencia B) se duplicaban de forma involuntaria en otra experiencia (Experiencia A) si el usuario hacía clic en la segunda experiencia antes de que el editor se cargara completamente. Este comportamiento también podría provocar la pérdida de modificaciones si la experiencia seleccionada inicialmente no tiene cambios. (TGT-52597)
* Se corrigió un problema en el cual los cambios realizados en el paso [!UICONTROL Modifications] de creación de la actividad no se guardaban de manera consistente. En algunos casos, después de completar todos los pasos y hacer clic en [!UICONTROL Save], el script personalizado agregado en la sección [!UICONTROL Modifications] no se reflejaba en el sitio activo, a pesar de que no había errores visibles durante el proceso de guardado. (TGT-52661)
* Se ha corregido un problema por el cual los cambios en el código personalizado no se guardaban correctamente y se reflejaban de forma involuntaria en varias experiencias dentro de la misma actividad. Además, los usuarios encontraban problemas de acceso al abrir o actualizar determinadas actividades, lo que provocaba que aparecieran pantallas en blanco. Estos problemas se han resuelto para garantizar una edición estable de la actividad y un aislamiento preciso de la experiencia. (TGT-52594)
* Se corrigió un problema en el cual los usuarios no podían navegar a una dirección URL diferente mientras se encontraban en [!UICONTROL Browse Mode]. Esto impedía que los probadores y editores validaran o previsualizaran páginas alternativas dentro de la misma sesión de actividad. (TGT-53052)
* Se corrigió un problema en el cual varias instancias de [!UICONTROL Visual Experience Composer] (VEC) se abrían simultáneamente durante la creación de la actividad. Este problema se produjo cuando los usuarios deshabilitaron [!UICONTROL Enhanced Experience Composer] (EEC) y quitaron la barra diagonal de la dirección URL del sitio web en el paso [!UICONTROL Page Delivery]. (TGT-52782)
* Se ha corregido un problema en el cual el menú desplegable de métrica [!UICONTROL Revenue] en el paso [!UICONTROL Goals & Settings] tenía el valor predeterminado incorrecto de [!UICONTROL Revenue per Visit] (RPVISIT), incluso después de que el usuario seleccionara una métrica diferente.  El problema se producía al contraer y volver a expandir el panel de configuración de métricas, lo que provocaba que se restableciera el valor seleccionado anteriormente. (TGT-52811 y TGT-52878)
* Se han corregido varios problemas en el flujo de trabajo de creación de actividades relacionado con la nomenclatura de ofertas y la traducción de contenido en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Multivariate Testing] (MVT):

  Problemas clave abordados:

   * La creación de varias ofertas de HTML con el mismo nombre (por ejemplo, &quot;Experiencia&quot;) ha activado el error &quot;No se permiten nombres de ofertas duplicados&quot;, pero la interfaz de usuario no indicaba claramente qué ofertas estaban causando el conflicto.
   * Al cambiar el nombre de las ofertas mediante el panel derecho, se actualizó el nombre en la interfaz de usuario, pero el cambio no se reflejó en la pestaña [!UICONTROL Manage Content] ni en la pestaña [!UICONTROL Offers], lo que provocó errores de validación persistentes.
   * En las actividades MVT, aunque el error de nombre duplicado no persistió después de cambiar el nombre, la IU seguía sin reflejar los nombres de ofertas actualizados de forma coherente en las pestañas. (TGT-52933)

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
