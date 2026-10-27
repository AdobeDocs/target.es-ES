---
keywords: Notas de la versión;notas de la versión preliminar;mejoras futuras;correcciones futuras;funciones futuras;próxima versión
description: Vea una lista de funciones, mejoras y correcciones incluidas en versiones anteriores de Adobe Target.
title: ¿Qué funciones se incluyen en las versiones anteriores de 2025?
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/cjheajZKokzwCNspfQckh6PHh5ecetdj7vZrrq9IqXw'
source-git-commit: 7f111df77c4b368dbe000a699ee19f5ff1ea266f
workflow-type: tm+mt
source-wordcount: '25402'
ht-degree: 5%
---
# Notas de la versión para versiones anteriores

Notas de la versión para versiones anteriores de [!DNL Adobe Target], incluidas las notas de la versión para [!DNL Target Standard/Premium], la plataforma [!DNL Target] y las bibliotecas Javascript de [!DNL Target] (at.js).

Las notas de la versión se enumeran en orden descendente por mes y año de publicación.

>[!NOTE]
>
>Consulte [Notas de la versión de Target (actual)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) para obtener información sobre las versiones de Target del mes actual (plataforma y Target Standard/Premium).

## Notas de la versión: 2025

### [!DNL Target Standard/Premium] 25.11.2 (14 de noviembre de 2025)

**Ofertas de decisiones**

+++Ver detalles

* **Las decisiones de oferta con selectores ocultos o no válidos no se pueden editar en la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual las decisiones de oferta vinculadas a selectores ocultos o no válidos no se podían editar a menos que el elemento fuera visible en el Compositor de experiencias visuales (VEC). Ahora se admite la edición directamente desde el panel, se restaura la funcionalidad disponible en la IU heredada y se garantiza que las decisiones de oferta se puedan modificar independientemente de la visibilidad del selector. (TGT-53899)

+++

**Recommendations**

+++Ver detalles

* **Al editar criterios en una actividad, la página se bloqueó.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual al editar los criterios de actividad la página se bloqueaba con errores de consola relacionados con `useCrudActionsCtx`. El editor de criterios ahora se carga y funciona correctamente, lo que garantiza que las actividades se puedan editar sin interrupción. (TGT-53971)
* La columna **[!UICONTROL Mensaje] no pudo mostrar intermitentemente los datos del producto en la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada de [!UICONTROL Recommendations] en el cual la columna [!UICONTROL Mensaje] de [!UICONTROL Búsqueda en el catálogo] no mostraba los datos del producto de forma intermitente, aunque hubiera valores presentes en la fuente. Ahora, la columna muestra de forma coherente los valores de mensaje correctos en todos los productos, lo que garantiza una visibilidad fiable sin necesidad de volver a configurar manualmente la columna. (TGT-52777)
* **[!UICONTROL El botón Descargar datos de Recommendations] no está visible después de guardar la actividad en la interfaz de usuario actualizada.** Se ha resuelto un problema en la IU actualizada en el cual el botón [!UICONTROL Descargar datos de recomendaciones] no aparecía en determinadas actividades guardadas, ni siquiera después de volver a guardarlas. El botón ahora se muestra de forma coherente en todas las actividades, lo que garantiza que los usuarios puedan exportar de forma fiable los datos de recomendaciones sin necesidad de soluciones alternativas. (TGT-53802)
* **Al abrir ciertos productos de una colección, se devolvió &quot;No se encontró el recurso solicitado&quot; y el modal carecía de una opción de cierre.** Se ha resuelto un problema en la interfaz de usuario de Recommendations actualizada en el cual, al abrir ciertos productos de una colección, se activaba el error &quot;No se encontró el recurso solicitado&quot; y se mostraba un modal en blanco sin una opción de cierre. El modal ahora carga los detalles del producto correctamente y siempre hay una opción de cierre disponible para salir correctamente. (TGT-53986)

+++

## [!DNL Target Standard/Premium] 25.11.1 (10 de noviembre de 2025)


**Analytics for Target (A4T)**

+++Ver detalles

* Mensaje de error de **[!UICONTROL Objetivos y configuración] al usar [!DNL Adobe Analytics] como fuente de informes en la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario [!UICONTROL Overview] actualizada en el cual la sección Objetivos mostraba el error &quot;Se ha producido un error. No podemos completar su solicitud. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste&quot; cuando [!DNL Adobe Analytics] (A4T) se seleccionó como origen de informes. Los objetivos ahora se muestran correctamente con las métricas [!UICONTROL Adobe Analytics], lo que garantiza una visibilidad coherente en las fuentes de informes. (TGT-54021)

+++

**Públicos**

+++Ver detalles

* **No se pueden seleccionar varias audiencias de informes en la IU actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual los usuarios no podían seleccionar varias audiencias de informes recién creadas simultáneamente al editar una actividad. Ahora se pueden asignar varias audiencias a la vez, lo que mejora la flexibilidad y eficacia en la configuración de los informes. (TGT-53253)

+++

**Ofertas de decisiones**

+++Ver detalles

* **No se pueden editar ni reemplazar las ofertas de toma de decisiones en la IU actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual las ofertas de toma de decisiones no se podían editar ni reemplazar a través del panel [!UICONTROL Modificaciones], y los nombres de las ofertas aparecían en blanco. Las ofertas de Decisioning ahora son totalmente accesibles y editables, lo que restaura la paridad con la IU heredada y garantiza que los clientes puedan administrar ofertas directamente dentro de las actividades. (TGT-53884)

+++

**Localización**

+++Ver detalles

* **Se corrigieron varios errores de localización en la interfaz de usuario coreana y japonesa.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 y TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles

* **La promoción por atributo con coincidencia de atributos de entidad no pudo cargar la clave de recomendación después de guardar la actividad.** Se corrigió un problema en el cual las promociones de tipo [!UICONTROL Promoción por atributo] con tipo de regla [!UICONTROL Coincidencia de atributos de entidad] no cargaban la clave de recomendación cuando se editaban después de guardar una actividad. El problema fue causado porque `customKeyId` no se solicitó a través de GraphQL. Las claves de recomendación ahora se cargan correctamente durante las ediciones de promoción. (TGT-53117)
* **La recomendación persiste visualmente al cambiar de ExpB a ExpA.** Se ha resuelto un problema en el cual al insertar una recomendación en la Experiencia B y, a continuación, cambiar a la Experiencia A, se dejaba visible el cuadro de oferta de recomendación. Esto solo era una incoherencia visual; las modificaciones ahora se representan correctamente al cambiar entre experiencias, lo que garantiza un comportamiento preciso de la interfaz de usuario. (TGT-53911)
* **La clave de recomendación no se carga para [!UICONTROL Promoción por atributo] con [!UICONTROL Atributo de entidad] que coincide.** Se ha resuelto un problema en el cual las promociones de tipo [!UICONTROL Promoción por atributo] con tipo de regla [!UICONTROL Coincidencia de atributos de entidad] no cargaban la clave de recomendación cuando se editaban después de guardar una actividad. Ahora, la clave de recomendación se recupera correctamente mediante GraphQL, lo que garantiza que las promociones se muestren y funcionen según lo esperado. (TGT-53917)
* **No funcionan las recomendaciones de edición en elementos ocultos de HTML en la IU actualizada.** Se ha resuelto un problema en la interfaz de usuario de [!UICONTROL New Create] y VEC en el cual no se podían editar las actividades de recomendación aplicadas a elementos de HTML ocultos. Esta funcionalidad ahora funciona según lo esperado, restaurando la paridad con la IU heredada y asegurando que las recomendaciones se puedan modificar independientemente de la visibilidad del elemento. (TGT-53953)
* **No se pueden editar las actividades de recomendación en elementos HTML ocultos en la IU actualizada.** Se ha resuelto un problema en la IU actualizada que impedía editar las actividades de recomendación aplicadas a elementos ocultos de HTML. Esta funcionalidad ahora funciona según lo esperado, restaurando la paridad con la IU heredada y asegurando que las recomendaciones se puedan modificar independientemente de la visibilidad del elemento. (TGT-53951)
* **Faltan intermitentemente valores de atributo en el catálogo de recomendaciones de la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada de [!UICONTROL Recommendations] en el cual los listados de búsqueda en el catálogo de forma intermitente no mostraban ciertos valores de atributo (por ejemplo, mensaje) aunque estuvieran presentes en la fuente del producto. Ahora, los valores de atributo se cargan de forma coherente en los resultados de búsqueda sin necesidad de reconfigurar las columnas, lo que mejora la fiabilidad y eficacia de la administración del catálogo. (TGT-52769)
* Falta el botón **[!UICONTROL Descargar recomendaciones] para [!DNL Recommendations] actividades en la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario [!DNL Recommendations] actualizada en el cual el botón [!UICONTROL Descargar recomendaciones] no estaba visible para las actividades A/B que usan recomendaciones. El botón ahora aparece correctamente, lo que permite a los usuarios exportar los datos de recomendaciones según lo esperado y en consonancia con la funcionalidad de la IU heredada. (TGT-53768)
* Falta el botón **[!UICONTROL Descargar datos de recomendación] en la interfaz de usuario de la descripción general actualizada.** Se ha resuelto un problema en la interfaz de usuario de [!UICONTROL Overview] actualizada en el cual el botón [!UICONTROL Descargar datos de recomendación] no era visible para las actividades que contenían recomendaciones. El botón ahora aparece correctamente, lo que garantiza que los usuarios puedan exportar los datos de Recommendations directamente sin necesidad de volver a la IU heredada. (TGT-53772)
* **La edición de criterios de actividad a veces resultaba en una pantalla en blanco en la IU actualizada.** Se ha resuelto un problema en la IU actualizada en el cual al hacer clic en [!UICONTROL Editar criterios en las experiencias], ocasionalmente se mostraba una pantalla en blanco para determinadas actividades. El editor de criterios ahora se carga de forma fiable en todas las actividades, lo que garantiza que los usuarios puedan editar sin interrupción. (TGT-53961)
* **No se pueden editar los criterios de secuencia en la interfaz de usuario actualizada.** Se ha resuelto un problema en la IU actualizada que causaba que, al intentar editar [!UICONTROL Criterios de secuencia], la ventana emergente de criterios permaneciera atascada durante la carga y mostrara una pantalla en blanco. El editor de criterios ahora se carga correctamente, lo que permite a los usuarios editar y actualizar los criterios de secuencia sin interrupción. (TGT-53985)

+++

**[!UICONTROL Informes]**

+++Ver detalles

* Las ubicaciones de **[!UICONTROL Prueba multivariada] (MVT) y el problema de informe de gráficos impidieron la generación del informe.** Se ha resuelto un problema en el cual las actividades MVT no podían generar [!UICONTROL Contribución de ubicación] e informes de gráficos en la interfaz de usuario de Target, con el error &quot;Se produjo un error. No podemos completar su solicitud&quot;. Ahora, los informes se cargan correctamente en la interfaz de usuario, lo que garantiza una visibilidad completa. (TGT-53654)
* Los informes de **MVT no se cargan debido a un error en el informe de contribución de [!UICONTROL Element].** Se ha corregido un problema por el cual los informes de actividad MVT no se cargaban en la interfaz de usuario de Target y mostraban el error &quot;No se pudo recuperar el informe de contribución de elementos&quot;. Los informes ahora se muestran correctamente, lo que garantiza una visibilidad completa de las contribuciones de elementos. (TGT-53691)
* **Exportar detalles del pedido a un problema de CSV para actividades de [!UICONTROL Segmentación de experiencias] (XT).** Se ha corregido un problema por el cual la opción [!UICONTROL Exportar detalles del pedido a CSV] aparecía incorrectamente para las actividades XT y devolvía un archivo vacío. La opción ahora solo se muestra para actividades AP, lo que garantiza una funcionalidad de exportación precisa y evita confusiones. (TGT-53798)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* El problema con el botón **[!UICONTROL Eliminar modificación] impidió la eliminación de las modificaciones de la actividad.** Se ha resuelto un problema en el cual el botón [!UICONTROL Eliminar modificación] de la interfaz de usuario de [!DNL Target] no funcionaba, lo que impedía que los usuarios eliminaran modificaciones dentro de las actividades. Ahora el botón funciona según lo esperado, lo que permite eliminar las modificaciones de forma fiable y sin demora. (TGT-53728)
* **Los selectores preferidos no se reconocen en la IU actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual los selectores preferidos, como `data-target-component-id`, no aparecían en la lista de selectores de CSS dentro del VEC. Los usuarios ahora pueden seleccionar de forma fiable los atributos preferidos en lugar de los nombres de clase generados dinámicamente, lo que garantiza una segmentación estable en las actualizaciones de la página de SPA. (TGT-53908)
* **La alineación de la ubicación de la actividad no coincide entre las páginas [!UICONTROL Editar] y [!UICONTROL Información general].** Se ha resuelto un problema en el cual la numeración de la ubicación de la actividad en la página [!UICONTROL Información general] no se alineaba con las actualizaciones realizadas en la página [!UICONTROL &#x200B; Editar experiencia]. Las ubicaciones ahora son coherentes en ambas vistas, lo que garantiza una alineación precisa y evita que falten posiciones o no estén numeradas correctamente. (TGT-53960 y TGT-53954)
* **No se puede volver a cambiar al modo [!UICONTROL Diseño] en el VEC actualizado.** Se ha resuelto un problema en la IU actualizada del VEC en el cual los usuarios no podían volver al modo [!UICONTROL Diseño] después de navegar a una nueva página en modo [!UICONTROL Examinar]. La opción [!UICONTROL Diseño] ahora funciona correctamente, lo que permite que las modificaciones se apliquen sin problemas en todas las páginas. (TGT-53988 y TGT-53993)
* **El parámetro de consulta no se muestra en la descripción general de la actividad.** Se ha resuelto un problema en la IU actualizada en el cual los parámetros de consulta no se mostraban en la página [!UICONTROL Información general] de las actividades, lo que provocaba discrepancias entre la [!UICONTROL Información general] y las direcciones URL de entrega de la página. Los parámetros de consulta ahora se muestran correctamente, lo que garantiza que las ubicaciones de la actividad estén completamente representadas y sean coherentes en todas las vistas. (TGT-53701)

+++

### [!DNL Target Standard/Premium] 25.10.1 (22 de octubre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**Actividades**

+++ Ver detalles
* **Se ha resuelto un problema de uso en la IU actualizada**. [!UICONTROL Los observadores] ahora pueden obtener una vista previa de las actividades usando la opción [!UICONTROL Ver actividad], al igual que en la IU heredada. (TGT-51741)
* Los usuarios de **[!UICONTROL Observer] ahora pueden ver el contenido de la actividad en la interfaz de usuario actualizada.** Se ha restaurado la visibilidad de los usuarios con la función Observador en la IU de actividad actualizada. Anteriormente, los observadores no podían ver las modificaciones, ofertas y cambios de contenido, una funcionalidad disponible en la interfaz de usuario heredada. (TGT-53785)
* Los usuarios de **[!UICONTROL Aprobador] ahora pueden editar los objetivos de la actividad sin error de privilegio de editor.** Se ha resuelto un problema de permisos en la interfaz de usuario de creación de actividades que impedía que los usuarios de nivel de aprobador guardaran cambios en la configuración avanzada de objetivos. Los usuarios afectados recibieron un error de `403 Forbidden.Resource` que requería privilegios de editor, a pesar de tener acceso suficiente. (TGT-53819)

+++

**Públicos**

+++Ver detalles

* **Se restauró la selección de varias audiencias en los informes de &quot;Solo esta actividad&quot;.** Se ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía que los usuarios seleccionaran varias audiencias en la sección [!UICONTROL Solo esta actividad] en [!UICONTROL Objetivos y configuración]. (TGT-53283)
* **Los gráficos de informes basados en audiencias ahora muestran correctamente los datos de conversión.** Se ha resuelto un problema en la ficha [!UICONTROL Informes] que provocaba que fallaran los gráficos al seleccionar audiencias no predeterminadas. Aunque había datos y métricas de confianza disponibles, el gráfico visual solo mostraba una línea sólida, lo que dificultaba el análisis. (TGT-53769)
* **La interfaz de usuario de [!UICONTROL Segmentación] ahora indica claramente las reglas de audiencia excluidas.** Se ha resuelto un problema en la sección [!UICONTROL Segmentación] de la interfaz de usuario de creación de actividad en el cual las reglas de audiencia establecidas en [!UICONTROL Excluir] no se mostraban claramente. Esto provocaba confusión al revisar la lógica de segmentación, especialmente para audiencias que excluían direcciones URL específicas. (TGT-53809)
* **Los valores de definición de audiencia ahora se pueden seleccionar y copiar en la ficha [!UICONTROL Segmentación].** Se ha resuelto un problema en la interfaz de creación de actividades que impedía que los usuarios seleccionaran y copiaran valores de reglas de audiencia en la ficha [!UICONTROL Segmentación]. Esta funcionalidad estaba disponible en la interfaz de usuario heredada pero no aparecía en la interfaz de usuario actualizada. (TGT-53856)

+++

**Localización**

+++Ver detalles

* **Se ha corregido un error de traducción de &quot;quote&quot; en el contexto del editor de páginas zh_CN.** Se ha corregido un error de traducción contextual en la configuración regional zh_CN en el que el término &quot;cotización&quot; se traducía de forma inexacta como &quot;报价&quot;, lo que implicaba una cotización de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el significado deseado hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53841)
* **Se ha corregido la traducción incorrecta de &quot;cita eliminada&quot; en el contexto del editor de páginas zh_CN.** Se ha corregido un error de traducción en la configuración regional zh_CN en el que &quot;cotización eliminada&quot; se representaba de forma inexacta como &quot;移除了报价&quot;, lo que implicaba una cotización de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53843)
* **Se ha corregido un error de traducción de &quot;cita reordenada&quot; en el contexto del editor de páginas zh_CN.** Se ha corregido un error de traducción contextual en la configuración regional zh_CN en el que &quot;oferta reordenada&quot; se traducía de forma inexacta como &quot;重新排列了报价&quot;, lo que implicaba una cotización de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53844)
* **Se ha corregido la traducción incorrecta de &quot;quote changed&quot; en el contexto del editor de páginas zh_CN.** Se ha corregido un error de traducción en la configuración regional zh_CN en el que &quot;quote changed&quot; se representaba de forma inexacta como &quot;更改了报价&quot;, lo que sugería un presupuesto de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53845)

+++

**Recommendations**

+++Ver detalles

* **Los cambios en el selector de CSS para Recommendations ahora se guardan correctamente.** Se ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía a los usuarios actualizar el selector de CSS para las ubicaciones de recomendación. Los cambios se revirtieron después de guardar y bloquear las actualizaciones de los contenedores de segmentación. (TGT-53835)
* **La selección de eventos de carga de página ahora persiste en las modificaciones de recomendaciones.** Se ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía a los usuarios guardar cambios al cambiar el tipo de evento de una recomendación de [!UICONTROL Vista] a [!UICONTROL Carga de página]. Aunque la selección parecía correcta, se revirtió después de salir, bloqueando la publicación de la actividad. (TGT-53957)

+++

**Informes**

+++Ver detalles

* **&quot;[!UICONTROL Exportar detalles del pedido a CSV]&quot; ahora descarga datos completos.** Se ha resuelto un problema en la interfaz de usuario [!UICONTROL Información general] que hacía que la opción &quot;[!UICONTROL Exportar detalles del pedido a CSV]&quot; descargara archivos vacíos, incluso cuando había datos de informe válidos. (TGT-53787)

+++

**Seguridad**

+++Ver detalles

* Se agregó **filtro previo de IMS para proteger los puntos de conexión GQL de la exposición de datos entre organizaciones.** Se ha resuelto una vulnerabilidad de seguridad en la pestaña Admin que afectaba a los extremos de GraphQL licenseGroups y targetProperties. El problema se debía al uso de la API JIL con un token de cliente de administrador que se podía aprovechar para acceder a datos de productos entre organizaciones. (TGT-53837)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* **Se ha restaurado la estabilidad de creación en la interfaz de usuario de creación de actividad.** Se ha resuelto un problema intermitente en la interfaz de usuario del VEC que provocaba que fallara la creación y que los vínculos se pudieran seleccionar inesperadamente, lo que redirigía a los usuarios fuera de la página. (TGT-53153)
* **Edición restaurada para actividades guardadas en la interfaz de usuario de creación de actividades.** Se ha resuelto un problema que impedía a los usuarios editar actividades después de guardar las modificaciones. Las actividades afectadas permanecieron atascadas en &quot;[!UICONTROL Aplicar modificaciones iniciales]&quot;, bloqueando más actualizaciones y ocultando el botón [!UICONTROL Cancelar]. (TGT-53631)
* **El VEC ya no se detiene en &quot;[!UICONTROL Aplicar modificaciones iniciales].&quot;** Se ha resuelto un problema de rendimiento en el VEC que provocaba largos retrasos al cargar experiencias con un gran número de modificaciones. Los usuarios afectados vieron la interfaz de usuario atascada en &quot;[!UICONTROL Aplicar modificaciones iniciales]&quot; durante varios minutos, especialmente en los escenarios de la Experiencia B. (TGT-53727)
* **El VEC ahora carga modificaciones sin elementos raíz.**
Se ha resuelto un problema en el VEC que provocaba que las experiencias se detuvieran al cargar modificaciones que carecían de un elemento raíz claro. Anteriormente, estas modificaciones provocaban que la interfaz de usuario se bloqueara indefinidamente en &quot;A[!UICONTROL aplicando modificaciones iniciales]&quot;. (TGT-53799)
* **Guardar cambios en actividades ahora funciona según lo esperado.** Se ha resuelto un problema relacionado con permisos en la nueva interfaz de usuario de creación que impedía a los usuarios guardar cambios al editar objetivos y configuración avanzada en las actividades. Los usuarios afectados veían una cinta de error roja y un mensaje &quot;Forbidden.Resource&quot;, a pesar de tener el acceso adecuado. (TGT-53816)
* **La interfaz de usuario de VEC ahora conserva las modificaciones de experiencia en todas las vistas.** Se han resuelto varios problemas en el VEC actualizado que afectaban al desarrollo de experiencias. Las modificaciones no persistían correctamente, especialmente al utilizar ofertas de HTML o al cambiar entre vistas. (TGT-53825)
* **Ahora todas las vistas se muestran correctamente cuando una modificación abarca varias experiencias.** Se ha resuelto un problema en la interfaz de usuario de creación de actividad en el cual solo se mostraba una vista cuando se aplicaba una modificación en varias vistas. La información del objeto de desplazamiento no mostraba todas las vistas asociadas, aunque la modificación se hubiera aplicado correctamente. (TGT-53827)
* **El VEC ya no se detiene intermitentemente en &quot;[!UICONTROL Aplicación de modificaciones iniciales].&quot;** Se ha resuelto un problema intermitente en el VEC en el cual las experiencias no se cargaban y permanecían atascadas en &quot;[!UICONTROL Aplicación de modificaciones iniciales]&quot;. Este comportamiento era incoherente y, a veces, activaba bucles de redirección o requería la limpieza manual de la caché. (TGT-53916)
* **No se pudo reproducir el problema de carga del VEC.** Investigamos un problema informado en el cual el VEC permanecía atascado en &quot;[!UICONTROL Aplicando modificaciones iniciales]&quot; al editar actividades existentes. Se sospechaba que el comportamiento estaba relacionado con contenido de HTML que no tenía un elemento principal. Seguiremos monitorizando la periodicidad y recomendaremos el uso de contenedores estructurados para las ofertas de HTML para garantizar la estabilidad. (TGT-53972)
* El modo **[!UICONTROL Diseño] del VEC ya no se comporta de forma intermitente como el modo [!UICONTROL Examinar].** Se ha resuelto un problema en la interfaz de usuario en el cual el modo [!UICONTROL Diseño] se comportaba de forma intermitente como el modo [!UICONTROL Examinar], lo que permitía vínculos `<a>` en los que se podía hacer clic e impedía la selección de elementos. Esto provocaba que la casilla de verificación hover desapareciera y bloqueara los flujos de trabajo de modificación. (TGT-53136)
* **Los clics en el botón en el modo [!UICONTROL Compositor] ya no almacenan en déclencheur la redirección de páginas.** Se ha resuelto un problema en la IU actualizada del VEC en el cual al hacer clic en un botón en modo [!UICONTROL Compositor] se producía una redirección inesperada a la URL de destino del botón. Esto impedía que los usuarios editaran los elementos de call-to-action (CTA) e interrumpía el flujo de trabajo de creación. (TGT-53137)
* **Las actualizaciones de código de oferta en las actividades de personalización automatizada ahora se guardan sin errores.** Se ha resuelto un problema en la nueva interfaz de usuario de creación que provocaba el error &quot;[!UICONTROL Entrada de usuario no válida]&quot; al actualizar el código de oferta en las actividades [!UICONTROL Automated Personalization]. El error bloqueaba a los usuarios la posibilidad de guardar cambios, incluso cuando la entrada era válida. (TGT-53586)
* El modo **[!UICONTROL Diseño] del VEC ahora bloquea la navegación de vínculos para componentes editables.** Se ha resuelto un problema en el VEC actualizado en el cual los elementos en los que se puede hacer clic, como botones y vínculos, activaban la redirección de páginas incluso en el modo [!UICONTROL Diseño]. Este comportamiento imitaba el modo [!UICONTROL Browse] e impedía que los usuarios modificaran componentes clave. (TGT-53696)
* **&quot;[!UICONTROL Se hizo clic en un elemento]&quot; métrica ahora funciona sin redireccionamiento ni error.** Se ha resuelto un problema en la nueva interfaz de usuario de creación que provocaba redirecciones inesperadas y pantallas en blanco al seleccionar la métrica de conversión &quot;[!UICONTROL Se hizo clic en un elemento]&quot;. Al hacer clic en un botón durante la instalación, se desencadenó la navegación en lugar de registrar el elemento, lo que dio como resultado un error &quot;[!UICONTROL no se encontró el elemento]&quot;. (TGT-53817)
* **Las actividades existentes ya no se quedan atascadas en el bucle de carga infinita durante la edición.** Se ha resuelto un problema en la nueva interfaz de usuario de Crear, en el que la edición de una actividad existente en el VEC provocaba que la página permaneciera atascada en un bucle de carga infinita. Este problema no afectaba a las actividades de nueva creación y se activaba por modificaciones preexistentes en la página. (TGT-53913)
* **Las páginas de actividad existentes con modificaciones ahora se cargan correctamente en el VEC.** Se ha resuelto un problema en el VEC actualizado que provocaba que las páginas permanecieran atascadas en la fase de carga al editar una actividad existente con modificaciones guardadas. Las nuevas actividades se cargaron sin problemas, pero las actividades configuradas anteriormente no se procesaron. (TGT-53967)

