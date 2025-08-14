---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d09e02db4ea94671e2450d1748b07def932916d9
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 11%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 24 de julio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.2 (14 de agosto de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

**[!UICONTROL Activities]**

+++Ver detalles
* **Se ha corregido un problema con la carga de actividades en la interfaz de usuario [!DNL Target] actualizada**: se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual algunas actividades no se cargaban al intentar editar. Este problema provocaba que los clientes dejaran a los usuarios en una pantalla de carga indefinida. Este problema afectaba a varias actividades y se notificaba que se producía de forma incoherente entre los clientes. Con esta corrección, las actividades afectadas ahora se cargan correctamente, lo que permite una edición sin problemas y reduce la interrupción de los flujos de trabajo de actividad. (TGT-53209)
* **Se ha corregido un error de guardado en el proceso de creación de actividad debido a la validación de `optionLocalId`**: se ha corregido un problema en el proceso de creación de actividad que impedía a los clientes guardar cambios debido a un error de validación de back-end: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Este problema se producía al modificar elementos específicos dentro de una actividad, lo que resultaba en una operación de guardado fallida. La corrección garantiza que las referencias de `optionLocalId` ahora se validen correctamente, lo que permite a los clientes guardar actividades sin encontrar este error. (TGT-53293)
* **Se ha corregido un bloqueo en el proceso de creación de actividades debido a referencias de opciones no válidas al cambiar de página**: se ha corregido un problema en el proceso de creación de actividades que hacía que la interfaz de usuario se bloqueara después de cambiar de página tres veces durante la edición. El bloqueo se activó por referencias de opciones no válidas, lo que dio como resultado errores de consola como &quot;No se encontró la opción con localId &#39;7&#39;&quot;. Con esta actualización, los clientes ahora pueden cambiar de página y aplicar modificaciones sin encontrar errores o interrupciones del sistema. (TGT-53295)
* **Se ha corregido un error de guardado en el proceso de creación de actividades debido a una entrada no válida del usuario al editar experiencias**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían guardar cambios en una actividad debido a un error no válido de entrada del usuario. El error se producía al modificar experiencias en la interfaz de usuario actualizada, lo que impedía que se confirmaran las actualizaciones. La actividad ahora se puede guardar correctamente, lo que permite a los clientes editar y publicar sin interrupción. (TGT-53267)
* **Se ha corregido un problema de carga en el proceso de creación de actividades que bloqueaba la edición en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades en el cual los clientes no podían editar actividades en la IU actualizada debido a una pantalla de carga continua. Los clientes ahora pueden abrir y modificar actividades sin encontrar errores de carga. (TGT-53415)

+++

**Fragmentos de experiencias (XF)**

+++Ver detalles
* **Se ha corregido un problema en el proceso de creación de actividades que permitía la edición no intencionada de fragmentos exportados por AEM mediante HTML**: se ha corregido un problema en el proceso de creación de actividades que permitía a los clientes editar el HTML de [!DNL Experience Fragments] (XF) exportado desde [!DNL Adobe Experience Manager] (AEM) en [!DNL Target]. Este comportamiento no fue intencionado, ya que los archivos XF deberían permanecer bloqueados para su edición una vez publicados desde AEM. La corrección garantiza que la opción &quot;Editar HTML&quot; ya no esté disponible para los fragmentos exportados por AEM, lo que preserva la integridad del contenido y el control esperado. (TGT-53286)

+++

**Modo de control de calidad**

+++Ver detalles
* **Se ha corregido un problema en el proceso de creación de actividades por el que los espacios iniciales en las direcciones URL provocaban vínculos de control de calidad rotos**: se ha corregido un problema en el proceso de creación de actividades por el que los espacios iniciales en la dirección URL de la actividad no se recortaban correctamente al guardar. Esto provocaba vínculos de control de calidad no válidos y un formato incorrecto en el back-end. Después de la actualización, las direcciones URL ahora se guardan correctamente, lo que evita que se rompan los vínculos y mejora la fiabilidad de los flujos de trabajo de control de calidad para los clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles
* **Se ha corregido un problema en la interfaz de usuario de la búsqueda en el catálogo en el cual la búsqueda avanzada no podía proporcionar sugerencias**: se ha corregido un problema en la nueva interfaz de usuario de [!UICONTROL Catalog Search] en el cual la característica [!UICONTROL Advanced Search] no podía proporcionar sugerencias. Los usuarios tenían que introducir valores exactos con una ortografía precisa, lo que hacía que la experiencia de búsqueda fuera engorrosa y propensa a errores. Con esta corrección, [!UICONTROL Advanced Search] ahora ofrece sugerencias relevantes a medida que los usuarios escriben, lo que mejora la facilidad de uso y reduce la fricción en la localización de productos. (TGT-52008)
* **Se han resuelto varios problemas de filtrado e interfaz de usuario para mejorar la capacidad de respuesta y la interacción con la entidad**: se han resuelto varios problemas, incluida la respuesta deficiente de los detalles de criterios en dispositivos de pantalla pequeña, la falta de resultados al seleccionar &quot;Todos los grupos de hosts&quot; en el filtro Entorno y la incapacidad para interactuar con entidades que no tienen nombre. Estas correcciones mejoran la facilidad de uso en todos los tamaños de pantalla, garantizan un filtrado preciso y permiten la interacción completa con todas las entidades de producto, lo que mejora la experiencia general para los usuarios. (TGT-52992)
* **Se han corregido los ID de producto que faltaban en la vista de detalles de Recommendations durante la creación de la actividad**: se ha corregido un problema en el proceso de creación de actividades [!DNL Recommendations] por el que los ID de producto faltaban en la pantalla de detalles del producto, lo que dificultaba a los clientes copiar o hacer referencia a los ID de producto durante los flujos de trabajo. Los ID de producto ahora aparecen claramente en la vista de detalles, lo que mejora la visibilidad y admite una administración de productos más eficiente para los clientes. (TGT-51964)
* **Se ha corregido un problema en el proceso de creación de actividades por el que no se mostraban mensajes de productos en la vista de recomendaciones**: se ha corregido un problema en el proceso de creación de actividades por el que la columna [!UICONTROL Message] de la vista [!DNL Recommendations] no mostraba datos de productos, aunque hubiera mensajes presentes. Los clientes tenían que eliminar manualmente y volver a añadir la columna para mostrar temporalmente el contenido, que a menudo volvía a desaparecer al desplazarse o buscar. Esta actualización restaura la visibilidad coherente de los mensajes del producto, lo que mejora la navegación por el catálogo y revisa los flujos de trabajo. (TGT-52777)
* **Se ha corregido un problema en el proceso de creación de actividades por el que al seleccionar &#39;Todos los grupos de hosts&#39; no se obtenían resultados en la vista de recomendaciones**. Se ha corregido un problema en el proceso de creación de actividades por el que al seleccionar el entorno &quot;Todos los grupos de hosts&quot; en la vista [!DNL Recommendations] no se obtenían resultados. Los clientes ahora pueden ver los datos de productos en todos los grupos de hosts según lo esperado, lo que mejora la visibilidad y la precisión del filtrado durante la configuración de la actividad. (TGT-53006)
* **Se corrigió un problema en el proceso de creación de actividades en el cual la opción de promoción principal no persistía después de guardar**: se corrigió un problema en el proceso de creación de actividades en el cual, al deshabilitar la opción de promoción principal en la configuración de actividades, no persistía después de guardar. Los clientes que intentaban eliminar la promoción principal encontraban la opción habilitada de nuevo al volver a visitar la actividad, lo que impedía una personalización adecuada. Esta actualización permite guardar los cambios de forma fiable, lo que permite a los clientes un control total de la configuración de la promoción. (TGT-53215)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* **Se corrigieron problemas con la carga de actividades y [!UICONTROL Cancel] botones en el proceso de creación de actividades**: se corrigió un problema en el proceso de creación de actividades en el cual ciertas actividades no se cargaban, lo que impedía a los clientes acceder a las modificaciones. Además, el botón [!UICONTROL Cancel] no responde, lo que impide que los clientes detengan el proceso de carga o salgan de la vista de edición. Esta corrección garantiza que las actividades ahora se carguen de forma fiable y que el botón [!UICONTROL Cancel] funcione según lo esperado, lo que mejora la estabilidad general y la experiencia del usuario en el Compositor de experiencias visuales. (VEC)(TGT-53218)
* **Se ha corregido un problema con el cambio de experiencia en la interfaz de usuario actualizada del VEC que bloqueaba la edición y deshabilitaba el botón [!UICONTROL Cancel]**: se ha corregido un problema en la interfaz de usuario actualizada del VEC por el que las modificaciones no se cargaban al cambiar entre experiencias en una actividad de segmentación de experiencias (XT). Los clientes no podían editar experiencias más allá de la que habían introducido inicialmente y el botón [!UICONTROL Cancel] faltaba o no respondía. Esta corrección garantiza que las modificaciones ahora se carguen correctamente en todas las experiencias y que el botón [!UICONTROL Cancel] funcione de forma fiable, incluso sin la extensión del asistente, lo que mejora los flujos de trabajo de edición y reduce la frustración. (TGT-53256)
* **Se corrigió un problema con la pantalla en blanco al cambiar entre varias experiencias en el proceso de creación de actividades**: se corrigió un problema por el cual el cambio entre varias experiencias provocaba la aparición de una pantalla en blanco. También se ha corregido un problema en el proceso de creación de actividades en el que los clientes encontraban una pantalla blanca al intentar modificar varias experiencias dentro de una actividad. Este problema se producía después de aplicar cambios a dos experiencias y seleccionar una tercera experiencia, lo que impedía realizar más ediciones. La actualización garantiza transiciones fluidas entre experiencias, lo que permite a los clientes realizar modificaciones sin interrupciones. (TGT-53266)
* **Se ha corregido un problema en el VEC por el cual los cambios en el código personalizado no se guardaban de forma fiable entre sesiones de edición**: se ha corregido un problema por el que las modificaciones de código personalizado realizadas en el Compositor de experiencias visuales (VEC) no se guardaban de forma fiable en un solo intento. Los clientes notificaron que los cambios, como las actualizaciones de estilo o la edición de HTML, faltaban intermitentemente en el sitio web y en las direcciones URL de control de calidad, incluso después de usar los botones [!UICONTROL Edit Content] y [!UICONTROL Save] finales. Esta regresión se ha resuelto para garantizar que todos los cambios en el código personalizado persistan según lo esperado en las sesiones de edición.** (TGT-53418)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
