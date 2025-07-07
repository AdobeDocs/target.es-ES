---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 34693e5c94328b5f1ad1d692d6a986cadb6349c4
workflow-type: tm+mt
source-wordcount: '3112'
ht-degree: 12%

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

Una vez completado el despliegue, se eliminará la opción y todos los usuarios realizarán una transición permanente a la interfaz de usuario actualizada. [!DNL Adobe] recomienda planificar con anticipación, ya que esta función se eliminará gradualmente en breve.

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
* **Edición de actividades existentes**: los cambios realizados en las actividades existentes (creadas originalmente en la interfaz de usuario heredada) mientras se usa la interfaz de usuario actualizada se publicarán en el sitio web. Sin embargo, estas actualizaciones no estarán visibles en la interfaz de usuario heredada si vuelve; solo aparecerán allí las últimas actualizaciones realizadas desde la interfaz de usuario heredada.
* **Consistencia de los detalles de la actividad**: los cambios más recientes, independientemente de la interfaz de usuario que utilice, se reflejarán en el sitio web activo. Sin embargo, la IU heredada solo mostrará los cambios más recientes realizados desde esa versión. Esto puede causar confusión si las actividades editadas en la interfaz de usuario actualizada tienen un aspecto diferente al que se ve en la interfaz de usuario heredada.

#### Recursos adicionales para obtener más información sobre la IU actualizada

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.
* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).
* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].
* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.
* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.
* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

+++

## [!DNL Target Standard/Premium] 25.6.4 (sábado, 27 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado la opción [!UICONTROL Rearrange] a la interfaz de usuario [!UICONTROL Visual Experience Composer] (VEC) actualizada para alinearla con la funcionalidad disponible en el VEC heredado. (TGT-46957 y TGT-52876)
* Se corrigió un problema en el cual las modificaciones realizadas en experiencias de variante (por ejemplo, la Experiencia B) en una actividad [!UICONTROL A/B Test] no se conservaban. Después de cambiar entre experiencias, los cambios en la variante desaparecerían. Este problema no afectaba a la experiencia de control de Campaign. (TGT-52664)
* Se ha corregido un problema en el cual algunos clientes no podían crear ni guardar actividades, mientras que otros podían realizar las mismas acciones sin problema. El problema era inconsistente entre cuentas.(TGT-52842)
* Se ha corregido un problema en el cual en el VEC actualizado, los usuarios no podían mover modificaciones al [!UICONTROL Page Load event], una capacidad que existía en la IU heredada. (TGT-52617)
* Se ha corregido un problema en la interfaz de usuario actualizada en el cual [!UICONTROL page load] eventos no eran visibles en [!DNL Target] al crear cambios; las actualizaciones solo se aplicaban a las vistas. (TGT-52604)
* Se ha corregido un problema que impedía que algunas modificaciones de la actividad se mostraran correctamente en el VEC actualizado. (TGT-52818)
* Se ha corregido una excepción de puntero nulo que se producía al recuperar datos de informes para actividades [!UICONTROL Automated Personalization] (AP). (TGT-52362)
* Se ha corregido un problema que impedía que los detalles de nivel de oferta aparecieran en el archivo .CSV para actividades [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Se ha corregido un problema que se producía al aplicar modificaciones en el VEC actualizado; los cambios aparecen inicialmente correctamente, incluido el [!UICONTROL Experience Fragment] esperado. Sin embargo, al cambiar de experiencia o al realizar ediciones adicionales, algunas modificaciones no se aplican debido a problemas con el selector. (TGT-52679)
* Se ha corregido un problema por el cual cuando se creaba una nueva actividad clonando una existente, los vínculos de control de calidad de la actividad clonada retenían incorrectamente las direcciones URL de la página de la actividad original. (TGT-52775)
* Se ha corregido un problema que impedía involuntariamente que [!UICONTROL On-device Decisioning] estuviera disponible en el VEC actualizado. (TGT-52371)
* Se ha corregido un problema que impedía editar una actividad de producto [!DNL Recommendations]. Al intentar acceder al VEC a través de la interfaz de usuario de Target, apareció un error en la página [!UICONTROL Overview] que impedía realizar ediciones. (TGT-52823)
* Se ha corregido un problema que impedía guardar una actividad de [!DNL Recommendations] cuando los nombres de experiencia superaban los 50 caracteres. (TGT-52619)
* Se ha corregido un problema en el cual los clientes no podían guardar una actividad de Recommendations después de modificar los criterios en la nueva interfaz de usuario. El problema parece estar relacionado con los permisos y no afecta a todos los usuarios con funciones similares. (TGT-52816)
* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Editor] no podían editar una actividad [!DNL Recommendations]. Al intentar cambiar el diseño y guardar la actividad, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario ya tuviera esa función en el espacio de trabajo relevante. (TGT-52836)