+++

### [!DNL Target Standard/Premium] 25.9.3 (30 de septiembre de 2025)

Esta versión incluye las siguientes mejoras y correcciones.

+++[!UICONTROL Públicos]

* **Las reglas de exclusión de audiencia se mostraban incorrectamente como inclusión en la interfaz de usuario de [!DNL Target].** Las audiencias configuradas con reglas de exclusión aparecían como incluidas al editar la segmentación dentro de una actividad. Aunque la lógica de exclusión se aplicó correctamente durante la ejecución, la interfaz de usuario no reflejó la regla con precisión, omitiendo la etiqueta &quot;excluyendo&quot;. La interfaz de usuario [!DNL Target] ahora muestra correctamente las reglas de exclusión en la configuración de audiencia y en los flujos de trabajo de segmentación, lo que garantiza la claridad y coherencia en la configuración de la campaña. (TGT-53808)
* **La sección [!UICONTROL Segmentación] no indica que se haya establecido una regla de audiencia para excluir.** Las audiencias configuradas con lógica de exclusión se mostraban incorrectamente como inclusión en la sección [!UICONTROL Segmentación] de la interfaz de usuario para la creación de actividades. Aunque el servidor aplicó correctamente la regla de exclusión, la interfaz de usuario no la representó visualmente, omitiendo la etiqueta &quot;Excluir&quot; y causando confusión durante la configuración de la campaña. La sección [!UICONTROL Segmentación] ahora muestra claramente las reglas de exclusión, lo que garantiza la coherencia entre la configuración de la audiencia y la visualización de la segmentación. (TGT-53809)

+++

+++Localización

