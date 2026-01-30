---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6b92e823c854996e074716a7b8c4856176710c24
workflow-type: tm+mt
source-wordcount: '1772'
ht-degree: 15%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.1.1 (lunes, 18 de enero de 2026)

**Actividades**

+++Ver detalles

* **No se puede copiar la actividad debido a una entrada de usuario no válida.** Se ha corregido el problema que provocaba que los usuarios vieran un error no útil de &quot;entrada de usuario no válida&quot; al copiar una actividad. Anteriormente, cuando se duplicaba una actividad, no se conservaban las asignaciones de propiedades específicas del espacio de trabajo, lo que provocaba que el backend rechazara la solicitud de guardado porque ABActivity requiere al menos una propiedad que pertenece a un espacio de trabajo no predeterminado. Esta discrepancia activó un error genérico en la interfaz de usuario, lo que dejó a los usuarios sin orientación. La corrección garantiza que las asignaciones del espacio de trabajo se mantengan correctamente durante las operaciones de copia, lo que permite a los usuarios guardar la actividad copiada sin modificarla y evitar errores de validación engañosos. (TGT-54282)
* **Habilite la columna de espacio de trabajo para la oferta del editor web.** Esta actualización soluciona la confusión de clientes causada por las ofertas de [!UICONTROL Default Workspace] que aparecen en otros espacios de trabajo dentro del editor web. Aunque este comportamiento funciona según lo diseñado, las ofertas [!UICONTROL Default Workspace] son visibles intencionalmente en todos los espacios de trabajo, los clientes notificaron que la interfaz de usuario no aclaraba el origen del espacio de trabajo, especialmente al crear actividades en un espacio de trabajo no predeterminado como &quot;Aprobadores&quot;. Para mejorar la claridad, la columna [!UICONTROL Workspace] se ha habilitado en la lista de ofertas del Editor web, lo que permite a los usuarios distinguir fácilmente a qué espacio de trabajo pertenece cada oferta y evitar malinterpretaciones de las ofertas adicionales mostradas. (TGT-54138)
* **Los vínculos con target=&quot;_blank&quot; se abren en una ficha nueva.** Esta corrección resuelve un problema en el cual los sitios web creados que contienen vínculos con ~target=&quot;_blank&quot;~ se abren en una nueva pestaña del explorador cuando se hace clic en el modo [!UICONTROL Browse], lo que interrumpe la experiencia de vista previa en el editor. El comportamiento se producía porque los atributos de vínculo nativo de la página creada no estaban siendo interceptados por el JavaScript insertado de la extensión, a diferencia de la IU heredada, donde los elementos de anclaje se transformaban y sus destinos se anulaban para mantener la navegación dentro del editor. La actualización garantiza que los vínculos que usan ~target=&quot;_blank&quot;~ ahora se gestionen correctamente dentro del Editor web, de modo que ya no abran pestañas externas durante la creación. (TGT-54134)
* **Anule la selección de Advertencia de propiedad.** Esta actualización presenta una advertencia visual para informar claramente a los usuarios cuando anulan la selección de una propiedad detectada automáticamente en el Editor de actividades. Anteriormente, al eliminar una propiedad detectada automáticamente, no había ninguna indicación de que la propiedad se eliminara de forma permanente, lo que podría provocar la pérdida accidental de la configuración de segmentación. La corrección agrega un icono de advertencia, coherente con el comportamiento de la IU heredada, para notificar a los usuarios de que, al anular la selección de la propiedad, se elimina de la actividad. (TGT-54121)
* El menú desplegable **[!UICONTROL Workspaces]está limitado a 20 en la sección [!UICONTROL Users].** Esta corrección resuelve un problema en el que la lista desplegable [!UICONTROL Workspaces] de la sección [!UICONTROL Administration] > [!UICONTROL Users] mostraba solo 20 espacios de trabajo, incluso cuando un usuario tenía acceso a muchos más. La llamada de GraphQL subyacente para `licenseGroups` también se limitó a 20 resultados, lo que provocó que la interfaz de usuario mostrara una lista incompleta a pesar de que el usuario tenía acceso a más espacios de trabajo en la organización. La actualización elimina este límite estricto, por lo que ahora se devuelve y se muestra correctamente el conjunto completo de espacios de trabajo disponibles. (TGT-53820)
* **Se corrigió un problema en el cual el modal de ofertas no mostraba la columna del área de trabajo.** Se corrigió un problema en el cual el modal de ofertas no mostraba la columna del área de trabajo en la interfaz de usuario actualizada. Esto causó confusión en los clientes, ya que las ofertas de [!UICONTROL Default Workspace] aparecieron junto con las ofertas del espacio de trabajo seleccionado sin ninguna indicación de su origen. La columna del espacio de trabajo ahora está habilitada para que los clientes puedan identificar claramente a qué espacio de trabajo pertenece cada oferta. (TGT-52320)

