---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fda279c909e2bb35e919d1bb4f4b611401a367cf
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 29 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (1 de septiembre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Activities]**

+++Ver detalles
* **Los clientes no pudieron copiar los nombres de actividad o documento de[!UICONTROL Activity Overview]**: anteriormente, los clientes no podían copiar el nombre de una actividad o la oferta o documento asociado directamente desde [!UICONTROL Activity Overview] en el proceso actualizado de creación de actividad. Esta limitación afectaba a la facilidad de uso, especialmente en pantallas más pequeñas. Los clientes ahora pueden copiar fácilmente los nombres de actividades y documentos sin soluciones alternativas. (TGT-51850)
* **Ingesta proactiva de datos de clientes [!DNL Target] depurados durante la creación de la actividad**: se ha mejorado el proceso de creación de actividades al habilitar la recopilación proactiva de informes, contenido y capturas de pantalla de [!DNL Target] clientes. Esta mejora aborda las lagunas de datos identificadas en los casos de uso existentes y ayuda a garantizar perspectivas más precisas durante la configuración de la actividad y el experimento. (TGT-52415)
* **Las actividades AP no recuperaron datos listos para modelos en la sección [!UICONTROL Reports]**: Los clientes que veían actividades de Automated Personalization (AP) en la sección [!UICONTROL Reports] no podían ver indicadores listos para modelos en el grupo de informes y nivel de oferta. Este problema se producía porque los datos listos para el modelo no se recuperaban correctamente del servidor. La funcionalidad se ha restaurado y los datos listos para el modelo ahora aparecen según lo esperado. (TGT-53600 y TGT-53601)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles
* **La lista de productos no estaba visible en el cuadro de diálogo [!UICONTROL View Collection]:** Anteriormente, los clientes no podían ver la lista de productos al ver una colección en la ficha [!UICONTROL Recommendations]. El cuadro de diálogo [!UICONTROL View Collection] ahora muestra correctamente los productos asociados, mejorando la transparencia y la facilidad de uso en la interfaz de usuario de Recommendations actualizada. (TGT-50531)
* **Se ha corregido un problema que causaba el filtrado con distinción de mayúsculas y minúsculas en [!UICONTROL Product Catalog Search] búsqueda avanzada**: El filtrado de búsqueda avanzada en la página [!UICONTROL Product Catalog Search] ahora ignora correctamente la distinción de mayúsculas y minúsculas, alineándose con el comportamiento de los servicios back-end y GraphQL. Esta actualización garantiza resultados de sugerencias coherentes y precisos para los clientes, independientemente del formato de texto. (TGT-53585)
* **La búsqueda avanzada en la interfaz de usuario [!UICONTROL Product Catalog Search] actualizada no proporcionó sugerencias**: Los clientes que usaban la característica de búsqueda avanzada en la interfaz de usuario [!UICONTROL Product Catalog Search] actualizada debían escribir los valores exactos con la ortografía correcta, ya que no se mostraba ninguna sugerencia. Esto dificultaba la localización eficiente de los productos. Las sugerencias ahora aparecen según lo esperado durante la entrada de búsqueda avanzada. (TGT-52008)

+++

**[!UICONTROL Reports]**

+++Ver detalles
* **No se han podido cargar los informes para la audiencia de escritorio debido a un error de nombre de audiencia no válido**: los clientes han encontrado un error de GraphQL al intentar ver los informes de la audiencia única en el proceso de creación de actividad. El sistema devolvió un mensaje &quot;Nombre de audiencia no válido: XXXXX&quot; que impedía el acceso a los datos de los informes. Ahora, los informes se cargan correctamente para la audiencia de escritorio. (TGT-53371)
* **El cambio de audiencias en la página de informes produjo errores en la interfaz de usuario de Target**: los clientes encontraron errores al seleccionar ciertas audiencias en la sección Reports de la interfaz de usuario de Target actualizada. Este problema se debía a la gestión de audiencias no válidas en las llamadas GraphQL back-end, lo que daba como resultado errores inesperados y datos faltantes. El problema se ha resuelto y las audiencias de escritorio ahora se cargan sin errores, incluso cuando no hay datos disponibles. (TGT-53370)
+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalles
* **Error al hacer clic en &quot;Aceptar cookies&quot; usando el [!UICONTROL Enhanced Experience Composer] (EEC) debido a la falta de una función**: Los clientes notificaron que al intentar aceptar cookies a través del EEC se produjo un error en la consola: `handleclickAcceptAllButton is not defined`. La funcionalidad de aceptación de cookies ahora funciona según lo esperado, lo que garantiza una experiencia más fluida durante la creación de actividades en la interfaz de usuario actualizada. (TGT-52794)
* **La nueva IU de EEC no pudo cargar ciertas páginas que anteriormente eran compatibles con la IU heredada**: Los clientes informaron que el nuevo EEC no podía cargar algunas páginas, a las que se podía acceder desde la IU heredada a pesar del código de eliminación de iframes presente en el sitio. El proceso actualizado de creación de actividades ahora admite la carga de estas páginas, lo que restaura la compatibilidad con los flujos de trabajo de creación de actividades. (TGT-53061)
* **El VEC mostraba una pantalla en blanco al editar experiencias**: Los clientes de un determinado inquilino informaron de que la pantalla del VEC se quedaba en blanco al intentar editar experiencias en el VEC actualizado. Este problema afectaba tanto a las actividades recién creadas como a las más antiguas, lo que impedía la continuidad del flujo de trabajo. El VEC ahora se carga correctamente, lo que permite a los clientes editar experiencias sin interrupción. (TGT-53547)
* **El VEC se bloqueó y mostró una pantalla en blanco al cargar ciertas actividades**: Los clientes de un determinado inquilino informaron que el VEC no pudo cargar actividades específicas. El editor de experiencias permaneció atascado en &quot;Aplicación de modificaciones iniciales&quot; antes de bloquearse y mostrar una pantalla en blanco. Los errores de consola indicaron un error al leer las propiedades no definidas. El editor ahora carga las actividades afectadas sin errores en el VEC actualizado. (TGT-53548)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