* **Se ha corregido una incoherencia terminológica en la traducción al chino simplificado de &quot;Vista de detalles completa&quot;.**
Anteriormente, el término &quot;Detalles&quot; se traducía incorrectamente como &quot;详情&quot; en la configuración regional del chino simplificado (zh_CN), lo que infringía las directrices terminológicas establecidas. Esto se ha corregido a &quot;详细信息&quot; para garantizar la coherencia con la base terminológica. (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **Los cuadros de recomendación eran difíciles de localizar y seleccionar en el VEC.** Después de agregar una oferta de Recommendations en (VEC), al hacer clic en la modificación en el panel izquierdo, no se resaltó ni se desplazó al cuadro de recomendación correspondiente de la página. Esto dificultaba la localización y edición de la oferta, especialmente cuando se ocultaba bajo selectores o se diseñaba mínimamente. Al hacer clic en una modificación de recomendación, ahora se resalta y se desplaza correctamente al elemento asociado, lo que mejora la facilidad de uso y la eficacia de la edición en el proceso actualizado de creación de actividades. (TGT-52571)
* **Los selectores de recomendación se volvieron a escribir incorrectamente después de guardar una actividad.** Al añadir una recomendación a un elemento del VEC, el selector era inicialmente correcto, pero después de guardar y volver a abrir la actividad, se cambió a un selector genérico. Los intentos de restaurar manualmente el selector original dieron como resultado errores de validación. Los selectores de recomendación ahora persisten con precisión después de guardar, lo que garantiza un direccionamiento y una editabilidad fiables en el proceso de creación de actividades actualizado. (TGT-53709)
* **No se pudo editar el contenido de criterios al modificar una actividad existente.** Al editar una actividad, la sección de contenido [!UICONTROL Criterios] parecía deshabilitada, con botones atenuados y sin respuesta. Este problema se resolvió asegurándose de que las configuraciones de [!UICONTROL Criterios] se puedan editar completamente durante las actualizaciones de la actividad. Los clientes ahora pueden modificar el contenido de [!UICONTROL Criteria] sin necesidad de cambiar de selección ni de utilizar soluciones alternativas, lo que mejora la flexibilidad y la facilidad de uso en el proceso actualizado de creación de actividades. (TGT-53812)
* **No se pudieron editar los criterios dentro de una actividad.** Las opciones [!UICONTROL Editar criterios]y [!UICONTROL Quitar criterios] se deshabilitaron al acceder a criterios desde una actividad. Sin embargo, los mismos criterios se pudieron editar correctamente a través de la pestaña [!UICONTROL Recommendations]. Los criterios ahora se pueden editar completamente tanto desde el flujo de trabajo de edición de actividades como desde la pestaña [!UICONTROL Recommendations], lo que garantiza una experiencia de edición uniforme y eficaz. (TGT-53814)

+++

+++[!UICONTROL Informes]

* **La generación de ofertas ad hoc en actividades de A[!UICONTROL Personalization automatizado] ha causado incoherencias en los informes.** El uso de la característica Generar ofertas ad hoc en las actividades de [!UICONTROL Automated Personalization] (AP) provocó informes inexactos. Específicamente, los ID de oferta se reutilizaban en todas las ubicaciones, lo que provocaba que los datos de los informes se atribuyeran erróneamente o se sobrescribieran. Las ofertas específicas ahora se generan con identificadores distintos por ubicación, lo que garantiza un seguimiento y unos informes precisos en todas las experiencias configuradas. (TGT-53757)
* **No se pudieron cargar los informes de actividad debido a un error de JavaScript.** Los clientes encontraron el mensaje &quot;Se produjo un error&quot; al acceder a la ficha [!UICONTROL Informes] para determinadas actividades. El error se debe a una excepción de JavaScript: no se pueden leer las propiedades de undefined (reading &#39;indexOf&#39;), desencadenadas durante la llamada de GraphQL `getAnalyticsReportSummary`. Ahora los informes se cargan correctamente y se ha mejorado el control de errores para evitar errores similares en el flujo de trabajo actualizado de creación de actividades. (TGT-53797)
* **Los informes se bloquearon después de interactuar con la barra de desplazamiento.** Al hacer clic en la barra de desplazamiento en la ficha [!UICONTROL Informes], la página se bloqueó y se produjo un error de JavaScript:
  Los informes de `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` ahora se cargan y se desplazan correctamente sin provocar errores ni bloqueos. (TGT-53828)
* **Los informes no mostraron la métrica principal.** La métrica principal, configurada como métrica de conversión mediante un mbox, no aparecía en los informes de actividad. La búsqueda por nombre de métrica o de mbox no arrojó resultados, lo que impidió ver los datos clave de rendimiento. Las métricas principales ahora aparecen correctamente en la pestaña [!UICONTROL Informes], lo que garantiza un seguimiento y análisis precisos del rendimiento de la campaña. (TGT-53773)
* **La ficha [!UICONTROL Informes] de la interfaz de usuario actualizada se bloqueó al interactuar con la barra de desplazamiento horizontal.** La vista [!UICONTROL Informes] se bloqueó intermitentemente con el error &quot;Se produjo un error&quot; al usar la barra de desplazamiento horizontal para acceder a las métricas fuera de la vista. La barra de desplazamiento ahora funciona de forma fiable, lo que permite a los clientes ver y analizar todas las métricas sin necesidad de soluciones alternativas, como reducir o utilizar la función de desplazamiento con desplazamiento. (TGT-53824)

+++

+++[!UICONTROL Compositor de experiencias visuales] (VEC)

* **Al hacer clic en las rutas de exploración en el VEC, no se mostraba de manera consistente el menú de edición.**
Al seleccionar elementos de HTML a través de las rutas de exploración del (VEC), el menú de edición no aparecía o desaparecía rápidamente de forma intermitente, lo que hacía que la selección de elementos no fuera fiable. El menú de edición ahora se muestra de forma coherente al navegar mediante rutas de exploración, lo que mejora el flujo de trabajo de selección de elementos en el proceso actualizado de creación de actividades. (TGT-52873)
* **El menú contextual no pudo aparecer intermitentemente en el VEC.** El menú contextual de la interfaz de usuario del VEC actualizada no aparecía de forma coherente al hacer clic en los elementos, lo que dificultaba el acceso a las opciones de edición. El menú contextual ahora se muestra de forma fiable tras la selección de elementos, lo que mejora el flujo de trabajo de edición y la facilidad de uso general en el proceso de creación de actividades actualizado. (TGT-53015)
* **No se pudo mostrar el menú contextual de ciertos elementos del VEC.** El menú contextual no se mostraba al seleccionar elementos específicos en el VEC actualizado, lo que dificultaba la aplicación de modificaciones. El menú contextual ahora se muestra de forma coherente para todos los elementos admitidos, lo que mejora la fiabilidad y facilidad de uso de la experiencia de edición en el flujo de trabajo de creación de actividades actualizado. (TGT-53248)
* **El menú contextual desapareció en el primer clic al usar rutas de exploración en el VEC.** La selección de un elemento principal mediante las rutas de exploración del VEC provocaba que el menú contextual apareciera brevemente y luego desapareciera, lo que dificultaba el acceso a las opciones de edición. El menú contextual ahora permanece visible y funcional al navegar por los elementos a través de las rutas, lo que mejora la fiabilidad del flujo de trabajo de selección de elementos en el proceso actualizado de creación de actividades. (TGT-53424)
* **No apareció el menú contextual para elementos de nivel superior en el VEC.** La selección de elementos de nivel superior, como etiquetas `<div>` o `<main>`, a través de las rutas de exploración del VEC no almacenó en déclencheur el menú contextual, lo que impidió realizar más acciones de edición. El menú contextual ahora aparece de forma coherente para todos los elementos admitidos, incluidos los contenedores de nivel superior, lo que mejora la flexibilidad y facilidad de uso del flujo de trabajo de creación de actividades. (TGT-53770)
* **Los elementos de una página específica no se podían editar en el VEC.** No se pudieron seleccionar o editar ciertos elementos de la página en el VEC actualizado. Este problema se aisló en esa página y no afectó a otras páginas dentro de la misma cuenta. Todos los elementos de la página ahora se pueden seleccionar y editar según lo esperado, lo que restaura la funcionalidad completa en el flujo de trabajo de creación de actividades. (TGT-53353)
* **Se mejoró el flujo de trabajo al ver elementos secundarios durante la selección de elementos en el VEC.** Para mejorar la facilidad de uso y la precisión durante la creación de la actividad, el VEC ahora muestra elementos secundarios al pasar el ratón por encima o seleccionar un elemento HTML principal. Esta mejora permite a los clientes comprender mejor la estructura de la página y realizar modificaciones más precisas, lo que optimiza el flujo de trabajo de edición en la IU actualizada. (TGT-53416)
* **No se pudieron editar los elementos de las actividades existentes mediante la barra de modificación.** Al editar actividades creadas anteriormente, la barra de modificación no se activaba para determinados elementos de la página, lo que impedía realizar actualizaciones. Este problema se observaba principalmente en las actividades modificadas y era difícil de reproducir en las recién creadas. La barra de modificación ahora muestra y permite editar de forma coherente todos los elementos admitidos, lo que mejora la fiabilidad y la facilidad de uso en el flujo de trabajo actualizado de creación de actividades. (TGT-53013)

+++

+++[!UICONTROL Espacios de trabajo]

* **Al clonar una actividad en un área de trabajo diferente, se produjo el error &quot;Entrada de usuario no válida&quot;.** Al intentar clonar una actividad de un espacio de trabajo a otro, se producía un error: &quot;InvalidProperty.Json - Unknown property name &#39;content&#39;&quot;. Este problema se debía a una administración incorrecta de los metadatos de la actividad durante el proceso de clonación. Ahora, las actividades se pueden clonar correctamente en todos los espacios de trabajo sin activar errores de validación, lo que garantiza flujos de trabajo de implementación de actividades más suaves. (TGT-53731 y TGT-53736)

+++

### [!DNL Target Standard/Premium] 25.9.2 (22 de septiembre de 2025)

En esta versión se incluyen las siguientes correcciones y mejoras:

**[!UICONTROL Públicos]**

+++Ver detalles

* **Se ha corregido un problema por el cual las actividades no se podían copiar debido a ID de audiencia no válidos.** Los clientes que intentaban copiar actividades en el proceso actualizado de creación de actividades encontraban un error provocado por ID de audiencia no válidos (por ejemplo, -1752722444307). Este problema de validación de back-end impedía la duplicación de actividades dentro del mismo espacio de trabajo. Este problema se ha resuelto y las actividades ahora se pueden copiar correctamente sin errores relacionados con la audiencia. (TGT-53717)
* **Se ha corregido un problema por el que aparecían errores de entrada de usuarios no válidos para audiencias solo de actividad en las actividades [!UICONTROL Automated Personalization] del modal [!UICONTROL Administrar contenido].** Los clientes encontraron errores de entrada de datos no válidos al configurar audiencias solo de actividad en el modal [!UICONTROL &#x200B; Administrar contenido] para actividades AP. Este problema se producía a pesar de que las audiencias se habían utilizado correctamente anteriormente. Las configuraciones de audiencia combinadas ahora se guardan correctamente sin activar errores de validación. (TGT-53749)

+++

**Documentación**

+++Ver detalles

* **Se han movido páginas de documentación de Web SDK específicas de Target al repositorio de Adobe Target.** Como parte de la reestructuración de la documentación de Web SDK, el contenido específico de [!DNL Target] se ha migrado de los documentos generales de Web SDK a [!DNL Adobe Target] [Guía para desarrolladores](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Este cambio mejora la capacidad de detección de contenido y garantiza que el equipo de productos adecuado mantenga una guía específica de la solución. (TGT-53374)

+++

**[!UICONTROL Decisiones de oferta]**

+++Ver detalles

* La opción **Decisión de oferta ahora está visible de forma consistente durante la creación de la actividad inicial.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual la opción [!UICONTROL Decisión de oferta] no aparecía durante el flujo de creación por primera vez para actividades A/B, especialmente cuando se accedía en modo incógnito en inquilinos con Decisiones de oferta habilitadas. La opción solo apareció después de ir al paso [!UICONTROL Segmentación] y regresar a [!UICONTROL Experiencias]. Esta corrección garantiza que la opción [!UICONTROL Decisión de oferta] esté disponible inmediatamente durante la configuración inicial, lo que mejora la facilidad de uso y reduce las confusiones. (TGT-51888)

+++

**[!UICONTROL Ofertas]**

+++Ver detalles

* **Se ha corregido un problema por el cual las ofertas de redireccionamiento no incluían `redirectOptions` en la carga útil al `includeContent=true`.** A los clientes que recuperaban ofertas de redireccionamiento con `includeContent=true ` les faltaba el campo `redirectOptions` en la carga de respuesta. Esta incoherencia afectaba a los flujos de trabajo, como la copia de ofertas y la creación de actividades. Las ofertas de redireccionamiento ahora incluyen correctamente `redirectOptions` cuando se solicita contenido. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Ver detalles

* Se ha restaurado el rastreo de clics **para las actividades de [!UICONTROL Recommendations] creadas en la interfaz de usuario actualizada.** Se ha resuelto un problema en el cual las actividades de [!UICONTROL Recommendations] creadas en la IU actualizada no registraban el rastreo de clics, lo que arrojaba cero conversiones notificadas. Las actividades creadas en la IU heredada rastreaban correctamente los clics y notificaban las conversiones según lo esperado. Esta corrección garantiza que las actividades de Recommendations creadas en la interfaz de usuario actualizada ahora incluyan los atributos de seguimiento correctos, restaurando la creación de informes de conversión y la alineación con las métricas de A4T. (TGT-53287)
* **Rastreo de clics restaurado para actividades de Recommendations.** Se ha resuelto un problema en el cual las actividades de [!UICONTROL Recommendations] creadas en la IU actualizada no registraban el rastreo de clics, lo que arrojaba cero conversiones notificadas. La IU heredada aplicó correctamente un identificador de seguimiento (`at-track-click`) al contenido de [!UICONTROL Recommendations], mientras que la IU actualizada insertó por error un marcador de posición (`__recsClickTrackIdPlaceholder__`), lo que impide el seguimiento del servidor. Esta corrección garantiza que el contenido de [!DNL Recommendations] ahora incluya el ID de seguimiento correcto, con lo que se restauran los informes de conversión y la alineación con las métricas de A4T. (TGT-53496)
* **Se ha resuelto el bloqueo del editor de colecciones en la IU actualizada.** Se ha corregido un problema en la IU actualizada del [!UICONTROL Compositor de experiencias visuales] (VEC) en el cual al abrir una colección desde el panel Editor, la página se bloqueaba con un TypeError: No se pueden leer las propiedades de undefined (leer &quot;customLocale&quot;). Este error se produjo en varios tipos de actividades, incluidas [!UICONTROL Recommendations] y pruebas A/B. (TGT-53703)
* **Opción para eliminar la colección seleccionada restaurada en el VEC.** Se ha corregido un problema en el VEC en el cual los usuarios solo podían reemplazar una colección seleccionada en una actividad de [!UICONTROL Recommendations], pero no podían eliminarla por completo. Esta limitación bloqueaba los casos de uso que requerían una eliminación limpia de la colección sin sustitución. Esta corrección introduce una opción clara para eliminar la colección seleccionada, lo que permite una mayor flexibilidad en la configuración de la actividad y su alineación con el comportamiento de la IU heredada. (TGT-53652)
* **Las colecciones de criterios personalizados ahora se muestran correctamente en la interfaz de usuario de [!UICONTROL Recommendations].** Se ha corregido un problema en la interfaz de Recommendations por el cual las colecciones creadas con criterios personalizados no mostraban los resultados de los productos. Aunque las colecciones basadas en atributos estándar funcionaban según lo esperado, las que utilizaban filtros personalizados devolvían &quot;No se encontraron resultados&quot; a pesar de las coincidencias de catálogo válidas. Esta corrección garantiza que las colecciones que utilizan atributos personalizados ahora se rellenen correctamente en la pestaña [!UICONTROL Product], lo que restaura la funcionalidad completa de los flujos de trabajo de recomendaciones personalizados. (TGT-53653)
* **Se ha corregido un problema por el que las colecciones no mostraban productos al abrir por primera vez la página [!UICONTROL Productos].** Los clientes que accedieron a las colecciones en la sección [!UICONTROL Recommendations] experimentaron resultados de productos vacíos al abrir por primera vez la página [!UICONTROL Productos]. Este problema se debía a un error del servidor en la consulta de GraphQL, que no cargaba datos de productos para colecciones con criterios personalizados. El problema se ha resuelto y los productos ahora aparecen correctamente sin requerir el cambio de entorno. (TGT-53694)
* **Se ha corregido un problema que impedía eliminar colecciones en actividades [!UICONTROL Recommendations] basadas en formularios.** Los clientes que crean actividades de [!UICONTROL Recommendations] y usan el [!UICONTROL Compositor de experiencias basadas en formularios] no pudieron anular la selección de una colección seleccionada anteriormente. La interfaz de usuario requería que se seleccionara una colección antes de guardar, lo que impedía que los usuarios volvieran a &quot;Todas las colecciones&quot;. Este comportamiento se ha actualizado para que coincida con la funcionalidad del VEC, lo que permite a los clientes guardar sin una colección seleccionada y establecer el valor predeterminado de &quot;Todas las colecciones&quot; según lo esperado. (TGT-53708)
* **Se ha corregido un problema que impedía establecer promociones por atributo debido a la falta de valores de colección o de reglas de filtrado.** Los clientes que configuraban promociones por atributo en el proceso de creación de actividades encontraban un error que indicaba que a una promoción le faltaba un ID de colección o valores de reglas de filtrado. Este problema de validación bloqueaba la progresión incluso cuando la configuración parecía completa. Las promociones ahora se pueden guardar correctamente cuando se configuran mediante el atributo. (TGT-53750)
* **Se ha corregido un problema que impedía guardar las actividades debido a nombres de experiencia duplicados.** Los clientes encontraban un error de entrada de datos no válido al guardar actividades que incluían combinaciones específicas de criterios y diseños. El error se activó por nombres de experiencia duplicados, incluso cuando la configuración parecía válida. Ahora, las actividades con configuraciones distintas se pueden guardar sin conflictos de nombres. (TGT-53805)
* **Se ha corregido un problema por el que la validación seguía siendo no válida para las promociones configuradas por el atributo.** Los clientes encontraban errores de validación persistentes al configurar promociones por atributo en el proceso de creación de actividades, incluso cuando todos los campos obligatorios se rellenaban correctamente. Este problema se debía a una lógica de validación incorrecta en el flujo de trabajo [!UICONTROL Recommendations]. Las promociones basadas en atributos ahora se validan y guardan según lo esperado. (TGT-53811)
* **Se ha corregido un problema que causaba que, al aplicar una promoción a una actividad de [!UICONTROL Recommendations] activa, se produjera un error.** Los clientes encontraron el error &quot;A una promoción le falta un ID de colección o valores de regla de filtrado&quot; al intentar aplicar una promoción principal a una actividad de [!UICONTROL Recommendations] activa, incluso después de proporcionar detalles de configuración válidos. Las promociones ahora se pueden aplicar correctamente a las actividades activas sin activar errores de validación, lo que garantiza una experiencia más fluida en la IU actualizada de creación de actividades. (TGT-53738)
* **Se ha corregido un problema por el cual los productos no eran visibles en colecciones dentro de la interfaz de usuario de [!UICONTROL Recommendations].** Los clientes de un solo inquilino notificaron que no se pudieron cargar las listas de productos al ver ciertas colecciones en la sección [!UICONTROL Recommendations] de la nueva interfaz de usuario. El problema se resolvió temporalmente cambiando de entorno, pero esta solución resultó en una mala experiencia de usuario. Las entidades de producto ahora se cargan de forma coherente sin requerir el cambio de entorno. (TGT-53783)
* **Se ha corregido un problema por el cual los criterios y diseños no se mostraban en una línea de la interfaz de usuario para la creación de actividades.** Anteriormente, los criterios y diseños del proceso de creación de actividades se mostraban en un formato comprimido, lo que dificultaba a los clientes ver y administrar elementos individuales. Cada criterio y diseño ahora aparecen en su propia línea, lo que mejora la legibilidad y la facilidad de uso en la interfaz de usuario actualizada. (TGT-53818)

+++

**Informes**

+++Ver detalles

* La métrica **[!UICONTROL Ingresos totales] ahora se incluye en las exportaciones de CSV desde informes de actividad.** Se ha resuelto un problema en la interfaz de usuario actualizada de [!UICONTROL Información general] en el cual los ingresos totales se mostraban correctamente en la vista del informe de actividad, pero no aparecían en la exportación de CSV, y se mostraban como 0 $. Esta discrepancia impedía a los usuarios confiar en los datos exportados para el análisis y la creación de informes sin conexión. (TGT-53325)
* La métrica **[!UICONTROL Ventas totales] ahora se incluye en las exportaciones CSV desde informes de actividad.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual la métrica [!UICONTROL Ventas totales] aparecía correctamente en la vista del informe de actividad, pero no aparecía en la exportación de CSV. Esta discrepancia impedía a los usuarios acceder a los datos de rendimiento completos en los informes descargados. Esta corrección garantiza que los valores de [!UICONTROL Ventas totales] ahora se incluyan con precisión en las exportaciones de CSV, lo que restaura la coherencia entre la creación de informes en la aplicación y el análisis sin conexión. (TGT-53330)
* **Mensajes de error mejorados para [!UICONTROL Visualización de gráfico] cuando las métricas no están habilitadas.** Se ha corregido un problema en el VEC en el cual [!UICONTROL Graph View] mostraba un mensaje genérico de &quot;Se ha producido un error&quot; cuando una métrica solicitada no estaba habilitada en el grupo de informes [!DNL Analytics] asociado. Este problema se desencadenó por un error de `not_enabled_metric` en la respuesta del servidor de GraphQL. Esta corrección reemplaza el error impreciso con un mensaje más informativo que ayuda a los usuarios a identificar los problemas de configuración en [!DNL Analytics], lo que reduce la confusión y las escalaciones de soporte innecesarias. (TGT-53577)
* **Se ha corregido un problema por el que la duración del informe superaba el límite admitido de 90 días.** Los clientes que usan el filtro &quot;[!UICONTROL Últimos X días]&quot; en la sección [!UICONTROL Informes] pudieron seleccionar duraciones superiores a 90 días, lo que podría provocar problemas de rendimiento y datos incompletos. El filtro se ha actualizado para aplicar un intervalo máximo de 90 días, lo que garantiza unos informes coherentes y fiables. (TGT-53795)
* **Se ha corregido un problema por el que los informes CSV de rendimiento se generaban usando el entorno predeterminado en lugar del seleccionado.** Anteriormente, cuando los clientes cambiaban el entorno en la configuración del informe y generaban un informe de rendimiento, el CSV resultante contenía datos del entorno predeterminado en lugar del seleccionado.  La interfaz de usuario ahora pasa correctamente el parámetro `environmentId`, asegurándose de que el informe refleje el entorno elegido. Además, se ha mejorado la gestión de errores. Si se producen errores de GraphQL durante la generación de CSV, la interfaz de usuario muestra ahora un mensaje de error claro en lugar de producir un archivo CSV vacío. (TGT-53064)
* **Se ha corregido un problema por el cual los informes de Analytics for Target (A4T) no mostraban datos en [!UICONTROL Visualización de gráfico].** Los clientes que usan [!DNL Target] con integración con A4T encontraron el error &quot;Se produjo un error&quot; al cambiar a la vista de gráfico en la pestaña Informes de las actividades de prueba A/B. Aunque la [!UICONTROL Vista de tabla] se cargó correctamente, [!UICONTROL Vista de gráfico] no pudo representar las tendencias de las métricas en el intervalo de tiempo seleccionado. [!UICONTROL La vista de gráfico] ahora muestra los datos de rendimiento según lo esperado para todas las métricas compatibles, lo que mejora la visibilidad y la precisión de los informes en la IU actualizada. (TGT-53573)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Los metadatos de **elemento ahora están visibles al pasar el ratón por encima en el menú de ruta de exploración.** Se ha mejorado el menú de ruta de exploración del VEC para mostrar detalles de elementos adicionales, como ID, clase y nombre, al pasar el ratón por encima de un elemento. Esta mejora ayuda a los usuarios a identificar y diferenciar los elementos con mayor facilidad durante la configuración de la actividad. (TGT-53409)
* **El desplazamiento de ruta de exploración ahora resalta el elemento correspondiente del VEC.** Se ha mejorado [!UICONTROL Compositor de experiencias visuales] para resaltar el elemento correspondiente en el editor al pasar el ratón por encima de los elementos del menú de ruta de exploración. También se muestra el tipo de elemento, como contenedor, texto en negrita o botón. Este comportamiento se aplica a los elementos del mismo nivel y excluye los tipos no compatibles como SVG, según la lista de validación. (TGT-53411)
* **Se ha restaurado la alerta de cambios no guardados en los flujos de trabajo de modificación del VEC.** Se ha corregido un problema en el VEC por el cual los usuarios ya no recibían notificaciones sobre cambios no guardados en las modificaciones de código personalizado. A diferencia de la IU heredada, la nueva experiencia carecía de indicadores al salir o cerrar el editor de personalización, lo que provocaba una pérdida accidental de progreso. Esta corrección restaura las alertas de todos los tipos de modificación, incluido el código personalizado, y garantiza que los usuarios reciban una advertencia antes de salir sin guardar. (TGT-53435).
* **Los cambios en el código personalizado ahora persisten durante la actualización de la página en el VEC.** Se ha corregido un problema en el VEC por el cual las modificaciones de código personalizado se perdían durante las actualizaciones del sitio web. Este problema se producía en páginas con varias recargas, lo que provocaba que el editor se restableciera y revertiera los cambios no guardados. La corrección garantiza que las ediciones de código personalizado permanezcan intactas incluso si la página se vuelve a cargar durante la edición, lo que evita la pérdida accidental del progreso. (TTGT-53501)
* **Problema de inicio de sesión resuelto para el acceso al sitio dentro del VEC.** Se ha corregido un problema en el cual los usuarios no podían iniciar sesión en su sitio al acceder a través del VEC. El flujo de inicio de sesión redirigía repetidamente a los usuarios a la página de inicio de sesión, lo que impedía la configuración y previsualización de la actividad. Esta corrección garantiza que el VEC ya no interfiera con el comportamiento de inicio de sesión, restaurando el acceso esperado para los usuarios autenticados. (TGT-53524)
* **Problema de duplicación de cookies resuelto en la extensión VEC Helper.** Se ha corregido un problema en el cual la extensión [!UICONTROL Ayuda de edición visual de Adobe Experience Cloud] duplicaba la cookie `at_qa_mode` durante el control de calidad mediante vínculos de vista previa. Al cambiar manualmente los índices de vista previa, se creaban varias cookies con valores en conflicto entre dominios, lo que impedía que los probadores cambiaran de variantes de forma fiable. Este comportamiento se observó incluso fuera de la interfaz de usuario de Target y afectó tanto a las cuentas internas como a las de cliente. Esta corrección garantiza una administración coherente de las cookies al evitar entradas duplicadas y alinear el ámbito del dominio, lo que permite un cambio de variante sin problemas sin requerir la limpieza manual de las cookies. (TGT-53579)
* **Se ha corregido un problema que causaba pérdidas de memoria al hacer clic en elementos en una página principal determinada.** Los clientes que crean actividades en esta página de inicio experimentan pérdidas de memoria al interactuar con elementos de la página. El problema estaba relacionado con las advertencias excesivas de la consola y el aumento del uso de memoria en los subfotogramas, especialmente en relación con los atributos de srcset mal formados. El uso de memoria ahora permanece estable durante la interacción. (TGT-53761)
* **Se corrigió un problema en el cual el VEC se bloqueaba y mostraba una pantalla en blanco al cargar ciertas actividades.** Los clientes de un inquilino específico informaron de que el editor no pudo cargar actividades específicas. El VEC permaneció atascado en &quot;Aplicación de modificaciones iniciales&quot; antes de bloquearse y mostrar una pantalla en blanco. El VEC ahora carga las actividades afectadas sin errores en el proceso actualizado de creación de actividades. (TGT-52932)
* **Se ha corregido un problema por el que el carril [!UICONTROL Administrar contenido] de las actividades de [!UICONTROL Automated Personalization] mostraba etiquetas de ubicación incoherentes.** Los clientes informaron que el carril [!UICONTROL Administrar contenido] mostraba números de ubicación que no coincidían en las fichas [!UICONTROL Experiencias] y [!UICONTROL Ofertas]. (por ejemplo, Ubicación 2 y Ubicación 4 en Experiencias y Ubicación 1 y Ubicación 2 en Oferta) incluso cuando solo se configuraron dos ubicaciones. Las etiquetas de ubicación ahora son coherentes y se asignan con precisión a las modificaciones, lo que mejora la claridad y la facilidad de uso en el proceso de creación de actividades. (TGT-52934)
* **Se ha corregido un problema por el cual se perdían modificaciones en el VEC después de guardar.** Los clientes informaron de que después de guardar una modificación en el VEC, la página se actualizaría y revertiría el cambio a su versión anterior. Este problema provocaba que se perdieran las actualizaciones más recientes a menos que toda la actividad se guardara inmediatamente. Las modificaciones ahora persisten correctamente después de guardar y el editor ya no revierte los cambios inesperadamente, lo que garantiza una experiencia fiable en el flujo de trabajo de creación de actividades. (TGT-53500)
* **Se mejoró la selección de elementos en el VEC al mostrar el tipo de elemento al pasar el ratón por encima y la selección.** Para mejorar la facilidad de uso durante la creación de actividades, el VEC ahora decora los elementos de HTML con su tipo al pasar el ratón por encima o seleccionarlos. Esta mejora ayuda a los clientes a identificar y seleccionar los elementos correctos con mayor facilidad. Los elementos seleccionados se resaltan con un color distinto y los elementos activados se destacan en azul. También se muestra el tipo de elemento, lo que proporciona un contexto más claro durante la edición. (TGT-53502)

+++

### Actualizaciones del flujo de datos (19 de septiembre de 2025)

La combinación de ID de flujo de datos y zona protegida debe ser única para [!DNL Adobe Target] conexiones de destino.

Se ha actualizado la lógica de validación de [!DNL Target] conexiones de destino para exigir que la combinación del ID de secuencia de datos y el nombre de la zona protegida sea única dentro de una organización de IMS. Esto significa que:

* El mismo par ID + nombre de zona protegida de secuencia de datos no se puede reutilizar en varias conexiones de destino [!DNL Target].
* El mismo ID de flujo de datos solo se puede utilizar para conexiones diferentes si están configuradas en entornos limitados diferentes.
* Esta regla se aplica a todas las selecciones de flujos de datos, incluso cuando se selecciona &quot;Ninguno&quot;.

Esta actualización garantiza una configuración coherente y evita conflictos entre entornos de varias zonas protegidas. Para obtener más información, consulte [Conexión de Adobe Target](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} en la guía *Destinos de Experience Platform*.

### [!DNL Target Standard/Premium] 25.9.1 (5 de septiembre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Fragmentos de experiencias]**

+++Ver detalles

* **Se mejoró la atribución de usuarios para [!UICONTROL ofertas del fragmento de experiencia AEM].** Se ha resuelto un problema en el VEC en el cual el campo &quot;[!UICONTROL Última actualización]&quot; para [!UICONTROL Fragmento de experiencia de AEM] (XF) ofrece de forma incorrecta un ID de código en lugar del nombre de usuario. Esta discrepancia se producía durante la selección de la oferta en la interfaz de usuario actualizada, lo que crea incoherencia con la interfaz de usuario heredada y las ofertas de HTML, que muestran correctamente el nombre del último editor. Esta corrección garantiza una atribución de usuario coherente entre los tipos de oferta, lo que mejora la transparencia y la alineación con el comportamiento esperado. (TGT-52880 y TGT-52898)

+++

**Offer Decisioning**

+++Ver detalles

* **Error de decisión de oferta resuelto para ofertas ODE.** Se ha resuelto un problema en el cual las ofertas del Motor de decisión de ofertas (ODE) insertadas a través de [!DNL Target] devolvían un error 400 debido a la falta de metadatos de formato. El mensaje de error indicaba que el tipo MIME era nulo, lo que impedía el procesamiento correcto de las decisiones de oferta. Esta corrección garantiza la administración adecuada de los metadatos de la oferta, restaura la funcionalidad para la entrega de contenido personalizado y permite la ejecución ininterrumpida de campañas de marketing. (TGT-53635)
* **Problema de representación de ofertas de ODS resuelto.** Se ha resuelto un problema en el cual las ofertas [!DNL Offer Decision Service] (ODS) creadas mediante [!DNL Adobe Journey Optimizer] (AJO) no se representaban cuando las actividades se creaban con el VEC en la interfaz de usuario actualizada. La misma configuración funcionaba correctamente en la interfaz de usuario heredada, lo que producía confusión y bloqueaba la ejecución de campañas. Esta corrección garantiza una entrega de ofertas coherente en ambas versiones de la interfaz de usuario, lo que restaura el comportamiento esperado para la personalización basada en AJO.

+++

**Informes**

+++Ver detalles

* **Opción de descarga restaurada en la sección de informes de la IU de descripción general de informes actualizada.** Se ha resuelto un problema en la nueva interfaz de usuario de información general en el cual el botón [!UICONTROL Descargar] no aparecía en la sección Informes, lo que impedía a los usuarios exportar puntuaciones de importancia de atributos. Esta actualización restaura la funcionalidad completa de exportación, lo que permite un acceso optimizado a los datos descargables para su análisis y sistema de informes. (TGT-53222)
* **[!UICONTROL Botón Descargar informe CSV completo] restaurado en la vista [!UICONTROL Atributos importantes].** Se ha resuelto un problema en la IU de creación de actividades actualizada en el cual el botón [!UICONTROL Descargar informe CSV completo] no aparecía en la sección [!UICONTROL Atributos importantes] de la vista Informes. Esta corrección restaura el acceso a las perspectivas descargables, lo que garantiza una funcionalidad coherente en las IU actualizadas y heredadas. (TGT-53238)
* **Problemas resueltos de la interfaz de usuario que afectan a la creación de informes de [!UICONTROL Segmentación automática] en la IU de descripción general actualizada.** Se han corregido varios problemas de interfaz de usuario en la interfaz de información general actualizada que afectaban a los informes de actividad de [!UICONTROL Segmentación automática]. Estas correcciones incluyen:

  * Faltan métricas de alza y confianza en los informes de resumen
  * Indicador de color incorrecto para la casilla de verificación &quot;modelos creados&quot;
  * Informe de gráfico no funcional a pesar de la variación de datos en [!DNL Analytics]
  * Falta el vínculo de descarga para los informes [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes]
  * Visualización del informe [!UICONTROL Segmentos automatizados] rotos

  Estas correcciones restauran el comportamiento esperado de los informes y mejoran la visibilidad del rendimiento de la segmentación automática [!UICONTROL 1 en la IU actualizada. &#x200B;]&#x200B;(TGT-53484)

+++

**[!UICONTROL Compositor de experiencias visuales]**

+++Ver detalles

* **Validación de formulario corregida para las condiciones de presencia de parámetros en la IU actualizada.** Se ha resuelto un problema en la IU actualizada que hacía que, al seleccionar &quot;[!UICONTROL El valor del parámetro de mbox personalizado está presente]&quot; o &quot;[!UICONTROL El parámetro está presente]&quot;, los clientes incorrectamente tuvieran que introducir un valor. Este comportamiento entra en conflicto con la lógica deseada, que simplemente comprueba la existencia de un parámetro independientemente de su valor. La corrección alinea la validación del formulario con el comportamiento esperado, lo que permite una configuración de la actividad más suave y admite la adopción completa de la IU actualizada. (TGT-53638)
* **Se ha corregido la lógica del formulario para las reglas de presencia de parámetros en la entrega de páginas.&quot;** Se ha resuelto un problema en la interfaz de usuario actualizada que hacía que seleccionar reglas de entrega de página como &quot;[!UICONTROL El parámetro está presente]&quot;, &quot;[!UICONTROL El parámetro no está presente]&quot;, &quot;[!UICONTROL El valor del parámetro está presente]&quot; o &quot;[!UICONTROL El valor del parámetro no está presente]&quot; requería incorrectamente que los usuarios especificaran un valor de parámetro adicional. Este comportamiento era incoherente con la interfaz de usuario heredada y contradecía la lógica pretendida de detectar la presencia de parámetros sin especificar un valor. Esta corrección restaura el comportamiento esperado de la configuración de reglas, optimiza la configuración de actividades y mejora la facilidad de uso. (TGT-53640)
* **Se mejoró la lógica de validación para el generador de reglas de varias páginas en la interfaz de usuario actualizada.** Se han resuelto varios problemas de validación en el generador de reglas de varias páginas en la IU actualizada. Estas correcciones incluyen:

  * Impedir la creación de reglas cuando el parámetro de mbox está vacío
  * Visualización de mensajes de error adecuados para estados de regla no válidos
  * Corrección de la lógica de validación para operadores unarios y basados en parámetros que no requieren valores de operando
  * Activación de las reglas de fragmento hash con operadores unarios mediante la restauración de la funcionalidad de guardado

  Estas actualizaciones garantizan una configuración de reglas precisa y mejoran la facilidad de uso en escenarios de entrega de páginas complejos. (TGT-53722)
* **Problema de cambio de nombre de ubicación resuelto en las actividades A/B y MVT.** Se ha corregido un error en la interfaz de usuario actualizada que causaba que, al cambiar el nombre de una ubicación en una actividad de [!UICONTROL prueba A/B] o [!UICONTROL prueba multivariable] (MVT), no persistiera después de navegar entre la lista de ubicaciones, el direccionamiento y atrás. Esta actualización garantiza que los cambios en el nombre de la ubicación se guarden y se reflejen de forma coherente en todo el flujo de trabajo de la actividad. (TGT-52367)
* Se ha corregido la persistencia de **nombre de ubicación para actividades MVT y AP en la interfaz de usuario actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada en el cual los nombres de ubicación editados en las actividades [!UICONTROL Prueba multivariada] (MVT) y [!UICONTROL Automated Personalization] (AP) no se guardaban correctamente. Después de cambiar el nombre de una ubicación, al navegar entre pestañas, como [!UICONTROL Segmentación] y [!UICONTROL Experiencias], los nombres volvieron a su estado anterior. Esta corrección garantiza una nomenclatura de ubicación coherente en todas las pestañas y mejora la fiabilidad durante la configuración de la actividad. (TGT-52927)
* **Se corrigió el etiquetado de ubicación en el panel Administrar experiencias para actividades MVT.** Se ha resuelto un problema en la IU actualizada en el cual el panel [!UICONTROL Administrar experiencias] de las actividades de [!UICONTROL Prueba multivariable] (MVT) mostraba una numeración de ubicación inconsistente. Esta corrección garantiza que las etiquetas de ubicación sean secuenciales y estén correctamente alineadas con las modificaciones definidas por el usuario, lo que mejora la claridad y la facilidad de uso durante la configuración de la experiencia. (TGT-52929)

+++

### [!DNL Target Standard/Premium] 25.8.4 (1 de septiembre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Actividades]**

+++Ver detalles

* **Los clientes no podían copiar nombres de actividades o documentos de la [!UICONTROL Información general de actividades]**: anteriormente, los clientes no podían copiar el nombre de una actividad o la oferta o documento asociado directamente desde la [!UICONTROL Información general de actividades] en el proceso actualizado de creación de actividades. Esta limitación afectaba a la facilidad de uso, especialmente en pantallas más pequeñas. Los clientes ahora pueden copiar fácilmente los nombres de actividades y documentos sin soluciones alternativas. (TGT-51850)
* **Ingesta proactiva de datos de clientes [!DNL Target] depurados durante la creación de la actividad**: se ha mejorado el proceso de creación de actividades al habilitar la recopilación proactiva de informes, contenido y capturas de pantalla de [!DNL Target] clientes. Esta mejora aborda las lagunas de datos identificadas en los casos de uso existentes y ayuda a garantizar perspectivas más precisas durante la configuración de la actividad y el experimento. (TGT-52415)
* Las actividades de **AP no obtuvieron datos listos para modelos en la sección [!UICONTROL Informes]**: Los clientes que veían actividades de Automated Personalization (AP) en la sección [!UICONTROL Informes] no podían ver indicadores listos para modelos en el grupo de informes y nivel de oferta. Este problema se producía porque los datos listos para el modelo no se recuperaban correctamente del servidor. La funcionalidad se ha restaurado y los datos listos para el modelo ahora aparecen según lo esperado. (TGT-53600 y TGT-53601)
* **Las actividades programadas para el futuro mostraron incorrectamente un estado &quot;[!UICONTROL Activo]&quot; en la descripción general de [!UICONTROL Actividad]**: Los clientes observaron que las actividades programadas para iniciarse en el futuro se marcaron incorrectamente como &quot;[!UICONTROL Activo]&quot; en la descripción general de [!UICONTROL Actividad]. Esta discordancia de estado se resolvió y las actividades programadas ahora se muestran correctamente como &quot;[!UICONTROL Programadas]&quot; sin que sea necesario actualizar la página. (TGT-52835)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles

* La lista de productos **no estaba visible en el cuadro de diálogo [!UICONTROL Ver colección]:** Anteriormente, los clientes no podían ver la lista de productos al ver una colección en la ficha [!UICONTROL Recommendations]. El cuadro de diálogo [!UICONTROL Ver colección] ahora muestra correctamente los productos asociados, lo que mejora la transparencia y la facilidad de uso en la interfaz de usuario actualizada de [!UICONTROL Recommendations]. (TGT-50531)
* **Se ha corregido un problema que causaba el filtrado con distinción de mayúsculas y minúsculas en la búsqueda avanzada de [!UICONTROL Catálogo de productos]**: El filtrado de búsqueda avanzada en la página [!UICONTROL Búsqueda en el catálogo de productos] ahora ignora correctamente la distinción de mayúsculas y minúsculas, alineándose con el comportamiento del servidor y de los servicios de GraphQL. Esta actualización garantiza resultados de sugerencias coherentes y precisos para los clientes, independientemente del formato de texto. (TGT-53585)
* **La búsqueda avanzada en la interfaz de usuario [!UICONTROL Búsqueda en el catálogo de productos] actualizada no proporcionó sugerencias**: Se pidió a los clientes que usaban la característica de búsqueda avanzada en la interfaz de usuario [!UICONTROL Búsqueda en el catálogo de productos] actualizada que escribieran valores exactos con la ortografía correcta, ya que no se mostraron sugerencias. Este problema dificultaba la localización eficiente de los productos. Las sugerencias ahora aparecen según lo esperado durante la entrada de búsqueda avanzada. (TGT-52008)
* **Algunos aprobadores no pudieron ver los productos en [!UICONTROL Búsqueda en el catálogo de productos]**: Los clientes con permisos de [!UICONTROL Aprobador] no pudieron ver ningún producto en [!UICONTROL Búsqueda en el catálogo de productos], a pesar de que otros usuarios con funciones idénticas tuvieron acceso. Este problema se debía a una incoherencia de los permisos que afectaba a la visibilidad del catálogo. Ahora todos los aprobadores pueden ver los productos en la sección [!UICONTROL Recommendations] según lo esperado. (TGT-53617)

+++ 

**[!UICONTROL Informes]**

+++Ver detalles

* **No se han podido cargar los informes para la audiencia de escritorio debido a un error de nombre de audiencia no válido**: los clientes han encontrado un error de GraphQL al intentar ver los informes de la audiencia única en el proceso de creación de actividad. El sistema devolvió un mensaje &quot;Nombre de audiencia no válido: XXXXX&quot; que impedía el acceso a los datos de los informes. Ahora, los informes se cargan correctamente para la audiencia de escritorio. (TGT-53371)
* **El cambio de audiencias en la página de informes produjo errores en la interfaz de usuario de Target**: los clientes encontraron errores al seleccionar ciertas audiencias en la sección [!UICONTROL Informes]. Este problema se debía a la gestión de audiencias no válidas en las llamadas GraphQL back-end, lo que daba como resultado errores inesperados y datos faltantes. El problema se ha resuelto y las audiencias de escritorio ahora se cargan sin errores, incluso cuando no hay datos disponibles. (TGT-53370)
* **[!UICONTROL La vista de gráfico] en la sección [!UICONTROL Informes] no mostraba valores de[!DNL Analytics]**: Los clientes que acceden a [!UICONTROL la vista de gráfico] en la sección Repuertos encontraron datos faltantes, y todos los valores aparecían como cero. Este problema se debió a una recuperación de datos incorrecta de [!UICONTROL Analytics]. [!UICONTROL La vista de gráfico] ahora muestra los valores precisos según lo esperado. (TGT-52792)
+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* **Error al hacer clic en &quot;Aceptar cookies&quot; usando el [!UICONTROL Compositor de experiencias mejorado] (EEC) debido a la falta de una función**: Los clientes notificaron que al intentar aceptar cookies a través del EEC se produjo un error de la consola: `handleclickAcceptAllButton is not defined`. La funcionalidad de aceptación de cookies ahora funciona según lo esperado, lo que garantiza una experiencia más fluida durante la creación de actividades en la interfaz de usuario actualizada. (TGT-52794)
* **La nueva IU de EEC no pudo cargar ciertas páginas que anteriormente eran compatibles con la IU heredada**: Los clientes informaron que el nuevo EEC no podía cargar algunas páginas, a las que se podía acceder desde la IU heredada a pesar del código de eliminación de iframes presente en el sitio. El proceso actualizado de creación de actividades ahora admite la carga de estas páginas, lo que restaura la compatibilidad con los flujos de trabajo de creación de actividades. (TGT-53061)
* **El VEC mostraba una pantalla en blanco al editar experiencias**: Los clientes de un determinado inquilino informaron de que la pantalla del VEC se quedaba en blanco al intentar editar experiencias en el VEC actualizado. Este problema afectaba tanto a las actividades recién creadas como a las más antiguas, lo que impedía la continuidad del flujo de trabajo. El VEC ahora se carga correctamente, lo que permite a los clientes editar experiencias sin interrupción. (TGT-53547)
* **El VEC se bloqueó y mostró una pantalla en blanco al cargar ciertas actividades**: Los clientes de un determinado inquilino informaron que el VEC no pudo cargar actividades específicas. El editor de experiencias permaneció atascado en &quot;Aplicación de modificaciones iniciales&quot; antes de bloquearse y mostrar una pantalla en blanco. Los errores de consola indicaron un error al leer las propiedades no definidas. El editor ahora carga las actividades afectadas sin errores en el VEC actualizado. (TGT-53548)
* **Borrar todos los valores de fecha usando Retroceso provocó que la página se bloqueara**: Los clientes que programan actividades en la sección [!UICONTROL Objetivos y configuración] experimentaron un bloqueo al usar Retroceso para borrar todos los valores de los campos &quot;[!UICONTROL Fecha y hora especificadas]&quot;. Este problema se debía a un error de referencia nulo en la lógica de control de fechas. La página ahora administra correctamente las entradas de fecha vacías sin bloqueos. (TGT-53624)
* **No apareció ningún producto en [!UICONTROL Búsqueda en el catálogo de productos] debido a una carga útil no válida**: Los clientes que accedieron a la sección [!UICONTROL Recommendations] en [!UICONTROL Búsqueda en el catálogo de productos] encontraron resultados vacíos causados por una carga útil de GraphQL no válida. Este error de servidor impedía que los datos del producto se cargaran correctamente. Los productos ahora se muestran según lo esperado en la IU actualizada. (TGT-53630)
* Se guardaron **[!DNL Scene7]imágenes con menor resolución en el VEC actualizado**: Los clientes que editaban experiencias en el VEC actualizado observaron que las URL de imagen de [!UICONTROL Scene7] se guardaron sin parámetros de resolución, lo que resultó en imágenes de menor calidad entregadas (400×400 en lugar de las 800×800 previstas). Las direcciones URL con imágenes ahora conservan los parámetros correctos para garantizar una resolución adecuada. (TGT-52631)
* **Las actividades en vivo aún no se pudieron editar en el VEC**: Los clientes pudieron acceder a las opciones de edición para actividades en vivo en el VEC actualizado, lo que podría conducir a cambios no deseados. Este problema se ha resuelto deshabilitando la funcionalidad de edición para las actividades activas. Los botones de edición ahora están ocultos en la lista de actividades y en la descripción general para los editores, mientras que los aprobadores y otras funciones no se ven afectados. (TGT-53055)
* **Se han retirado las actividades [!UICONTROL fallidas] y [!UICONTROL en borrador] de la sección actualizada del VEC**: Las opciones de actividades [!UICONTROL fallidas] y [!UICONTROL en borrador] se han eliminado del VEC actualizado. La nueva IU ya no admite estados de borrador y las campañas que dan error no se almacenan en el servidor. Estas opciones ya no son relevantes. Los filtros relacionados y los campos de back-end (por ejemplo, `uiSyncFailed`, `errorMessage`) también se han eliminado para optimizar la administración de la actividad. (TGT-53150)
* **No se puede iniciar sesión en el VEC para una actividad**: Los clientes que intentaban iniciar sesión en su sitio a través del VEC fueron redirigidos repetidamente a la página de inicio de sesión, lo que impidió el acceso a la edición de la actividad. Este problema no se podía reproducir internamente y podría haber estado relacionado con la gestión de sesiones en el sitio. El flujo de inicio de sesión se ha estabilizado y los clientes ahora pueden acceder al VEC sin errores de redirección. (TGT-53524)
* **Pulsar el botón Atrás dos veces en el modo [!UICONTROL Examinar] provocó el bloqueo del VEC**: Los clientes que navegaban a través del modo [!UICONTROL Examinar] en el VEC experimentaron bloqueos al pulsar dos veces el botón Atrás del explorador. Este problema provocaba que el editor se bloqueara y requiriera una actualización de la página. El editor ahora gestiona la navegación trasera de forma fiable sin bloqueos. (GT-53568)
* **No se pudieron editar las actividades debido a asignaciones de ubicación no definidas**: los clientes encontraron un error al intentar editar las actividades, debido a identificadores de ubicación no definidos en la lógica `LocationMapping.behaviorTargetedActivity`. Este problema provocaba un error 400 y bloqueaba las actualizaciones de la actividad. Ahora, las actividades se pueden editar sin errores de validación relacionados con la ubicación. (TGT-53607)
* **Al guardar actividades, se produjo un error de entrada de usuario no válido**: Los clientes encontraron un error de entrada de usuario no válido al intentar guardar actividades después de realizar modificaciones menores en el VEC actualizado. El error se debía a asignaciones de ubicación no coincidentes en la lógica de validación del servidor. Ahora, las actividades se pueden guardar correctamente sin activar errores relacionados con la ubicación. (TGT-53603)

+++

### [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!UICONTROL Actividades]**

+++Ver detalles

* **Se ha corregido un problema por el cual al guardar actividades se activaba un error de entrada de usuario no válido debido a datos de propiedad con formato incorrecto**: Los clientes encontraban un error crítico al intentar guardar actividades existentes. El mensaje de error indicaba una entrada de usuario no válida, que hacía referencia específicamente a un contenido de nombre de propiedad no reconocido en la carga útil JSON. En particular, las nuevas actividades que utilizan la misma propiedad se guardaron correctamente, lo que sugiere que el problema se aisló en los datos de actividad heredados. El proceso de creación de actividades ahora gestiona correctamente las configuraciones de propiedades heredadas, lo que evita errores de entrada no válidos y garantiza un comportamiento de guardado coherente en las actividades nuevas y existentes. (TGT-53507)
* **Se ha corregido un problema que impedía que los clientes guardaran una actividad debido a un error InvalidProperty.Json**: Los clientes encontraron un error al intentar guardar una actividad en la interfaz de usuario actualizada, incluso sin realizar ninguna modificación. El mensaje de error indicaba una estructura JSON no válida: &quot;JSON no válido. Nombre de propiedad &#39;content&#39; no reconocido. Ubicación: línea - 1, columna - 432&quot;. Este problema se debía a una propiedad no reconocida en la carga útil de la solicitud y ahora se ha resuelto. Los clientes pueden guardar las actividades correctamente sin encontrar este error. (TGT-53513)
* **Se ha corregido un problema por el cual las actividades programadas mostraban incorrectamente un estado [!UICONTROL Activo] hasta que se actualizó la página**: Los clientes observaban que, al programar una actividad para que se ponga en marcha en una fecha y hora futuras, el estado aparecía inmediatamente como [!UICONTROL Activo] en lugar de [!UICONTROL Programado]. Esto causaba confusión, aunque el mensaje de confirmación indicaba correctamente que la actividad estaba programada. Al actualizar la página, se corrigió la visualización del estado. Este problema se ha resuelto y las actividades programadas muestran correctamente el estado Programado sin necesidad de actualizar. (TGT-52937)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Ver detalles

* **Se ha corregido un problema por el cual los clientes no podían escribir nombres de grupos de informes durante el proceso de creación de actividades**: Los clientes que usaban [!DNL Adobe Analytics] como fuente de informes durante el proceso de creación de actividades no podían escribir en la lista desplegable [!UICONTROL Grupo de informes] para buscar grupos de informes específicos. Esto afectaba a los flujos de trabajo de las organizaciones con un gran número de grupos de informes, donde el desplazamiento manual retrasaba considerablemente la configuración. La lista desplegable no se ordenaba alfabéticamente y no respondía de forma coherente a la entrada escrita, lo que dificultaba la localización de grupos de informes como &quot;Office + Tienda - Web - Producción&quot;. Este problema se ha resuelto y los clientes ahora pueden buscar de forma eficaz escribiendo los nombres de los grupos de informes. (TGT-53345)

+++

**[!UICONTROL Públicos]**

+++Ver detalles

* **Se ha corregido un problema por el cual las audiencias de &quot;Lapso de tiempo&quot; caducadas bloqueaban el guardado de actividades incluso después de su eliminación**: Los clientes no podían guardar actividades en la interfaz de usuario actualizada debido a un error relacionado con las audiencias de &quot;Lapso de tiempo&quot; caducadas. Incluso después de eliminar la audiencia afectada, el mensaje de error persistió: &quot;La actividad contiene una audiencia con un lapso de tiempo no válido&quot;. Este problema se producía porque el sistema seguía validando la audiencia solo de actividad, incluso cuando ya no estaba en uso. El comportamiento se complicó aún más por las discrepancias de zona horaria. La lógica de validación se ha corregido y los clientes ahora pueden guardar actividades sin encontrar este error. (TGT-53517)

+++

**[!UICONTROL Fragmento de experiencia]s**

+++Ver detalles

* **Se ha corregido un problema que impedía a los clientes insertar fragmentos de experiencias usando [!UICONTROL Insertar antes] o [!UICONTROL Insertar después] en la interfaz de usuario**. Los clientes encontraban un error al intentar insertar [!UICONTROL Fragmentos de experiencias] en una actividad mediante las opciones &quot;Insertar antes&quot; o &quot;Insertar después&quot; en la interfaz de usuario actualizada. El mensaje de error mostrado era: &quot;El contenido de la oferta debe contener exactamente un elemento de HTML&quot;. Este problema era específico de la interfaz de usuario actualizada y no se producía en la versión anterior. Este problema ya se ha resuelto y los clientes pueden insertar [!UICONTROL Fragmentos de experiencias] correctamente sin encontrar este error. (TGT-53442)

+++

**[!UICONTROL Decisiones de oferta]**

+++Ver detalles

* **Se ha corregido un problema que impedía que los clientes editaran ofertas de decisión y seleccionaran elementos de página específicos en la interfaz de usuario actualizada**: en el proceso de creación de actividades actualizado, los clientes no podían editar ofertas de decisión existentes ni seleccionar elementos de página específicos en el Compositor de experiencias visuales (VEC). Las ofertas de decisión se mostraban incorrectamente como ofertas de HTML y los cambios realizados durante la edición no se guardaban. Además, ciertas direcciones URL regionales, como el sitio de Japón, no se cargaban correctamente en el VEC, lo que bloqueaba la creación y las actualizaciones de actividades. Las ofertas de decisión ahora se muestran correctamente, los elementos de página se pueden seleccionar según lo esperado y las URL regionales se cargan correctamente en el VEC, lo que restaura la funcionalidad de edición completa. (TGT-53425)
* **Se ha corregido un problema por el cual los selectores [!UICONTROL Decisión de oferta] no se podían modificar ni cambiar inesperadamente después de guardar**: en el proceso actualizado de creación de actividades, los clientes no podían modificar el selector [!UICONTROL Decisión de oferta] según lo previsto. Los intentos de cambiar el selector no se han realizado correctamente y el selector se ha revertido a un valor incorrecto después de guardar. Este comportamiento provocaba que la oferta de decisión desapareciera del Compositor de experiencias visuales (VEC), lo que bloqueaba futuras ediciones. Los cambios de selector ahora se conservan correctamente, y las ofertas de decisión siguen siendo visibles y editables en el VEC después de guardar. (TGT-53433)
* **Se ha corregido un problema por el cual [!UICONTROL Decisiones de oferta] desaparecían de la actividad después de guardarla**: Las [!UICONTROL Decisiones de oferta] agregadas durante el proceso de creación de actividad no se conservaban después de guardar y volver a abrir la actividad. Este problema se producía al editar contenido dinámico e insertar [!UICONTROL Decisiones de oferta]con selectores y propiedades específicos. Las [!UICONTROL Decisiones de oferta] ahora persisten correctamente después de guardar y los selectores permanecen intactos, lo que garantiza un comportamiento de edición y direccionamiento coherente. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Ver detalles

* **Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el que la descarga de CSV con criterios personalizados arrojaba el error 404**: se ha corregido un problema por el que los clientes no podían descargar el CSV con criterios personalizados en el proceso de creación de actividades. El vínculo de descarga ahora funciona correctamente, lo que permite a los clientes exportar criterios personalizados según lo esperado. (TGT-51966)
* **Se ha corregido una carga incoherente de imágenes en [!UICONTROL Búsqueda en el catálogo]**: se ha corregido un problema por el que las miniaturas y las imágenes de[!UICONTROL &#x200B; Búsqueda en el catálogo] no se cargaban de forma coherente en el proceso de creación de actividades. Las imágenes no aparecían a menos que la columna &quot;URL en miniatura&quot; estuviera visible y algunas imágenes de producto se cargaran parcialmente o no se cargaran después de las acciones de navegación o búsqueda. El comportamiento de carga de imágenes se ha estabilizado y las miniaturas ahora se muestran de forma fiable, independientemente de la visibilidad de la columna o las acciones de navegación. (TGT-52778)
* **Se ha corregido un problema por el cual editar una recomendación en una experiencia duplicada afectaba a la experiencia original**: Los clientes notificaron que modificar una recomendación en una experiencia duplicada alteraba involuntariamente la experiencia original. En concreto, después de duplicar la Experiencia B en el proceso de creación de actividades y editar su diseño o criterios, los mismos cambios se reflejaron en la Experiencia B original, a pesar de ser entidades independientes. Las experiencias duplicadas ahora mantienen configuraciones independientes, lo que garantiza que las ediciones realizadas en una experiencia no afecten a la original. (TGT-53369)
* **Se ha corregido un problema por el cual los cambios realizados en una experiencia duplicada afectaban involuntariamente a la experiencia original de una actividad**: Los clientes notificaron que, al duplicar una experiencia dentro de una actividad y asignar una nueva audiencia, cualquier cambio realizado en el diseño o los criterios de la experiencia duplicada también se reflejaba en la experiencia original. Este problema se producía aunque no se realizaban ediciones directamente en la versión original, lo que afectaba a la capacidad de crear variaciones independientes dentro de la misma actividad. El proceso de creación de actividades ahora aísla correctamente las experiencias duplicadas, asegurándose de que las ediciones realizadas en una experiencia no afecten a la experiencia original. (TGT-53361)
* **Se ha corregido un problema por el que el [!UICONTROL Catálogo de recomendaciones] fallaba de forma intermitente a la hora de mostrar datos completos de atributos del producto**: en la interfaz de usuario de [!DNL Recommendations] actualizada, los clientes experimentaban un problema por el que algunos atributos de productos, como el mensaje, no se mostraban de forma coherente en los resultados de [!UICONTROL Búsqueda en el catálogo], aunque los datos existían en la fuente. Este problema requería que los clientes reconfiguraran manualmente la visibilidad de la columna para recuperar los valores que faltaban. [!UICONTROL La búsqueda en el catálogo] ahora muestra de forma fiable todos los atributos configurados, lo que elimina la necesidad de restablecer manualmente las columnas. (TGT-52769)
* **Se ha corregido un problema por el que una [!UICONTROL promoción principal] no se podía deshabilitar en una actividad activa**: no se guardaron los intentos de deshabilitar una [!UICONTROL promoción principal] en una actividad activa. Después de seleccionar [!UICONTROL Cambiar promoción] y deshabilitarla, la promoción permaneció activa al volver a editar la actividad, lo que impidió que se actualizaran las configuraciones de recomendación. La configuración de la promoción ahora se guarda correctamente, lo que permite a los clientes deshabilitar o modificar las promociones en actividades activas según lo esperado. (TGT-53231)
* **Se ha corregido un problema que causaba que, al habilitar una [!DNL Recommendations] [!UICONTROL Promoción] sin datos, se generara un mensaje de error no claro**: al habilitar una [!UICONTROL Promoción principal] o [!UICONTROL Promoción secundaria] en una actividad [!DNL Recommendations] sin especificar los valores necesarios, se generaba un mensaje genérico de &quot;Error de entrada no válido&quot;. El problema subyacente era un campo de configuración que faltaba, pero el mensaje de error no indicaba claramente la causa, lo que dificultaba la resolución de problemas. El proceso de creación de actividades ahora proporciona un mensaje de error claro y procesable cuando faltan campos obligatorios, como `collectionId` o reglas, lo que ayuda a los clientes a identificar y resolver problemas de configuración rápidamente. (TGT-52616)
* **Se ha corregido un problema que impedía que la lista [!UICONTROL Producto] se mostrara en el modal [!UICONTROL Editar] dentro de la pestaña [!UICONTROL Recomendaciones]**: Los clientes no podían ver la lista de productos filtrados al editar una [!UICONTROL colección] o [!UICONTROL exclusión] en la pestaña [!UICONTROL Recomendaciones]. Se esperaba que la lista se actualizara en tiempo real en función de las reglas aplicadas, pero no pareció como estaba previsto. Este problema se ha resuelto y la lista de productos ahora se muestra correctamente y se actualiza dinámicamente a medida que se modifican las reglas. (TGT-53481)
* **Se ha corregido un problema con el diseño del cuadro de diálogo Ver detalles en la interfaz de usuario actualizada**: el diseño del modal Ver detalles en la interfaz de usuario actualizada se ha modificado para mejorar la claridad y la facilidad de uso. El cuadro de diálogo ahora incluye dos pestañas:
  * Pestaña [!UICONTROL Detalles]: muestra toda la información relevante para el elemento seleccionado.
  * Pestaña [!UICONTROL Inventario]: muestra todos los productos filtrados por las reglas de recopilación y exclusión actuales.

  Esta mejora ayuda a los clientes a navegar y comprender mejor los datos específicos de los artículos y el contexto del inventario dentro del proceso de creación de actividades. (TGT-53503)

  * **Se ha corregido un problema por el cual las promociones eliminadas en las actividades de recomendación volvían a aparecer después de guardar**: Los clientes notificaron que cuando las promociones [!UICONTROL front] o [!UICONTROL back] se eliminaron de las actividades [!DNL Recommendations] y se guardó la actividad, las promociones seguían apareciendo al volver a abrirse. Este problema se producía en los entornos de ensayo y producción y afectaba al proceso de creación de actividades actualizado. El problema se ha resuelto. Las promociones que se eliminan de una actividad ahora se mantienen correctamente después de guardar. (TGT-53490)

+++

**Informes**

+++Ver detalles

* **Se ha corregido un problema por el que el informe [!UICONTROL Segmentos automatizados] mostraba valores de audiencia nulos**: Los clientes notificaron que [!UICONTROL Segmentos automatizados] en los informes de actividad mostraban valores nulos para los datos de audiencia, lo que impedía realizar análisis precisos del rendimiento del segmento. Este problema ocurría al acceder a la sección [!UICONTROL Informes] y seleccionar [!UICONTROL Segmentos automatizados], aunque se esperaban datos de audiencia válidos. [!UICONTROL Segmentos automatizados] ahora muestra correctamente los valores de audiencia, lo que garantiza perspectivas de segmentación y creación de informes fiables. (TGT-52793)

+++

**Aplicaciones de una sola página (SPA)**

+++Ver detalles

* **Se ha corregido un problema que causaba que al cambiar entre los modos [!UICONTROL Examinar] y [!UICONTROL Diseño] se restableciera el estado de SPA en la interfaz de usuario actualizada**: Los clientes informaron de que al cambiar entre los modos [!UICONTROL Examinar] y [!UICONTROL Diseño] en la interfaz de usuario actualizada, el editor web se volvía a cargar y se restablecía el estado de las SPA. Este problema interrumpía los flujos de trabajo y requería que los clientes volvieran a introducir la información. El problema se ha resuelto. El estado de SPA ahora se conserva al alternar entre modos, lo que garantiza una experiencia más fluida y coherente durante la creación de la actividad. (TGT-53074)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* **Se ha corregido un problema en el proceso de creación de actividades que bloqueaba la progresión al paso [!UICONTROL Segmentación] en las actividades AP**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían continuar con el paso [!UICONTROL Segmentación] en las actividades [!UICONTROL Automated Personalization] (AP) a menos que se agregaran dos ubicaciones. Este comportamiento difería de la experiencia anterior, en la que una sola ubicación con varias ofertas era suficiente. El requisito se ha corregido, lo que permite a los clientes seguir utilizando configuraciones de una sola ubicación como parte de sus flujos de trabajo de AP. (TGT-53426)
* **Se ha corregido un problema por el que el nuevo proceso de creación de actividades no establecía el parámetro fmt=png-alpha para imágenes transparentes**: En la interfaz de usuario actualizada, las imágenes insertadas durante el proceso de creación de actividades ya no incluían el parámetro `fmt=png-alpha` de forma predeterminada, lo que resultaba en una pérdida de transparencia. Este comportamiento difería del de la IU anterior, que añadía automáticamente el parámetro a las direcciones URL de la imagen, conservando los fondos transparentes. El proceso de creación de actividades ahora aplica correctamente el parámetro `fmt=png-alpha` a las direcciones URL de las imágenes cuando se requiere transparencia, lo que garantiza la representación coherente de los recursos transparentes. (TGT-52615)
* **Se ha corregido un problema que impedía a los clientes buscar grupos de informes en la interfaz de usuario actualizada**: en la interfaz de usuario actualizada, la lista desplegable [!UICONTROL Grupos de informes] de la sección [!UICONTROL Objetivos y configuración] no permitía a los clientes escribir y buscar, lo que dificultaba la localización de grupos de informes específicos, especialmente para inquilinos con un gran número de entradas. A diferencia de la IU anterior, la lista no se ordenaba y carecía de filtrado basado en la entrada. Se ha corregido este problema. Los clientes ahora pueden escribir para buscar y filtrar grupos de informes, restaurando la funcionalidad disponible en la interfaz de usuario heredada. (TGT-53514)

+++

**[!UICONTROL Espacios de trabajo]**

+++Ver detalles

* **Se ha corregido un problema en el cual un cliente restringido a un solo espacio de trabajo podía ver actividades desde otros espacios de trabajo**: Los clientes con acceso limitado a un espacio de trabajo inesperadamente podían ver actividades en todos los espacios de trabajo al seleccionar [!UICONTROL Todos los espacios de trabajo] en el proceso de creación de actividades. Esta visibilidad planteaba el riesgo de cambios no deseados en las actividades activas en otros espacios de trabajo, lo que podría afectar al rendimiento del sitio web. Los controles de acceso de Workspace se han reforzado para garantizar que los clientes puedan ver e interactuar únicamente con las actividades dentro del espacio de trabajo asignado. (TGT-53101)
* **Se ha corregido un problema que causaba que un cliente pudiera ver actividades desde [!UICONTROL Workspace predeterminado] sin tener acceso:** Un cliente con acceso limitado al área de trabajo de ensayo pudo ver actividades desde [!UICONTROL Workspace predeterminado] mediante el proceso de creación de actividades. Este comportamiento se produjo a pesar de la configuración back-end y los derechos de acceso correctos. Los controles de acceso de Workspace se han reforzado para garantizar que los clientes puedan ver las actividades solo dentro de su espacio de trabajo asignado. (TGT-53297)

+++

### [!DNL Target Standard/Premium] 25.8.2 (14 de agosto de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

**[!UICONTROL Actividades]**

+++Ver detalles

* **Se ha corregido un problema con la carga de actividades en la interfaz de usuario [!DNL Target] actualizada**: se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual algunas actividades no se cargaban al intentar editar. Este problema provocaba que los clientes dejaran a los usuarios en una pantalla de carga indefinida. Este problema afectaba a varias actividades y se notificaba que se producía de forma incoherente entre los clientes. Con esta corrección, las actividades afectadas ahora se cargan correctamente, lo que permite una edición sin problemas y reduce la interrupción de los flujos de trabajo de actividad. (TGT-53209)
* **Se ha corregido un error de guardado en el proceso de creación de actividad debido a la validación de `optionLocalId`**: se ha corregido un problema en el proceso de creación de actividad que impedía a los clientes guardar cambios debido a un error de validación de back-end: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Este problema se producía al modificar elementos específicos dentro de una actividad, lo que resultaba en una operación de guardado fallida. La corrección garantiza que las referencias de `optionLocalId` ahora se validen correctamente, lo que permite a los clientes guardar actividades sin encontrar este error. (TGT-53293)
* **Se ha corregido un bloqueo en el proceso de creación de actividades debido a referencias de opciones no válidas al cambiar de página**: se ha corregido un problema en el proceso de creación de actividades que hacía que la interfaz de usuario se bloqueara después de cambiar de página tres veces durante la edición. El bloqueo se activó por referencias de opciones no válidas, lo que dio como resultado errores de consola como &quot;No se encontró la opción con localId &#39;7&#39;&quot;. Con esta actualización, los clientes ahora pueden cambiar de página y aplicar modificaciones sin encontrar errores o interrupciones del sistema. (TGT-53295)
* **Se ha corregido un error de guardado en el proceso de creación de actividades debido a una entrada no válida del usuario al editar experiencias**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían guardar cambios en una actividad debido a un error no válido de entrada del usuario. El error se producía al modificar experiencias en la interfaz de usuario actualizada, lo que impedía que se confirmaran las actualizaciones. La actividad ahora se puede guardar correctamente, lo que permite a los clientes editar y publicar sin interrupción. (TGT-53267)
* **Se ha corregido un problema de carga en el proceso de creación de actividades que bloqueaba la edición en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades en el cual los clientes no podían editar actividades en la IU actualizada debido a una pantalla de carga continua. Los clientes ahora pueden abrir y modificar actividades sin encontrar errores de carga. (TGT-53415)
* **Se ha corregido un problema con los requisitos de experiencia en el proceso de creación de actividades para actividades AP en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades por el que las actividades [!UICONTROL Automated Personalization] (AP) requerían dos ubicaciones en lugar de dos experiencias en la IU actualizada. Este comportamiento bloqueaba los casos de uso en los que los clientes configuraban una sola ubicación con varias ofertas, lo que era compatible anteriormente. El requisito se ha corregido para que coincida con la funcionalidad original, lo que permite a los clientes continuar con actividades AP utilizando dos experiencias independientemente del recuento de ubicación. (TGT-53429)
* **Se corrigió el comportamiento del campo de elemento rastreado en el modo de rastreo de clics para evitar entradas no guardadas y mejorar la claridad**: se corrigió un problema en el proceso de creación de actividades en el cual el campo [!UICONTROL Elemento rastreado] en el modo [!DNL Click Track] era editable, pero no conservaba el nombre introducido, lo que causaba confusión a los clientes. El campo ahora está desactivado para evitar entradas no guardadas, y se ha aclarado la denominación de los elementos seleccionados para mejorar la configuración del objetivo y la precisión del seguimiento.** (TGT-53458)
* **Se ha corregido un problema en el proceso de creación de actividades que bloqueaba la asignación de nombres a los componentes rastreados en el modo [!UICONTROL Click Track]**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían asignar nombres a los componentes rastreados en el modo [!UICONTROL Click Track]. Después de introducir un nombre, el campo parecía editable, pero no conservaba la entrada, por defecto tenía etiquetas genéricas como &quot;MI OBJETIVO PRINCIPAL 0&quot; en modo de edición. El campo de elemento rastreado ahora está desactivado y se ha aclarado el comportamiento de nomenclatura para mejorar la configuración del objetivo y la precisión del seguimiento. (TGT-51396)

+++

**Fragmentos de experiencias (XF)**

+++Ver detalles

* **Se ha corregido un problema en el proceso de creación de actividades que permitía la edición no intencionada de fragmentos exportados por AEM mediante HTML**: se ha corregido un problema en el proceso de creación de actividades que permitía a los clientes editar el HTML de [!DNL Experience Fragments] (XF) exportado desde [!DNL Adobe Experience Manager] (AEM) en [!DNL Target]. Este comportamiento no fue intencionado, ya que los archivos XF deberían permanecer bloqueados para su edición una vez publicados desde AEM. La corrección garantiza que la opción &quot;Editar HTML&quot; ya no esté disponible para los fragmentos exportados por AEM, lo que preserva la integridad del contenido y el control esperado. (TGT-53286)
* **Se ha corregido un problema intermitente de vista previa del contenido XF en el proceso de creación de actividades en la interfaz de usuario actualizada**: se ha corregido un problema en el proceso de creación de actividades por el que el contenido XF fallaba intermitentemente al procesarse en el modo de vista previa en la interfaz de usuario actualizada. Aunque el contenido se entregaba correctamente, la previsualización no se mostraba de forma coherente, lo que dificultaba a los clientes validar la configuración de la oferta. Las previsualizaciones de XF ahora se cargan de forma fiable, lo que mejora la confianza y la eficacia durante la configuración de la actividad. (TGT-53318)

+++

**Modo de control de calidad**

+++Ver detalles

* **Se ha corregido un problema en el proceso de creación de actividades por el que los espacios iniciales en las direcciones URL provocaban vínculos de control de calidad rotos**: se ha corregido un problema en el proceso de creación de actividades por el que los espacios iniciales en la dirección URL de la actividad no se recortaban correctamente al guardar. Esto provocaba vínculos de control de calidad no válidos y un formato incorrecto en el back-end. Después de la actualización, las direcciones URL ahora se guardan correctamente, lo que evita que se rompan los vínculos y mejora la fiabilidad de los flujos de trabajo de control de calidad para los clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles

* **Se ha corregido un problema en la interfaz de usuario de la búsqueda en el catálogo en el cual la búsqueda avanzada no podía proporcionar sugerencias**: se ha corregido un problema en la nueva interfaz de usuario de [!UICONTROL Búsqueda en el catálogo] en el que la característica [!UICONTROL Búsqueda avanzada] no podía proporcionar sugerencias. Los usuarios tenían que introducir valores exactos con una ortografía precisa, lo que hacía que la experiencia de búsqueda fuera engorrosa y propensa a errores. Con esta corrección, la [!UICONTROL Búsqueda avanzada] ahora ofrece sugerencias relevantes a medida que los usuarios escriben, mejorando la facilidad de uso y reduciendo la fricción en la localización de productos. (TGT-52008)
* **Se han resuelto varios problemas de filtrado e interfaz de usuario para mejorar la capacidad de respuesta y la interacción con la entidad**: se han resuelto varios problemas, incluida la respuesta deficiente de los detalles de criterios en dispositivos de pantalla pequeña, la falta de resultados al seleccionar &quot;Todos los grupos de hosts&quot; en el filtro Entorno y la incapacidad para interactuar con entidades que no tienen nombre. Estas correcciones mejoran la facilidad de uso en todos los tamaños de pantalla, garantizan un filtrado preciso y permiten la interacción completa con todas las entidades de producto, lo que mejora la experiencia general para los usuarios. (TGT-52992)
* **Se han corregido los ID de producto que faltaban en la vista de detalles de Recommendations durante la creación de la actividad**: se ha corregido un problema en el proceso de creación de actividades [!DNL Recommendations] por el que los ID de producto faltaban en la pantalla de detalles del producto, lo que dificultaba a los clientes copiar o hacer referencia a los ID de producto durante los flujos de trabajo. Los ID de producto ahora aparecen claramente en la vista de detalles, lo que mejora la visibilidad y admite una administración de productos más eficiente para los clientes. (TGT-51964)
* **Se ha corregido un problema en el proceso de creación de actividades por el que no se mostraban mensajes de productos en la vista de recomendaciones**: se ha corregido un problema en el proceso de creación de actividades por el que la columna [!UICONTROL Mensaje] de la vista [!DNL Recommendations] no mostraba datos de productos, aunque hubiera mensajes presentes. Los clientes tenían que eliminar manualmente y volver a añadir la columna para mostrar temporalmente el contenido, que a menudo volvía a desaparecer al desplazarse o buscar. Esta actualización restaura la visibilidad coherente de los mensajes del producto, lo que mejora la navegación por el catálogo y revisa los flujos de trabajo. (TGT-52777)
* **Se ha corregido un problema en el proceso de creación de actividades por el que al seleccionar &#39;Todos los grupos de hosts&#39; no se obtenían resultados en la vista de recomendaciones**. Se ha corregido un problema en el proceso de creación de actividades por el que al seleccionar el entorno &quot;Todos los grupos de hosts&quot; en la vista [!DNL Recommendations] no se obtenían resultados. Los clientes ahora pueden ver los datos de productos en todos los grupos de hosts según lo esperado, lo que mejora la visibilidad y la precisión del filtrado durante la configuración de la actividad. (TGT-53006)
* **Se corrigió un problema en el proceso de creación de actividades en el cual la opción de promoción principal no persistía después de guardar**: se corrigió un problema en el proceso de creación de actividades en el cual, al deshabilitar la opción de promoción principal en la configuración de actividades, no persistía después de guardar. Los clientes que intentaban eliminar la promoción principal encontraban la opción habilitada de nuevo al volver a visitar la actividad, lo que impedía una personalización adecuada. Esta actualización permite guardar los cambios de forma fiable, lo que permite a los clientes un control total de la configuración de la promoción. (TGT-53215)
* **Se ha corregido una ordenación incoherente por la columna [!UICONTROL Última actualización]:** Se ha corregido un problema en el proceso de creación de actividades por el que la ordenación del catálogo por la columna [!UICONTROL Última actualización] producía resultados incoherentes. Los clientes no podían organizar los datos de productos de forma fiable en función de las marcas de tiempo de actualización, lo que dificultaba la revisión y administración del catálogo. La ordenación ahora funciona según lo esperado, lo que mejora la precisión y la facilidad de uso en la IU actualizada. (TGT-53116)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* **Se corrigieron problemas con la carga de actividades y el botón [!UICONTROL Cancelar] en el proceso de creación de actividades**: se corrigió un problema en el proceso de creación de actividades en el cual ciertas actividades no se cargaban, lo que impedía a los clientes acceder a las modificaciones. Además, el botón [!UICONTROL Cancelar] no responde, lo que impide que los clientes detengan el proceso de carga o salgan de la vista de edición. Esta corrección garantiza que las actividades ahora se carguen de forma fiable y que el botón [!UICONTROL Cancel] funcione según lo esperado, lo que mejora la estabilidad general y la experiencia del usuario en el Compositor de experiencias visuales. (VEC)(TGT-53218)
* **Se ha corregido un problema con el cambio de experiencia en la interfaz de usuario de VEC actualizada que bloqueaba la edición y deshabilitaba el botón [!UICONTROL Cancelar]**: se ha corregido un problema en la interfaz de usuario de VEC actualizada por el que las modificaciones no se cargaban al cambiar entre experiencias en una actividad de Segmentación de experiencias (XT). Los clientes no podían editar experiencias que no fueran la que habían introducido inicialmente y el botón [!UICONTROL Cancelar] no se mostraba o no respondía. Esta corrección garantiza que las modificaciones ahora se carguen correctamente en todas las experiencias y que el botón [!UICONTROL Cancelar] funcione de forma fiable, incluso sin la extensión del Asistente, lo que mejora los flujos de trabajo de edición y reduce la frustración. (TGT-53256)
* **Se corrigió un problema con la pantalla en blanco al cambiar entre varias experiencias en el proceso de creación de actividades**: se corrigió un problema por el cual el cambio entre varias experiencias provocaba la aparición de una pantalla en blanco. También se ha corregido un problema en el proceso de creación de actividades en el que los clientes encontraban una pantalla blanca al intentar modificar varias experiencias dentro de una actividad. Este problema se producía después de aplicar cambios a dos experiencias y seleccionar una tercera experiencia, lo que impedía realizar más ediciones. La actualización garantiza transiciones fluidas entre experiencias, lo que permite a los clientes realizar modificaciones sin interrupciones. (TGT-53266)
* **Se ha corregido un problema en el VEC por el cual los cambios en el código personalizado no se guardaban de forma fiable entre sesiones de edición**: se ha corregido un problema por el que las modificaciones de código personalizado realizadas en el Compositor de experiencias visuales (VEC) no se guardaban de forma fiable en un solo intento. Los clientes informaron que los cambios, como las actualizaciones de estilo o la edición de HTML, faltaban intermitentemente en el sitio web y las direcciones URL de control de calidad, incluso después de usar los botones [!UICONTROL Editar contenido] y [!UICONTROL Guardar] finales. Esta regresión se ha resuelto para garantizar que todos los cambios en el código personalizado persistan según lo esperado en las sesiones de edición.** (TGT-53418)
* **Se ha corregido el error que faltaba `triggerViews` en la interfaz de usuario actualizada durante la creación de la actividad**: se ha corregido un problema en el proceso de creación de actividades por el que `triggerViews` no aparecían en la interfaz de usuario actualizada, aunque se hubieran implementado correctamente en la página. Esto afectó a varios clientes y dificultó la validación de déclencheur basados en vistas durante la configuración de la actividad. `TriggerViews` ahora se muestra según lo esperado, lo que permite a los clientes completar y probar sus configuraciones de forma fiable. (TGT-53239)
* **Se ha corregido un problema de carga de vistas en el proceso de creación de actividades para páginas web específicas en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades por el que las vistas no se cargaban en la IU actualizada para páginas web específicas, a pesar de estar correctamente implementadas y ser visibles en las llamadas de entrega o de interacción. Esto afectaba a varios clientes y dificultaba la validación de la segmentación basada en vistas. Las vistas ahora se rellenan de forma coherente en todas las páginas compatibles, lo que mejora la fiabilidad durante la configuración de la actividad. (TGT-53246)
* **Se ha corregido un problema intermitente de carga de vistas en el proceso de creación de actividades en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades por el que las vistas no aparecían de forma intermitente en la IU actualizada durante la edición de actividades. Aunque el nombre de vista correcto estaba presente en la carga útil de red, no se reconocía de forma coherente en la interfaz, lo que afectaba a la capacidad de los clientes para configurar la personalización basada en vistas. Las vistas ahora aparecen de forma fiable, lo que admite flujos de trabajo de configuración y validación más suaves. (TGT-53223)
* **Se ha corregido un problema en el proceso de creación de actividades por el que los nombres de las acciones rastreadas no se guardaban en la IU actualizada**: se ha corregido un problema en el proceso de creación de actividades por el que las métricas de acciones rastreadas no se podían guardar en la IU actualizada. Después de nombrar un elemento rastreado y guardar la actividad, el nombre se restablecería a una etiqueta predeterminada cuando se reabriera, lo que causaría confusión e interrumpiría la configuración del objetivo. Las acciones rastreadas ahora conservan sus nombres asignados, lo que permite a los clientes establecer y administrar métricas de conversión con precisión. (TGT-53453)

+++

### [!DNL Target Standard/Premium] 25.8.1 (7 de agosto de 2025)

Esta versión incluye las siguientes mejoras y correcciones:

**Actividades**

+++Ver detalles

* Se han corregido varios problemas con la interfaz de usuario actualizada, incluidos errores al eliminar tipos de página debido al espaciado en los valores de entrada, la copia de actividades no fiable entre espacios de trabajo y las reglas de entrega de páginas con error en entornos de control de calidad. (TGT-52703)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual los usuarios con el rol [!UICONTROL Editor] podían acceder e intentar editar actividades activas, las cuales deberían restringirse. Las pantallas de lista de actividades y de información general mostraban incorrectamente las opciones de edición para actividades en directo, lo que producía posibles cambios no deseados. (TGT-53055)
* Se ha corregido un problema en la interfaz de usuario de [!UICONTROL Búsqueda avanzada] por el cual al seleccionar los operadores &quot;el valor está presente&quot; o &quot;el valor no está presente&quot; se pedía a los usuarios que ingresaran un operando, que no debería ser necesario para estas condiciones. (TGT-51961)
* Se ha corregido un problema en la IU actualizada por el que los intentos de copiar actividades del espacio de trabajo de ensayo al de producción fallaban de forma consistente, incluso en entornos de zona protegida. Los clientes han encontrado varios mensajes de error, incluidas &quot;Audiencia anónima ya utilizada por la actividad&quot; e &quot;ID de audiencia no válido&quot;, a pesar de usar configuraciones válidas y tener los permisos de espacio de trabajo adecuados. (TGT-52394)

+++

**Fragmentos de experiencias (XF)**

+++Ver detalles

* Se ha corregido un problema por el cual el contenido de fragmento de experiencia (XF) no se podía procesar en la vista previa del [!UICONTROL Compositor de experiencias visuales] (VEC) a pesar de funcionar correctamente en la entrega de contenido. (TGT-53318)

+++

**Localización**

+++Ver detalles

* Se ha corregido un problema de localización en el que el botón Añadir promoción de la sección Promociones aparecía sin localizar en varios entornos de idioma en el inquilino de control de calidad. (TGT-53263)

+++

**Ofertas**

+++Ver detalles

* Se ha corregido un problema en el cual la edición de una oferta de HTML existente a través del Compositor de experiencias visuales (VEC) provocaba que todas las modificaciones se eliminaran de la entrega de contenido. Los cambios aparecen atenuados en la pestaña de modificación y no se reflejan en las vistas previas de control de calidad, a pesar de que se aplican correctamente en la interfaz de usuario heredada. (TGT-52863)
* Se ha corregido un problema en la IU actualizada de [!DNL Target] en el cual las modificaciones de ofertas de HTML realizadas en el [!UICONTROL Compositor de experiencias visuales] (VEC) no persistían después de pasar de la pestaña [!UICONTROL Segmentación] a [!UICONTROL Experiencias]. (TGT-52874)
* Se ha corregido un problema en la IU actualizada de [!DNL Target] por el cual la inserción de una oferta de HTML antes y otra después del mismo selector provocaba una generación de ubicación incorrecta. Cuando los clientes regresaron de la ficha [!UICONTROL Segmentación] a la ficha [!UICONTROL Experiencia], solo se retuvo un selector, lo que resultó en modificaciones perdidas y entrega de contenido interrumpida. Este comportamiento difería de la interfaz de usuario heredada, que conservaba correctamente ambas modificaciones con identificadores de ubicación distintos. (TGT-52891)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada por el cual al hacer clic en una oferta agregada dentro del carril [!UICONTROL Modificaciones], el panel derecho [!UICONTROL Configuración] aparecía y desaparecía intermitentemente, lo que dificultaba la interacción con la configuración de la oferta. (TGT-53288)
* Se ha corregido un problema por el cual las ofertas de HTML agregadas a variaciones específicas de audiencia dentro de una actividad no se guardaban ni aparecían de forma coherente en la sección de modificación. Después de cambiar entre audiencias durante la edición, las ofertas aplicadas anteriormente a veces desaparecían o no se procesaban, lo que interrumpía la validación y retrasaba la preparación de la actividad. (TGT-53440)
* Se ha corregido un problema que causaba que, al copiar una actividad que incluía ofertas, se crearan ofertas duplicadas en la nueva actividad. Este comportamiento causaba un desorden y una confusión innecesarios, especialmente al mover actividades entre espacios de trabajo. La corrección garantiza que las ofertas de [!DNL Target] ahora se copien correctamente en el espacio de trabajo de destino sin duplicación, lo que optimiza la administración de actividades y mejora la eficacia del flujo de trabajo. (TGT-53454)

+++

**Aplicaciones de una sola página (SPA)**

+++Ver detalles

* Se ha corregido un problema en el VEC actualizado que impedía que los clientes aplicaran modificaciones a las vistas de [!UICONTROL Aplicación de una sola página] (SPA). Mientras que las actividades creadas en la IU antigua admitían la segmentación específica de la vista, la nueva IU no detectaba ni permitía las ediciones en esas vistas, con los controles de cambio de vista apareciendo deshabilitados. (TGT-52556)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Se ha corregido un problema por el cual las modificaciones realizadas en las experiencias dentro del [!UICONTROL Compositor de experiencias visuales] no eran visibles o aparecían de forma incoherente en la interfaz de usuario. (TGT-TGT-53381)
* Se ha corregido un problema en el VEC actualizado en el cual la sección [!UICONTROL Administrar contenido] no mostraba texto alternativo para las miniaturas de experiencias. Este problema dificultaba a los usuarios la identificación de documentos, especialmente cuando los nombres de archivo eran largos o estaban truncados. (TGT-52291)
* Se corrigió un error en el cual los clientes encontraban errores de validación incorrectos al configurar las reglas [!UICONTROL envío de página] en las actividades VEC. En concreto, operadores como &quot;es igual a cualquiera de&quot; y &quot;no es igual a ninguno de&quot; activaron &quot;Entrada no válida para el tipo de operador&quot; al introducir valores de texto, aunque se debería admitir texto. (TGT-52629)
* Se han corregido varios problemas que provocaban un comportamiento incoherente en el panel [!UICONTROL Modificaciones] de la interfaz de usuario actualizada al seleccionar ofertas con el botón &quot;Seleccionar una oferta&quot;. En lugar de reemplazar la oferta existente, la interfaz de usuario agregó un duplicado e intentó interactuar con cualquiera de las ofertas, lo que resultó en errores de consola como `selectorNotFound`. Además, algunas ofertas no muestran el botón &quot;Seleccionar una oferta&quot;, que solo muestra propiedades editables. (TGT-53321)
* Se ha corregido un problema en la interfaz de usuario actualizada de [!DNL Target] por el cual los cambios de código de HTML realizados durante la configuración de la actividad no persistían en las páginas de variación, aunque se guardaban correctamente para los grupos de control. A pesar de varios intentos y de volver a crear pruebas sin agrupaciones de páginas, las páginas de variación no conservaban las modificaciones, lo que afectaba a la entrega de contenido y a la validación del control de calidad. (TGT-53436)
* Se ha corregido un problema en el VEC actualizado en el cual el operador &quot;es igual a cualquiera de&quot; en las reglas de entrega de página no acepta valores de entrada. Al configurar los parámetros del cliente en todos los mboxes, seleccionar este operador daba como resultado un error de &quot;Entrada no válida&quot;, lo que impedía la creación de reglas. (TGT-52623)

+++

**Espacios de trabajo**

+++Ver detalles

* Mejora del flujo de trabajo al copiar actividades entre espacios de trabajo. Anteriormente, la copia de actividades entre espacios de trabajo provocaba errores de sincronización debido a la falta de audiencias y a propiedades sin asignar. Esta actualización presenta un flujo de trabajo más inteligente e intuitivo que garantiza que las actividades copiadas estén correctamente configuradas y listas para su publicación. (TGT-47094)
* Se ha corregido un problema en el cual los clientes no podían copiar actividades entre espacios de trabajo debido a un error en la mutación `copyActivityBatchOperations`. Los intentos de duplicar actividades dieron como resultado un error de servidor (500) y una carga de respuesta nula. (TGT-52405)
* Se ha corregido un problema en el cual las actividades no se sincronizaban cuando las ofertas a las que se hace referencia en la configuración no eran accesibles en el espacio de trabajo seleccionado. Esto provocaba errores de publicación y dejaba las actividades en un estado fallido. (TGT-52535)
* Se corrigieron varios problemas al copiar actividades entre espacios de trabajo en la interfaz de usuario [!DNL Target] actualizada. Los clientes encontraron errores relacionados con el acceso a la audiencia, especialmente con las actividades activas y la validación incorrecta de privilegios, incluso cuando el usuario tenía los roles &quot;[!UICONTROL Aprobador]&quot; en los espacios de trabajo de origen y destino. (TGT-53002)
* Se ha corregido un problema en la IU actualizada por el cual la copia de actividades dentro del mismo espacio de trabajo duplicaba de forma innecesaria ofertas y audiencias asociadas. (TGT-53457)
* Se ha corregido un problema que se producía al tratar casos en los que las audiencias ad hoc (anónimas) no se copiaban correctamente entre espacios de trabajo no predeterminados o de espacios de trabajo no predeterminados a predeterminados. Aunque las actualizaciones anteriores garantizaban la duplicación adecuada en los escenarios predeterminados, no predeterminados y del mismo espacio de trabajo, esta mejora se centraba en preservar las configuraciones de audiencia combinadas que abarcan varios espacios de trabajo. La corrección garantiza un comportamiento de audiencia coherente y una segmentación precisa en todas las transiciones del espacio de trabajo. (TGT-53268)

+++

### [!DNL Target Standard/Premium] 25.7.4 (1 de agosto de 2025)

Esta versión resuelve problemas recientes, causados principalmente por las personalizaciones complejas de los clientes, e incluye las siguientes correcciones y mejoras:

**Actividades**

+++Ver detalles

* Se ha corregido un problema en el cual un cliente encontraba el error &quot;Entrada de usuario no válida&quot; al intentar guardar una actividad activa, incluso sin realizar cambios. La respuesta de GraphQL indica un problema de ID local duplicado. (TGT-53329 Y TGT-53373 Y TGT-53195)
* Se ha corregido un problema que impedía crear una experiencia de redireccionamiento en el VEC actualizado. Se ignoró la dirección URL de redireccionamiento y se mostró la página original en su lugar. (TGT-53306)

+++

**Localización**

+++Ver detalles

* Se ha corregido un problema de localización en el modal [!UICONTROL Create Criteria], al seleccionar la opción &quot;entre los siguientes valores&quot; en la lista desplegable [!UICONTROL Elegir regla de precio], se deslocalizó la cadena &quot;a&quot; en la sección [!UICONTROL Reglas de inclusión]. (TGT-49754)
* Se ha corregido un problema de localización con la cadena &quot;[!UICONTROL Todos los grupos de hosts]&quot; en la lista desplegable [!UICONTROL Entorno] del Asistente para la creación de fuentes que no está localizada correctamente. (TGT-46737)

+++

**QA**

+++Ver detalles

* Se ha corregido un problema en el cual el entorno de control de calidad no podía cargar datos en varias pestañas, lo que inutilizaba la interfaz. (TGT-53377)
* Se ha corregido un problema que impedía crear una actividad en el entorno de control de calidad. El proceso se redirigió a la página [!UICONTROL Actividades] en lugar de completarse correctamente. (TGT-53328)

+++

**Recommendations**

+++Ver detalles

* Se corrigió un problema en el cual al pasar el ratón por encima del operando &quot;aprendizaje profundo&quot; mientras se creaba una colección en [!DNL Recommendations], la página se bloqueaba. (TGT-53305)
* Se ha corregido un problema por el cual las sugerencias de filtros en [!UICONTROL Búsqueda en el catálogo] en la IU actualizada eran inexactas. (TGT-52007)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el cual el filtro Operandos aparecía al usar los operadores &quot;el valor está presente&quot; o &quot;el valor no está presente&quot;, aunque debería estar oculto. (TGT-53012)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Se ha corregido un problema que había cuando un usuario hacía clic en [!UICONTROL Administrar contenido] y luego hacía clic en [!UICONTROL Listo] mientras editaba una actividad de Automated Personalization (AP), y la página se quedaba en blanco y no respondía. (TGT-53047 y TGT-52993)
* Se ha corregido un problema por el cual al seleccionar la métrica de conversión [!UICONTROL Visualizó un mbox] en [!UICONTROL Objetivos y configuración] la página se bloqueaba. (TGT-53346, TGT-53343 y TGT-53348)
* Se corrigió un problema en el cual la característica [!UICONTROL Redirigir a la dirección URL] no funcionaba como se esperaba; no se produce ninguna redirección incluso con direcciones URL válidas. (TGT-53307)

+++

**Espacios de trabajo**

+++Ver detalles

* Se ha corregido un problema que se producía al copiar actividades entre espacios de trabajo y que provocaba entradas duplicadas de &quot;Audience Copy&quot; y conflictos de ID. Las audiencias ahora se copian con ID únicos, contexto de espacio de trabajo y control recursivo para audiencias combinadas (hasta 5 niveles). (TGT-53081)
* Se ha corregido un problema que se producía cuando el área de trabajo se establecía en &quot;[!UICONTROL Todos los espacios de trabajo]&quot; y al copiar una actividad que ya existe en el área de trabajo predeterminada se producía un error incorrecto:

  &quot;Se debe incluir al menos una propiedad para los espacios de trabajo no predeterminados&quot;.

  Dado que la copia se encuentra dentro del espacio de trabajo predeterminado, no se debe requerir ninguna propiedad. Al intentar agregar una propiedad y guardar, se produce un segundo error:

  &quot;Entrada de usuario no válida&quot;

+++

### [!DNL Target Standard/Premium] 25.7.3 (viernes, 24 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles

* Se corrigió un problema en el cual el método `buildViews` de la clase de generador establecía incorrectamente `viewMaxLocalId` en el recuento total de vistas, en lugar de en la asignación de `viewLocalId` más alta. (TGT-53207)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada por el cual las ofertas eliminadas en las actividades [!UICONTROL Automated Personalization] (AP) se mostraban como `Deleted option with ID: X` en lugar de sus nombres originales (por ejemplo, `Offer Name [Deleted]`, como se muestra en la interfaz de usuario heredada). Esta corrección restaura el etiquetado significativo de las ofertas eliminadas, lo que mejora la claridad y hace que la creación de informes sea más precisa y fácil de usar. (TGT-52921)
* Se corrigió un problema en el cual algunas actividades migraron del front-end [!DNL Target] a [!DNL Target] Central tenían configuraciones de métricas incoherentes debido a un error de sincronización corregido anteriormente. Específicamente, las actividades que originalmente usaron una métrica de conversión y luego se actualizaron a una métrica basada en análisis retuvieron valores obsoletos en los campos `primaryMetricType` y `successCriteria`. (TGT-52643)
* Se corrigió un problema en el cual todo el contenido de una página de vista previa de control de calidad se podía editar debido a la inclusión no deseada del atributo `contentEditable` en las modificaciones de HTML. Esto permitía a los usuarios hacer clic y editar cualquier texto de la página, lo que podía causar problemas de diseño y confusión durante el control de calidad. (TGT-53247)
* Se ha corregido un problema por el cual al mover una modificación de [!DNL Page Load] a una [!UICONTROL vista] se duplicaba la modificación y permanecía en [!UICONTROL carga de página] mientras que también aparecía en la [!UICONTROL vista]. Además, si se quita la modificación de la [!UICONTROL vista], también se quitaría incorrectamente de la [!UICONTROL carga de página]. (TGT-53270)

+++

**API**

+++Ver detalles

* Se ha corregido un problema en la capa de persistencia del back-end por el cual las opciones eliminadas se almacenaban correctamente, pero no se podía acceder a ellas a través de puntos finales de API existentes. Como resultado, las aplicaciones de front-end no pudieron recuperar nombres significativos para las opciones eliminadas, lo que afectó a las vistas históricas de los informes. Esta corrección garantiza que los datos de opciones eliminados conservados ahora se puedan mostrar correctamente en la interfaz de usuario. (TGT-52973)
* Se implementó un nuevo extremo de migración para admitir la transferencia de opciones de actividad eliminadas de actividades basadas en JCR a [!DNL Target] actividades centrales. Esta funcionalidad permite un seguimiento y un sistema de informes coherentes entre sistemas. Esta característica garantiza que las opciones eliminadas se conserven y sincronicen en el front-end y back-end de [!DNL Target], lo que mejora la integridad de los datos y los informes históricos. (TGT-53217)
* Se ha introducido un nuevo extremo de API que permite a los usuarios restaurar las opciones de actividad eliminadas anteriormente desde una base de datos secundaria. Esta funcionalidad aprovecha la infraestructura existente proporcionada por las clases `RemovedCampaignElements` y `RemovedOptionInfo`, lo que garantiza la reintegración perfecta de las opciones eliminadas en las actividades activas. (TGT-52903)
* Se ha corregido un problema en el cual las actividades [!DNL Recommendations] que contenían nombres de métricas de más de 25 caracteres no se podían abrir ni editar debido a limitaciones de API. Esta corrección garantiza la compatibilidad con los nombres de métricas que superan el límite de caracteres y restaura el acceso completo a las actividades afectadas. (TGT-52839)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles

* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias basadas en formularios] que hacía que el editor se bloqueara después de hacer clic en el icono **[!UICONTROL Administrar contenido]** ( ![Administrar contenido](/help/main/assets/icons/Experience.svg) ) al crear o editar una actividad de [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalles

* Se ha corregido un problema que impedía que [!UICONTROL Búsqueda en el catálogo] cargara resultados adicionales al desplazarse al final de la lista y restaurara un comportamiento coherente con la interfaz de usuario heredada. (TGT-53088)
* Se ha corregido un problema que impedía eliminar elementos del cuadro de diálogo [!UICONTROL Detalles de criterios]. (TGT-53245)
* Se ha corregido un problema que impedía abrir o interactuar con productos sin nombre. Este problema se producía al seleccionar entornos que devolvían resultados sin nombre, lo que impedía el acceso a los detalles del producto. (TGT-53007)
* Se ha corregido un problema que hacía que la página [!UICONTROL Búsqueda en el catálogo] se bloqueara y mostrara una pantalla en blanco al seleccionar ciertos productos. (TGT-53087)
* Se ha corregido un problema en el cual los usuarios no podían editar la actividad de site_cart_z1 [!DNL Recommendation] en la interfaz de usuario de [!DNL Target]. Al intentar abrir la actividad, se produjo un error en la página [!UICONTROL Información general] que bloqueaba el acceso al editor. (TGT-53221)

+++

**Creación de informes**

+++Ver detalles

* Se corrigió un problema en el cual el campo de espacio aislado de la base de datos de actividad no se borraba al cambiar el origen de informes de [!DNL Customer Journey Analytics] o [!DNL Analytics] a [!DNL Target]. Anteriormente, la interfaz de usuario enviaba correctamente la zona protegida: null, pero el backend ignoraba este valor, lo que dejaba los datos obsoletos de la zona protegida en su lugar. El servidor ahora borra correctamente el campo de la zona protegida cuando se recibe un valor nulo. (TGT-52798)
* Se ha vuelto a implementar la capa de persistencia de opciones eliminadas en el backend de Target para admitir la creación de informes históricos precisos en las actividades [!UICONTROL Automated Personalization] (AP). Anteriormente, cuando se eliminaba una opción, se perdía su nombre, lo que dificultaba la interpretación de los datos de rendimiento anteriores.

  **Mejoras de clave**:

  * Las opciones eliminadas ahora se rastrean usando la infraestructura existente de `RemovedCampaignElements` y `RemovedOptionInfo`.
  * Cuando se elimina una opción de una actividad AP, se conservan sus metadatos (por ejemplo, ID y nombre).
  * La interfaz de usuario de creación de informes ahora puede mostrar el nombre de opción original (por ejemplo, `Option Name [Deleted]`) junto con las métricas históricas, lo que mejora la claridad y la facilidad de uso.

  Esta actualización garantiza la creación de informes coherentes y significativos, incluso después de eliminar las opciones de una actividad. (TGT-52986)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Se ha corregido un problema en el VEC por el cual la aplicación de una modificación a una vista provocaba duplicación y activaba un error de &quot;entrada de usuario no válida&quot;. (TGT-52886)
* Se ha corregido un problema con la funcionalidad [!UICONTROL Deshacer] para las opciones [!UICONTROL Insertar antes] e [!UICONTROL Insertar después] al configurar ofertas de imágenes en el VEC.

  Anteriormente, deshacer una acción [!UICONTROL Insertar antes] o [!UICONTROL Insertar después] en las ofertas de imagen resultó en un comportamiento incoherente o en un error al revertir correctamente la modificación, especialmente en las actividades creadas en la IU heredada de [!DNL Target]. Este problema se ha resuelto para garantizar que las acciones de deshacer ahora funcionen de forma fiable para estas modificaciones. (TGT-52809)

* Se corrigió un problema en el cual el atributo `contentEditable` se establecía involuntariamente como verdadero y persistía en el contenido de HTML guardado. Esta actualización garantiza una salida de HTML más limpia y esperada sin un comportamiento de edición no deseado. (TGT-52319)
* Para evitar la pérdida permanente de opciones eliminadas y garantizar un comportamiento coherente entre servicios, se ha implementado la funcionalidad de eliminación suave para las opciones de la interfaz de usuario y los microservicios relacionados.

  **Cambios clave**:

  * Las opciones ya no se eliminan de forma permanente. En su lugar, se marcan con un nuevo indicador eliminado: true en el objeto XML de parámetros.
  * Solo la interfaz de usuario [!DNL Target] actualizada usa este indicador para excluir de la representación las opciones eliminadas y para evitar que se envíen a los servicios Edge.
  * Las opciones eliminadas siguen formando parte de la carga útil de la actividad durante las ediciones, lo que garantiza la trazabilidad y evita al mismo tiempo la entrega de opciones inexistentes a los clientes.

  Esta actualización mejora la integridad de los datos y se ajusta a las prácticas recomendadas para administrar eliminaciones en sistemas distribuidos. (TGT-52726)

+++

**Espacios de trabajo**

+++Ver detalles

* Se ha corregido un problema que se producía al copiar una actividad de un espacio de trabajo no predeterminado a predeterminado o entre espacios de trabajo no predeterminados. Las ofertas ahora se duplican con un seguimiento y un nombre mejorados para evitar conflictos.

  **Mejoras de clave**:
  * Las ofertas se vuelven a crear en el espacio de trabajo de destino con ID y metadatos actualizados.
  * Se cambia el nombre de las ofertas copiadas con el formato: &quot;Copia del nombre de la oferta&quot; más un número aleatorio o una marca de tiempo para garantizar su exclusividad.
  * El sistema actualiza los estados de oferta y actividad para reflejar los nuevos ID.
  * Esta funcionalidad evita errores causados por varios nombres de &quot;copia de oferta&quot; idénticos durante acciones de copia repetidas.
  * Es posible que las ofertas no aparezcan inmediatamente en la lista de ofertas del espacio de trabajo de destino, pero se procesen y se muestren correctamente.

  Esta actualización mejora la fiabilidad y la trazabilidad al administrar ofertas en varios espacios de trabajo. (TGT-53080)

+++

### [!DNL Target Standard/Premium] 25.7.2 (sábado, 18 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles

* Se ha añadido una advertencia de confirmación adicional al cancelar las ediciones de la actividad con cambios no guardados: ¿Seguro que desea guardar esta actividad? Si no guarda, se perderán todos los cambios.&quot; Este mensaje ayuda a evitar la pérdida accidental de datos. (TGT-52865)
* Se ha restaurado la funcionalidad heredada en el control deslizante [!UICONTROL Priority] de [!UICONTROL Goals &amp; Settings], lo que permite a los clientes introducir un valor numérico directamente, como se admite en la interfaz de usuario heredada. (TGT-53185 y TGT-53219)

+++

**Públicos**

+++Ver detalles

* Se ha corregido un problema que impedía guardar o editar actividades que contenían audiencias personalizadas. Los clientes han encontrado el mensaje de error &quot;No podemos completar su solicitud. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste.&quot; al intentar guardar cambios o incluso guardarlos sin cambios en determinadas actividades. (TGT-53189)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Ver detalles

* Se ha corregido un problema que había cuando los clientes veían informes de actividades específicas en la página [!UICONTROL Objetivos y configuración], en el vínculo [!UICONTROL Ver en Analytics] se señala incorrectamente al entorno de control de calidad en lugar de al entorno de producción. (TGT-53163)

+++

**[!UICONTROL Experiencias] y [!UICONTROL Ofertas]**

+++Ver detalles

* Se corrigió un problema en el cual invocar `triggerView` mediante código personalizado causaba un bucle infinito. (TGT-52885)
* Se corrigió un problema que ocasionaba discrepancias entre `LocalIds` definidos para actividades y los `LocalIds` utilizados en definiciones de experiencia. (TGT-52669)
* Se ha corregido un problema por el cual faltaban nombres de métricas en la página de la actividad [!UICONTROL Información general], que solo mostraba &quot;Oferta&quot; en lugar del nombre de métrica correcto. (TGT-53054)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles

* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias basadas en formularios] que impedía guardar la actividad y activaba el mensaje de error: &quot;No se pueden leer propiedades de indefinido (leyendo &#39;mapa&#39;)&quot;. (TGT-53145)

+++

**Recommendations**

+++Ver detalles

* Se ha corregido un problema por el cual al hacer clic en un producto desde [!UICONTROL Búsqueda en el catálogo] se mostraba el error &quot;No se pudieron recuperar los detalles del producto&quot; y se abría un modal sin una opción de cierre. (TGT-53082)
* Se corrigió un problema en el cual [recommendations como ofertas](/help/main/c-recommendations/recommendations-as-an-offer.md) en actividades de [!UICONTROL prueba A/B] no se actualizaban correctamente al cambiar colecciones o promociones. (TGT-52884)
* Se ha corregido un problema en el entorno de producción por el cual al hacer clic en una entidad en la IU actualizada se mostraba el error: &quot;No se pudieron recuperar los detalles del producto. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste.&quot; (TGT-53071)

+++

**Informes**

+++Ver detalles

* Se ha corregido un problema en el cual al guardar detalles de pedidos en un archivo CSV, se producía un archivo vacío. (TGT-52225)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* Se ha resuelto un problema en la página [!UICONTROL Objetivos y configuración] en el cual los selectores utilizados en varias experiencias no se resaltaban como seleccionados de forma consistente. (TGT-53062)
* Se ha corregido un problema que impedía la edición de la actividad y activaba el mensaje de error: &quot;No se pueden leer las propiedades de undefined (leyendo &#39;mapa&#39;)&quot;. (TGT-53161)

+++

**Espacios de trabajo**

+++Ver detalles

* Se ha mejorado la administración de ofertas ad hoc al cambiar de espacio de trabajo.
  * Al cambiar del espacio de trabajo predeterminado a un espacio de trabajo no predeterminado (o entre espacios de trabajo no predeterminados), las ofertas ad hoc ahora se copian correctamente. Durante la inicialización, el contexto del espacio de trabajo se actualiza y se asigna un nuevo ID a la oferta para garantizar su exclusividad.
  * No se producen cambios al permanecer en el mismo espacio de trabajo. (TGT-53079)
* Se ha corregido un problema que impedía que los clientes [copiaran actividades entre diferentes espacios de trabajo](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6). (TGT-52753 y TGT-47094)
* Se corrigió un problema que se producía al cambiar propiedades entre espacios de trabajo.
  * Al cambiar entre el espacio de trabajo predeterminado y un espacio de trabajo no predeterminado, si la propiedad actual existe en el espacio de trabajo de destino, se conserva la propiedad.
  * Si la lista [!UICONTROL Properties] muestra una advertencia (probablemente para indicar que algunas propiedades podrían no ser compatibles) y el cliente hace clic en [!UICONTROL Agregar] o [!UICONTROL Quitar] y luego hace clic en [!UICONTROL Guardar], se quitarán todas las propiedades que no estén en el área de trabajo de destino. Si el cliente hace clic en [!UICONTROL Cancelar], todas las propiedades permanecerán, aunque no existan en el área de trabajo de destino. (TGT-47094)
  * Si permanece en el mismo espacio de trabajo o cambia de un espacio de trabajo no predeterminado al predeterminado u otro, todo permanece tal cual. (TGT-53078)
* Se ha actualizado la lógica de validación de entidad para respetar el contexto original del espacio de trabajo de la actividad. Las entidades como [!UICONTROL Fragmentos de experiencias] (XF) ahora se validan en función del espacio de trabajo en el que se creó originalmente la actividad. Por ejemplo, si existe un XF en el espacio de trabajo por defecto y la actividad se copia del espacio de trabajo X al espacio de trabajo Y, la validación seguirá pasando siempre que el XF sea válido en el espacio de trabajo original (por defecto). (TGT-53196)
* Compatibilidad mejorada para copiar audiencias específicas durante la duplicación de actividades.
  * Las audiencias específicas, incluidas las métricas, los informes, las páginas y los tipos solo de actividad, ahora se copian automáticamente en los siguientes casos:
    * Al copiar una actividad del espacio de trabajo predeterminado a un espacio de trabajo no predeterminado.
    * Al copiar una actividad en el mismo espacio de trabajo. (TGT-53197)

+++

### [!DNL Target Standard/Premium] 25.7.1 (sábado, 11 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles

* Se ha corregido un problema en el cual la dirección URL del control de calidad de la actividad [!UICONTROL 1 incluía un parámetro de consulta innecesario: `at_preview_evaluate_as_true_audience_ids`. &#x200B;]&#x200B;(TGT-52907)
* Se ha corregido un problema por el cual las direcciones URL de vista previa incluían incorrectamente audiencias adicionales más allá de la escrita explícitamente por el usuario. Este comportamiento se ha corregido para garantizar que solo se aplique la audiencia especificada al generar un control de calidad o un vínculo de vista previa. (TGT-52912)
* Se ha corregido un problema que impedía a los usuarios crear actividades de [!UICONTROL Segmentación automática] (AT) si [!UICONTROL Asignación automática] (AA) se seleccionaba primero durante la configuración de la asignación de tráfico. Este problema provocaba un error de validación del back-end e impedía guardar la actividad. (TGT-53096)

+++

**Públicos**

+++Ver detalles

* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Aprobador] no podían agregar ni guardar refinamientos de audiencia solo de actividad. Al intentar hacerlo, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario tenía permisos suficientes para aprobar y administrar actividades. (TGT-52984)
* Se ha corregido un problema que se producía cuando se eliminaba una audiencia específica de una actividad mediante la opción [!UICONTROL Quitar refinamiento de audiencia], por lo que la audiencia ya no aparece en la lista de audiencias para volver a seleccionarse dentro de la misma actividad. Este comportamiento impedía a los usuarios volver a añadir la misma audiencia a menos que se volviera a crear desde cero. (TGT-52979)
* Se ha corregido un problema en el cual los refinamientos de audiencia solo de actividad desaparecían de la interfaz de usuario inmediatamente después de eliminarse de una ubicación, incluso antes de guardar la actividad. Este comportamiento contradecía la funcionalidad esperada y la guía de información del objeto, que indica: &quot;Todas las audiencias no utilizadas de esta biblioteca se eliminarán una vez guardada la actividad&quot;. (TGT-52982)
* Se ha corregido un problema que se producía al intentar asignar una audiencia distinta de [!UICONTROL Todos los visitantes] a una actividad. Al guardar, se muestra el siguiente mensaje de error: &quot;No podemos completar su solicitud. Póngase en contacto con [!UICONTROL Adobe Client Care] si el problema persiste.&quot; (TGT-53008)
* Se ha corregido un problema que bloqueaba el guardado de una actividad después de crear y asignar una nueva audiencia dentro del editor de actividades. El mensaje de error mostrado era: &quot;No podemos completar su solicitud. Póngase en contacto con [!UICONTROL Adobe Client Care] si el problema persiste&quot;. (TGT-52977)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Ver detalles

* Se corrigió un problema en el cual copiar una actividad existente y cambiar el origen de informes a [!DNL Adobe Analytics] (A4T) resultaría en un error de &quot;entrada de usuario no válida&quot;. El error se activó cuando ciertas acciones de métricas incompatibles con los informes de [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` y `restart_new_experience`, se retuvieron de la actividad original. (TGT-52900)
* Se ha corregido un problema que impedía que los clientes crearan o guardaran una actividad al seleccionar [!DNL Adobe Analytics] (A4T) como fuente de informes en el paso [!UICONTROL Objetivos y configuración]. El problema se produjo específicamente al seleccionar una métrica de [!UICONTROL Evento personalizado] (por ejemplo, &quot;Evento personalizado 16&quot;), lo que dio como resultado el siguiente error: &quot;Entrada de usuario no válida&quot;. (TGT-52910)
* Se ha corregido un problema por el cual al hacer clic en el vínculo &quot;[!UICONTROL Ver en Analytics]&quot; se redirigía a los usuarios a la página principal en lugar del panel [!DNL Analytics] deseado. (TGT-53092 y TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Se ha corregido un problema que se producía al ver una actividad de [!DNL Recommendations] en la interfaz de usuario actualizada de [!UICONTROL Información general], la sección [!UICONTROL Objetivos y configuración] no se carga cuando se selecciona [!DNL Adobe Analytics] (A4T) como fuente de informes. Se muestra el siguiente mensaje de error: &quot;Se ha producido un error. No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste. (TGT-52999)

+++

**[!UICONTROL Experiencias] y [!UICONTROL Ofertas]**

+++Ver detalles
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Se corrigió un problema en el cual la característica [!UICONTROL Administrar contenido] no validaba correctamente el estado de una ubicación después de eliminar todas las opciones de contenido. Este problema podría provocar un comportamiento incoherente o errores al intentar guardar o continuar con la configuración de la actividad. (TGT-52801)
* Se ha corregido un problema en el cual los usuarios encontraban un error de &quot;entrada no válida&quot; al añadir una nueva página y eliminar elementos específicos dentro de diferentes experiencias. El error se desencadena cuando se genera un duplicado de `LocalIds` durante la manipulación de elementos, especialmente al cambiar entre experiencias y modificar estructuras de páginas compartidas. (TGT-52720)
* Se ha corregido un problema que causaba que, al usar la característica [!UICONTROL Generar oferta ad hoc], aparecieran ubicaciones indefinidas en el panel [!UICONTROL Administrar contenido]. (TGT-53076 y TGT-53070)
* Se ha aclarado el comportamiento con el cliente en el que las modificaciones realizadas mediante una oferta de HTML podrían no aparecer al navegar desde el paso [!UICONTROL Segmentación] a [!UICONTROL Experiencias]. Para este cliente, el sitio web afectado generaba dinámicamente varios selectores DOM que cambiaban con cada carga de página. Como resultado, el selector utilizado originalmente para la modificación no se puede encontrar cuando se vuelve a abrir el editor, lo que hace que la modificación parezca no estar presente o no ser válida. Este escenario funciona según lo diseñado. Para garantizar que las modificaciones persistan visualmente en el editor, se recomienda que los clientes utilicen selectores estables y coherentes que no cambien entre las recargas de la página. (TGT-52874)
* Se ha corregido un problema en el cual al intentar eliminar o desactivar una oferta que formaba parte de una experiencia excluida se activaba un error de &quot;entrada de usuario no válida&quot;. Este problema se producía aunque la oferta no se usaba de forma activa en las experiencias incluidas. (TGT-52917)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles

* Se ha corregido un problema en las actividades basadas en formularios en el cual duplicar una experiencia y editar el código personalizado en una de las experiencias duplicadas aplicaba involuntariamente esos cambios a todas las experiencias duplicadas. Cada experiencia ahora conserva su propio código personalizado de forma independiente después de la duplicación. (TGT-51600)

+++

**Localización**

+++Ver detalles

* Se han actualizado las cadenas de localización en la nueva IU para francés (fr_FR), alemán (de_DE), italiano (it_IT), coreano (ko_KO) y chino simplificado (zh_CN).

+++

**[!DNL Recommendations]**

+++Ver detalles

* Se agregó una nueva fuente [!DNL Recommendations] [status](/help/main/c-recommendations/c-products/feeds.md#status): [!UICONTROL Error de importación parcial]. (KB-2215)
* Se corrigió un problema que afectaba el flujo de trabajo de creación de actividad al agregar [!DNL Recommendations] con [!UICONTROL promociones]. Cuando los usuarios seleccionaron &quot;[!UICONTROL Promocionar por atributo]&quot; y agregaron una regla de filtrado (por ejemplo, [!UICONTROL Coincidencia de parámetros]), el tipo de regla y los valores de operando seleccionados no se conservaron después de guardar y reeditar la actividad. Al volver a abrir, el tipo de regla de filtrado cambiaba inesperadamente y faltaban los valores de operando. (TGT-53059)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Recommendations] por el cual cualquier promoción creada con una sola regla se interpretaba y mostraba de forma incorrecta como un tipo de promoción &quot;Lista de elementos&quot;, independientemente de la lógica de la regla. (TGT-53063)
* Se ha corregido un problema que se producía al usar la interfaz de usuario [!UICONTROL Información general]actualizada, el botón &quot;[!UICONTROL Descargar datos de Recommendations]&quot; que faltaba para las actividades de [!UICONTROL Segmentación de experiencias] (XT) que incluyen [!DNL Recommendations]. (TGT-52730 y TGT-52756)
* Anteriormente, la interfaz de usuario de Recommendations solo mostraba el número de entidades importadas correctamente desde una fuente. Sin embargo, el formato de mensaje back-end incluye tanto el número de entidades importadas como el número total de entidades con el formato: `# of entities imported / # of total entities`. Debido a esta discrepancia, los usuarios solo veían el primer valor (recuento importado) en la interfaz de usuario, lo que provocaba confusión. La interfaz de usuario ahora muestra ambos números. (TGT-53073)
* Se ha corregido un problema en el cual los clientes no podían guardar una regla de filtrado al configurar una promoción &quot;[!UICONTROL Promocionar por atributo]&quot; en una actividad A/B basada en formularios con recomendaciones. Después de guardar y volver a abrir la actividad, faltaba la regla de filtrado y la actividad no se pudo guardar correctamente. (TGT-53057)

  +++

**Informes**

+++Ver detalles

* Se ha corregido un problema en el cual al seleccionar &quot;[!UICONTROL Exportar detalles de pedidos a CSV]&quot; desde la página [!UICONTROL Informes], se descargaba un archivo vacío. Este problema ocurría incluso cuando había datos de pedido válidos en la actividad. (TGT-52225)
* Se ha corregido un problema que se producía al intentar guardar una actividad después de crear y asignar una nueva audiencia de informes. El mensaje de error devuelto fue: &quot;Acceso denegado. Para realizar esta operación, se requieren todos los privilegios siguientes: [editor].&quot; Este problema se producía a pesar de que el usuario tenía acceso de nivel de aprobador. (TGT-53103)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* Se ha resuelto un problema en el cual la aplicación de una modificación a una vista resultaba en la duplicación de la vista y la actividad devolvía un error de &quot;entrada de usuario no válida&quot;. Esta corrección garantiza que las modificaciones de la vista se apliquen correctamente sin activar errores de duplicación o validación. (TGT-52886)
* Se ha corregido un problema por el cual las modificaciones de código personalizado se mostraban incorrectamente para la experiencia incorrecta. En concreto, los cambios destinados a una experiencia se mostraron en una experiencia diferente, lo que provocó confusión y posibles errores de configuración en las actividades activas. (TGT-52776)
* Se ha corregido un problema que impedía editar o guardar modificaciones de código personalizado en la nueva interfaz de usuario de VEC. Específicamente:

  * Después de editar un bloque de código personalizado y guardar, los cambios no se reflejaron en la interfaz de usuario ni en la previsualización de control de calidad.
  * En algunos casos, las modificaciones no se podían eliminar a menos que se cerrara y se volviera a abrir la actividad.
  * Como solución alternativa, los usuarios tenían que copiar el código, eliminar la modificación y volver a crearlo manualmente con el contenido actualizado. (TGT-53072)

* Se ha corregido un problema por el cual al editar y guardar código personalizado el panel [!UICONTROL Modificaciones] dejaba de responder. (TGT-53075)
* Se ha corregido un problema por el cual las modificaciones realizadas en el código personalizado en experiencias de variante se reflejaban de forma involuntaria en la experiencia [!UICONTROL Control]. Esto provocaba cambios no deseados en el comportamiento de entrega. La experiencia [!UICONTROL Control] ahora permanece aislada de las ediciones de código personalizado realizadas en otras experiencias. (TGT-52413)
* Se ha corregido un problema en el cual las modificaciones realizadas en una experiencia (por ejemplo, la Experiencia B) se duplicaban de forma involuntaria en otra experiencia (Experiencia A) si el usuario hacía clic en la segunda experiencia antes de que el editor se cargara completamente. Este comportamiento también podría provocar la pérdida de modificaciones si la experiencia seleccionada inicialmente no tiene cambios. (TGT-52597)
* Se corrigió un problema en el cual los cambios realizados en el paso [!UICONTROL Modificaciones] de creación de actividades no se guardaban de manera consistente. En algunos casos, después de completar todos los pasos y hacer clic en [!UICONTROL Guardar], el script personalizado agregado en la sección [!UICONTROL Modificaciones] no se reflejaría en el sitio activo, a pesar de que no haya errores visibles durante el proceso de guardado. (TGT-52661)
* Se ha corregido un problema por el cual los cambios en el código personalizado no se guardaban correctamente y se reflejaban de forma involuntaria en varias experiencias dentro de la misma actividad. Además, los usuarios encontraban problemas de acceso al abrir o actualizar determinadas actividades, lo que provocaba que aparecieran pantallas en blanco. Estos problemas se han resuelto para garantizar una edición estable de la actividad y un aislamiento preciso de la experiencia. (TGT-52594)
* Se ha corregido un problema por el cual los usuarios no podían navegar a una dirección URL diferente mientras estaban en [!UICONTROL Modo de exploración]. Esto impedía que los probadores y editores validaran o previsualizaran páginas alternativas dentro de la misma sesión de actividad. (TGT-53052)
* Se ha corregido un problema por el cual varias instancias de [!UICONTROL Compositor de experiencias visuales] (VEC) se abrían simultáneamente durante la creación de la actividad. Este problema se produjo cuando los usuarios deshabilitaron el [!UICONTROL Compositor de experiencias mejorado] (EEC) y quitaron la barra diagonal de la dirección URL del sitio web en el paso [!UICONTROL Entrega de páginas]. (TGT-52782)
* Se ha corregido un problema en el cual el menú desplegable de métrica [!UICONTROL Ingresos] en el paso [!UICONTROL Objetivos y configuración] establecía de forma predeterminada de forma incorrecta [!UICONTROL Ingresos por visita] (RPVISIT), incluso después de que el usuario seleccionara una métrica diferente.  El problema se producía al contraer y volver a expandir el panel de configuración de métricas, lo que provocaba que se restableciera el valor seleccionado anteriormente. (TGT-52811 y TGT-52878)
* Se han corregido varios problemas en el flujo de trabajo de creación de actividades relacionado con la nomenclatura de ofertas y la traducción de contenido en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Multivariate Testing] (MVT):

  Problemas clave abordados:

  * La creación de varias ofertas de HTML con el mismo nombre (por ejemplo, &quot;Experiencia&quot;) ha activado el error &quot;No se permiten nombres de ofertas duplicados&quot;, pero la interfaz de usuario no indicaba claramente qué ofertas estaban causando el conflicto.
  * Al cambiar el nombre de las ofertas mediante el panel derecho, se actualizó el nombre en la interfaz de usuario, pero el cambio no se reflejó en la ficha [!UICONTROL Administrar contenido] ni en la ficha [!UICONTROL Ofertas], lo que provocó errores de validación persistentes.
  * En las actividades MVT, aunque el error de nombre duplicado no persistió después de cambiar el nombre, la IU seguía sin reflejar los nombres de ofertas actualizados de forma coherente en las pestañas. (TGT-52933)

  +++

### [!DNL Target Standard/Premium] 25.6.4 (sábado, 27 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado la opción [!UICONTROL Reorganizar] a la interfaz de usuario actualizada del [!UICONTROL Compositor de experiencias visuales] (VEC) para que se ajuste a la funcionalidad disponible en el VEC heredado. (TGT-46957 y TGT-52876)
* Se ha corregido un problema en el cual las modificaciones realizadas en experiencias de variante (por ejemplo, Experiencia B) en una actividad [!UICONTROL Prueba A/B] no se conservaban. Después de cambiar entre experiencias, los cambios en la variante desaparecerían. Este problema no afectaba a la experiencia de control de Campaign. (TGT-52664)
* Se ha corregido un problema en el cual algunos clientes no podían crear ni guardar actividades, mientras que otros podían realizar las mismas acciones sin problema. El problema era inconsistente entre cuentas. (TGT-52842)
* Se ha corregido un problema en el cual en el VEC actualizado, los usuarios no podían mover modificaciones al [!UICONTROL evento de carga de página], una capacidad que existía en la IU heredada. (TGT-52617)
* Se ha corregido un problema en la interfaz de usuario actualizada en el cual los eventos [!UICONTROL page load] no eran visibles en [!DNL Target] al crear cambios; las actualizaciones solo se aplicaban a las vistas. (TGT-52604)
* Se ha corregido un problema que impedía que algunas modificaciones de la actividad se mostraran correctamente en el VEC actualizado. (TGT-52818)
* Se ha corregido una excepción de puntero nulo que se producía al recuperar datos de informes para actividades [!UICONTROL Automated Personalization] (AP). (TGT-52362)
* Se ha corregido un problema que impedía que los detalles de nivel de oferta aparecieran en el archivo .CSV para las actividades [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Se ha corregido un problema que se producía al aplicar modificaciones en el VEC actualizado; los cambios aparecen inicialmente correctamente, incluido el [!UICONTROL Fragmento de experiencia] esperado. Sin embargo, al cambiar de experiencia o al realizar ediciones adicionales, algunas modificaciones no se aplican debido a problemas con el selector. (TGT-52679)
* Se ha corregido un problema por el cual cuando se creaba una nueva actividad clonando una existente, los vínculos de control de calidad de la actividad clonada retenían incorrectamente las direcciones URL de la página de la actividad original. (TGT-52775)
* Se ha corregido un problema que impedía de forma involuntaria que [!UICONTROL Toma de decisiones en el dispositivo] estuviera disponible en el VEC actualizado. (TGT-52371)
* Se ha corregido un problema que impedía editar una actividad de producto [!DNL Recommendations]. Al intentar acceder al VEC a través de la interfaz de usuario de Target, apareció un error en la página [!UICONTROL Información general] que impedía realizar ediciones. (TGT-52823)
* Se ha corregido un problema que impedía guardar una actividad de [!DNL Recommendations] cuando los nombres de experiencia superaban los 50 caracteres. (TGT-52619)
* Se ha corregido un problema en el cual los clientes no podían guardar una actividad de Recommendations después de modificar los criterios en la nueva interfaz de usuario. El problema parece estar relacionado con los permisos y no afecta a todos los usuarios con funciones similares. (TGT-52816)
* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Editor] no podían editar una actividad [!DNL Recommendations]. Al intentar cambiar el diseño y guardar la actividad, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario ya tuviera esa función en el espacio de trabajo relevante. (TGT-52836)

### [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que causaba que, al copiar una actividad de un espacio de trabajo a otro, se produjeran errores como &quot;no debe ser nulo&quot; o &quot;Se ha producido un error&quot;. (TGT-52474)
* Se ha corregido un problema por el cual los informes [!UICONTROL Segmentos automatizados] y [!UICONTROL Atributos importantes] no se generaban para ciertas actividades. (TGT-52904)
* Se ha corregido un problema en el VEC actualizado en el cual la administración de contenido predeterminado en las actividades [!UICONTROL Automated Personalization] (AP) no coincidía con la IU heredada. El sistema ahora agrega automáticamente un(a) `optionGroup` predeterminado denominado &quot;Contenido predeterminado&quot; con `optionGroupLocalId = 0` cuando no se agrega ningún grupo explícitamente. Este grupo incluye la opción predeterminada (por ejemplo, `optionLocalId: 0`). Si se elimina el contenido predeterminado, también se elimina el grupo de opciones correspondiente. (TGT-52651)
* Se ha corregido un problema en las actividades [!UICONTROL Prueba multivariada] (MVT) en el cual se impedía incorrectamente reutilizar `experienceLocalId` de experiencias eliminadas anteriormente. (TGT-52672)
* Se ha corregido un problema que impedía copiar o editar actividades que contuvieran un fragmento de experiencia. Esto desencadenó el error: `Enum "AemOfferType" cannot represent value: "html"`. (TGT-52635)
* Se ha corregido un problema por el cual las direcciones URL de las ubicaciones de actividades no mostraban los parámetros de consulta debido a caracteres no válidos, como barras inclinadas (/). (TNT52845)
* Se mejoró el mensaje de error de validación para [!DNL A/B Test] actualizaciones de la actividad a través de la API back-end. Cuando hay nombres de ubicación duplicados, el mensaje ahora indica claramente: &quot;No se permiten nombres duplicados&quot; para `locations.selectors`. (TGT-52589)
* Se ha corregido un error que se producía al actualizar una actividad [!UICONTROL Recommendations] activa debido a una propiedad no reconocida en la carga de la solicitud. El sistema ahora gestiona correctamente el JSON no válido. Error de &quot;nombre de propiedad no reconocido&quot;. (TGT-52723)
* Se ha corregido un problema que impedía crear un diseño de [!DNL Recommendations]. Al hacer clic en [!UICONTROL Crear], se activó el mensaje: &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot;. (TGT-52395 y TGT-52899)
* Se corrigió un problema en el cual se bloqueaba volver a guardar un diseño de [!DNL Recommendations] sin modificaciones. (TGT-52879)
* Se ha corregido un error de validación del servidor que provocaba el error &quot;400 Bad Request&quot; al guardar una actividad de [!UICONTROL Recommendations]. (TGT-52716)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias basadas en formularios] por el cual al pasar el ratón por encima de un mbox con caracteres especiales en la lista desplegable [!UICONTROL Ubicación], el editor se quedaba en blanco y se activaba un mensaje &quot;No se pudo ejecutar querySelector&quot; en &quot;Elemento&quot;.&quot; No se pudo recuperar la dirección de URL especificada. (TGT-52717)
* Se ha mejorado la precisión del estado de la fuente con un nuevo indicador &quot;PARTIALLY_IMPORTED&quot;. Anteriormente, las fuentes se marcaban como &quot;correctas&quot; incluso cuando no se importaban todas las filas de un archivo, lo que resultaba confuso. (TGT-52892)
* Se corrigió un error en el cual, después de migrar a AP V2, ciertas llamadas de API a `/admin/rest/ui/v1/campaigns` devolvían errores del lado del cliente (HTTP 4xx). (TGT-52721)

### [!DNL Target Standard/Premium] 25.6.2 (viernes, 12 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado un [nuevo artículo de preguntas frecuentes](/help/main/c-intro/updated-ui-faq.md) para responder preguntas comunes sobre la interfaz de usuario de [!DNL Target] actualizada y el [!UICONTROL Compositor de experiencias visuales] (VEC).
* Se ha corregido un problema en el cual la regla &quot;[!UICONTROL URL - no contiene]&quot; en [!UICONTROL Entrega de página] no funcionaba, lo que permitía que el contenido se mostrara incluso cuando debería haberse bloqueado. (TGT-52754)
* Se ha corregido un problema en el cual [!UICONTROL Entrega de páginas] mostraba incorrectamente el mensaje de error: &quot;No se permiten direcciones URL de página duplicadas. (TGT-52765)
* Se ha corregido un problema por el cual las audiencias para [!UICONTROL Entrega de páginas] URL que contenían fragmentos de experiencia se creaban con # anexado erróneamente. (TGT-52786)
* Se ha corregido un problema por el cual al copiar una actividad y editar la configuración en la página [!UICONTROL Objetivos y configuración] la interfaz de usuario de [!DNL Target] dejaba de responder. (TGT-52797)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado que permitía incorrectamente redirigir una página adicional en una actividad de [!UICONTROL prueba A/B] a la misma dirección URL. (TGT-51838)
* Se ha corregido un problema por el cual los cambios realizados en las métricas de la página [!UICONTROL Objetivos y configuración] no se guardaban al editar una actividad. (TGT-52799)
* Se ha corregido un problema por el cual al añadir una nueva experiencia mientras el editor web se estaba cargando, la nueva experiencia duplicaba contenido de la experiencia anterior. (TGT-51397)
* Se ha restaurado la capacidad de usar código personalizado fuera de la etiqueta `<head>`, una característica disponible anteriormente en la interfaz de usuario de Target heredada. (TGT-52304 y TGT-52300)
* Se ha eliminado una validación innecesaria al seleccionar el espacio de trabajo predeterminado durante la creación de la actividad. La validación de propiedades obligatoria ya no se aplica al espacio de trabajo predeterminado, pero permanece en su lugar para los espacios de trabajo no predeterminados. (TGT-52449)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado en el cual no se detectaban llamadas a `triggerView()`. (TGT-52575)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado que impedía a los usuarios agregar modificaciones a las vistas de la [!UICONTROL aplicación de una sola página] (SPA). (TGT-52556)
* Se ha corregido un problema en la interfaz de usuario actualizada de [!DNL Target] que impedía que los clientes vieran los detalles de la oferta. (TGT-52607)
* Se ha corregido un problema por el cual las actualizaciones realizadas en las ofertas de la [!UICONTROL Biblioteca de ofertas] no se reflejaban en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado. (TGT-52637)
* Se ha corregido un problema que impedía que la sección Ofertas se mostrara correctamente al crear una actividad. (TGT-52773)
* Se agregó la validación para asegurarse de que todas las `optionLocalIds` a las que se hace referencia en `optionGroups` existan en la matriz de opciones. Las referencias no válidas se eliminan automáticamente durante la creación de la actividad. (TGT-52687)
* Se ha corregido un problema por el cual los grupos de informes y las exclusiones no se conservaban después de agregar una nueva oferta. (TGT-52728)
* Se corrigió un problema en el cual las actividades sin un botón [!UICONTROL Control de calidad de la actividad] mostraban un selector de opciones vacío. (TGT-52733)
* Se ha corregido un problema en el cual los vínculos de control de calidad no representaban el contenido correctamente. (TGT-52718)
* Se ha corregido un problema en el cual el reemplazo de un elemento por un fragmento de experiencia no reflejaba correctamente los cambios en el entorno de control de calidad. (TGT-52762)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado que provocaba un error de &quot;Entrada no válida&quot; cuando los usuarios intentaban agregar fragmentos de experiencia. (TGT-52701)
* Se ha corregido un problema por el cual el modal &quot;Editar audiencia&quot; aparecía vacío al editar la segmentación de audiencia en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado. (TGT-52749)
* Se ha añadido un mensaje para informar a los usuarios de cuando una entidad no es accesible en el espacio de trabajo seleccionado. (TGT-52767)
* Se ha corregido un problema en el cual la interfaz de usuario no permitía la asignación manual de un ID de entorno a un criterio. En su lugar, tomó de manera predeterminada el ID del grupo de hosts [!UICONTROL Búsqueda en el catálogo de productos]. Esta corrección garantiza que los cambios de criterios ahora se apliquen en todos los entornos, no solo en el predeterminado. (TGT-52817)
* Se ha corregido un problema por el cual faltaba la opción &quot;[!UICONTROL Descargar datos de Recommendations]&quot; para actividades de [!UICONTROL Segmentación de experiencias] (XT) con recomendaciones. (TGT-52730 y TGT-52756)

### [!DNL Target Standard/Premium] 25.6.1 (sábado, 06 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema en el cual los vínculos de control de calidad no proporcionaban la experiencia correcta para la actividad asociada. (TGT-52163 y TGT-52790)
* Se ha corregido un problema por el que los vínculos de control de calidad no incluían el ID de audiencia asociado. (TGT-52722)
* Se ha corregido un problema para garantizar que las experiencias se entreguen solo cuando las condiciones configuradas de la URL de entrega de páginas se cumplan con precisión. (TGT-52696)
* Se ha corregido un problema que impedía que los clientes crearan una plantilla de diseño [!DNL Recommendations]. Al intentar crear una plantilla, se activó el error: &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot;. (TGT-52395)
* Se ha corregido un problema que impedía guardar [!DNL Recommendations] diseños con matrices de Velocity. El mensaje de error &quot;Debe haber al menos 1 variable de entidad utilizada dentro del script&quot; se activó incorrectamente. (TGT-52734)
* Se ha corregido un problema por el cual no se podía acceder a las modificaciones desde el [!UICONTROL Compositor de experiencias visuales] (VEC) cuando la página no se cargaba para las páginas web internas. (TGT-52488 &amp;TGT-52470)
* Se ha corregido un problema en el cual el panel [!UICONTROL Modificaciones] no era visible en tamaños de pantalla más pequeños en el VEC. (TGT-52470)
* Se ha corregido un problema en el VEC actualizado en el cual el cambio del modo [!UICONTROL Examinar] de nuevo al modo [!UICONTROL Diseño] provocaba un error de consola e impedía una mayor interacción. (TGT-52532)
* Se ha corregido un problema en el VEC por el cual al hacer clic en ciertos elementos se ampliaba su tamaño de forma involuntaria. (TGT-52497)
* Se ha corregido un problema en el cual algunos elementos de página no se cargaban o no se reconocían en el VEC, lo que impedía interacciones como seleccionar botones o banners e interrumpir el seguimiento de eventos preciso en las actividades de. (TGT-52663)
* Se ha corregido un problema que impedía que los clientes eliminaran o eliminaran ofertas en actividades [!UICONTROL Automated Personalization] (AP). (TGT-52690)
* Se ha corregido un problema que provocaba un comportamiento incoherente de calificación de actividades en actividades de varias páginas. (TGT-52694)
* Se ha corregido un problema que hacía que la página [!UICONTROL Información general] de la actividad mostrara una dirección URL no válida para [!UICONTROL Ubicación de la actividad]. (TGT-52695)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada que provocaba que aparecieran entradas duplicadas para las ubicaciones de actividades. (TGT-52693)
* Se ha corregido un problema que activaba un error de `getAudiencesV3`, lo que impedía que los clientes editaran o copiaran actividades. (TGT-52709)
* Se ha corregido un problema que provocaba un error de carga útil no válido al agregar [!UICONTROL Fragmentos de experiencias] u ofertas de HTML a una actividad. (TGT-52779 y TGT-52773)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual E[!UICONTROL Fragmentos de experiencia] no se mostraba correctamente debido a un error de entrada no válido. (TGT-52701)
* Se ha corregido un problema que impedía que los clientes editaran actividades en el [!UICONTROL Compositor de experiencias basadas en formularios] debido a un error de usuario no válido. (TGT-52470)
* Se ha corregido un problema de localización en coreano en el que traducciones anteriores usaban caracteres fuera del plano multilingüe básico. La traducción actualizada utiliza caracteres adecuados que transmiten con precisión el significado deseado. (TGT-52508 y TGT-52509)
* Se ha corregido un problema de localización en coreano en el que la traducción de &quot;fecha&quot; era incoherente al seleccionar fechas de inicio y finalización de una actividad. (TGT-52510)

### [!DNL Target Standard/Premium] 25.5.4 (29 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que impedía añadir o editar direcciones URL en modo de control de calidad. (TGT-51941)
* Se ha agregado una configuración de tráfico en modo de control de calidad en [!UICONTROL Informes] > [!UICONTROL Configuración de informes] ( ![icono de Configuración de informes](/help/main/assets/icons/Setting.svg) ) para que se ajuste a la funcionalidad de la IU heredada de [!DNL Target]. (TGT-52228 y TGT-52329)
* Se ha corregido un problema en el cual la actividad basada en formularios generaba vínculos de control de calidad incorrectos. La dirección URL/ubicación de la actividad incluía un &quot;1&quot; no deseado al final, que ahora se ha eliminado para garantizar una vinculación precisa. (TGT-52355 y TGT-52358)
* Se ha corregido un problema en el cual la actividad basada en formularios generaba vínculos de control de calidad incorrectos. La dirección URL de actividad incluía un `http://pid-ppc` no deseado al principio de la dirección URL, que ahora se ha eliminado para garantizar una vinculación precisa. (TGT-52557)
* Se ha corregido un problema en el cual [!DNL Target] generaba vínculos de control de calidad no válidos para actividades basadas en formularios. (TGT-52528 y TGT-52603)
* Se ha corregido un problema por el cual parecía que se procesaba el guardado de una actividad modificada pero nunca se completó, y no se mostraba ningún mensaje de error en [!DNL Target]. (TGT-52461)
* Se ha corregido un problema en el cual el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado no detectaba automáticamente el valor `at_property`. (TGT-52347)
* Se ha corregido un problema que causaba que se registraran dos modificaciones cuando solo se esperaba una después de cambiar entre los modos [!UICONTROL Examinar] y [!UICONTROL Diseño] en el VEC al interactuar con un elemento de formulario. (TGT-52455)
* Se ha corregido un problema que impedía seleccionar la configuración [!UICONTROL Se hizo clic en un elemento] en el VEC actualizado debido a un error que indicaba que el selector no era válido, ya se estaba utilizando o no era visible. (TGT-52467)
* Se ha corregido un problema por el cual al agregar una casilla de [!UICONTROL Oferta de recomendación] en el VEC actualizado, se mostraban cuadros duplicados (fantasma). Al cambiar entre Experiencia A y B se han añadido repetidamente más cuadros fantasma. (TGT-52505 y TGT-52519)
* Se ha corregido un problema en la interfaz de usuario de [!DNL Target] actualizada en el cual los cambios realizados en una oferta de HTML a través del menú [!UICONTROL Oferta] no se reflejaban en la actividad asociada y viceversa. Este comportamiento ahora coincide con la IU heredada, donde las actualizaciones se sincronizan correctamente entre el menú [!UICONTROL Oferta] y la actividad. (TGT-52540 y TGT-52541)
* Se ha corregido un problema por el cual las actualizaciones recientes de [!UICONTROL Fragmentos de experiencias] en la [!UICONTROL Biblioteca de ofertas] no se reflejaban al intentar usarlas en una actividad. (TGT-52659)
* Se ha corregido un problema de localización en la traducción al chino simplificado de un mensaje de confirmación. A la versión anterior le faltaban comillas alrededor del nombre de la ubicación y utilizaba un lenguaje informal, a diferencia de la guía de estilo del cliente. La traducción actualizada ahora utiliza la puntuación adecuada y un tono formal. (TGT-52364)

### [!DNL Target Standard/Premium] 25.5.3 (22 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema en el cual la característica de búsqueda por nombre de la lista [!UICONTROL Actividades] no funcionaba correctamente con consultas de varias palabras. (TGT-52529)
* Se ha corregido un problema que impedía excluir experiencias de [!UICONTROL actividades de Automated Personalization] (AP). (TGT-52383)
* Se ha corregido un problema por el cual la opción &quot;[!UICONTROL Contains]&quot; no se mostraba en [!UICONTROL Reglas de filtro] al administrar contenido en actividades AP. (TGT-52384)
* Se ha corregido una incoherencia de la creación de informes en las actividades [!UICONTROL Automated Personalization] (AP), relacionada específicamente con la forma en que se realiza el seguimiento de las ofertas predeterminadas y se crean los informes correspondientes con los valores `optionLocalId` del sistema interno de [!DNL Target].
* Se ha corregido un problema en el cual los vínculos de control de calidad no ofrecían la experiencia de actividad deseada. (TGT-52163)
* Se ha corregido un problema en el cual los usuarios con permisos de [!UICONTROL Aprobador] no podían editar actividades activas correctamente y recibían el mensaje de error &quot;Acceso denegado&quot;. (TGT-52416)
* Se ha corregido un problema en el cual los refinamientos de audiencia no se mostraban para ciertas actividades en la interfaz de usuario actualizada de [!DNL Target]. (TGT-52057)
* Se ha corregido un problema que provocaba que las refinaciones de audiencia y las audiencias de actividad se invirtieran en la interfaz de usuario actualizada. (TGT-52158)
* Se ha corregido un problema en el cual la generación de ofertas ad hoc resultaba en ofertas duplicadas. (TGT-51938)
* Se ha corregido un problema que bloqueaba las actualizaciones de ofertas y mostraba de forma incorrecta el error &quot;Usuario no válido&quot;. (TGT-52361)
* Se ha corregido un problema que impedía guardar actividades existentes, lo que activaba un error de &quot;Entrada de usuario no válida&quot;. (TGT-52422)
* Se ha corregido un problema que bloqueaba la edición de ofertas de HTML existentes, lo que activaba un error de &quot;Entrada de usuario no válida&quot; al guardar, incluso cuando no se realizaban cambios en el código. (TGT-52351)
* Se ha corregido un problema que impedía que [!DNL Target] reconociera el carácter &quot;#&quot; en la dirección URL de un sitio web. (TGT-52093)
* Se ha corregido un problema que impedía editar [!DNL Recommendations] actividades para agregar o actualizar promociones, lo que provocaba errores al guardar y promociones duplicadas. (TGT-52343)
* Se ha corregido un problema que impedía realizar cambios en los criterios o diseños en [!DNL Recommendations] actividades, lo que daba como resultado un error de &quot;JSON no válido: nombre de propiedad no reconocido&quot;. (TGT-52375)
* Se ha corregido un problema por el cual los criterios de secuencia no se mostraban correctamente en el [!UICONTROL Compositor de experiencias visuales] (VEC) para las actividades [!DNL Recommendations]. (TGT-52435)
* Se corrigió un problema en el cual las vistas no se identificaban correctamente en las páginas de SPA al usar [!DNL Adobe Experience Platform Web SDK]. (TGT-52106)
* Se ha corregido un problema en el cual los detalles de la toma de decisiones en el dispositivo (ODS) no se guardaban correctamente, a pesar de estar incluidos en la carga útil de la operación por lotes. (TGT-52406)
* Se ha agregado un campo `audienceMetadata` a las actividades, lo que permite leerlo y actualizarlo durante la edición. (TGT-51004)
* Se ha añadido un mensaje de error para avisar a los usuarios cuando un periodo de tiempo de audiencia no es válido. (TGT52522)
* Se ha actualizado la estructura de la actividad para admitir audiencias duplicadas de diferentes tipos. (TGT-51200)

<!--
### [!DNL Adobe Target] [!DNL AI Assistant] release (May 16, 2025)

We are thrilled to announce the launch of the [!DNL AI Assistant] in [!DNL Adobe Target]! This powerful user interface feature is designed to help you navigate and understand [!DNL Target] concepts with ease. Available across multiple products in [!DNL Adobe Experience Cloud], including [!DNL Target], [!DNL AI Assistant] is here to revolutionize your experience.

[!DNL AI Assistant] in [!UICONTROL Target] is a conversational tool that you can use to accelerate your workflows with [!DNL Experience Platform] applications and services. Use [!DNL AI Assistant] to boost your overall productivity and amplify your understanding of product knowledge

In [!DNL Target], the first phase of [!DNL AI Assistant] provides invaluable product knowledge grounded in [!DNL Experience League] documentation. Whether you are setting up a profile script, troubleshooting errors, or considering an upgrade to the AEP Web SDK, [!DNL AI Assistant] has you covered.

For more information, see [Coworker skills for Adobe Target](/help/main/c-intro/coworker-skills.md).
-->

### [!DNL Target Standard/Premium] 25.5.2 (8 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Los usuarios de [!DNL Target] con derechos de [!UICONTROL Administrador de productos] y [!UICONTROL Administrador de sistemas] ahora pueden editar toda la configuración en las páginas de [!UICONTROL Administración], independientemente de su rol en [!DNL Target]. Los usuarios sin estos permisos tienen acceso de solo lectura a esta configuración. Esta actualización asegura un control de acceso más estricto sobre [Configuración de administración](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Se ha corregido un problema de almacenamiento en caché que impedía guardar la actividad [Preferencias del sitio](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Se ha corregido un problema en el cual los clientes no podían habilitar la selección por ID y clase en la sección [!UICONTROL Preferencias del sitio] después de cargar el sitio en el VEC. La configuración de [!UICONTROL Preferencias del sitio] se revirtió automáticamente a deshabilitada incluso después de habilitarse. (TGT-52207)
* Se ha corregido un problema en el cual el [!UICONTROL Compositor de experiencias visuales] (VEC) no mostraba la página correcta cuando las direcciones URL de [entrega de páginas](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) terminaban con una barra diagonal (/). (TGT-52237)
* Se ha corregido un problema que impedía eliminar las modificaciones de código personalizado al cambiar experiencias. (TGT-52240)
* Se ha corregido un problema en el cual las modificaciones de HTML en el VEC superponían elementos de página existentes. (TGT-52265)
* Se ha corregido un problema que impedía editar código personalizado en el VEC actualizado debido a que el código personalizado existente no era visible en el editor. (TGT-52272)
* Se ha corregido un problema que provocaba el mensaje de error &quot;No se permiten nombres duplicados&quot; al guardar una actividad de Recommendations. (TGT-52318)
* Se ha corregido un problema en el VEC actualizado que impedía a los clientes editar elementos de texto o eliminar objetos contenedores. (TGT-52348)
* Se ha corregido un problema que impedía que [!DNL Customer Journey Analytics] se mostrara correctamente en una página de actividad [!UICONTROL Información general]. (TGT-52359)
* Se ha corregido un problema que impedía que los grupos de informes persistieran en las actividades [!UICONTROL Automated Personalization] (AP). (TGT-52368)
* Se ha corregido un problema que impedía guardar actividades que incluían Offer Decisioning. (TGT-52390)
* Se ha corregido un problema por el cual se seleccionaba la oferta predeterminada, pero se mostraba contenido de otras ofertas en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Prueba multivariable] (MVT). (TGT-52372)
* Se ha corregido la lógica de permisos de GET para comprobar con O entre el acceso completo a la organización y el acceso específico a la organización y al usuario. (TGT-52374)
* Se ha corregido un problema por el cual los nombres de audiencia no se mostraban después de seleccionar una audiencia para [!UICONTROL Contenido administrado] y [!UICONTROL Audiencias de informes], aunque se había habilitado [!UICONTROL Mostrar solo seleccionados]. (TGT-52393)

### [!DNL Target Standard/Premium] 25.5.1 (5 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que impedía que se mostraran los refinamientos de audiencia para determinadas actividades en la IU actualizada. (TGT-52057)
* Se ha corregido un problema que impedía el uso de audiencias combinadas en actividades de. (TGT-52346)
* Se ha corregido un problema que impedía la creación de una nueva actividad en un espacio de trabajo no predeterminado mediante una audiencia solo de actividad desde el mismo espacio de trabajo. (TGE-52349)
* Se ha corregido un problema que provocaba que las audiencias solo de actividad desaparecieran de la interfaz de usuario actualizada después de crear y seleccionar una audiencia nueva. (TGT=52091)
* Se ha corregido un problema que impedía el uso de audiencias duplicadas en las actividades de. (TGT-51200 y TGT-52057)
* Se ha corregido un problema que provocaba que las refinaciones de audiencia y las audiencias de actividad se invirtieran en la interfaz de usuario actualizada. (TGT-52158)
* Se ha corregido un problema que impedía la creación de una nueva actividad debido al error de entrada del usuario: &quot;espacio de trabajo no predeterminado no permitido para este usuario&quot;. (TGT-52267)
* Se ha corregido un problema que impedía que las ofertas se mostraran en la interfaz de usuario actualizada tanto para espacios de trabajo predeterminados como no predeterminados. [!DNL Target] ahora muestra ofertas de ambos espacios de trabajo. (TGT-52339)
* Se ha corregido un problema en el cual [!DNL Target] no advertía a los clientes al editar una actividad y cambiar un elemento de sitio web modificado. (TGT-52100)
* Se ha corregido un problema por el cual al editar una oferta con ofertas ad hoc se creaba una nueva oferta en lugar de actualizar la existente. (TGT-52135)
* Se ha corregido un problema que provocaba un error de carga no válida al mover ofertas a carpetas. (TGT-52325)
* Se ha corregido un problema que provocaba un error de entrada del usuario al mover ofertas a carpetas. (TGT-52296)
* Se agregó un campo `audienceMetadata` para cada actividad, y se aseguró de que se lea y actualice al editar la actividad. (TGT-51004)

### [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba discrepancias en los listados de audiencia entre la página de configuración de [!UICONTROL Actividad] y la página de información general de [!UICONTROL Informes]. (TGT-52203)
* Se ha corregido un problema que impedía añadir una nueva página a una actividad debido a un error de entrada de usuario no válido. (TGT-52263)
* Se ha corregido un problema que provocaba que `OptionLocalIDs` se incrementara incorrectamente cuando la opción permanecía sin cambios. (TGT-52187)
* Se ha corregido un problema que provocaba que `location` y `OptionLocalIDs` se incrementaran incorrectamente cuando la opción permanecía sin cambios. (TGT-52188)
* Se ha corregido un problema que provocaba que la ubicación en la página [!UICONTROL Información general] de la actividad fuera incorrecta. (TGT-52182)
* Se ha corregido un problema por el cual no se mostraba una advertencia de selector no válido para una ubicación no válida. (TGT-52110)
* Se ha corregido un problema que impedía que los archivos de informes descargados mostraran correctamente los datos presentes en la interfaz de usuario de informes. (TGT-52068)
* Se ha corregido un problema para que las operaciones por lotes no fallaran después de agregar reglas de entrega de página. (TGT-52097)
* Se ha corregido un problema que provocaba que [!DNL Target] recortara todos los parámetros de consulta de la dirección URL del sitio web. (TGT-52100)
* Se ha resuelto un error de consola que impedía que los clientes crearan actividades en la interfaz de usuario [!DNL Target] heredada y actualizada. (TGT-52181)
* Se ha corregido un problema que impedía a los clientes añadir nuevas páginas, lo que provocaba un error de entrada de usuario no válido. (TGT-52258)
* Se ha corregido un problema que provocaba que las modificaciones desaparecieran después de agregar páginas adicionales y luego volver a la pestaña [!UICONTROL Experiencias]. (TGT-52264)
* Se ha corregido un problema que impedía a los clientes cambiar la audiencia en una actividad de [!UICONTROL segmentación de experiencias] (XT). (TGT-52191)
* Se ha corregido un error que impedía editar una actividad XT debido a una regla de IU no admitida. (TGT-52273)
* Se ha corregido un problema en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado en el cual las rutas de exploración no siempre se mostraban en la parte inferior del editor, lo que causaba dificultades al seleccionar elementos con precisión. (TGT-52169)
* Se ha corregido un problema por el cual la lista desplegable [!UICONTROL Audiencia] no mostraba todas las audiencias debido a la paginación. (TGT-52204)
* Se ha corregido un problema que provocaba un mensaje de entrada de datos no válido al agregar nuevas ofertas en actividades [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Se ha corregido un problema por el cual [!UICONTROL Analytics for Target] (A4T) se seleccionaba incorrectamente como fuente de informes, aunque el cliente no tuviera acceso a A4T. (TGT-52226)
* Se ha corregido un problema que impedía guardar una actividad con la métrica de URL [!UICONTROL Ver una página]. (TGT-52260)
* Se ha corregido un problema que impedía que los clientes seleccionaran espacios de trabajo al crear ofertas dentro de una actividad. (TGT-52289)
* Se ha corregido un problema que bloqueaba a los clientes la creación de actividades en todos los espacios de trabajo. (Tgt-52218)
* Se ha corregido un problema por el cual las modificaciones de una experiencia se mostraban incorrectamente al cambiar a otra experiencia. (TGT-52184)
* Se corrigió un problema en el cual la oferta predeterminada se mostraba incorrectamente en la interfaz de usuario de [!DNL Target] al abrir la actividad. (TGT-52198)

### Actualización de permisos de Target (22 de abril de 2025)

Esta actualización futura mejora el control de la organización sobre las configuraciones de instancia de [!DNL Target], lo que evita actualizaciones accidentales que podrían afectar a la entrega de la actividad en varios equipos de prueba y personalización.

Efectivo el 22 de abril de 2025, solamente los administradores de [!UICONTROL Product] y [!UICONTROL Solutions] podrán actualizar la configuración en las secciones de [!UICONTROL Administración], independientemente de sus roles en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tendrán acceso de solo lectura a las secciones [!UICONTROL Administración].

Para obtener más información, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

### [!DNL Target Standard/Premium] 25.4.4 (17 de abril de 2025)

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

### [!DNL Target Standard/Premium] 25.4.3 (11 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un error que impedía que los clientes abrieran la ventana emergente de información de audiencia para determinadas actividades de [!UICONTROL Segmentación de experiencias] (XT). (TGT-52049)
* Se ha corregido un problema en el cual la configuración de audiencia se revertía a &quot;[!UICONTROL Todos los visitantes]&quot; después de los cambios realizados en el [!UICONTROL Compositor de experiencias visuales] (VEC). (TGT-52132)
* Se ha corregido un problema en el cual los refinamientos de audiencia no se mostraban para actividades específicas (TGT-52057)
* Se ha corregido un problema que impedía a los clientes insertar un [!UICONTROL Fragmento de experiencia] en el espacio de trabajo predeterminado. (TGT-52073)
* Se ha corregido un problema por el cual una oferta se mostraba como &quot;Contenido no encontrado&quot; y no se mostraba en la página [!UICONTROL Ofertas] para una actividad de [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Se ha añadido la capacidad de permitir audiencias duplicadas dentro de una actividad. (TGT-51200)
* Se ha corregido un problema por el cual aparecía un nombre de mbox incorrecto en la página [!UICONTROL Objetivos y configuración] para una actividad XT después de la edición. (TGT-52026)
* Se corrigió un problema en el cual `defaultContent` se mostraba en las opciones a pesar de no estar en `experiences/optionLocations`. (TGT-52036)
* Se ha corregido un problema para garantizar que las cadenas vacías no se convirtieran en valores nulos. (TGT-52037)
* Se ha corregido un problema que requería que los clientes reconfiguraran [!UICONTROL Objetivo de optimización] en [!UICONTROL Configuración de informes] en la página [!UICONTROL Objetivos y configuración] después de las ediciones. (TGT-52071)
* Se ha corregido un problema en el cual una actividad sin reglas de entrega de página mostraba varias reglas en la página [!UICONTROL Información general]. (TGT-52084)
* Se ha añadido un mensaje de error para los usuarios que intentan guardar una oferta con caracteres fuera del plano multilingüe básico, como emojis. (TGT-52105)
* Se ha corregido un problema que causaba que, al abrir una actividad, se mostrara el siguiente mensaje de error: &quot;Esta actividad está utilizando una o más audiencias eliminadas en el origen&quot;. (TGT-52120)
* Se ha corregido un problema por el cual las métricas de ClickTrack no se mostraban en el [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado durante la edición. (TGT-52152)
* Se ha corregido un problema en el cual una dirección URL con un parámetro de consulta como ubicación de la actividad no mostraba el parámetro de consulta en la página [!UICONTROL Información general] de la actividad. (TGT-51635)
* Se ha corregido un problema que impedía que se mostrara toda la URL de la experiencia en [!UICONTROL modo Examinar] en el [!UICONTROL Compositor de experiencias visuales] (VEC). (TGT-52101)
* Se ha corregido un problema por el cual al editar una actividad de, la entrega de la página agregaba &quot;/&quot; al final de la dirección URL, lo que resultaba no válido. (TGT-52114)
* Se ha corregido un problema por el cual el vínculo [!UICONTROL Control de calidad de la actividad] del [!UICONTROL Compositor de experiencias basadas en formularios] se redireccionaba incorrectamente a la página principal de [!DNL Adobe Experience Cloud]. (TGT-52055)
* Se ha corregido un problema por el cual las páginas adicionales agregadas a la actividad [!UICONTROL Prueba A/B] no se conservaban después de guardar y volver a abrir. (TGT-51994)
* Se ha corregido un problema que impedía que los clientes eliminaran estilos en la sección de estilos en línea. (TGT-52070)
* Se ha restaurado el acceso a [tarjetas de definición de audiencia](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) en el cuadro de diálogo [!UICONTROL Control de calidad de la actividad], de forma similar a la IU heredada. (TGT-52056)
* La IU actualizada no guardó páginas o audiencias sin realizar modificaciones. Si los clientes agregaron nuevas páginas o audiencias a una actividad pero no realizaron cambios en ellas, [!DNL Target] descartó las audiencias sin modificar al guardar. Se han añadido notificaciones en lugares relevantes para informar a los usuarios de este comportamiento. (TGT-52104)

### [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba que las audiencias de experiencia desaparecieran de las actividades de. (TGT-52003)
* Se ha corregido un problema que provocaba elementos inesperados durante la entrega. (TGT-52011)
* Se ha corregido un problema que impedía que los clientes vieran la audiencia en el gráfico de segmentación de la página de vista Encima[!UICONTROL r]y durante la edición de la actividad. (TGT-52050)
* Se ha corregido un problema que impedía que los clientes reordenaran experiencias en orden de prioridad en [!UICONTROL actividades de segmentación de experiencias] (XT). (TGT-52054)
* Se ha corregido un problema que provocaba un procesamiento incorrecto al deshacer cambios de estilo de texto. (TGT-51876)
* Se ha corregido un problema que al modificar una oferta de redireccionamiento, [!DNL Target] también quitaba cualquier selector de [!UICONTROL ClickTrack] asociado con esa oferta. (TGT-51936)
* Se ha corregido un problema que provocaba que [!DNL Target] guardara el selector de forma incorrecta al cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Se ha corregido un problema que provocaba un error de nombre no válido después de abrir y cerrar el selector de mbox en la página [!UICONTROL Objetivos y configuración] sin realizar ningún cambio. (TGT-51983)
* Se ha corregido un problema que bloqueaba la edición de ofertas ad hoc creadas en la IU heredada de [!DNL Target]. (TGT-51984)
* Se ha corregido un problema que bloqueaba las actividades de edición que tienen ofertas ad-hoc que contienen código personalizado. (TGT-51995)
* Se ha corregido un problema que provocaba que las reglas de exclusión se mostraran como reglas de inclusión al editar definiciones de audiencia combinadas. (TGT-51999)
* Se ha corregido un problema que impedía que el código personalizado se mostrara correctamente durante la edición de experiencias. (TGT-52005)
* Se ha corregido un problema que hacía que la opción [!UICONTROL Insertar antes] no estuviera disponible para insertar contenido antes de la barra de navegación. (TGT-52031)
* Se ha corregido un problema que impedía resaltar correctamente la experiencia predeterminada en los informes. (TGT-51716)
* Se ha corregido un problema que activaba un mensaje de `default message [Invalid optionLocalIds: xx]]` al crear una actividad. (TGT-52038)

### Versión 2.11.8 de at.js (31 de marzo de 2025)

* Se ha resuelto una vulnerabilidad identificada por CodeQL en la validación de sufijos de cadena para evitar casos extremos durante las operaciones de cambio de tamaño y movimiento. (TNT-51516)

### [!DNL Target Standard/Premium] 25.3.8 (28 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema que hacía que la página [!UICONTROL Actividades] se cargara lentamente. (TGT-51151)

### [!DNL Target Standard/Premium] 25.3.7 (26 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema que bloqueaba el guardado de actividades de varias páginas si una página se eliminaba después de realizar modificaciones. (TGT-51988)
* Se ha resuelto un error que se producía al editar una actividad: `default message [Invalid optionLocalIds: xx]]`. (TGT-51985)
* Se ha resuelto un problema en el cual al agregar nuevas modificaciones a una actividad se eliminaban las existentes. (TGT-51981)
* Se ha resuelto un problema en el cual reemplazar una audiencia por &quot;[!UICONTROL Todos los visitantes]&quot; durante la creación o edición de la actividad provocaba el error &quot;No se permiten audiencias duplicadas&quot;. (TGT-51978)
* Se ha resuelto un problema que provocaba el error &quot;Entrada de usuario no válida&quot; al guardar una actividad [!UICONTROL Prueba A/B]. (TGT-51976)
* Se ha resuelto un problema que impedía que las métricas calculadas se mostraran correctamente en la página [!UICONTROL Objetivos y configuración]. (TGT-51975)
* Se ha resuelto un problema que impedía la coincidencia de `companyName` y `reportSuite` en la configuración de [!DNL Analytics] para la métrica `pageviews`. (TGT-51965)
* Se ha resuelto un problema en el cual al cambiar de experiencia en una actividad de se eliminaban modificaciones. (TGT-51945)
* Se ha resuelto un problema en el cual al eliminar una audiencia de página también se eliminaban los selectores [!UICONTROL ClickTrack]. (TGT-51935)
* Se ha resuelto un problema que impedía editar una actividad después de abrir su página [!UICONTROL Información general]. (TGT-51931)
* Se ha resuelto un problema que provocaba un error de `[Unused optionLocalIds: 0]]` durante la creación de la actividad. (TGT-51920)
* Se ha resuelto un problema en el cual algunos cambios no se traducían correctamente después de eliminar los cambios de estilo de texto. (TGT-51876)
* Se ha resuelto un problema que impedía que las audiencias de destino se actualizaran correctamente en [!UICONTROL Compositor de experiencias basadas en formularios]. (TGT-51845)
* Se ha resuelto un problema en el cual la dirección URL del [!UICONTROL Compositor de experiencias visuales] no se actualizaba correctamente durante la navegación de la actividad. (TGT-51832)
* Se ha resuelto un problema que impedía que las ofertas aparecieran en la interfaz de usuario de [!UICONTROL Ofertas], a pesar de mostrarse correctamente al crear una actividad y agregar ofertas. (TGT-51805)
* Se ha resuelto un problema en el cual algunas actividades carecían de una pantalla de reserva para mostrar el contenido predeterminado cuando no se podía entregar el contenido personalizado o de destino. (TGT-51638)
* Se ha resuelto un problema que impedía que las ofertas en directo y ciertas carpetas se mostraran correctamente en la interfaz de usuario de [!UICONTROL Ofertas]. (TGT-51628)
* Se ha resuelto un problema que impedía que algunas cadenas de URL y goURL se localizaran correctamente. (TGT-35741)
* Se ha corregido un problema que impedía que las funciones ([!UICONTROL Aprobador], [!UICONTROL Editor] y [!UICONTROL Observador]) se localizaran correctamente en la interfaz de usuario de [!DNL Target]. (TGT-29925)

### [!DNL Target Standard/Premium] 25.3.6 (14 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto el error &quot;Entrada de usuario no válida&quot; en las actividades de [!UICONTROL Compositor de experiencias visuales] (VEC) con [!UICONTROL Rastreo de clics] habilitado cuando se usa el mismo selector de [!UICONTROL ClickTrack] varias veces. (TGT-51921)
* Se ha corregido el error &quot;Entrada de usuario no válida&quot; en las actividades VEC con ubicaciones compartidas (por ejemplo, selector HEAD) y ofertas idénticas. (TGT-51879)
* Se ha corregido un problema que provocaba que las modificaciones de experiencia se compartieran entre audiencias. (TGT-51815)
* Se han resuelto errores de validación al crear actividades debido a conflictos de ID de segmento. Los errores se produjeron cuando [!DNL Target] detectó actividades existentes usando segmentos anónimos. (TGT-51784)
* Se ha resuelto un problema que impedía que [!DNL Target] guardara actividades con reglas de exclusión en una audiencia. (TGT-51581)
* Se ha resuelto un problema que impedía a los clientes crear, eliminar o mover carpetas sin acceso al espacio de trabajo predeterminado. (TGT-51499)
* Se ha resuelto un problema que provocaba que las solicitudes GET fallaran al recuperar la lista de métricas [!DNL Analytics]. (TGT-51106)

### [!DNL Target Standard/Premium] 25.3.5 (11 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema que impedía a los usuarios cambiar ofertas en el panel [!UICONTROL Modificaciones]. (TGT-51800)
* Se ha resuelto un problema por el cual las acciones se mostraban incorrectamente en el panel izquierdo para experiencias y audiencias, incluido el modo [!UICONTROL ClickTrack]. (TGT-51895)
* Se ha resuelto un problema en el cual los selectores [!UICONTROL ClickTrack] no se aplicaban a la página de audiencia correcta. (TGT-51871)

### [!DNL Target Standard/Premium] 25.3.4 (7 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha resuelto un problema en el cual las audiencias solo de actividad no eran visibles en el panel [!UICONTROL Audiencias], lo que impedía su edición o reutilización. (TGT-51860)
* Se ha corregido un problema que impedía que los clientes de [!DNL Target Standard] crearan actividades mediante la creación de informes de [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Se ha corregido un problema que excluía los contadores de ID locales de la carga útil durante las operaciones de creación y edición por lotes. (TGT-51867)

### [!DNL Target Standard/Premium] 25.3.2 (6 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema por el cual al copiar una actividad con una audiencia solo de actividad no se podía crear una nueva actividad y se utilizaba por error la audiencia de la actividad original. (TGT-51855)
* Se ha corregido un problema que impedía editar [!UICONTROL actividades de segmentación de experiencias] (XT) con audiencias solo de actividad. (TGT-51846)
* Se ha corregido un problema en el cual el [!UICONTROL Compositor de experiencias visuales] (VEC) no podía aplicar correctamente las modificaciones a una experiencia en la primera edición. (TGT-51843)
* Se ha corregido un problema que activaba un error de &quot;ID&quot; al hacer clic en ciertos elementos dentro del VEC. (TGT-51814)
* Se ha actualizado la administración de errores en el VEC durante la creación de actividades. (TGT-51759)
* Se ha corregido un problema por el cual una vista que faltaba en el panel [!UICONTROL Modificaciones] provocaba un error de &quot;entrada de usuario no válida&quot; al guardar la actividad. (TGT-51827)
* Se ha corregido un problema que impedía la creación de criterios de recomendaciones. (TGT-51834)
* Se ha añadido un mensaje de confirmación antes de redirigir a una dirección URL diferente. (TGT-51703)
* Se han corregido problemas con las pruebas de integración de GraphQL en ofertas y carpetas. (TGT-51839)

### [!DNL Target Standard/Premium] 25.3.1 (3 de marzo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Una audiencia combinada puede incluir subgrupos, cada uno de los cuales contiene varias audiencias. En esta versión se ha corregido un problema que impedía que se mostraran las audiencias de subgrupos en el cuadro de diálogo [!UICONTROL Reglas]. (TGT-51813)
* Se ha resuelto un problema en el cual algunas audiencias de experiencia se reemplazaban por [!UICONTROL Todos los visitantes] al abrir actividades antiguas. (TGT-51812)
* Se ha resuelto un problema que impedía editar actividades con audiencias solo de actividad. (TGT-51807)
* Se ha resuelto un problema que impedía editar las modificaciones del encabezado de página en la interfaz de usuario de [!DNL Target] actualizada. (TGT-51797)
* Se ha resuelto un error nulo que se producía al duplicar una experiencia, eliminar otra experiencia y, a continuación, intentar guardar la actividad. (TGT-51796)
* Se ha resuelto un problema que impedía que las reglas de exclusión de audiencia se mostraran en el panel de información de la audiencia durante el paso [!UICONTROL Segmentación] de la creación de actividades. (TGT-51579)
* Se han actualizado los mensajes de error localizados en coreano. (TGT-51701 y TGT-51699)

### [!DNL Target Standard/Premium] 25.2.3 (26 de febrero de 2025)

Esta versión incluye las siguientes actualizaciones:

* Se ha resuelto un problema que impedía realizar actualizaciones de la actividad después de la versión [!DNL Target] 25.2.1 para algunas actividades. (TGT-51781)
* Se ha resuelto un problema en el cual se eliminaban todos los cambios de audiencia en el estado al cancelar el proceso de creación de actividades (seleccionando [!UICONTROL Cancelar] en lugar de [!UICONTROL Agregar audiencia]). (TGT-51769 y TGT-51770)
* Se ha resuelto un problema en el cual el [!UICONTROL Compositor de experiencias visuales] (VEC) no se podía cargar para algunas actividades, particularmente cuando se usaba código personalizado.  Este problema hizo que el VEC mostrara una pantalla en blanco o que la interfaz de usuario [!DNL Target] volviera a su versión anterior. (TGT-51758)
* Se ha resuelto un problema en el cual las modificaciones se descartaban después de editar la entrega de página para las audiencias. (TGT-51756)
* Se ha resuelto un problema en el cual todas las audiencias que no eran métricas (audiencias de página y experiencia) se eliminaban de las actividades al cambiar un tipo de métrica en la página [!UICONTROL Objetivos y configuración]. (TGT-51753)
* Se ha resuelto un problema en el cual al hacer clic en [!UICONTROL Cancelar] mientras se editaba una actividad, se desplazaba la interfaz de usuario de Target a [!UICONTROL Lista de actividades] en lugar de a la página [!UICONTROL Detalles de la actividad]. (TGT-51731)
* Se ha resuelto un problema que impedía que los clientes descargaran informes mediante la opción [!UICONTROL Exportar informes a CSV]. (TGT-51708)
* Se ha resuelto un problema en el Compositor de experiencias basadas en formularios en el cual se mostraba incorrectamente a [!DNL Target Standard] clientes como usuarios de [!UICONTROL Propiedades], una característica de [!DNL Target Premium]. (TGT-51678)
* Se ha corregido un problema que bloqueaba la visualización de atributos [!DNL Adobe Experience Platform] al crear nuevas ofertas. (TGT-51665)
* Se han movido todos los filtros activos del inventario [!DNL Recommendations] a la búsqueda rápida, lo que alinea la interfaz de usuario con la búsqueda en el catálogo [!UICONTROL Catalog Search] en lugar del carril [!UICONTROL Filter]. (TGT-50723)

### Versión 2.11.7 de at.js (26 de febrero de 2025)

Esta versión incluye la siguiente actualización:

* Se corrigió el registro de telemetría cuando `localStorage` no está disponible. La telemetría estaba ocasionando un problema a algunos clientes que tenían `localStorage` deshabilitado en sus navegadores.

Para obtener más información sobre esta versión de at.js y las anteriores, consulte [Detalles de la versión de at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

### Target Standard/Premium 25.2.1 (martes, 17 de febrero de 2025) {#ui-update-2}

Esta versión incluye las siguientes actualizaciones:

* Actualización de la interfaz de usuario de [!UICONTROL Actividades]
* Actualización de la interfaz de usuario [!DNL Recommendations]

#### Actualización de la interfaz de usuario de [!UICONTROL Actividades]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!UICONTROL Actividades] actualizada.

>[!NOTE]
>
>A partir del 17 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Actividades]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Actividades]. Las fases posteriores actualizarán los clientes restantes.

>[!IMPORTANT]
>
>Para obtener información importante acerca del plan de fin de vida útil de la opción de versión de interfaz de usuario [!DNL Target], consulte [[!DNL Target] Desaprobación de la opción de versión de interfaz de usuario](/help/main/r-release-notes/release-notes.md#toggle).

En función del último sistema de diseño de [!DNL Adobe Spectrum], la actualización estandariza los patrones de diseño que antes eran incoherentes, a la vez que agrega nuevas mejoras, como las siguientes:

* [Se rediseñó el sistema de informes](/help/main/administrating-target/reporting.md) para obtener mejores datos sobre los resultados de la actividad.
* [[!UICONTROL Se ha actualizado la página Registro de cambios]](/help/main/c-activities/change-log.md), y ahora se obtiene la información de [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} para obtener información en tiempo real.
* [Vistas de lista personalizables](/help/main/c-activities/activities.md) para una mejor flexibilidad en las diferentes necesidades del equipo.
* [Información rápida y pantallas de detalles mejoradas](/help/main/c-activities/activities.md) para obtener acceso a la información con mayor facilidad.
* [Opciones de filtro y búsqueda persistentes en la sesión](/help/main/c-activities/activities.md).
* [Se ha vuelto a compilar por completo el [!UICONTROL Compositor de edición visual]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) con compatibilidad para las últimas actualizaciones de seguridad de los proveedores de navegadores y una interfaz de usuario moderna.

  Para obtener información sobre las diferencias entre el VEC actualizado y la versión anterior, consulte:

  * [Cambios en el Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
  * [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Se ha actualizado [!DNL Chrome] la extensión](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) que admite Manifiesto V3 para aumentar la seguridad y mejorar la compatibilidad con cookies de origen.

![Actualización de actividades](/help/main/r-release-notes/assets/activities-refresh.png)

#### Actualización de la interfaz de usuario [!DNL Recommendations]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!DNL Recommendations] actualizada.

>[!NOTE]
>
>A partir del 17 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Recommendations]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Actividades]. Las fases posteriores actualizarán los clientes restantes.

En función del último sistema de diseño de [!DNL Adobe Spectrum], la actualización estandariza los patrones de diseño que antes eran incoherentes, a la vez que agrega nuevas mejoras, como las siguientes:

* La [búsqueda en el catálogo de productos](/help/main/c-recommendations/c-products/catalog-search.md) ahora incluye una base de datos actualizada que permite una sincronización de productos en tiempo real.
* Los objetos de [!UICONTROL Recommendations] ([!UICONTROL Criterios], [!UICONTROL Diseños], [!UICONTROL Colecciones] y [!UICONTROL Exclusiones]) [creados a través de API ya están disponibles en la interfaz de usuario](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* [La configuración de Recommendations](/help/main/administrating-target/recommendations-settings.md) se ha consolidado en la sección [!UICONTROL Administración].
* Vistas de lista personalizables para una mejor flexibilidad en diferentes necesidades del equipo.
* Editores de código JSON y HTML actualizados con [resaltado de sintaxis y numeración de líneas](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Pantallas de información y detalles rápidos y mejorados para un acceso más sencillo a la información.
* Opciones de filtro y búsqueda persistentes de sesión.

![Actualización de la interfaz de usuario de Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

### Target Standard/Premium 25.1.1 (viernes, 09 de enero de 2025). {#ui-update-1}

Esta versión incluye las siguientes actualizaciones:

#### Actualización de la interfaz de usuario de [!UICONTROL Biblioteca de ofertas]

Para mejorar la experiencia de usuario de [!DNL Adobe Target] usuarios, esta versión actualiza la interfaz de usuario de la [!UICONTROL Biblioteca de ofertas].

>[!NOTE]
>
>Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. En el primer paso se actualizó el grupo inicial de clientes de Target a la nueva interfaz de usuario de Ofertas. Las fases posteriores actualizarán los clientes restantes.

>[!IMPORTANT]
>
>Para obtener información importante acerca del plan de fin de vida útil de la opción de versión de interfaz de usuario [!DNL Target], consulte [[!DNL Target] Desaprobación de la opción de versión de interfaz de usuario](/help/main/r-release-notes/release-notes.md#toggle).

Con el último sistema de diseño de [!DNL Adobe Spectrum], esta actualización estandariza los patrones de diseño incoherentes e introduce nuevas mejoras, entre las que se incluyen las siguientes:

* **Administración de ofertas en lotes**: Seleccione y elimine o mueva varias ofertas simultáneamente.

* **[!UICONTROL Editor de código] actualizaciones**: editores HTML y JSON actualizados con resaltado de sintaxis y numeración de líneas.

* **Tarjetas de oferta mejoradas**: Información rápida y tarjetas de detalles mejoradas para facilitar el acceso a la información.

* **Filtros y búsquedas persistentes**: agrega opciones de filtro y búsqueda persistentes en la sesión.

Para obtener más información, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) y los subartículos de esta sección. Todos los artículos de Ofertas de esta sección se han actualizado para reflejar estos cambios en la interfaz de usuario.

Este breve vídeo resalta los cambios que se han producido en esta versión:

![Vídeo de actualización de la IU de ofertas](/help/main/r-release-notes/assets/offers-video-v2.gif)
