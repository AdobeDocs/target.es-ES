---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 7%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 27 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (28 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Activities]**

+++Ver detalles
* **Se ha corregido un problema por el cual las actividades programadas mostraban incorrectamente un estado &quot;[!UICONTROL Live]&quot; en la interfaz de usuario actualizada durante el proceso de creación de actividades**: las actividades con fechas de activación futuras ahora muestran correctamente un estado &quot;[!UICONTROL Scheduled]&quot;. (TGT-53187)
* **Las actividades programadas mostraban incorrectamente un estado de [!UICONTROL Live] hasta que se actualizó la página**: Los clientes notificaron que, al programar una actividad para que se publique en una fecha y hora futuras, el estado aparecía inicialmente como [!UICONTROL Live] en lugar de [!UICONTROL Scheduled]. Esto causaba confusión a pesar del mensaje de confirmación que indica el comportamiento de programación correcto. El estado de la actividad ahora refleja con precisión [!UICONTROL Scheduled] inmediatamente después de guardarla, sin que sea necesario actualizar la página. (TGT-52937)
* **Los cambios en las experiencias duplicadas afectaron involuntariamente a la experiencia original**: Los clientes informaron que, al duplicar una experiencia dentro de una actividad y asignar una nueva audiencia, cualquier cambio realizado en la experiencia duplicada, como el diseño o los criterios, también se reflejaba en la experiencia original. Esto impedía la creación de variaciones independientes y afectaba a los flujos de trabajo de producción. Ahora, las experiencias duplicadas se pueden editar de forma independiente sin afectar a la versión original. (TGT-53361)
* **Se ha corregido un problema que impedía que los clientes guardaran una actividad debido a un error de `InvalidProperty.Json`**: Anteriormente, los clientes encontraban un error de &quot;entrada de usuario no válida&quot; al intentar guardar una actividad sin realizar cambios. El error se debía a un nombre de propiedad no reconocido &quot;content&quot; en la carga útil JSON. Este problema se ha resuelto y las actividades ahora se pueden guardar correctamente en la interfaz de usuario actualizada, incluso cuando no se realizan modificaciones. (TGT-53513)

+++

**Analytics for Target (A4T)**

+++Ver detalles
* **No se pueden escribir los nombres de los grupos de informes al crear actividades de A4T**: Los clientes no podían escribir en la lista desplegable [!UICONTROL Report Suite] al seleccionar [!UICONTROL Analytics] como fuente de informes en la interfaz de usuario actualizada.  Este problema dificultaba la localización de grupos de informes específicos, especialmente para organizaciones con listas grandes. La lista desplegable ahora admite la escritura y búsqueda por nombre, lo que mejora la eficacia durante el proceso de creación de actividades. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Ver detalles
* **Las audiencias de &quot;Lapso de tiempo&quot; caducadas bloquearon el guardado de la actividad incluso después de la eliminación**: anteriormente, los clientes no podían guardar una actividad si anteriormente había incluido una audiencia de &quot;Lapso de tiempo&quot; caducada, incluso después de que se eliminara esa audiencia. Este problema se debía a la validación persistente en la audiencia solo de actividad, que seguía almacenando en déclencheur errores. Ahora las actividades se pueden guardar según lo esperado una vez eliminadas las audiencias caducadas. (TGT-53517)
* **Desaparecieron páginas adicionales y múltiples audiencias después de guardar una actividad**: Anteriormente, los clientes que creaban una actividad [!UICONTROL A/B Test] en el proceso de creación de actividad experimentaron una pérdida de páginas adicionales configuradas y múltiples audiencias después de guardar. Este comportamiento fue inesperado y causó confusión durante la configuración. Estas configuraciones ahora se mantienen correctamente después de guardar la actividad. (TGT-52357)

+++

**Ofertas de decisión**

+++Ver detalles
* **No se pueden editar las ofertas de decisión ni seleccionar elementos de página específicos en el VEC actualizado**: Los clientes encontraron varios problemas en la IU actualizada que bloquearon su capacidad para actualizar actividades existentes o crear otras nuevas:

   * Las ofertas de decisión se mostraban incorrectamente como ofertas de HTML, lo que impedía realizar ediciones.
   * No se pudieron seleccionar elementos de página específicos en el VEC.
   * Los cambios realizados durante la edición no se han guardado.
   * Algunas direcciones URL regionales no se cargaban correctamente en el VEC y era necesario realizar ajustes manuales en las cookies.

  Los clientes ahora pueden editar ofertas de decisión, seleccionar elementos de página con precisión y guardar cambios según lo esperado. Las páginas regionales también se cargan correctamente en el VEC. (TGT-53425)

