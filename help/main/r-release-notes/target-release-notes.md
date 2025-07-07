---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dc291b4573e00512edd44b94304be2a25106b234
workflow-type: tm+mt
source-wordcount: '1882'
ht-degree: 11%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 7 de julio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.1 (miércoles, 08 de julio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema en el cual los refinamientos de audiencia solo de actividad desaparecían de la interfaz de usuario inmediatamente después de eliminarse de una ubicación, incluso antes de guardar la actividad. Este comportamiento contradecía la funcionalidad esperada y la guía de información del objeto, que indica: &quot;Todas las audiencias no utilizadas de esta biblioteca se eliminarán una vez guardada la actividad&quot;. (TGT-52982)
* Se corrigió un problema que se producía al intentar asignar una audiencia distinta de [!UICONTROL All Visitors] a una actividad. Al guardar, se muestra el siguiente mensaje de error: &quot;No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste.&quot; (TGT-53008)
* Se ha corregido un problema que bloqueaba el guardado de una actividad después de crear y asignar una nueva audiencia dentro del editor de actividades. El mensaje de error mostrado era: &quot;No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste.&quot; (TGT-52977)
* Se ha corregido un problema que se producía al intentar guardar una actividad después de crear y asignar una nueva audiencia de informes. El mensaje de error devuelto fue: &quot;Acceso denegado. Para realizar esta operación, se requieren todos los privilegios siguientes: [editor].&quot; Este problema se producía a pesar de que el usuario tenía acceso de nivel de aprobador. (TGT-53103)
* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Approver] no podían agregar ni guardar refinamientos de audiencia solo de actividad. Al intentar hacerlo, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario tenía permisos suficientes para aprobar y administrar actividades. (TGT-52984)
* Se ha corregido un problema que se producía cuando se eliminaba una audiencia específica de actividad mediante la opción [!UICONTROL Remove Audience Refinement], de modo que la audiencia ya no aparecía en la lista de audiencias para volver a seleccionarse dentro de la misma actividad. Este comportamiento impedía a los usuarios volver a añadir la misma audiencia a menos que se volviera a crear desde cero. (TGT-52979)
* Se ha corregido un problema que impedía a los usuarios crear actividades [!UICONTROL Auto-Target] (AT) si [!UICONTROL Auto-Allocate] (AA) se seleccionaba primero durante la configuración de la asignación de tráfico. Este problema provocaba un error de validación del back-end e impedía guardar la actividad. (TGT-53096)
* Se corrigió un problema en el cual los usuarios no podían navegar a una dirección URL diferente mientras se encontraban en [!UICONTROL Browse Mode]. Esto impedía que los probadores y editores validaran o previsualizaran páginas alternativas dentro de la misma sesión de actividad. (TGT-53052)
* Se corrigió un problema en el cual el uso de la característica [!UICONTROL Manage Content] en las actividades [!UICONTROL Automated Personalization] (AP) hacía que la página se bloqueara y permaneciera en blanco. Este problema se produjo después de hacer clic en [!UICONTROL Done] en el administrador de contenido, especialmente en las actividades creadas o editadas en la interfaz de usuario actualizada. (TGT-53047)
* Se corrigió un problema en el cual la característica [!UICONTROL Manage Content] no validaba correctamente el estado de una ubicación después de quitar todas las opciones de contenido. Esto podría generar un comportamiento incoherente o errores al intentar guardar o continuar con la configuración de la actividad. (TGT-52801)
* Se corrigió un problema en el cual varias instancias de [!UICONTROL Visual Experience Composer] (VEC) se abrían simultáneamente durante la creación de la actividad. Este problema se produjo cuando los usuarios deshabilitaron [!UICONTROL Enhanced Experience Composer] (EEC) y quitaron la barra diagonal de la dirección URL del sitio web en el paso [!UICONTROL Page Delivery]. (TGT-52782)
* Se ha corregido un problema en el cual los usuarios encontraban un error de &quot;entrada no válida&quot; al añadir una nueva página y eliminar elementos específicos dentro de diferentes experiencias. El error se activó porque se generó un duplicado de `LocalIds` durante la manipulación de elementos, especialmente al cambiar entre experiencias y modificar estructuras de páginas compartidas. (TGT-52720)
* Se ha resuelto un problema en el cual la aplicación de una modificación a una vista resultaba en la duplicación de la vista y la actividad devolvía un error de &quot;entrada de usuario no válida&quot;. Esta corrección garantiza que las modificaciones de la vista se apliquen correctamente sin activar errores de duplicación o validación. (TGT-52886)
* Se ha corregido un problema por el cual las modificaciones de código personalizado se mostraban incorrectamente para la experiencia incorrecta. En concreto, los cambios destinados a una experiencia se mostraron en una experiencia diferente, lo que provocó confusión y posibles errores de configuración en las actividades activas. (TGT-52776)
* Se ha corregido un problema que impedía editar o guardar modificaciones de código personalizado en la nueva interfaz de usuario de VEC. Específicamente:

   * Después de editar un bloque de código personalizado y guardar, los cambios no se reflejaron en la interfaz de usuario ni en la previsualización de control de calidad.
   * En algunos casos, las modificaciones no se podían eliminar a menos que se cerrara y se volviera a abrir la actividad.
   * Como solución alternativa, los usuarios tenían que copiar el código, eliminar la modificación y volver a crearlo manualmente con el contenido actualizado. (TGT-53072)