+++

**Propiedades**

+++Ver detalles
* **La edición de actividad no debe agregar la propiedad detectada automáticamente si ya se ha eliminado.** Esta corrección soluciona un problema que causaba que al editar una actividad se reintrodujera automáticamente una propiedad detectada automáticamente que el usuario había eliminado anteriormente. Al volver a abrir una actividad para editarla, el sistema restauró incorrectamente la propiedad eliminada, lo que produjo un comportamiento incoherente y confusión en [!UICONTROL Properties List]. La actualización garantiza que, una vez eliminada una propiedad detectada automáticamente, permanece eliminada durante todas las ediciones posteriores y no vuelve a aparecer a menos que el usuario la vuelva a añadir explícitamente. (TGT-54182)
* **No agregue las propiedades detectadas automáticamente si ya se han quitado.** Esta corrección garantiza que una vez que un usuario elimine manualmente una propiedad detectada automáticamente de una actividad, el sistema ya no la vuelva a introducir durante la navegación posterior dentro del editor de actividades. Anteriormente, si un usuario anulaba la selección de una propiedad detectada automáticamente, se movía al paso [!UICONTROL Targeting] y luego se devolvía a [!UICONTROL Experiences], el editor rellenaba la propiedad eliminada en función de la lista detectada automáticamente almacenada en el segmento de estado Editor de actividades. La lógica actualizada ahora compara las propiedades detectadas automáticamente con las propiedades actuales en el segmento ~ActivityState~ e impide volver a agregar cualquier propiedad detectada automáticamente que el usuario ya haya quitado. Esto da como resultado un comportamiento coherente en todos los pasos y respeta la intención del usuario. (TGT-54181)
* **Agregar texto detectado automáticamente a la lista de propiedades.** Esta mejora actualiza [!UICONTROL Properties List] para etiquetar claramente cualquier propiedad que el sistema haya detectado automáticamente. Cuando una propiedad detectada automáticamente también está presente en el elemento visible para el usuario [!UICONTROL Properties List], ahora muestra el texto &quot;(Detección automática)&quot; junto a su nombre, usando el valor almacenado en el estado ~ActivityEditorSlice~. Esto refleja el comportamiento de la interfaz de usuario heredada y ayuda a los usuarios a distinguir fácilmente entre las propiedades seleccionadas manualmente y las identificadas automáticamente. (TGT-54120)
* **Agregar [!UICONTROL Properties] detectado automáticamente al estado.** Esta actualización garantiza que el estado ~ActivityEditorSlice.ExperienceEditor~ mantenga de manera consistente una lista actualizada de todos los ID de propiedad detectados automáticamente pasados desde el Editor Web a la ficha de la Actividad [!UICONTROL Experiences]. Cada vez que el usuario navega a la pestaña [!UICONTROL Experiences], el estado se actualiza con las propiedades recién detectadas, al tiempo que se evitan los duplicados, lo que garantiza un seguimiento preciso y un comportamiento descendente confiable. (TGT-54119)

+++

**Recommendations**

+++Ver detalles
* La lista desplegable **[!UICONTROL Environment]muestra solo 100 resultados.** Esta corrección corrige una limitación en la que los clientes con más de 100 entornos solo podían ver las primeras 100 entradas en la lista desplegable [!UICONTROL Environment] en [!UICONTROL Recommendations]. La consulta de GraphQL subyacente (~getEnvironmentsV2~) se paginó con un tamaño de página codificado de 100, lo que hizo que la interfaz de usuario mostrara solo una lista parcial incluso cuando había páginas adicionales disponibles. Para los clientes que tienen más de 100 entornos, este problema provocaba la falta de opciones y una experiencia de selección incompleta. La actualización aumenta el límite para que todos los entornos se devuelvan y se muestren, lo que garantiza una visibilidad completa independientemente del recuento de entornos. (TGT-53903)