## [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que causaba que, al copiar una actividad de un espacio de trabajo a otro, se produjeran errores como &quot;no debe ser nulo&quot; o &quot;Se ha producido un error&quot;. (TGT-52474)
* Se corrigió un problema en el cual los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes] no se generaban para ciertas actividades. (TGT-52904)
* Se ha corregido un problema en el VEC actualizado en el cual la administración de contenido predeterminado en las actividades [!UICONTROL Automated Personalization] (AP) no coincidía con la IU heredada. El sistema ahora agrega automáticamente un(a) `optionGroup` predeterminado denominado &quot;Contenido predeterminado&quot; con `optionGroupLocalId = 0` cuando no se agrega ningún grupo explícitamente. Este grupo incluye la opción predeterminada (por ejemplo, `optionLocalId: 0`). Si se elimina el contenido predeterminado, también se elimina el grupo de opciones correspondiente. (TGT-52651)
* Se ha corregido un problema en las actividades [!UICONTROL Multivariate Test] (MVT) en el cual se impedía incorrectamente reutilizar un(a) `experienceLocalId` de experiencias eliminadas anteriormente. (TGT-52672)
* Se ha corregido un problema que impedía copiar o editar actividades que contuvieran un fragmento de experiencia. Esto desencadenó el error: `Enum "AemOfferType" cannot represent value: "html"`. (TGT-52635)
* Se ha corregido un problema por el cual las direcciones URL de las ubicaciones de actividades no mostraban los parámetros de consulta debido a caracteres no válidos, como barras inclinadas (/). (TNT52845)
* Se mejoró el mensaje de error de validación para [!DNL A/B Test] actualizaciones de la actividad a través de la API back-end. Cuando hay nombres de ubicación duplicados, el mensaje ahora indica claramente: &quot;No se permiten nombres duplicados&quot; para `locations.selectors`. (TGT-52589)
* Se ha corregido un error que se producía al actualizar una actividad [!UICONTROL Recommendations] activa debido a una propiedad no reconocida en la carga de la solicitud. El sistema ahora gestiona correctamente el JSON no válido. Error de &quot;nombre de propiedad no reconocido&quot;. (TGT-52723)
* Se ha corregido un problema que impedía crear un diseño de [!DNL Recommendations]. Al hacer clic en [!UICONTROL Create], se activó el mensaje: &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot;. (TGT-52395 y TGT-52899)
* Se corrigió un problema en el cual se bloqueaba volver a guardar un diseño de [!DNL Recommendations] sin modificaciones. (TGT-52879)
* Se ha corregido un error de validación de servidor que provocaba el error &quot;400 Bad Request&quot; al guardar una actividad [!UICONTROL Recommendations]. (TGT-52716)
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] por el cual al pasar el ratón por encima de un mbox con caracteres especiales en la lista desplegable [!UICONTROL Location], el editor se quedaba en blanco y se activaba un mensaje &quot;No se pudo ejecutar &#39;querySelector&#39; en &#39;Elemento&#39;&quot;. No se pudo recuperar la dirección de URL especificada. (TGT-52717)
* Se ha mejorado la precisión del estado de la fuente con un nuevo indicador &quot;PARTIALLY_IMPORTED&quot;. Anteriormente, las fuentes se marcaban como &quot;correctas&quot; incluso cuando no se importaban todas las filas de un archivo, lo que resultaba confuso. (TGT-52892)
* Se corrigió un error en el cual, después de migrar a AP V2, ciertas llamadas de API a `/admin/rest/ui/v1/campaigns` devolvían errores del lado del cliente (HTTP 4xx). (TGT-52721)