* **Los selectores de decisión de oferta no se pudieron modificar y cambiar inesperadamente después de guardar**: Los clientes notificaron que, al aplicar decisiones de oferta en la interfaz de usuario actualizada, el selector no se podía cambiar a partir de su valor predeterminado. Se omitieron los intentos de modificar el selector (por ejemplo, a `#tf-cq-hr or body`) y, después de guardar la actividad, el selector se reemplazó con un valor genérico como `#cdq_element_0`. Este problema provocaba que la oferta desapareciera del Compositor de experiencias visuales (VEC) y bloqueaba nuevas ediciones. Los clientes ahora pueden modificar los selectores de Decisión de oferta según lo previsto y los selectores guardados persisten correctamente sin cambios inesperados. (TGT-53433)
* **Las decisiones de oferta desaparecieron de las actividades después de guardarlas**: Los clientes informaron que las decisiones de oferta aplicadas a los elementos de página en la interfaz de usuario actualizada ya no eran visibles después de guardar la actividad. En algunos casos, el selector se cambiaba de forma inesperada y la oferta no se podía procesar en el VEC al reeditarla. Las decisiones de oferta ahora persisten correctamente después de guardar y los selectores permanecen estables, lo que garantiza que las ofertas sean visibles y editables según lo esperado. (TGT-53434)

+++

**Fragmentos de experiencias**

+++Ver detalles
* **Los clientes recibieron un error al insertar [!UICONTROL Experience Fragments] con [!UICONTROL Insert Before] o[!UICONTROL Insert After]**: los clientes encontraron un error al intentar insertar [!UICONTROL Experience Fragments] en una actividad con las opciones [!UICONTROL Insert Before] o [!UICONTROL Insert After] en la interfaz de usuario actualizada. El mensaje de error mostrado era:

  &quot;El contenido de la oferta debe contener exactamente un elemento HTML.&quot;

  Este problema era específico de la interfaz de usuario actualizada y no se producía en la versión anterior. Se ha resuelto y los clientes pueden insertar [!UICONTROL Experience Fragments] correctamente sin encontrar este error. (TGT-53432)

* **Mensaje de error al agregar [!UICONTROL Experience Fragment] a una actividad**: Anteriormente, los clientes que intentaban insertar un [!UICONTROL Experience Fragment] mediante la opción [!UICONTROL Insert Before] o [!UICONTROL Insert After] encontraron el error: &quot;El contenido de la oferta debe contener exactamente un elemento de HTML&quot;. Este error apareció a pesar de que el fragmento era válido y aceptado en la interfaz de usuario heredada, que incluía un conmutador para admitir esta configuración. El problema se ha resuelto en el VEC actualizado. (TGT-53442)

+++

**Localización**

+++Ver detalles
* **No se localizaron los mensajes de mensaje de mensaje en el paso [!UICONTROL Goals & Settings]**: Anteriormente, los clientes encontraban un mensaje de mensaje de mensaje no localizado al escribir caracteres no admitidos (como emojis) en el campo [!UICONTROL Objective] durante el proceso de creación de la actividad. Los mensajes de Toast ahora están correctamente localizados en todos los idiomas compatibles, lo que garantiza una experiencia coherente y accesible para los clientes globales. (TGT-52251)
* **No se localizó una cadena en el cuadro de diálogo [!UICONTROL Create Audience]**: Anteriormente, el mensaje &quot;Elija al menos una fecha de inicio o finalización para &#39;no se repite&#39;&quot; aparecía sin localizar en el modal [!UICONTROL Create Audience] al configurar atributos de intervalo de tiempo. La cadena está ahora correctamente localizada en todos los idiomas admitidos, lo que garantiza una experiencia coherente para los clientes globales en el flujo de trabajo [!UICONTROL Audiences]. (TGT-52253)
* **La información del objeto en el cuadro de diálogo [!UICONTROL Create Audience] no estaba localizada**: Anteriormente, cuando los clientes pasaban el ratón por encima de la información del objeto de error después de escribir caracteres no admitidos (como emojis) en el campo Nombre de audiencia, la información del objeto parecía no localizada. La información sobre herramientas ahora muestra mensajes correctamente localizados en todos los idiomas admitidos, lo que garantiza una experiencia coherente y accesible en el flujo de trabajo [!UICONTROL Audiences]. (TGT-52254)

