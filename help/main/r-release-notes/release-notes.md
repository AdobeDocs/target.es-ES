---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d87f1fbe78512363d4fe30935cbb4f2556b4a06b
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 19%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizado: [!DNL Target] desaprobación de la versión de IU (17 de junio de 2025) {#revised}

A partir del 17 de junio de 2025, todas las organizaciones de IMS deberían haberse habilitado para la interfaz de usuario [!DNL Target] actualizada, ya sea para usuarios específicos o para toda la organización, a fin de comenzar a probar la nueva experiencia.

Debido a problemas identificados recientemente, relacionados principalmente con personalizaciones complejas de clientes, el equipo [!DNL Target] ha ajustado la cronología de desuso:

* **30 de junio de 2025**: la [interfaz de usuario actualizada [!DNL Target] 4&rbrace; se convertirá en la experiencia predeterminada para todas las organizaciones de IMS que tengan habilitada la opción de versión de la interfaz de usuario.](/help/main/c-intro/understand-the-target-ui.md)

   * Los clientes que actualmente ven la IU heredada de forma predeterminada ahora verán la IU actualizada al iniciar sesión.
   * La opción de versión de la interfaz de usuario permanecerá disponible hasta finales de julio, lo que permitirá a los usuarios volver si es necesario.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recomienda encarecidamente usar la interfaz de usuario [!DNL Target] actualizada. Cambie a la IU heredada solo si se produce un problema de bloqueo. Consulte [[!DNL Target] Desaprobación de la opción de versión de la interfaz de usuario (23 de mayo de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#toggle) en las notas de la versión de versiones anteriores para obtener información importante acerca de la opción.

* **Del 15 de julio al 30 de julio de 2025**: la opción de versión de la interfaz de usuario se deshabilitará de forma permanente por fases. Las organizaciones de IMS afectadas ya no podrán volver a la IU heredada.

   * Las excepciones se revisarán caso por caso.
   * Los retrasos en la desaprobación de la alternancia solo se concederán brevemente (unos días) mientras se resuelven los problemas del bloqueador.

Póngase en contacto con el servicio de atención al cliente de [Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) si tiene dudas o si prevé que surgirán problemas durante esta transición.

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