## [!DNL Target Standard/Premium] 25.6.2 (viernes, 12 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado un [nuevo artículo de preguntas frecuentes](/help/main/c-intro/updated-ui-faq.md) para responder preguntas comunes sobre la actualización de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC).
* Se ha corregido un problema en el cual la regla &quot;[!UICONTROL URL - does not contain]&quot; en [!UICONTROL Page Delivery] no funcionaba, lo que permitía que el contenido se mostrara incluso cuando debería haberse bloqueado. (TGT-52754)
* Se ha corregido un problema en el cual [!UICONTROL Page Delivery] mostraba incorrectamente el mensaje de error: &quot;No se permiten direcciones URL de página duplicadas. (TGT-52765)
* Se corrigió un problema en el cual las audiencias para [!UICONTROL Page Delivery] direcciones URL que contenían fragmentos de experiencia se creaban con # anexado incorrectamente. (TGT-52786)
* Se ha corregido un problema por el cual al copiar una actividad y editar la configuración en la página [!UICONTROL Goals and Settings] la interfaz de usuario de [!DNL Target] dejaba de responder. (TGT-52797)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado que permitía incorrectamente redirigir una página adicional en una actividad de [!UICONTROL A/B Test] a la misma dirección URL. (TGT-51838)
* Se corrigió un problema en el cual los cambios realizados en las métricas de la página [!UICONTROL Goals and Settings] no se guardaban al editar una actividad. (TGT-52799)
* Se ha corregido un problema por el cual al añadir una nueva experiencia mientras el editor web se estaba cargando, la nueva experiencia duplicaba contenido de la experiencia anterior. (TGT-51397)
* Se ha restaurado la capacidad de usar código personalizado fuera de la etiqueta `<head>`, una característica disponible anteriormente en la interfaz de usuario de Target heredada. (TGT-52304 y TGT-52300)
* Se ha eliminado una validación innecesaria al seleccionar el espacio de trabajo predeterminado durante la creación de la actividad. La validación de propiedades obligatoria ya no se aplica al espacio de trabajo predeterminado, pero permanece en su lugar para los espacios de trabajo no predeterminados. (TGT-52449)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado en el cual no se detectaban llamadas a `triggerView()`. (TGT-52575)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado que impedía a los usuarios agregar modificaciones a las vistas de [!UICONTROL Single Page Application] (SPA). (TGT-52556)
* Se ha corregido un problema en la interfaz de usuario actualizada de [!DNL Target] que impedía que los clientes vieran los detalles de la oferta. (TGT-52607)
* Se corrigió un problema en el cual las actualizaciones realizadas en las ofertas de [!UICONTROL Offers Library] no se reflejaban en el [!UICONTROL Visual Experience Composer] (VEC) actualizado. (TGT-52637)
* Se ha corregido un problema que impedía que la sección Ofertas se mostrara correctamente al crear una actividad. (TGT-52773)
* Se agregó la validación para asegurarse de que todas las `optionLocalIds` a las que se hace referencia en `optionGroups` existan en la matriz de opciones. Las referencias no válidas se eliminan automáticamente durante la creación de la actividad. (TGT-52687)
* Se ha corregido un problema por el cual los grupos de informes y las exclusiones no se conservaban después de agregar una nueva oferta. (TGT-52728)
* Se corrigió un problema en el cual las actividades sin un botón [!UICONTROL Activity QA] mostraban un selector de opciones vacío. (TGT-52733)
* Se ha corregido un problema en el cual los vínculos de control de calidad no representaban el contenido correctamente. (TGT-52718)
* Se ha corregido un problema en el cual el reemplazo de un elemento por un fragmento de experiencia no reflejaba correctamente los cambios en el entorno de control de calidad. (TGT-52762)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado que provocaba un error de &quot;Entrada no válida&quot; cuando los usuarios intentaban agregar fragmentos de experiencia. (TGT-52701)
* Se ha corregido un problema en el cual el modal &quot;Editar audiencia&quot; aparecía vacío al editar la segmentación de audiencia en el [!UICONTROL Visual Experience Composer] (VEC) actualizado. (TGT-52749)
* Se ha añadido un mensaje para informar a los usuarios de cuando una entidad no es accesible en el espacio de trabajo seleccionado. (TGT-52767)
* Se ha corregido un problema en el cual la interfaz de usuario no permitía la asignación manual de un ID de entorno a un criterio. En su lugar, estableció de forma predeterminada el ID del grupo de hosts [!UICONTROL Product Catalog Search]. Esta corrección garantiza que los cambios de criterios ahora se apliquen en todos los entornos, no solo en el predeterminado. (TGT-52817)
* Se corrigió un problema en el cual faltaba la opción &quot;[!UICONTROL Download Recommendations data]&quot; para las actividades [!UICONTROL Experience Targeting] (XT) con recomendaciones. (TGT-52730 y TGT-52756)