+++

**[!DNL Recommendations]**

+++Ver detalles
* **No se puede deshabilitar [!UICONTROL Front Promotion] en la actividad activa**: se corrigió un problema en el cual los clientes no podían deshabilitar [!UICONTROL Front Promotion] en las actividades activas mediante la interfaz de usuario actualizada. Los cambios realizados en la sección de promoción durante el proceso de creación de actividad ahora se mantienen según lo esperado, lo que garantiza una configuración precisa de las actividades activas en [!UICONTROL Product Catalog Search]. (TGT-53231)
* **La edición de la recomendación de una experiencia duplicada afectó a la experiencia original**: Los clientes notificaron que, al duplicar una experiencia dentro de una actividad y modificar el diseño de recomendación o los criterios en el duplicado, esos cambios se aplicaron involuntariamente a la experiencia original.  Este problema impedía la creación de variaciones independientes y alteraba el comportamiento esperado en el proceso actualizado de creación de actividades. Ahora, las experiencias duplicadas se pueden editar de forma independiente sin afectar a la versión original. (TGT-53369)
* **No se puede ver la lista de productos al editar una colección o exclusión en la ficha [!UICONTROL Recommendations]**. Anteriormente, la lista de productos filtrada mediante reglas aplicadas no era visible en el modo de edición, lo que dificultaba a los clientes confirmar qué productos se incluían o excluían. La lista de productos ahora se muestra correctamente y se actualiza en tiempo real a medida que se modifican las reglas, lo que mejora la visibilidad y la facilidad de uso en la IU actualizada de [!DNL Recommendations]. (TGT-53481)
* **Se ha actualizado el diseño del cuadro de diálogo [!UICONTROL View Details] en la ficha [!UICONTROL Recommendations]**: anteriormente, el cuadro de diálogo [!UICONTROL View Details] no tenía una estructura clara, lo que dificultaba el acceso de los clientes a la información específica del artículo y relacionada con el inventario. El diseño se ha actualizado para incluir dos pestañas: una muestra los detalles del elemento seleccionado y la segunda muestra el inventario filtrado por las reglas actuales de la colección o exclusión. Esta mejora mejora mejora la claridad y la facilidad de uso de la interfaz de usuario [!DNL Recommendations] actualizada. (TGT-53503)
* **Los clientes no pudieron buscar grupos de informes en la lista desplegable [!UICONTROL Goals & Settings]**: Anteriormente, la lista desplegable de grupos de informes en la sección [!UICONTROL Goals & Settings] del proceso de creación de actividades no admitía la entrada de texto para la búsqueda, lo que dificultaba que los clientes con un gran número de grupos de informes localizaran el correcto. Se ha restaurado esta funcionalidad, disponible en la interfaz de usuario heredada. Los clientes ahora pueden escribir para buscar y seleccionar grupos de informes de forma más eficaz. (TGT-53514)
* **Los clientes no pueden descargar el CSV con criterios personalizados en la interfaz de usuario [!DNL Recommendations]**: Anteriormente, al hacer clic en el vínculo de descarga de los CSV con criterios personalizados en la ficha [!UICONTROL Recommendations], se devolvió un error 404 y no se pudo abrir en una nueva ficha. El vínculo de descarga ahora se abre en una nueva pestaña y proporciona correctamente el archivo CSV, lo que mejora la accesibilidad y la facilidad de uso para los clientes que administran criterios personalizados. (TGT-51966)
* **Al habilitar una promoción de [!UICONTROL Recommendations] sin datos de entrada, se desencadenó un mensaje de error genérico**: anteriormente, los clientes que habilitaban una promoción principal o secundaria en una actividad de Recommendationsations sin especificar los campos obligatorios encontraron un &quot;error de entrada no válido&quot; con el código `error.restapi.missingFields`. El sistema ahora proporciona un mensaje de error claro y procesable que indica qué campos faltan, lo que mejora la facilidad de uso y reduce la confusión durante el proceso de creación de actividades. (TGT-52616)
* Las miniaturas y las imágenes de **producto no se cargaban de manera consistente en[!UICONTROL Catalog Search]**: los clientes notificaron que las miniaturas de producto y las imágenes de tamaño completo en [!UICONTROL Catalog Search] faltaban o se rompían intermitentemente, especialmente después de navegar o modificar la visibilidad de la columna. Las miniaturas e imágenes ahora se cargan de forma fiable, independientemente de la configuración de columna o del comportamiento de navegación, lo que mejora la experiencia general en el flujo de trabajo [!UICONTROL Recommendations]. (TGT-52778)
* **No se puede crear [!UICONTROL Designs] y [!UICONTROL Criteria] en el entorno [!UICONTROL Stage]**: los clientes encontraron el error &quot;Entrada de usuario no válida&quot; al intentar crear [!UICONTROL Designs] o [!UICONTROL Criteria] en la ficha [!UICONTROL Recommendations] en el entorno [!UICONTROL Stage]. Los clientes ahora pueden crear correctamente [!UICONTROL Designs] y [!UICONTROL Criteria] sin errores en el entorno [!UICONTROL Stage]. (TGT-53205)
* **[!UICONTROL Promotions]no se eliminaron de [!UICONTROL Recommendations] actividades después de guardar**: los clientes informaron que las promociones agregadas a [!DNL Recommendation] actividades siguieron apareciendo incluso después de quitarse y guardarse. Este problema afectaba a los entornos de ensayo y producción y persistió en varios intentos de guardado. Las promociones ahora reflejan correctamente los cambios realizados durante la edición de la actividad en el proceso actualizado de creación de actividades. (TGT-53490)

