---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 7%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 21 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Activities]**

+++Ver detalles
* **Se ha corregido un problema por el cual al guardar actividades se activaba un error de entrada de usuario no válido debido a datos de propiedad con formato incorrecto**: Los clientes encontraban un error crítico al intentar guardar actividades existentes. El mensaje de error indicaba una entrada de usuario no válida, que hacía referencia específicamente a un contenido de nombre de propiedad no reconocido en la carga útil JSON. En particular, las nuevas actividades que utilizan la misma propiedad se guardaron correctamente, lo que sugiere que el problema se aisló en los datos de actividad heredados. El proceso de creación de actividades ahora gestiona correctamente las configuraciones de propiedades heredadas, lo que evita errores de entrada no válidos y garantiza un comportamiento de guardado coherente en las actividades nuevas y existentes. (TGT-53507)
* **Se ha corregido un problema que impedía que los clientes guardaran una actividad debido a un error InvalidProperty.Json**: Los clientes encontraron un error al intentar guardar una actividad en la interfaz de usuario actualizada, incluso sin realizar ninguna modificación. El mensaje de error indicaba una estructura JSON no válida: &quot;JSON no válido. Nombre de propiedad &#39;content&#39; no reconocido. Ubicación: línea - 1, columna - 432&quot;. Este problema se debía a una propiedad no reconocida en la carga útil de la solicitud y ahora se ha resuelto. Los clientes pueden guardar las actividades correctamente sin encontrar este error. (TGT-53513)
* **Se ha corregido un problema por el cual las actividades programadas mostraban incorrectamente un estado [!UICONTROL Live] hasta la actualización de la página**: Los clientes observaban que, al programar una actividad para que se publique en una fecha y hora futuras, el estado aparecía inmediatamente como [!UICONTROL Live] en lugar de [!UICONTROL Scheduled]. Esto causaba confusión, aunque el mensaje de confirmación indicaba correctamente que la actividad estaba programada. Al actualizar la página, se corrigió la visualización del estado. Este problema se ha resuelto y las actividades programadas muestran correctamente el estado Programado sin necesidad de actualizar. (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Ver detalles
* **Se ha corregido un problema por el cual los clientes no podían escribir nombres de grupos de informes durante el proceso de creación de actividades**: Los clientes que usaban [!DNL Adobe Analytics] como fuente de informes durante el proceso de creación de actividades no podían escribir en la lista desplegable [!UICONTROL Report Suite] para buscar grupos de informes específicos. Esto afectaba a los flujos de trabajo de las organizaciones con un gran número de grupos de informes, donde el desplazamiento manual retrasaba considerablemente la configuración. La lista desplegable no se ordenaba alfabéticamente y no respondía de forma coherente a la entrada escrita, lo que dificultaba la localización de grupos de informes como &quot;Office + Tienda - Web - Producción&quot;. Este problema se ha resuelto y los clientes ahora pueden buscar de forma eficaz escribiendo los nombres de los grupos de informes. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Ver detalles
* **Se ha corregido un problema por el cual las audiencias de &quot;Lapso de tiempo&quot; caducadas bloqueaban el guardado de actividades incluso después de su eliminación**: Los clientes no podían guardar actividades en la interfaz de usuario actualizada debido a un error relacionado con las audiencias de &quot;Lapso de tiempo&quot; caducadas. Incluso después de eliminar la audiencia afectada, el mensaje de error persistió: &quot;La actividad contiene una audiencia con un lapso de tiempo no válido&quot;. Este problema se producía porque el sistema seguía validando la audiencia solo de actividad, incluso cuando ya no estaba en uso. El comportamiento se complicó aún más por las discrepancias de zona horaria. La lógica de validación se ha corregido y los clientes ahora pueden guardar actividades sin encontrar este error. (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++Ver detalles
* **Se ha corregido un problema que impedía que los clientes insertaran fragmentos de experiencias usando [!UICONTROL Insert Before] o [!UICONTROL Insert After] en la interfaz de usuario**. Los clientes encontraban un error al intentar insertar [!UICONTROL Experience Fragments] en una actividad usando las opciones &quot;Insertar antes&quot; o &quot;Insertar después&quot; en la interfaz de usuario actualizada. El mensaje de error mostrado era: &quot;El contenido de la oferta debe contener exactamente un elemento de HTML&quot;. Este problema era específico de la interfaz de usuario actualizada y no se producía en la versión anterior. Este problema se ha resuelto y los clientes pueden insertar [!UICONTROL Experience Fragments] correctamente sin encontrar este error. (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++Ver detalles
* **Se ha corregido un problema que impedía que los clientes editaran ofertas de decisión y seleccionaran elementos de página específicos en la interfaz de usuario actualizada**: en el proceso de creación de actividades actualizado, los clientes no podían editar ofertas de decisión existentes ni seleccionar elementos de página específicos en el Compositor de experiencias visuales (VEC). Las ofertas de decisión se mostraban incorrectamente como ofertas de HTML y los cambios realizados durante la edición no se guardaban. Además, ciertas direcciones URL regionales, como el sitio de Japón, no se cargaban correctamente en el VEC, lo que bloqueaba la creación y las actualizaciones de actividades. Las ofertas de decisión ahora se muestran correctamente, los elementos de página se pueden seleccionar según lo esperado y las URL regionales se cargan correctamente en el VEC, lo que restaura la funcionalidad de edición completa. (TGT-53425)
* **Se ha corregido un problema por el cual los selectores [!UICONTROL Offer Decision] no se podían modificar ni cambiar inesperadamente después de guardar**: en el proceso actualizado de creación de actividades, los clientes no podían modificar el selector [!UICONTROL Offer Decision] según lo previsto. Los intentos de cambiar el selector no se han realizado correctamente y el selector se ha revertido a un valor incorrecto después de guardar. Este comportamiento provocaba que la oferta de decisión desapareciera del Compositor de experiencias visuales (VEC), lo que bloqueaba futuras ediciones. Los cambios de selector ahora se conservan correctamente, y las ofertas de decisión permanecen visibles y editables en el VEC después de guardar.(TGT-53433)
* **Se ha corregido un problema por el cual [!UICONTROL Offer Decisions] desaparecía de la actividad después de guardar**: [!UICONTROL Offer Decisions] agregados durante el proceso de creación de la actividad no se conservaban después de guardar y volver a abrir la actividad. Este problema se producía al editar contenido dinámico e insertar [!UICONTROL Offer Decisions] con selectores y propiedades específicos. [!UICONTROL Offer Decisions] ahora persiste correctamente después de guardar y los selectores permanecen intactos, lo que garantiza un comportamiento de edición y direccionamiento coherente. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Ver detalles
* **Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el que la descarga de CSV con criterios personalizados arrojaba el error 404**: se ha corregido un problema por el que los clientes no podían descargar el CSV con criterios personalizados en el proceso de creación de actividades. El vínculo de descarga ahora funciona correctamente, lo que permite a los clientes exportar criterios personalizados según lo esperado. (TGT-51966)
* **Se corrigió una carga incoherente de imágenes en[!UICONTROL Catalog Search]**: se corrigió un problema por el que las miniaturas y las imágenes de [!UICONTROL  Catalog Search] no se cargaban de manera consistente en el proceso de creación de actividades. Las imágenes no aparecían a menos que la columna &quot;URL en miniatura&quot; estuviera visible y algunas imágenes de producto se cargaran parcialmente o no se cargaran después de las acciones de navegación o búsqueda. El comportamiento de carga de imágenes se ha estabilizado y las miniaturas ahora se muestran de forma fiable, independientemente de la visibilidad de la columna o las acciones de navegación. (TGT-52778)
* **Se ha corregido un problema por el cual editar una recomendación en una experiencia duplicada afectaba a la experiencia original**: Los clientes notificaron que modificar una recomendación en una experiencia duplicada alteraba involuntariamente la experiencia original. En concreto, después de duplicar la Experiencia B en el proceso de creación de actividades y editar su diseño o criterios, los mismos cambios se reflejaron en la Experiencia B original, a pesar de ser entidades independientes. Las experiencias duplicadas ahora mantienen configuraciones independientes, lo que garantiza que las ediciones realizadas en una experiencia no afecten a la original. (TGT-53369)
* **Se ha corregido un problema por el cual los cambios realizados en una experiencia duplicada afectaban involuntariamente a la experiencia original de una actividad**: Los clientes notificaron que, al duplicar una experiencia dentro de una actividad y asignar una nueva audiencia, cualquier cambio realizado en el diseño o los criterios de la experiencia duplicada también se reflejaba en la experiencia original. Este problema se producía aunque no se realizaban ediciones directamente en la versión original, lo que afectaba a la capacidad de crear variaciones independientes dentro de la misma actividad. El proceso de creación de actividades ahora aísla correctamente las experiencias duplicadas, asegurándose de que las ediciones realizadas en una experiencia no afecten a la experiencia original. (TGT-53361)
* **Se ha corregido un problema en el cual [!UICONTROL Recommendation Catalog] no mostraba de forma intermitente los datos completos de atributos de productos**: en la interfaz de usuario de [!DNL Recommendations] actualizada, los clientes experimentaron un problema en el cual algunos atributos de productos, como el mensaje, no se mostraban de forma coherente en los resultados de [!UICONTROL Catalog Search], aunque los datos existían en la fuente. Este problema requería que los clientes reconfiguraran manualmente la visibilidad de la columna para recuperar los valores que faltaban. [!UICONTROL Catalog Search] ahora muestra de forma fiable todos los atributos configurados, lo que elimina la necesidad de restablecer manualmente las columnas. (TGT-52769)
* **Se ha corregido un problema que impedía deshabilitar [!UICONTROL Front Promotion] en una actividad activa**: no se guardaron los intentos de deshabilitar [!UICONTROL Front Promotion] en una actividad activa. Después de seleccionar [!UICONTROL Change Promotion] y deshabilitarlo, la promoción permaneció activa al volver a editar la actividad, lo que impidió que se actualizaran las configuraciones de recomendación. La configuración de la promoción ahora se guarda correctamente, lo que permite a los clientes deshabilitar o modificar las promociones en actividades activas según lo esperado. (TGT-53231)
* **Se ha corregido un problema que causaba que, al habilitar [!DNL Recommendations] [!UICONTROL Promotion] sin datos, se generara un mensaje de error no claro**: al habilitar [!UICONTROL Front] o [!UICONTROL Back Promotion] en una actividad [!DNL Recommendations] sin especificar los valores necesarios, se generaba un mensaje genérico de &quot;error de entrada no válido&quot;. El problema subyacente era un campo de configuración que faltaba, pero el mensaje de error no indicaba claramente la causa, lo que dificultaba la resolución de problemas. El proceso de creación de actividades ahora proporciona un mensaje de error claro y procesable cuando faltan campos obligatorios, como `collectionId` o reglas, lo que ayuda a los clientes a identificar y resolver problemas de configuración rápidamente. (TGT-52616)
* **Se ha corregido un problema que impedía que la lista [!UICONTROL Product] se mostrara en el modal [!UICONTROL Edit] dentro de la ficha [!UICONTROL Recommendations]**: Los clientes no podían ver la lista de productos filtrados al editar [!UICONTROL collection] o [!UICONTROL exclusion] en la ficha [!UICONTROL Recommendations]. Se esperaba que la lista se actualizara en tiempo real en función de las reglas aplicadas, pero no pareció como estaba previsto. Este problema se ha resuelto y la lista de productos ahora se muestra correctamente y se actualiza dinámicamente a medida que se modifican las reglas. (TGT-53481)
* **Se ha corregido un problema con el diseño del cuadro de diálogo Ver detalles en la interfaz de usuario actualizada**: el diseño del modal Ver detalles en la interfaz de usuario actualizada se ha modificado para mejorar la claridad y la facilidad de uso. El cuadro de diálogo ahora incluye dos pestañas:
   * [!UICONTROL Details] ficha: muestra toda la información relevante para el elemento seleccionado.
   * Pestaña [!UICONTROL Inventory]: muestra todos los productos filtrados por la colección actual y las reglas de exclusión.

  Esta mejora ayuda a los clientes a navegar y comprender mejor los datos específicos de los artículos y el contexto del inventario dentro del proceso de creación de actividades. (TGT-53503)

   * **Se ha corregido un problema por el cual las promociones eliminadas en las actividades de recomendación volvían a aparecer después de guardar**: Los clientes notificaron que cuando se eliminaron [!UICONTROL front] o [!UICONTROL back] promociones de [!DNL Recommendations] actividades y se guardó la actividad, las promociones seguían apareciendo tras la reapertura. Este problema se producía en los entornos de ensayo y producción y afectaba al proceso de creación de actividades actualizado. El problema se ha resuelto. Las promociones que se eliminan de una actividad ahora se mantienen correctamente después de guardar. (TGT-53490)

+++

**Informes**

+++Ver detalles
* **Se ha corregido un problema por el cual el informe [!UICONTROL Automated Segments] mostraba valores de audiencia nulos**: Los clientes notificaron que [!UICONTROL Automated Segments] en los informes de actividad mostraban valores nulos para los datos de audiencia, lo que impedía realizar un análisis preciso del rendimiento del segmento. Este problema se produjo al acceder a la sección [!UICONTROL Reports] y seleccionar [!UICONTROL Automated Segments], aunque se esperaban datos de audiencia válidos. [!UICONTROL Automated Segments] ahora muestra correctamente los valores de audiencia, lo que garantiza información confiable de informes y segmentación. (TGT-52793)

+++

**Aplicaciones de una sola página (SPA)**

+++Ver detalles
* **Se ha corregido un problema que causaba que al cambiar entre los modos [!UICONTROL Browse] y [!UICONTROL Design] se restableciera el estado de SPA en la interfaz de usuario actualizada**: Los clientes informaron de que al cambiar entre los modos [!UICONTROL Browse] y [!UICONTROL Design] en la interfaz de usuario actualizada se volvía a cargar el editor web y se restablecía el estado de las SPA. Este problema interrumpía los flujos de trabajo y requería que los clientes volvieran a introducir la información. El problema se ha resuelto. El estado de SPA ahora se conserva al alternar entre modos, lo que garantiza una experiencia más fluida y coherente durante la creación de la actividad. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalles
* **Se ha corregido un problema en el proceso de creación de actividades que bloqueaba la progresión al paso [!UICONTROL Targeting] en las actividades AP**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían continuar al paso [!UICONTROL Targeting] en las actividades [!UICONTROL Automated Personalization] (AP) a menos que se agregaran dos ubicaciones. Este comportamiento difería de la experiencia anterior, en la que una sola ubicación con varias ofertas era suficiente. El requisito se ha corregido, lo que permite a los clientes seguir utilizando configuraciones de una sola ubicación como parte de sus flujos de trabajo de AP. (TGT-53426)
* **Se ha corregido un problema por el que el nuevo proceso de creación de actividades no establecía el parámetro fmt=png-alpha para imágenes transparentes**: En la interfaz de usuario actualizada, las imágenes insertadas durante el proceso de creación de actividades ya no incluían el parámetro `fmt=png-alpha` de forma predeterminada, lo que resultaba en una pérdida de transparencia. Este comportamiento difería del de la IU anterior, que añadía automáticamente el parámetro a las direcciones URL de la imagen, conservando los fondos transparentes. El proceso de creación de actividades ahora aplica correctamente el parámetro `fmt=png-alpha` a las direcciones URL de las imágenes cuando se requiere transparencia, lo que garantiza la representación coherente de los recursos transparentes. (TGT-52615)
* **Se ha corregido un problema que impedía a los clientes buscar grupos de informes en la interfaz de usuario actualizada**: en la interfaz de usuario actualizada, la lista desplegable [!UICONTROL Report Suites] de la sección [!UICONTROL Goals & Settings] no permitía a los clientes escribir y buscar, lo que dificultaba la localización de grupos de informes específicos, especialmente para los inquilinos con un gran número de entradas. A diferencia de la IU anterior, la lista no se ordenaba y carecía de filtrado basado en la entrada. Este problema se ha resuelto. Los clientes ahora pueden escribir para buscar y filtrar grupos de informes, restaurando la funcionalidad disponible en la interfaz de usuario heredada. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Ver detalles
* **Se ha corregido un problema en el cual un cliente restringido a un solo espacio de trabajo podía ver actividades desde otros espacios de trabajo**: Los clientes con acceso limitado a un espacio de trabajo inesperadamente podían ver actividades en todos los espacios de trabajo al seleccionar [!UICONTROL All Workspaces] en el proceso de creación de actividades. Esta visibilidad planteaba el riesgo de cambios no deseados en las actividades activas en otros espacios de trabajo, lo que podría afectar al rendimiento del sitio web. Los controles de acceso de Workspace se han reforzado para garantizar que los clientes puedan ver e interactuar únicamente con las actividades dentro del espacio de trabajo asignado. (TGT-53101)
* **Se ha corregido un problema en el cual un cliente podía ver actividades desde [!UICONTROL Default Workspace] sin tener acceso:** Un cliente con acceso limitado al área de trabajo de ensayo pudo ver actividades desde [!UICONTROL Default Workspace] mediante el proceso de creación de actividades. Este comportamiento se produjo a pesar de la configuración back-end y los derechos de acceso correctos. Los controles de acceso de Workspace se han reforzado para garantizar que los clientes puedan ver las actividades solo dentro del espacio de trabajo asignado.(TGT-53297)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
