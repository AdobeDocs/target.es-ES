---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 24%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba discrepancias en los listados de audiencia entre la página de configuración de [!UICONTROL Activity] y la página de información general de [!UICONTROL Reporting]. (TGT-52203)
* Se ha corregido un problema que impedía añadir una nueva página a una actividad debido a un error de entrada de usuario no válido. (TGT-52263)
* Se ha corregido un problema que provocaba que `OptionLocalIDs` se incrementara incorrectamente cuando la opción permanecía sin cambios. (TGT-52187)
* Se ha corregido un problema que provocaba que `location` y `OptionLocalIDs` se incrementaran incorrectamente cuando la opción permanecía sin cambios. (TGT-52188)
* Se ha corregido un problema que provocaba que la ubicación en la página [!UICONTROL Overview] de la actividad fuera incorrecta. (TGT-52182)
* Se ha corregido un problema por el cual no se mostraba una advertencia de selector no válido para una ubicación no válida. (TGT-52110)
* Se ha corregido un problema que impedía que los archivos de informes descargados mostraran correctamente los datos presentes en la interfaz de usuario de informes. (TGT-52068)
* Se ha corregido un problema para que las operaciones por lotes no fallaran después de agregar reglas de entrega de página. (TGT-52097)
* Se ha corregido un problema que provocaba que [!DNL Target] recortara todos los parámetros de consulta de la dirección URL del sitio web. (TGT-52100)
* Se ha resuelto un error de consola que impedía que los clientes crearan actividades en la interfaz de usuario [!DNL Target] heredada y actualizada. (TGT-52181)
* Se ha corregido un problema que impedía a los clientes añadir nuevas páginas, lo que provocaba un error de entrada de usuario no válido. (TGT-52258)
* Se ha corregido un problema que provocaba que las modificaciones desaparecieran después de agregar páginas adicionales y luego volver a la pestaña [!UICONTROL Experiences]. (TGT-52264)
* Se ha corregido un problema que impedía a los clientes cambiar la audiencia en una actividad de [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Se ha corregido un error que impedía editar una actividad XT debido a una regla de IU no admitida. (TGT-52273)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado en el cual las rutas de exploración no siempre se mostraban en la parte inferior del editor, lo que provocaba dificultades al seleccionar elementos con precisión. (TGT-52169)
* Se ha corregido un problema por el cual la lista desplegable [!UICONTROL Audience] no mostraba todas las audiencias debido a la paginación. (TGT-52204)
* Se ha corregido un problema que provocaba un mensaje de entrada de datos no válido al agregar nuevas ofertas en actividades de [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Se ha corregido un problema por el cual [!UICONTROL Analytics for Target] (A4T) se seleccionaba incorrectamente como origen de informes, aunque el cliente no tuviera acceso a A4T. (TGT-52226)
* Se ha corregido un problema que impedía guardar una actividad con la métrica de URL [!UICONTROL View a Page]. (TGT-52260)
* Se ha corregido un problema que impedía que los clientes seleccionaran espacios de trabajo al crear ofertas dentro de una actividad. (TGT-52289)
* Se ha corregido un problema que bloqueaba a los clientes la creación de actividades en todos los espacios de trabajo. (Tgt-52218)
* Se ha corregido un problema por el cual las modificaciones de una experiencia se mostraban incorrectamente al cambiar a otra experiencia. (TGT-52184)
* Se corrigió un problema en el cual la oferta predeterminada se mostraba incorrectamente en la interfaz de usuario de [!DNL Target] al abrir la actividad. (TGT-52198)

## Actualización de permisos de Target (22 de abril de 2025)

Esta actualización futura mejora el control de la organización sobre las configuraciones de instancia de [!DNL Target], lo que evita actualizaciones accidentales que podrían afectar a la entrega de la actividad en varios equipos de prueba y personalización.

A partir del 22 de abril de 2025, solo los administradores de [!UICONTROL Product] y [!UICONTROL Solutions] podrán actualizar la configuración en las secciones de [!UICONTROL Administration], independientemente de sus funciones en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tendrán acceso de sólo lectura a las secciones [!UICONTROL Administration].

Para obtener más información, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (17 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha añadido un mensaje de error para guiar a los usuarios en la resolución de opciones duplicadas en una actividad. (TGT-51927)
* Se corrigió un problema en el cual los selectores de `ClickTrack` no se eliminaban al eliminar páginas o experiencias con ofertas de redireccionamiento. (TGT-51952)
* Se ha corregido un problema que se producía al permitir selectores vacíos de `ClickTrack`. [!DNL Target] ahora requiere que el campo de selector no esté vacío. (TGT-52107)
* Se ha corregido un problema que permitía incorrectamente métricas con nombres duplicados. Las métricas ahora requieren nombres únicos. (TGT-52201)
* Se ha corregido un problema por el cual las definiciones de audiencia no eran visibles al editar la segmentación a nivel de oferta en actividades [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Se ha corregido un problema que impedía que los clientes con derechos de [!UICONTROL Editor] guardaran actividades. (TGT-52227)
* `OptionLocalIDs` ya no se incrementa incorrectamente cuando la opción permanece sin cambios. (TGT-52139)
* Se ha corregido un problema que provocaba el mensaje &quot;No válido `optionLocalIds`&quot; al intentar crear una actividad. (TGT-52154)
* Se han corregido las discrepancias entre `OptionLocalIDs` definidas para una actividad y las utilizadas para definir experiencias. (TGT-52215)
* Se ha corregido un problema que provocaba un error de validación que se producía al intentar crear una actividad A/B. (TGT-51923)

## [!DNL Target Standard/Premium] 25.4.3 (11 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un error que impedía que los clientes abrieran la ventana emergente de información de audiencia para determinadas actividades de [!UICONTROL Experience Targeting] (XT). (TGT-52049)
* Se corrigió un problema en el cual la configuración de audiencia se revertía a &quot;[!UICONTROL All Visitors]&quot; después de los cambios realizados en el [!UICONTROL Visual Experience Composer] (VEC). (TGT-52132)
* Se ha corregido un problema en el cual los refinamientos de audiencia no se mostraban para actividades específicas (TGT-52057)
* Se ha corregido un problema que impedía a los clientes insertar un(a) [!UICONTROL Experience Fragment] en el espacio de trabajo predeterminado. (TGT-52073)
* Se ha corregido un problema por el cual una oferta se mostraba como &quot;Contenido no encontrado&quot; y no se mostraba en la página [!UICONTROL Offers] de una actividad [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Se ha añadido la capacidad de permitir audiencias duplicadas dentro de una actividad. (TGT-51200)
* Se ha corregido un problema por el cual se mostraba un nombre de mbox incorrecto en la página [!UICONTROL Goals & Settings] para una actividad XT después de editar. (TGT-52026)
* Se corrigió un problema en el cual `defaultContent` se mostraba en las opciones a pesar de no estar en `experiences/optionLocations`. (TGT-52036)
* Se ha corregido un problema para garantizar que las cadenas vacías no se convirtieran en valores nulos. (TGT-52037)
* Se ha corregido un problema que requería que los clientes reconfiguraran [!UICONTROL Optimization Goal] en [!UICONTROL Reporting Settings] en la página [!UICONTROL Goals & Settings] después de las ediciones. (TGT-52071)
* Se ha corregido un problema en el cual una actividad sin reglas de entrega de página mostraba varias reglas en la página [!UICONTROL Overview]. (TGT-52084)
* Se ha añadido un mensaje de error para los usuarios que intentan guardar una oferta con caracteres fuera del plano multilingüe básico, como emojis. (TGT-52105)
* Se ha corregido un problema que causaba que, al abrir una actividad, se mostrara el siguiente mensaje de error: &quot;Esta actividad está utilizando una o más audiencias eliminadas en el origen&quot;. (TGT-52120)
* Se ha corregido un problema en el cual las métricas de ClickTrack no se mostraban en el [!UICONTROL Visual Experience Composer] (VEC) actualizado durante la edición. (TGT-52152)
* Se corrigió un problema en el cual una dirección URL con un parámetro de consulta como ubicación de la actividad no mostraba el parámetro de consulta en la página [!UICONTROL Overview] de la actividad. (TGT-51635)
* Se ha corregido un problema que impedía que se mostrara toda la dirección URL de la experiencia en [!UICONTROL Browse mode] dentro del [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Se ha corregido un problema por el cual al editar una actividad de, la entrega de la página agregaba &quot;/&quot; al final de la dirección URL, lo que resultaba no válido. (TGT-52114)
* Se ha corregido un problema por el cual el vínculo [!UICONTROL Activity QA] en [!UICONTROL Form-Based Experience Composer] se redireccionaba incorrectamente a la página principal de [!DNL Adobe Experience Cloud]. (TGT-52055)
* Se corrigió un problema en el cual las páginas adicionales agregadas a la actividad [!UICONTROL A/B Test] no se conservaban después de guardar y volver a abrir. (TGT-51994)
* Se ha corregido un problema que impedía que los clientes eliminaran estilos en la sección de estilos en línea. (TGT-52070)
* Se ha restaurado el acceso a [tarjetas de definición de audiencia](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) en el cuadro de diálogo [!UICONTROL Activity QA], de forma similar a la IU heredada. (TGT-52056)
* La IU actualizada no guardó páginas o audiencias sin realizar modificaciones. Si los clientes agregaron nuevas páginas o audiencias a una actividad pero no realizaron cambios en ellas, [!DNL Target] descartó las audiencias sin modificar al guardar. Se han añadido notificaciones en lugares relevantes para informar a los usuarios de este comportamiento. (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba que las audiencias de experiencia desaparecieran de las actividades de. (TGT-52003)
* Se ha corregido un problema que provocaba elementos inesperados durante la entrega. (TGT-52011)
* Se ha corregido un problema que impedía que los clientes vieran la audiencia en el gráfico de segmentación de la página de vista Superior[!UICONTROL r]y durante la edición de la actividad. (TGT-52050)
* Se ha corregido un problema que impedía que los clientes reordenaran experiencias en orden de prioridad en actividades [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Se ha corregido un problema que provocaba un procesamiento incorrecto al deshacer cambios de estilo de texto. (TGT-51876)
* Se ha corregido un problema que al modificar una oferta de redireccionamiento, [!DNL Target] también quitaba los selectores [!UICONTROL ClickTrack] asociados con esa oferta. (TGT-51936)
* Se ha corregido un problema que provocaba que [!DNL Target] guardara el selector de forma incorrecta al cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Se ha corregido un problema que provocaba un error de nombre no válido después de abrir y cerrar el selector de mbox en la página [!UICONTROL Goals & Settings] sin realizar ningún cambio. (TGT-51983)
* Se ha corregido un problema que bloqueaba la edición de ofertas ad hoc creadas en la IU heredada de [!DNL Target]. (TGT-51984)
* Se ha corregido un problema que bloqueaba las actividades de edición que tienen ofertas ad-hoc que contienen código personalizado. (TGT-51995)
* Se ha corregido un problema que provocaba que las reglas de exclusión se mostraran como reglas de inclusión al editar definiciones de audiencia combinadas. (TGT-51999)
* Se ha corregido un problema que impedía que el código personalizado se mostrara correctamente durante la edición de experiencias. (TGT-52005)
* Se ha corregido un problema que hacía que la opción [!UICONTROL Insert Before] no estuviera disponible para insertar contenido antes de la barra de navegación. (TGT-52031)
* Se ha corregido un problema que impedía resaltar correctamente la experiencia predeterminada en los informes. (TGT-51716)
* Se ha corregido un problema que activaba un mensaje de `default message [Invalid optionLocalIds: xx]]` al crear una actividad. (TGT-52038)

## Versión 2.11.8 de at.js (31 de marzo de 2025)

* Se ha resuelto una vulnerabilidad identificada por CodeQL en la validación de sufijos de cadena para evitar casos extremos durante las operaciones de cambio de tamaño y movimiento. (TNT-51516)

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