+++

**[!UICONTROL Reports]**

+++Ver detalles
* **[!UICONTROL Automated Segments]mostró una audiencia nula en los informes de actividad**: Los clientes observaron que, al ver [!UICONTROL Automated Segments] en la sección [!UICONTROL Reports] de una actividad, el campo de audiencia parecía nulo, aunque se esperaban datos de segmento válidos. Este problema afectaba a la visibilidad de la segmentación de audiencia y la precisión de la creación de informes. [!UICONTROL Automated Segments] ahora muestra correctamente la información de audiencia asociada en los informes de actividad. (TGT-52793)
* **No se pudieron descargar los informes de actividad en formato CSV**: Los clientes que intentaban exportar los informes de actividad desde la ficha [!UICONTROL Reports] encontraron un error al seleccionar la opción de descarga CSV. Este problema afectaba tanto a los informes estándar como a las exportaciones de detalles de pedidos. Los informes ahora se descargan correctamente en formato CSV. (TGT-53464)

+++

**Aplicaciones de una sola página (SPA)**

+++Ver detalles
* **El cambio entre los modos [!UICONTROL Browse] y [!UICONTROL Design] restablece los estados de aplicación de una sola página (SPA) en el editor web**: Los clientes informaron de que cambiar entre los modos [!UICONTROL Browse] y [!UICONTROL Design] en el VEC provocaba que el editor web se recargara, restableciendo el estado de SPA e interrumpiendo el proceso de creación de actividades. El editor ahora conserva el estado de navegación de la SPA al cambiar de modo, lo que garantiza una experiencia de edición más fluida y coherente. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Ver detalles
* **Cambiar el nombre de una ubicación en una actividad [!UICONTROL Automated Personalization] (AP) o [!UICONTROL Multivariate Test] (MVT) no persistió después de ir al paso [!UICONTROL Targeting] y regresar.** Los clientes ahora pueden editar y guardar correctamente los nombres de las ubicaciones, y los cambios permanecerán visibles a lo largo del proceso de creación de actividades. (TGT-52367)
* **La interfaz de usuario del VEC heredado que se muestra en los inquilinos en el entorno [!UICONTROL Stage]**: se ha corregido un problema que se producía al acceder a ciertos inquilinos en el entorno [!UICONTROL Stage] y que se mostraba incorrectamente en la interfaz de usuario heredada en lugar del VEC actualizado. Este problema se podía reproducir en varias rutas de inicio de sesión y afectaba a la sección [!UICONTROL Activities]. La interfaz actualizada ahora se muestra correctamente para ambos inquilinos en el entorno [!UICONTROL Stage]. (TGT-52261)
* **Al seleccionar un color de fondo, la página se bloqueó en el VEC actualizado**:
Se ha corregido un problema en el cual al seleccionar un color de fondo del panel [!UICONTROL Style] en el VEC actualizado, la página se bloqueaba y se dejaba en blanco. Los errores de la consola indicaron un error al leer las propiedades de un elemento no definido, específicamente relacionado con `querySelector`. Los clientes ahora pueden seleccionar los colores de fondo de forma segura sin provocar un bloqueo. (TGT-53561)
* **No se pudieron guardar las actividades debido a un error de entrada de usuario no válido**: se corrigió un error al intentar guardar las actividades existentes en el VEC actualizado. El error solo aparecía durante las ediciones, no al crear nuevas actividades con la misma propiedad. El mensaje de error incluye:

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  Ahora, las actividades que utilizan la propiedad afectada se pueden guardar correctamente después de editarlas. (TGT-53507)