## [!DNL Target Standard/Premium] 25.6.1 (sábado, 06 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema en el cual los vínculos de control de calidad no proporcionaban la experiencia correcta para la actividad asociada. (TGT-52163 y TGT-52790)
* Se ha corregido un problema por el que los vínculos de control de calidad no incluían el ID de audiencia asociado. (TGT-52722)
* Se ha corregido un problema para garantizar que las experiencias se entreguen solo cuando las condiciones configuradas de la URL de entrega de páginas se cumplan con precisión. (TGT-52696)
* Se ha corregido un problema que impedía que los clientes crearan una plantilla de diseño [!DNL Recommendations]. Al intentar crear una plantilla, se activó el error: &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot;. (TGT-52395)
* Se ha corregido un problema que impedía guardar [!DNL Recommendations] diseños con matrices de Velocity. El mensaje de error &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot; se activó incorrectamente. (TGT-52734)
* Se ha corregido un problema por el cual no se podía acceder a las modificaciones en el [!UICONTROL Visual Experience Composer] (VEC) cuando la página no se cargaba para páginas web internas. (TGT-52488 &amp;TGT-52470)
* Se ha corregido un problema en el cual el panel [!UICONTROL Modifications] no era visible en tamaños de pantalla más pequeños en el VEC. (TGT-52470)
* Se ha corregido un problema en el VEC actualizado en el cual el cambio del modo [!UICONTROL Browse] de nuevo al modo [!UICONTROL Design] provocaba un error de consola e impedía una mayor interacción. (TGT-52532)
* Se ha corregido un problema en el VEC por el cual al hacer clic en ciertos elementos se ampliaba su tamaño de forma involuntaria. (TGT-52497)
* Se ha corregido un problema en el cual algunos elementos de página no se cargaban o no se reconocían en el VEC, lo que impedía interacciones como seleccionar botones o banners e interrumpir el seguimiento de eventos preciso en las actividades de. (TGT-52663)
* Se ha corregido un problema que impedía que los clientes eliminaran o eliminaran ofertas en actividades [!UICONTROL Automated Personalization] (AP). (TGT-52690)
* Se ha corregido un problema que provocaba un comportamiento incoherente de calificación de actividades en actividades de varias páginas. (TGT-52694)
* Se ha corregido un problema que hacía que la página [!UICONTROL Overview] de la actividad mostrara una dirección URL no válida para [!UICONTROL Activity Location]. (TGT-52695)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada que provocaba que aparecieran entradas duplicadas para las ubicaciones de actividades. (TGT-52693)
* Se ha corregido un problema que activaba un error de `getAudiencesV3`, lo que impedía que los clientes editaran o copiaran actividades. (TGT-52709)
* Se ha corregido un problema que provocaba un error de carga no válida al agregar [!UICONTROL Experience Fragments] u ofertas de HTML a una actividad. (TGT-52779 y TGT-52773)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual E[!UICONTROL xperience Fragments] no se mostraba correctamente debido a un error de entrada no válido. (TGT-52701)
* Se ha corregido un problema que impedía que los clientes editaran actividades en [!UICONTROL Form-based Experience Composer] debido a un error de usuario no válido. (TGT-52470)
* Se ha corregido un problema de localización en coreano en el que traducciones anteriores usaban caracteres fuera del plano multilingüe básico. La traducción actualizada utiliza caracteres adecuados que transmiten con precisión el significado deseado. (TGT-52508 y TGT-52509)
* Se ha corregido un problema de localización en coreano en el que la traducción de &quot;fecha&quot; era incoherente al seleccionar fechas de inicio y finalización de una actividad. (TGT-52510)

