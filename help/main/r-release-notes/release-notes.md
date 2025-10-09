---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f0536e466d59fc4e3cccd61c25b7fe7f48f03954
workflow-type: tm+mt
source-wordcount: '4858'
ht-degree: 7%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.9.3 (30 de septiembre de 2025)

Esta versión incluye las siguientes mejoras y correcciones.

+++[!UICONTROL Audiences]

* **Las reglas de exclusión de audiencia se mostraban incorrectamente como inclusión en la interfaz de usuario de [!DNL Target].** audiencias configuradas con reglas de exclusión aparecieron como incluidas al editar la segmentación dentro de una actividad. Aunque la lógica de exclusión se aplicó correctamente durante la ejecución, la interfaz de usuario no reflejó la regla con precisión, omitiendo la etiqueta &quot;excluyendo&quot;. La interfaz de usuario [!DNL Target] ahora muestra correctamente las reglas de exclusión en la configuración de audiencia y en los flujos de trabajo de segmentación, lo que garantiza la claridad y coherencia en la configuración de la campaña. (TGT-53808)
* **La sección [!UICONTROL Targeting] no indica que se haya establecido una regla de audiencia para excluir.Las audiencias de** configuradas con lógica de exclusión se mostraban incorrectamente como inclusión en la sección [!UICONTROL Targeting] de la interfaz de usuario de la creación de actividades. Aunque el servidor aplicó correctamente la regla de exclusión, la interfaz de usuario no la representó visualmente, omitiendo la etiqueta &quot;Excluir&quot; y causando confusión durante la configuración de la campaña. La sección [!UICONTROL Targeting] ahora muestra claramente las reglas de exclusión, lo que garantiza la coherencia entre la configuración de la audiencia y la visualización de la segmentación. (TGT-53809)

+++

+++Localización