+++

**Informes**

+++Ver detalles

* **Se corrigió un problema en el cual la flecha [!UICONTROL Reports] no indicaba claramente columnas expandibles.** Se corrigió un problema en el cual la tabla de informes no mostraba claramente que se podrían expandir columnas adicionales en la interfaz de usuario actualizada. Se ha agregado información de objeto que desaparece a la flecha [!UICONTROL Reports] cerca de los encabezados de columna para ayudar a los clientes a comprender que hay más columnas disponibles.

+++

**Vistas**

+++Ver detalles

* **No se pueden eliminar las modificaciones aplicadas a las vistas.** Esta corrección resuelve un problema en el cual los usuarios no podían eliminar modificaciones dentro de una actividad a menos que la modificación se hubiera vuelto a aplicar primero a vistas adicionales. Al editar una actividad (por ejemplo, ID de actividad 302467), los intentos de eliminar cualquier modificación no tenían ningún efecto, lo que impedía a los usuarios eliminar cambios no deseados. Sin embargo, una vez que se volvió a aplicar una modificación usando &quot;Aplicar a más vistas&quot; y se asignó a un evento `Page Load`, la eliminación de repente funcionó según lo esperado. (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalles
* El nombre **[!UICONTROL Experience Fragment]se truncó en la nueva interfaz de usuario del VEC** (TGT-54312)
* **No se puede usar [!UICONTROL Advanced Settings] para la métrica [!UICONTROL Revenue].** Esta corrección resuelve un problema en el que los usuarios encontraron un error 403 &quot;Acceso denegado&quot; al configurar [!UICONTROL Advanced Settings] para la métrica [!UICONTROL Revenue] en [!UICONTROL Goals & Settings]. El problema se producía al agregar una condición de dependencia vinculada al objetivo principal; el backend requería incorrectamente el privilegio de editor incluso para usuarios que ya tenían permisos suficientes para crear y editar actividades. Como resultado, se ha producido un error al guardar la actividad a pesar de una configuración válida. La actualización corrige la comprobación de permisos para que los usuarios con acceso adecuado puedan agregar correctamente dependencias de métrica de ingresos sin activar un error de recurso prohibido. (TGT-54092)
* **Se ha corregido un problema que hacía que el botón Agregar no se aplicara a las imágenes seleccionadas.** Se ha corregido un problema que impedía que los clientes agregaran ciertas imágenes al seleccionar o actualizar una imagen en el proceso de creación de actividades. Cuando los clientes buscaron recursos específicos, por ejemplo, las imágenes devueltas al buscar &quot;ipp&quot;, al hacer clic en el botón [!UICONTROL Add] no se aplicó la imagen seleccionada y no se creó ninguna modificación. La selección de otras imágenes, como `Homepage-banner-1-moz.jpg`, continuó funcionando según lo esperado. Esta actualización garantiza que todas las imágenes válidas se puedan aplicar de forma coherente en la IU actualizada. (TGT-53610)
* **Se corrigió un problema en el cual al eliminar una condición de URL se restablecía la configuración de la métrica de objetivos.** Se ha corregido un problema por el cual al eliminar una única condición de URL en la métrica [!UICONTROL Goal] se restablecía toda la configuración en la interfaz de usuario actualizada. Cuando los clientes intentaron eliminar una condición de dirección URL guardada en [!UICONTROL Conversion] > [!UICONTROL Viewed a Page], el tipo de objetivo cambió inesperadamente a [!UICONTROL Viewed an Mbox] y se eliminaron todas las opciones configuradas anteriormente. Esta actualización garantiza que solo se elimine la condición de URL seleccionada y que todos los ajustes de objetivo restantes permanezcan intactos. (TGT-53271)
* **Se ha corregido un problema que hacía que la búsqueda no buscara en las subcarpetas.** Se corrigió un problema en el cual la búsqueda de ofertas no arrojaba resultados de subcarpetas en la interfaz de usuario actualizada. Los clientes solo podían encontrar una oferta si navegaban manualmente a la carpeta en la que se almacenaba, lo que provocaba que el comportamiento de búsqueda no fuera coherente con las funciones de la API. Buscar ahora admite la búsqueda recursiva en carpetas para que los clientes puedan localizar ofertas sin necesidad de abrir cada carpeta individualmente. (TGT-51954)

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

## Información de versión preliminar {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