* **Las imágenes transparentes ya no incluían el parámetro &quot;fmt=png-alpha&quot; en el VEC actualizado**: Los clientes informaron que, al reemplazar imágenes en la IU actualizada, ya no se conservaban los fondos transparentes. Las direcciones URL de imagen generadas por el VEC actualizado omitieron el parámetro `fmt=png-alpha`, que anteriormente garantizaba la transparencia en la IU antigua. La interfaz de usuario actualizada ahora anexa correctamente el parámetro `fmt=png-alpha` para imágenes transparentes, restaurando el comportamiento de procesamiento esperado. (TGT-52615)
* **Los clientes no pudieron continuar a la sección de segmentación en las actividades AP sin agregar dos ubicaciones**: Los clientes que crearon actividades [!UICONTROL Automated Personalization] (AP) en la IU actualizada no pudieron continuar a la sección de segmentación a menos que se agregaran dos ubicaciones. Este comportamiento difería del de la IU anterior, en que una sola ubicación era suficiente. El problema bloqueaba la creación y el guardado de actividades para los clientes que preferían usar solo una ubicación. Los clientes ahora pueden continuar con la segmentación y guardar actividades AP con una sola ubicación, lo que restaura la funcionalidad esperada. (TGT-53426)
* **Ofertas de HTML duplicadas en el espacio de trabajo al cambiar de experiencia**: anteriormente, los clientes que insertaban ofertas de HTML en contenido duplicado experimentado en el espacio de trabajo después de cambiar de experiencia. Este problema también provocaba que el espacio de trabajo se volviera no desplazable, lo que afectaba a la facilidad de uso. Las ofertas de HTML ya no se duplican y el espacio de trabajo permanece desplazable al cambiar experiencias en el VEC actualizado. (TGT-53487)
* **La actualización manual de un selector CSS hizo que la pantalla del VEC se quedara en blanco**: Los clientes informaron que, mientras editaban una oferta en el VEC, la actualización manual del selector CSS activaba una pantalla en blanco, incluso cuando el selector era válido y estaba presente en la página. La pantalla del VEC ahora permanece estable cuando los selectores se actualizan manualmente durante el proceso de creación de la actividad. (TGT-53553)
* **Problema de truncamiento en el campo Fecha de inicio al seleccionar &quot;fecha y hora especificadas&quot; en[!UICONTROL Goals & Settings]**: los clientes experimentaron un problema de truncamiento en el campo [!DNL Start date] al elegir la opción de fecha y hora especificada en la sección de duración de la página [!UICONTROL Goals & Settings] durante la creación de la actividad. La fecha y la hora completas ahora se muestran correctamente en las configuraciones regionales admitidas. (TGT-47843)
* El icono **Filter desapareció al minimizar el explorador en el carril [!UICONTROL Manage Content]**: Los clientes notificaron que el icono de filtro en el carril [!UICONTROL Manage Content] del flujo de creación de actividades [!UICONTROL Automated Personalization] desapareció cuando se cambió el tamaño de la ventana del explorador o se minimizó. El icono de filtro ahora permanece visible y accesible independientemente del tamaño del explorador, lo que mejora la facilidad de uso en las resoluciones de pantalla. (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++Ver detalles
* **Los clientes restringidos a un solo espacio de trabajo podían ver actividades desde otros espacios de trabajo**: Los clientes con acceso limitado a un espacio de trabajo específico aún podían seleccionar [!UICONTROL All Workspaces] en la interfaz de usuario actualizada y ver actividades desde otros espacios de trabajo. Este comportamiento planteaba el riesgo de cambios no deseados en las actividades activas fuera del ámbito asignado. Las restricciones de Workspace ahora se aplican correctamente y los clientes solo pueden ver actividades en el espacio de trabajo asignado. (TGT-53101)
* **Los clientes podían ver actividades desde [!UICONTROL Default Workspace] sin acceso**: Los clientes podían ver actividades desde [!UICONTROL Default Workspace] a pesar de no tener acceso a él. Los permisos de Workspace ahora se aplican correctamente en la interfaz de usuario actualizada, lo que garantiza que los clientes solo vean las actividades asociadas con el espacio de trabajo asignado. (TGT-53297)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