* **Se ha corregido una incoherencia terminológica en la traducción al chino simplificado de &quot;Vista de detalles completa&quot;.**
Anteriormente, el término &quot;Detalles&quot; se traducía incorrectamente como &quot;详情&quot; en la configuración regional del chino simplificado (zh_CN), lo que infringía las directrices terminológicas establecidas. Esto se ha corregido a &quot;详细信息&quot; para garantizar la coherencia con la base terminológica. (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **Los cuadros de recomendación eran difíciles de localizar y seleccionar en el VEC.** Después de agregar una oferta de recomendaciones en (VEC), al hacer clic en la modificación en el panel izquierdo, no se resaltó ni se desplazó al cuadro de recomendaciones correspondiente de la página. Esto dificultaba la localización y edición de la oferta, especialmente cuando se ocultaba bajo selectores o se diseñaba mínimamente. Al hacer clic en una modificación de recomendación, ahora se resalta y se desplaza correctamente al elemento asociado, lo que mejora la facilidad de uso y la eficacia de la edición en el proceso actualizado de creación de actividades. (TGT-52571)
* **Los selectores de recomendación se reescribieron incorrectamente después de guardar una actividad.** Al agregar una recomendación a un elemento del VEC, el selector era inicialmente correcto, pero después de guardar y volver a abrir la actividad, se cambió a un selector genérico. Los intentos de restaurar manualmente el selector original dieron como resultado errores de validación. Los selectores de recomendación ahora persisten con precisión después de guardar, lo que garantiza un direccionamiento y una editabilidad fiables en el proceso de creación de actividades actualizado. (TGT-53709)
* **No se pudo editar el contenido de criterios al modificar una actividad existente.** Al editar una actividad, la sección de contenido [!UICONTROL Criteria] parecía deshabilitada, con botones atenuados y sin respuesta. Este problema se resolvió asegurándose de que las configuraciones de [!UICONTROL Criteria] se puedan editar completamente durante las actualizaciones de la actividad. Los clientes ahora pueden modificar el contenido de [!UICONTROL Criteria] sin necesidad de cambiar de selección ni utilizar soluciones alternativas, lo que mejora la flexibilidad y la facilidad de uso en el proceso actualizado de creación de actividades. (TGT-53812)
* **No se pudieron editar los criterios dentro de una actividad.** Las opciones [!UICONTROL Edit Criteria] y [!UICONTROL Remove Criteria] se deshabilitaron al acceder a criterios desde una actividad. Sin embargo, los mismos criterios se pudieron editar correctamente mediante la ficha [!UICONTROL Recommendations]. Ahora, los criterios se pueden editar completamente tanto desde el flujo de trabajo de edición de actividades como desde la pestaña [!UICONTROL Recommendations], lo que garantiza una experiencia de edición uniforme y eficaz. (TGT-53814)

+++

+++[!UICONTROL Reports]

* **La generación de ofertas ad hoc en actividades de A[!UICONTROL utomated Personalization] ha causado incoherencias en los informes.** Al usar la característica Generar ofertas ad-hoc en actividades [!UICONTROL Automated Personalization] (AP) se generaron informes inexactos. Específicamente, los ID de oferta se reutilizaban en todas las ubicaciones, lo que provocaba que los datos de los informes se atribuyeran erróneamente o se sobrescribieran. Las ofertas específicas ahora se generan con identificadores distintos por ubicación, lo que garantiza un seguimiento y unos informes precisos en todas las experiencias configuradas. (TGT-53757)
* **No se pudieron cargar los informes de actividad debido a un error de JavaScript.** clientes encontraron el mensaje &quot;Se produjo un error&quot; al acceder a la ficha [!UICONTROL Reports] para determinadas actividades. El error se debe a una excepción de JavaScript: no se pueden leer las propiedades de undefined (reading &#39;indexOf&#39;), desencadenadas durante la llamada de GraphQL `getAnalyticsReportSummary`. Ahora los informes se cargan correctamente y se ha mejorado el control de errores para evitar errores similares en el flujo de trabajo actualizado de creación de actividades. (TGT-53797)
* **Los informes se bloquearon después de interactuar con la barra de desplazamiento.** Al hacer clic en la barra de desplazamiento de la ficha [!UICONTROL Reports], la página se bloqueó y se produjo un error de JavaScript:
  Los informes de `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` ahora se cargan y se desplazan correctamente sin provocar errores ni bloqueos. (TGT-53828)
* **Los informes no mostraron la métrica principal.**: la métrica principal, configurada como métrica de conversión mediante un mbox, no aparecía en los informes de actividad. La búsqueda por nombre de métrica o de mbox no arrojó resultados, lo que impidió ver los datos clave de rendimiento. Las métricas principales ahora aparecen correctamente en la pestaña [!UICONTROL Reports], lo que garantiza un seguimiento y un análisis precisos del rendimiento de la campaña. (TGT-53773)
* **La ficha [!UICONTROL Reports] de la interfaz de usuario actualizada se bloqueó al interactuar con la barra de desplazamiento horizontal.** La vista [!UICONTROL Reports] se bloqueó intermitentemente con el error &quot;Se produjo un error&quot; al usar la barra de desplazamiento horizontal para acceder a las métricas fuera de la vista. La barra de desplazamiento ahora funciona de forma fiable, lo que permite a los clientes ver y analizar todas las métricas sin necesidad de soluciones alternativas, como reducir o utilizar la función de desplazamiento con desplazamiento. (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **Al hacer clic en las rutas de exploración en el VEC, no se mostraba de manera consistente el menú de edición.**
Al seleccionar elementos de HTML a través de las rutas de exploración del (VEC), el menú de edición no aparecía o desaparecía rápidamente de forma intermitente, lo que hacía que la selección de elementos no fuera fiable. El menú de edición ahora se muestra de forma coherente al navegar mediante rutas de exploración, lo que mejora el flujo de trabajo de selección de elementos en el proceso actualizado de creación de actividades. (TGT-52873)
* **El menú contextual no aparece intermitentemente en el VEC.** El menú contextual en la interfaz de usuario actualizada del VEC no aparecía de manera consistente al hacer clic en elementos, lo que dificultaba el acceso a las opciones de edición. El menú contextual ahora se muestra de forma fiable tras la selección de elementos, lo que mejora el flujo de trabajo de edición y la facilidad de uso general en el proceso de creación de actividades actualizado. (TGT-53015)
* **No se ha podido mostrar el menú contextual de ciertos elementos del VEC.** El menú contextual no se mostraba al seleccionar elementos específicos en el VEC actualizado, lo que dificultaba la aplicación de modificaciones. El menú contextual ahora se muestra de forma coherente para todos los elementos admitidos, lo que mejora la fiabilidad y facilidad de uso de la experiencia de edición en el flujo de trabajo de creación de actividades actualizado. (TGT-53248)
* **El menú contextual desapareció en el primer clic al usar rutas de exploración en el VEC.** Al seleccionar un elemento principal a través de las rutas de exploración del VEC, el menú contextual aparecía brevemente y luego desaparecía, lo que dificultaba el acceso a las opciones de edición. El menú contextual ahora permanece visible y funcional al navegar por los elementos a través de las rutas, lo que mejora la fiabilidad del flujo de trabajo de selección de elementos en el proceso actualizado de creación de actividades. (TGT-53424)
* **El menú contextual no aparecía para los elementos de nivel superior del VEC.** La selección de elementos de nivel superior, como las etiquetas `<div>` o `<main>`, a través de las rutas de exploración del VEC no almacenó en déclencheur el menú contextual, lo que impidió realizar más acciones de edición. El menú contextual ahora aparece de forma coherente para todos los elementos admitidos, incluidos los contenedores de nivel superior, lo que mejora la flexibilidad y facilidad de uso del flujo de trabajo de creación de actividades. (TGT-53770)
* **Los elementos de una página específica no se podían editar en el VEC.** Algunos elementos de la página no se pudieron seleccionar o editar en el VEC actualizado. Este problema se aisló en esa página y no afectó a otras páginas dentro de la misma cuenta. Todos los elementos de la página ahora se pueden seleccionar y editar según lo esperado, lo que restaura la funcionalidad completa en el flujo de trabajo de creación de actividades. (TGT-53353)
* **Se ha mejorado el flujo de trabajo al ver elementos secundarios durante la selección de elementos en el VEC.** Para mejorar la facilidad de uso y la precisión durante la creación de la actividad, el VEC ahora muestra elementos secundarios al pasar el ratón por encima o seleccionar un elemento HTML principal. Esta mejora permite a los clientes comprender mejor la estructura de la página y realizar modificaciones más precisas, lo que optimiza el flujo de trabajo de edición en la IU actualizada. (TGT-53416)
* **No se pudieron editar los elementos de las actividades existentes mediante la barra de modificación.** Al editar las actividades creadas anteriormente, la barra de modificación no se pudo activar para ciertos elementos de la página, lo que impidió realizar actualizaciones. Este problema se observaba principalmente en las actividades modificadas y era difícil de reproducir en las recién creadas. La barra de modificación ahora muestra y permite editar de forma coherente todos los elementos admitidos, lo que mejora la fiabilidad y la facilidad de uso en el flujo de trabajo actualizado de creación de actividades. (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **Al clonar una actividad en un área de trabajo diferente, se produjo el error &quot;Entrada de usuario no válida&quot;.** Al intentar clonar una actividad de un espacio de trabajo a otro, se produjo un error: &quot;InvalidProperty.Json - Unknown property name &#39;content&#39;&quot;.&quot; Este problema se debía a una administración incorrecta de los metadatos de la actividad durante el proceso de clonación. Ahora, las actividades se pueden clonar correctamente en todos los espacios de trabajo sin activar errores de validación, lo que garantiza flujos de trabajo de implementación de actividades más suaves. (TGT-53731 y TGT-53736)

+++

## [!DNL Target Standard/Premium] 25.9.2 (22 de septiembre de 2025)

En esta versión se incluyen las siguientes correcciones y mejoras:

**[!UICONTROL Audiences]**

+++Ver detalles
* **Se ha corregido un problema por el cual las actividades no se podían copiar debido a ID de audiencia no válidos.** clientes que intentaban copiar actividades en el proceso de creación de actividades actualizado encontraron un error causado por ID de audiencia no válidos (por ejemplo, -1752722444307). Este problema de validación de back-end impedía la duplicación de actividades dentro del mismo espacio de trabajo. Este problema se ha resuelto y las actividades ahora se pueden copiar correctamente sin errores relacionados con la audiencia. (TGT-53717)
* **Se ha corregido un problema por el que aparecían errores de entrada de usuarios no válidos para audiencias solo de actividad en las actividades [!UICONTROL Automated Personalization] del modal [!UICONTROL Manage Content].** clientes encontraron errores de entrada de usuario no válidos al configurar audiencias solo de actividad en el modal [!UICONTROL  Manage Content] para actividades AP. Este problema se producía a pesar de que las audiencias se habían utilizado correctamente anteriormente. Las configuraciones de audiencia combinadas ahora se guardan correctamente sin activar errores de validación. (TGT-53749)

+++

**Documentación**

+++Ver detalles
* **Se han movido páginas de documentación de Web SDK específicas de Target al repositorio de Adobe Target.** Como parte de la reestructuración de la documentación de Web SDK, el contenido específico de [!DNL Target] se ha migrado de los documentos generales de Web SDK a [!DNL Adobe Target] [Guía para desarrolladores](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Este cambio mejora la capacidad de detección de contenido y garantiza que el equipo de productos adecuado mantenga una guía específica de la solución. (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++Ver detalles
* La opción **Decisión de oferta ahora está visible de forma consistente durante la creación de la actividad inicial.** ha resuelto un problema en la interfaz de usuario actualizada en el que la opción [!UICONTROL Offer Decision] no aparecía durante el flujo de creación por primera vez para actividades A/B, especialmente cuando se accedía en modo incógnito en inquilinos con Decisiones de oferta habilitadas. La opción solo apareció después de navegar al paso [!UICONTROL Targeting] y regresar a [!UICONTROL Experiences]. Esta corrección garantiza que la opción [!UICONTROL Offer Decision] esté disponible inmediatamente durante la configuración inicial, lo que mejora la facilidad de uso y reduce las confusiones. (TGT-51888)

+++

**[!UICONTROL Offers]**

+++Ver detalles
* **Se ha corregido un problema por el cual las ofertas de redireccionamiento no incluían `redirectOptions` en la carga útil al `includeContent=true`.A los clientes de** que recuperaban ofertas de redireccionamiento con `includeContent=true ` les faltaba el campo `redirectOptions` en la carga de respuesta. Esta incoherencia afectaba a los flujos de trabajo, como la copia de ofertas y la creación de actividades. Las ofertas de redireccionamiento ahora incluyen correctamente `redirectOptions` cuando se solicita contenido. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Ver detalles
* **Rastreo de clics restaurado para [!UICONTROL Recommendations] actividades creadas en la interfaz de usuario actualizada.** ha resuelto un problema en el cual [!UICONTROL Recommendations] actividades creadas en la interfaz de usuario actualizada no registraban el rastreo de clics, lo que arrojaba cero conversiones notificadas. Las actividades creadas en la IU heredada rastreaban correctamente los clics y notificaban las conversiones según lo esperado. Esta corrección garantiza que las actividades de Recommendations creadas en la interfaz de usuario actualizada ahora incluyan los atributos de seguimiento correctos, restaurando la creación de informes de conversión y la alineación con las métricas de A4T. (TGT-53287)
* **Rastreo de clics restaurado para actividades de Recommendations.** ha resuelto un problema en el cual [!UICONTROL Recommendations] actividades creadas en la interfaz de usuario actualizada no registraban el rastreo de clics, lo que arrojaba cero conversiones notificadas. La interfaz de usuario heredada aplicó correctamente un identificador de seguimiento (`at-track-click`) al contenido de [!UICONTROL Recommendations], mientras que la interfaz de usuario actualizada insertó por error un marcador de posición (`__recsClickTrackIdPlaceholder__`), lo que impide el seguimiento del servidor. Esta corrección garantiza que el contenido de [!DNL Recommendations] ahora incluya el ID de seguimiento correcto, con lo que se restauran los informes de conversión y la alineación con las métricas de A4T. (TGT-53496)
* **Se ha resuelto el bloqueo del editor de colecciones en la IU actualizada.** Se ha corregido un problema en la IU actualizada de [!UICONTROL Visual Experience Composer] (VEC) por el cual al abrir una colección desde el panel Editor, la página se bloqueaba con un TypeError: No se pueden leer las propiedades de undefined (leer &quot;customLocale&quot;). Este error se produjo en varios tipos de actividades, incluidas [!UICONTROL Recommendations] y pruebas A/B. (TGT-53703)
* **Opción para eliminar la colección seleccionada restaurada en el VEC.** Se ha corregido un problema en el VEC en el cual los usuarios solo podían reemplazar una colección seleccionada en una actividad [!UICONTROL Recommendations], pero no podían eliminarla por completo. Esta limitación bloqueaba los casos de uso que requerían una eliminación limpia de la colección sin sustitución. Esta corrección introduce una opción clara para eliminar la colección seleccionada, lo que permite una mayor flexibilidad en la configuración de la actividad y su alineación con el comportamiento de la IU heredada. (TGT-53652)
* **Las colecciones de criterios personalizados ahora se muestran correctamente en la interfaz de usuario de [!UICONTROL Recommendations].** Se ha corregido un problema en la interfaz de Recommendations por el cual las colecciones creadas con criterios personalizados no mostraban los resultados de los productos. Aunque las colecciones basadas en atributos estándar funcionaban según lo esperado, las que utilizaban filtros personalizados devolvían &quot;No se encontraron resultados&quot; a pesar de las coincidencias de catálogo válidas. Esta corrección garantiza que las colecciones que utilizan atributos personalizados ahora se rellenen correctamente en la pestaña [!UICONTROL Product], lo que restaura la funcionalidad completa de los flujos de trabajo de recomendaciones personalizadas. (TGT-53653)
* **Se ha corregido un problema por el cual las colecciones no mostraban productos al abrir por primera vez la página [!UICONTROL Products].** clientes que acceden a colecciones en la sección [!UICONTROL Recommendations] experimentaron resultados de productos vacíos al abrir por primera vez la página [!UICONTROL Products]. Este problema se debía a un error del servidor en la consulta de GraphQL, que no cargaba datos de productos para colecciones con criterios personalizados. El problema se ha resuelto y los productos ahora aparecen correctamente sin requerir el cambio de entorno. (TGT-53694)
* **Se ha corregido un problema que impedía eliminar colecciones en las actividades [!UICONTROL Recommendations] basadas en formularios.** Los clientes que crearon [!UICONTROL Recommendations] actividades usando [!UICONTROL Form-Based Experience Composer] no pudieron anular la selección de una colección seleccionada anteriormente. La interfaz de usuario requería que se seleccionara una colección antes de guardar, lo que impedía que los usuarios volvieran a &quot;Todas las colecciones&quot;. Este comportamiento se ha actualizado para que coincida con la funcionalidad del VEC, lo que permite a los clientes guardar sin una colección seleccionada y establecer el valor predeterminado de &quot;Todas las colecciones&quot; según lo esperado. (TGT-53708)
* **Se corrigió un problema en el cual las promociones no se podían establecer por atributo debido a que faltaban valores de colección o de reglas de filtrado.** clientes que configuraban promociones por atributo en el proceso de creación de actividad encontraron un error que indicaba que a una promoción le faltaba un ID de colección o valores de reglas de filtrado. Este problema de validación bloqueaba la progresión incluso cuando la configuración parecía completa. Las promociones ahora se pueden guardar correctamente cuando se configuran mediante el atributo. (TGT-53750)
* **Se ha corregido un problema por el cual las actividades no se podían guardar debido a nombres de experiencia duplicados.** clientes encontraron un error de entrada de datos no válido al guardar actividades que incluían combinaciones específicas de criterios y diseños. El error se activó por nombres de experiencia duplicados, incluso cuando la configuración parecía válida. Ahora, las actividades con configuraciones distintas se pueden guardar sin conflictos de nombres. (TGT-53805)
* **Se ha corregido un problema por el que la validación permanecía inválida para las promociones configuradas por el atributo.** clientes han encontrado errores de validación persistentes al configurar promociones por atributo en el proceso de creación de actividades, incluso cuando todos los campos obligatorios se han rellenado correctamente. Este problema se debió a una lógica de validación incorrecta en el flujo de trabajo [!UICONTROL Recommendations]. Las promociones basadas en atributos ahora se validan y guardan según lo esperado. (TGT-53811)
* **Se ha corregido un problema que causaba que, al aplicar una promoción a una actividad de [!UICONTROL Recommendations] activa, se activara un error.** clientes encontraron el error &quot;A una promoción le falta un ID de colección o valores de regla de filtrado&quot; al intentar aplicar una promoción principal a una actividad de [!UICONTROL Recommendations] activa, incluso después de proporcionar detalles de configuración válidos. Las promociones ahora se pueden aplicar correctamente a las actividades activas sin activar errores de validación, lo que garantiza una experiencia más fluida en la IU actualizada de creación de actividades. (TGT-53738)
* **Se ha corregido un problema por el cual los productos no eran visibles en colecciones dentro de la interfaz de usuario de [!UICONTROL Recommendations].** clientes de un solo inquilino informaron que no se pudieron cargar las listas de productos al ver ciertas colecciones en la sección [!UICONTROL Recommendations] de la nueva interfaz de usuario. El problema se resolvió temporalmente cambiando de entorno, pero esta solución resultó en una mala experiencia de usuario. Las entidades de producto ahora se cargan de forma coherente sin requerir el cambio de entorno. (TGT-53783)
* **Se ha corregido un problema por el cual los criterios y diseños no se mostraban en una línea de la interfaz de usuario para la creación de actividades.** Anteriormente, los criterios y diseños del proceso de creación de actividades se mostraban en un formato comprimido, lo que dificultaba a los clientes la visualización y administración de elementos individuales. Cada criterio y diseño ahora aparecen en su propia línea, lo que mejora la legibilidad y la facilidad de uso en la interfaz de usuario actualizada. (TGT-53818)

+++

**Informes**

+++Ver detalles
* La métrica **[!UICONTROL Total Revenue]ahora se incluye en las exportaciones de CSV desde informes de actividad.** ha resuelto un problema en la interfaz de usuario actualizada [!UICONTROL Overview] en el cual los ingresos totales se mostraban correctamente en la vista del informe de actividad, pero no aparecían en la exportación del CSV, y se mostraban como 0 $. Esta discrepancia impedía a los usuarios confiar en los datos exportados para el análisis y la creación de informes sin conexión. (TGT-53325)
* La métrica **[!UICONTROL Total Sales]ahora se incluye en las exportaciones de CSV desde informes de actividad.** ha resuelto un problema en la interfaz de usuario actualizada en el cual la métrica [!UICONTROL Total Sales] aparecía correctamente en la vista del informe de actividad, pero no aparecía en la exportación de CSV. Esta discrepancia impedía a los usuarios acceder a los datos de rendimiento completos en los informes descargados. Esta corrección garantiza que los valores de [!UICONTROL Total Sales] ahora se incluyan con precisión en las exportaciones de CSV, lo que restaura la coherencia entre la creación de informes en la aplicación y el análisis sin conexión. (TGT-53330)
* **Mensajes de error mejorados para [!UICONTROL Graph View] cuando las métricas no están habilitadas.** Se ha corregido un problema en el VEC por el cual [!UICONTROL Graph View] mostraba un mensaje genérico &quot;Se produjo un error&quot; cuando una métrica solicitada no estaba habilitada en el grupo de informes [!DNL Analytics] asociado. Este problema se desencadenó por un error de `not_enabled_metric` en la respuesta del servidor de GraphQL. Esta corrección reemplaza el error impreciso con un mensaje más informativo que ayuda a los usuarios a identificar los problemas de configuración en [!DNL Analytics], lo que reduce la confusión y las escalaciones de soporte innecesarias. (TGT-53577)
* **Se ha solucionado un problema por el que la duración del informe superaba el límite admitido de 90 días.** Los clientes que usan el filtro &quot;[!UICONTROL Last X Days]&quot; en la sección [!UICONTROL Reports] pudieron seleccionar duraciones superiores a 90 días, lo que podría provocar problemas de rendimiento y datos incompletos. El filtro se ha actualizado para aplicar un intervalo máximo de 90 días, lo que garantiza unos informes coherentes y fiables. (TGT-53795)
* **Se ha corregido un problema por el cual los informes CSV de rendimiento se generaban usando el entorno predeterminado en lugar del seleccionado.** Anteriormente, cuando los clientes cambiaban el entorno en la configuración del informe y generaban un informe de rendimiento, el CSV resultante contenía datos del entorno predeterminado en lugar del seleccionado.  La interfaz de usuario ahora pasa correctamente el parámetro `environmentId`, asegurándose de que el informe refleje el entorno elegido. Además, se ha mejorado la gestión de errores. Si se producen errores de GraphQL durante la generación de CSV, la interfaz de usuario muestra ahora un mensaje de error claro en lugar de producir un archivo CSV vacío. (TGT-53064)
* **Se ha corregido un problema por el cual los informes de Analytics for Target (A4T) no mostraban datos en [!UICONTROL Graph View].** clientes que usan [!DNL Target] con integración de A4T encontraron el error &quot;Se produjo un error&quot; al cambiar a la vista de gráfico en la pestaña Informes de las actividades de prueba A/B. Aunque [!UICONTROL Table View] se cargó correctamente, [!UICONTROL Graph View] no pudo procesar las tendencias de las métricas en el intervalo de tiempo seleccionado. [!UICONTROL Graph View] ahora muestra los datos de rendimiento según lo esperado para todas las métricas admitidas, lo que mejora la visibilidad y la precisión de los informes en la interfaz de usuario actualizada. (TGT-53573)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* Los metadatos de **elemento ahora están visibles al pasar el ratón por encima en el menú de ruta de exploración.** mejoró el menú de ruta de exploración en el VEC para mostrar detalles de elementos adicionales como ID, clase y nombre al pasar el ratón por encima de un elemento. Esta mejora ayuda a los usuarios a identificar y diferenciar los elementos con mayor facilidad durante la configuración de la actividad. (TGT-53409)
* **El desplazamiento de ruta de exploración ahora resalta el elemento correspondiente del VEC.** mejoró [!UICONTROL Visual Experience Composer] para resaltar el elemento correspondiente en el editor al pasar el ratón por encima de los elementos del menú de ruta de exploración. También se muestra el tipo de elemento, como contenedor, texto en negrita o botón. Este comportamiento se aplica a los elementos del mismo nivel y excluye los tipos no compatibles como SVG, según la lista de validación. (TGT-53411)
* **Alerta de cambios no guardados restaurada en flujos de trabajo de modificación de VEC.** Se ha corregido un problema en el VEC por el cual los usuarios ya no recibían notificaciones sobre cambios no guardados en las modificaciones de código personalizado. A diferencia de la IU heredada, la nueva experiencia carecía de indicadores al salir o cerrar el editor de personalización, lo que provocaba una pérdida accidental de progreso. Esta corrección restaura las alertas de todos los tipos de modificación, incluido el código personalizado, y garantiza que los usuarios reciban una advertencia antes de salir sin guardar. (TGT-53435).
* **Los cambios en el código personalizado ahora persisten durante la actualización de la página en el VEC.** Se ha corregido un problema en el VEC por el cual las modificaciones de código personalizado se perdían durante las actualizaciones del sitio web. Este problema se producía en páginas con varias recargas, lo que provocaba que el editor se restableciera y revertiera los cambios no guardados. La corrección garantiza que las ediciones de código personalizado permanezcan intactas incluso si la página se vuelve a cargar durante la edición, lo que evita la pérdida accidental del progreso. (TTGT-53501)
* **Problema de inicio de sesión resuelto para el acceso al sitio dentro del VEC.** Se ha corregido un problema en el cual los usuarios no podían iniciar sesión en su sitio al acceder a él a través del VEC. El flujo de inicio de sesión redirigía repetidamente a los usuarios a la página de inicio de sesión, lo que impedía la configuración y previsualización de la actividad. Esta corrección garantiza que el VEC ya no interfiera con el comportamiento de inicio de sesión, restaurando el acceso esperado para los usuarios autenticados. (TGT-53524)
* **Problema de duplicación de cookies resuelto en la extensión VEC Helper.** Se ha corregido un problema en el cual la extensión [!UICONTROL Adobe Experience Cloud Visual Editing Helper] duplicaba la cookie `at_qa_mode` durante el control de calidad mediante vínculos de vista previa. Al cambiar manualmente los índices de vista previa, se creaban varias cookies con valores en conflicto entre dominios, lo que impedía que los probadores cambiaran de variantes de forma fiable. Este comportamiento se observó incluso fuera de la interfaz de usuario de Target y afectó tanto a las cuentas internas como a las de cliente. Esta corrección garantiza una administración coherente de las cookies al evitar entradas duplicadas y alinear el ámbito del dominio, lo que permite un cambio de variante sin problemas sin requerir la limpieza manual de las cookies. (TGT-53579)
* **Se corrigió un problema en el cual al hacer clic en elementos en una página de inicio determinada se producían pérdidas de memoria.** clientes que crean actividades en esta página de inicio experimentaron pérdidas de memoria al interactuar con elementos de página. El problema estaba relacionado con las advertencias excesivas de la consola y el aumento del uso de memoria en los subfotogramas, especialmente en relación con los atributos de srcset mal formados. El uso de memoria ahora permanece estable durante la interacción. (TGT-53761)
* **Se corrigió un problema en el cual el VEC se bloqueaba y mostraba una pantalla en blanco al cargar ciertas actividades.** clientes de un inquilino específico informaron que el editor no pudo cargar actividades específicas. El VEC permaneció atascado en &quot;Aplicación de modificaciones iniciales&quot; antes de bloquearse y mostrar una pantalla en blanco. El VEC ahora carga las actividades afectadas sin errores en el proceso actualizado de creación de actividades. (TGT-52932)
* **Se ha corregido un problema por el que el carril [!UICONTROL Manage Content] de las actividades [!UICONTROL Automated Personalization] mostraba etiquetas de ubicación incoherentes.** Los clientes notificaron que el carril [!UICONTROL Manage Content] mostraba números de ubicación no coincidentes en las fichas [!UICONTROL Experiences] y [!UICONTROL Offers]. (por ejemplo, Ubicación 2 y Ubicación 4 en Experiencias y Ubicación 1 y Ubicación 2 en Oferta) incluso cuando solo se configuraron dos ubicaciones. Las etiquetas de ubicación ahora son coherentes y se asignan con precisión a las modificaciones, lo que mejora la claridad y la facilidad de uso en el proceso de creación de actividades. (TGT-52934)
* **Se corrigió un problema en el cual las modificaciones en el VEC se perdían después de guardar.** Clientes informaron que después de guardar una modificación en el VEC, la página se actualizaría y revertiría el cambio a su versión anterior. Este problema provocaba que se perdieran las actualizaciones más recientes a menos que toda la actividad se guardara inmediatamente. Las modificaciones ahora persisten correctamente después de guardar y el editor ya no revierte los cambios inesperadamente, lo que garantiza una experiencia fiable en el flujo de trabajo de creación de actividades. (TGT-53500)
* **Se ha mejorado la selección de elementos en el VEC al mostrar el tipo de elemento al pasar el ratón por encima y la selección.** Para mejorar la capacidad de uso durante la creación de la actividad, el VEC ahora decora los elementos de HTML con su tipo al pasar el ratón por encima o seleccionarlos. Esta mejora ayuda a los clientes a identificar y seleccionar los elementos correctos con mayor facilidad. Los elementos seleccionados se resaltan con un color distinto y los elementos activados se destacan en azul. También se muestra el tipo de elemento, lo que proporciona un contexto más claro durante la edición. (TGT-53502)

+++

## Actualizaciones del flujo de datos (19 de septiembre de 2025)

La combinación de ID de flujo de datos y zona protegida debe ser única para [!DNL Adobe Target] conexiones de destino.

Se ha actualizado la lógica de validación de [!DNL Target] conexiones de destino para exigir que la combinación del ID de secuencia de datos y el nombre de la zona protegida sea única dentro de una organización de IMS. Esto significa que:

* El mismo par ID + nombre de zona protegida de secuencia de datos no se puede reutilizar en varias conexiones de destino [!DNL Target].
* El mismo ID de flujo de datos solo se puede utilizar para conexiones diferentes si están configuradas en entornos limitados diferentes.
* Esta regla se aplica a todas las selecciones de flujos de datos, incluso cuando se selecciona &quot;Ninguno&quot;.

Esta actualización garantiza una configuración coherente y evita conflictos entre entornos de varias zonas protegidas. Para obtener más información, consulte [Conexión de Adobe Target](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} en la guía *Destinos de Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 de septiembre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Experience Fragments]**

+++Ver detalles
* **Se mejoró la atribución de usuarios para [!UICONTROL AEM Experience Fragment] ofertas.** ha resuelto un problema en el VEC en el cual el campo &quot;[!UICONTROL Last updated]&quot; para [!UICONTROL AEM Experience Fragment] (XF) ofertas mostraba incorrectamente un ID de código en lugar del nombre de usuario. Esta discrepancia se producía durante la selección de la oferta en la interfaz de usuario actualizada, lo que crea incoherencia con la interfaz de usuario heredada y las ofertas de HTML, que muestran correctamente el nombre del último editor. Esta corrección garantiza una atribución de usuario coherente entre los tipos de oferta, lo que mejora la transparencia y la alineación con el comportamiento esperado. (TGT-52880 y TGT-52898)

+++

**Offer Decisioning**

+++Ver detalles
* **Error de decisión de oferta resuelto para ofertas ODE.** ha resuelto un problema en el cual las ofertas del Motor de decisión de ofertas (ODE) insertadas a través de [!DNL Target] devolvían un error 400 debido a la falta de metadatos de formato. El mensaje de error indicaba que el tipo MIME era nulo, lo que impedía el procesamiento correcto de las decisiones de oferta. Esta corrección garantiza la administración adecuada de los metadatos de la oferta, restaura la funcionalidad para la entrega de contenido personalizado y permite la ejecución ininterrumpida de campañas de marketing. (TGT-53635)
* **Problema de procesamiento de ofertas de ODS resuelto.** ha resuelto un problema en el cual las ofertas [!DNL Offer Decision Service] (ODS) creadas mediante [!DNL Adobe Journey Optimizer] (AJO) no se representaban cuando las actividades se creaban mediante el VEC en la interfaz de usuario actualizada. La misma configuración funcionaba correctamente en la interfaz de usuario heredada, lo que producía confusión y bloqueaba la ejecución de campañas. Esta corrección garantiza una entrega de ofertas coherente en ambas versiones de la interfaz de usuario, lo que restaura el comportamiento esperado para la personalización basada en AJO.

+++

**Informes**

+++Ver detalles
* **Opción de descarga restaurada en la sección de informes de la IU actualizada de Información general de informes.** ha resuelto un problema en la nueva interfaz de usuario de información general en el que el botón [!UICONTROL Download] no aparecía en la sección Informes, lo que impedía a los usuarios exportar puntuaciones de importancia de atributos. Esta actualización restaura la funcionalidad completa de exportación, lo que permite un acceso optimizado a los datos descargables para su análisis y sistema de informes. (TGT-53222)
* Botón **[!UICONTROL Download full CSV report]restaurado en la vista [!UICONTROL Important attributes].** ha resuelto un problema en la interfaz de usuario de creación de actividades actualizada en el que faltaba el botón [!UICONTROL Download full CSV report] en la sección [!UICONTROL Important Attributes] de la vista Informes. Esta corrección restaura el acceso a las perspectivas descargables, lo que garantiza una funcionalidad coherente en las IU actualizadas y heredadas. (TGT-53238)
* **Problemas resueltos de la interfaz de usuario que afectan a la creación de informes de [!UICONTROL Auto Target] en la IU de descripción general actualizada.** Se han corregido varios problemas de interfaz de usuario en la interfaz de información general actualizada que afectaban a los informes de actividad [!UICONTROL Auto Target]. Estas correcciones incluyen:

   * Faltan métricas de alza y confianza en los informes de resumen
   * Indicador de color incorrecto para la casilla de verificación &quot;modelos creados&quot;
   * Informe de gráfico no funcional a pesar de la variación de datos en [!DNL Analytics]
   * Falta el vínculo de descarga para los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes]
   * Visualización del informe [!UICONTROL Automated Segments] interrumpida

  Estas correcciones restauran el comportamiento esperado de los informes y mejoran la visibilidad del rendimiento de [!UICONTROL Auto Target] en la interfaz de usuario actualizada. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Ver detalles
* **Validación de formulario corregida para las condiciones de presencia de parámetros en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual al seleccionar &quot;[!UICONTROL Custom mbox parameter value is present]&quot; o &quot;[!UICONTROL Parameter is present]&quot; se requería incorrectamente que los clientes especificaran un valor. Este comportamiento entra en conflicto con la lógica deseada, que simplemente comprueba la existencia de un parámetro independientemente de su valor. La corrección alinea la validación del formulario con el comportamiento esperado, lo que permite una configuración de la actividad más suave y admite la adopción completa de la IU actualizada. (TGT-53638)
* **Se ha corregido la lógica del formulario para las reglas de presencia de parámetros en la entrega de páginas.&quot;** ha resuelto un problema en la interfaz de usuario actualizada que hacía que, al seleccionar reglas de entrega de páginas como &quot;[!UICONTROL Parameter is present]&quot;, &quot;[!UICONTROL Parameter is not present]&quot;, &quot;[!UICONTROL Parameter value is present]&quot; o &quot;[!UICONTROL Parameter value is not present]&quot;, se exigiera incorrectamente a los usuarios que especificaran un valor de parámetro adicional. Este comportamiento era incoherente con la interfaz de usuario heredada y contradecía la lógica pretendida de detectar la presencia de parámetros sin especificar un valor. Esta corrección restaura el comportamiento esperado de la configuración de reglas, optimiza la configuración de actividades y mejora la facilidad de uso. (TGT-53640)
* **Se ha mejorado la lógica de validación para el generador de reglas de varias páginas en la IU actualizada.** ha resuelto varios problemas de validación en el generador de reglas de varias páginas dentro de la interfaz de usuario actualizada. Estas correcciones incluyen:

   * Impedir la creación de reglas cuando el parámetro de mbox está vacío
   * Visualización de mensajes de error adecuados para estados de regla no válidos
   * Corrección de la lógica de validación para operadores unarios y basados en parámetros que no requieren valores de operando
   * Activación de las reglas de fragmento hash con operadores unarios mediante la restauración de la funcionalidad de guardado

  Estas actualizaciones garantizan una configuración de reglas precisa y mejoran la facilidad de uso en escenarios de entrega de páginas complejos. (TGT-53722)
* **Problema de cambio de nombre de ubicación resuelto en las actividades A/B y MVT.** Se ha corregido un error en la interfaz de usuario actualizada que hacía que el cambio de nombre de una ubicación en una actividad [!UICONTROL A/B Test] o [!UICONTROL Multivariate Test] (MVT) no persistiera después de navegar entre la lista de ubicaciones, el direccionamiento y atrás. Esta actualización garantiza que los cambios en el nombre de la ubicación se guarden y se reflejen de forma coherente en todo el flujo de trabajo de la actividad. (TGT-52367)
* **Se ha corregido la persistencia de nombre de ubicación para actividades MVT y AP en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual los nombres de ubicación editados en las actividades [!UICONTROL Multivariate Test] (MVT) y [!UICONTROL Automated Personalization] (AP) no se guardaban correctamente. Después de cambiar el nombre de una ubicación, al desplazarse entre las fichas, como [!UICONTROL Targeting] y [!UICONTROL Experiences], los nombres volvieron a su estado anterior. Esta corrección garantiza una nomenclatura de ubicación coherente en todas las pestañas y mejora la fiabilidad durante la configuración de la actividad. (TGT-52927)
* Se ha corregido el etiquetado de ubicación **en el panel Administrar experiencias para actividades MVT.** ha resuelto un problema en la interfaz de usuario actualizada en el que el panel [!UICONTROL Manage Experiences] de las actividades [!UICONTROL Multivariate Test] (MVT) mostraba una numeración de ubicación incoherente. Esta corrección garantiza que las etiquetas de ubicación sean secuenciales y estén correctamente alineadas con las modificaciones definidas por el usuario, lo que mejora la claridad y la facilidad de uso durante la configuración de la experiencia. (TGT-52929)

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