* Se ha corregido un problema por el cual al editar y guardar código personalizado el panel [!UICONTROL Modifications] dejaba de responder. (TGT-53075)
* Se ha corregido un problema por el cual las modificaciones realizadas en el código personalizado en experiencias de variante se reflejaban de forma involuntaria en la experiencia [!UICONTROL Control]. Esto provocaba cambios no deseados en el comportamiento de entrega. La experiencia [!UICONTROL Control] ahora permanece aislada de las ediciones de código personalizado realizadas en otras experiencias. (TGT-52413)
* Se ha corregido un problema en el flujo de trabajo de creación de actividades por el que las modificaciones realizadas en una experiencia (por ejemplo, la Experiencia B) se duplicaban de forma involuntaria en otra experiencia (Experiencia A) si el usuario hacía clic en la segunda experiencia antes de que el editor se cargara completamente. Este comportamiento también podría provocar la pérdida de modificaciones si la experiencia seleccionada inicialmente no tiene cambios. (TGT-52597)
* Se corrigió un problema en el cual los cambios realizados en el paso [!UICONTROL Modifications] de creación de la actividad no se guardaban de manera consistente. En algunos casos, después de completar todos los pasos y hacer clic en [!UICONTROL Save], el script personalizado agregado en la sección [!UICONTROL Modifications] no se reflejaba en el sitio activo, a pesar de que no había errores visibles durante el proceso de guardado. (TGT-52661)
* Se ha corregido un problema por el cual los cambios en el código personalizado no se guardaban correctamente y se reflejaban de forma involuntaria en varias experiencias dentro de la misma actividad. Además, los usuarios encontraban problemas de acceso al abrir o actualizar determinadas actividades, lo que provocaba que aparecieran pantallas en blanco. Estos problemas se han resuelto para garantizar una edición estable de la actividad y un aislamiento preciso de la experiencia. (TGT-52594)
* Se corrigió un problema en el cual al usar la característica [!UICONTROL Generate Adhoc Offer] aparecían ubicaciones indefinidas en el panel [!UICONTROL Manage Content]. (TGT-53076 y TGT-53070)
* Se ha aclarado el comportamiento con el cliente, donde las modificaciones realizadas mediante una oferta de HTML podrían no aparecer al navegar desde el paso [!UICONTROL Targeting] hacia atrás a [!UICONTROL Experiences]. Para este cliente, el sitio web afectado generaba dinámicamente varios selectores DOM que cambiaban con cada carga de página. Como resultado, el selector utilizado originalmente para la modificación no se puede encontrar cuando se vuelve a abrir el editor, lo que hace que la modificación parezca no estar presente o no ser válida. Esto funciona según lo diseñado. Para garantizar que las modificaciones persistan visualmente en el editor, se recomienda que los clientes utilicen selectores estables y coherentes que no cambien entre las recargas de la página. (TGT-52874)
* Se ha corregido un problema en el cual al intentar eliminar o desactivar una oferta que formaba parte de una experiencia excluida se activaba un error de &quot;entrada de usuario no válida&quot;. Este problema se producía aunque la oferta no se usaba de forma activa en las experiencias incluidas. (TGT-52917)
* Se ha corregido un problema en el cual el menú desplegable de métrica [!UICONTROL Revenue] en el paso [!UICONTROL Goals & Settings] tenía el valor predeterminado incorrecto de [!UICONTROL Revenue per Visit] (RPVISIT), incluso después de que el usuario seleccionara una métrica diferente.  se ha producido un problema al contraer y volver a expandir el panel de configuración de métricas, lo que provocaba que se restableciera el valor seleccionado anteriormente. (TGT-52811 y TGT-52878)
* Se ha corregido un problema que bloqueaba
* Se han corregido varios problemas en el flujo de trabajo de creación de actividades relacionado con la nomenclatura de ofertas y la traducción de contenido en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Multivariate Testing] (MVT):

  Problemas clave abordados:

   * La creación de varias ofertas de HTML con el mismo nombre (por ejemplo, &quot;Experiencia&quot;) ha activado el error &quot;No se permiten nombres de ofertas duplicados&quot;, pero la interfaz de usuario no indicaba claramente qué ofertas estaban causando el conflicto.
   * Al cambiar el nombre de las ofertas mediante el panel derecho, se actualizó el nombre en la interfaz de usuario, pero el cambio no se reflejó en la pestaña [!UICONTROL Manage Content] ni en la pestaña [!UICONTROL Offers], lo que provocó errores de validación persistentes.
   * En las actividades MVT, aunque el error de nombre duplicado no persistió después de cambiar el nombre, la IU seguía sin reflejar los nombres de ofertas actualizados de forma coherente en las pestañas. (TGT-52933)