## [!DNL Target] desaprobación de cambio de versión de IU (23 de mayo de 2025) {#toggle}

>[!IMPORTANT]
>
>El equipo [!DNL Target] ha ajustado la cronología para la desaprobación de la versión de la interfaz de usuario. Consulte [Actualización: [!DNL Target] Desaprobación de la opción de versión de IU (17 de junio de 2025)](#revised) para obtener más información.

El despliegue de la nueva interfaz de usuario [!DNL Target] se completará el **27 de mayo de 2025**. En ese momento, todos los clientes tendrán acceso a la última versión de la interfaz de usuario.

A partir del **22 de junio de 2025**, se eliminará la opción de versión de la interfaz de usuario. Todos los usuarios realizarán una transición permanente a la nueva interfaz, sin opción de volver a la versión anterior.

>[!NOTE]
>
>Los clientes con casos especiales que necesiten conservar la opción después del 22 de junio pueden ponerse en contacto con el Servicio de atención al cliente de Adobe para obtener ayuda.

### Información importante sobre la opción de versión de la IU

Ofrecemos una característica temporal que le permite alternar entre la interfaz de usuario [!DNL Target] actualizada y la versión heredada mediante un botón de alternancia. Esta opción solo está disponible durante la fase final del despliegue de la interfaz de usuario.

![Alternar versión de IU de Target](/help/main/r-release-notes/assets/toggle.png)

Una vez completado el despliegue, se eliminará la opción y todos los usuarios realizarán una transición permanente a la interfaz de usuario actualizada el **22 de junio de 2025**. Adobe recomienda realizar la planificación con antelación, ya que esta función se eliminará pronto.

### Limitaciones del comportamiento de alternancia de IU

* **Visibilidad de nuevas actividades**: las actividades creadas en la interfaz de usuario actualizada no serán visibles si vuelve a la interfaz de usuario heredada.
* **Edición de actividades existentes**: los cambios realizados en las actividades existentes (creadas originalmente en la interfaz de usuario heredada) mientras se usa la interfaz de usuario actualizada se publicarán en el sitio web. Sin embargo, estas actualizaciones no estarán visibles en la interfaz de usuario heredada si vuelve; solo aparecerán allí las últimas actualizaciones realizadas desde la interfaz de usuario heredada.
* **Consistencia de los detalles de la actividad**: los cambios más recientes, independientemente de la interfaz de usuario que utilice, se reflejarán en el sitio web activo. Sin embargo, la IU heredada solo mostrará los cambios más recientes realizados desde esa versión. Esto puede causar confusión si las actividades editadas en la interfaz de usuario actualizada tienen un aspecto diferente al que se ve en la interfaz de usuario heredada.

### Más información sobre la IU actualizada

* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).

* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].

* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.

* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.

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