* Se corrigió un problema en el cual al seleccionar &quot;[!UICONTROL Export order details to CSV]&quot; de la página [!UICONTROL Reports] se descargaba un archivo vacío. Este problema ocurría incluso cuando había datos de pedido válidos en la actividad. (TGT-52225)
* Se corrigió un problema en el cual copiar una actividad existente y cambiar el origen de informes a [!DNL Adobe Analytics] (A4T) resultaría en un error de &quot;entrada de usuario no válida&quot;. El error se activó cuando ciertas acciones de métricas incompatibles con los informes de [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` y `restart_new_experience`, se retuvieron de la actividad original. (TGT-52900)
* Se ha corregido un problema que impedía que los clientes crearan o guardaran una actividad al seleccionar [!DNL Adobe Analytics] (A4T) como fuente de informes en el paso [!UICONTROL Goals & Settings]. El problema se produjo específicamente al seleccionar una métrica de [!UICONTROL Custom Event] (por ejemplo, &quot;Evento personalizado 16&quot;), dando como resultado el siguiente error: &quot;Entrada de usuario no válida&quot;. (TGT-52910)
* Se ha corregido un problema que causaba que, al hacer clic en el vínculo &quot;[!UICONTROL View in Analytics]&quot;, se redirigiera a los usuarios a la página principal en lugar del panel [!DNL Analytics] deseado. (TGT-53092 y TGT-53093)
* Se ha corregido un problema que se producía al clonar una actividad existente y cambiar el origen de los informes de [!DNL Target] a [!DNL Adobe Analytics]. Los usuarios se encontraron con un error &quot;400 - Entrada de usuario no válida&quot; que impedía guardar la actividad. (TGT-52875)
* Se ha corregido un problema por el cual las direcciones URL de vista previa incluían incorrectamente audiencias adicionales más allá de la escrita explícitamente por el usuario. Este comportamiento se ha corregido para garantizar que solo se aplique la audiencia especificada al generar un control de calidad o un vínculo de vista previa. (TGT-52912)
* Se ha corregido un problema en el cual la dirección URL [!UICONTROL Activity QA] incluía un parámetro de consulta innecesario: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Se ha corregido un problema en las actividades basadas en formularios en el cual duplicar una experiencia y editar el código personalizado en una de las experiencias duplicadas aplicaba involuntariamente esos cambios a todas las experiencias duplicadas. Cada experiencia ahora conserva su propio código personalizado de forma independiente después de la duplicación. (TGT-51600)
* Se corrigió un problema que afectaba el flujo de trabajo de creación de actividad al agregar [!DNL Recommendations] con [!UICONTROL promotions]. Cuando los usuarios seleccionaron &quot;[!UICONTROL Promote by Attribute]&quot; y agregaron una regla de filtrado (por ejemplo, [!UICONTROL Parameter Matching]), el tipo de regla y los valores de operando seleccionados no se retuvieron después de guardar y volver a editar la actividad. Al volver a abrir, el tipo de regla de filtrado cambiaba inesperadamente y faltaban los valores de operando. (TGT-53059)
* Se ha corregido un problema que se producía al ver una actividad [!DNL Recommendations] en la interfaz de usuario [!UICONTROL Overview] actualizada, y que provocaba que la sección [!UICONTROL Goals & Settings] no se cargara cuando se seleccionaba [!DNL Adobe Analytics] (A4T) como origen de informes. Se muestra el siguiente mensaje de error: &quot;Se ha producido un error. No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste. (TGT-52999)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el cual cualquier promoción creada con una sola regla se interpretaba y mostraba de forma incorrecta como un tipo de promoción &quot;Lista de elementos&quot;, independientemente de la lógica de la regla. (TGT-53063)
* Se corrigió un problema que se producía al usar la [!UICONTROL Overview]IU actualizada, el botón &quot;[!UICONTROL Download Recommendations Data]&quot; no estaba presente para las actividades [!UICONTROL Experience Targeting] (XT) que incluyen [!DNL Recommendations]. (TGT-52730 y TGT-52756)
* Anteriormente, la interfaz de usuario de Recommendations solo mostraba el número de entidades importadas correctamente desde una fuente. Sin embargo, el formato de mensaje back-end incluye tanto el número de entidades importadas como el número total de entidades con el formato:

  `# of entities imported / # of total entities`

  Debido a esta discrepancia, los usuarios solo veían el primer valor (recuento importado) en la interfaz de usuario, lo que provocaba confusión. La interfaz de usuario ahora muestra ambos números. (TGT-53073)

* Se ha corregido un problema de traducción contextual en la configuración regional coreana (ko-KR) para la cadena &quot;Previsualizar experiencia&quot;. (TGT-52928)
* Se han corregido incoherencias terminológicas identificadas en la traducción al chino simplificado (zh_CN) de varias cadenas de texto. (TGT-52954 y TGT-52955)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
