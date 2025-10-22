---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 17%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.10.1 (22 de octubre de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**Actividades**

+++ Ver detalles
* **Se ha resuelto un problema de uso en la IU actualizada**. [!UICONTROL Observers] ahora puede obtener una vista previa de las actividades usando la opción [!UICONTROL View Activity], al igual que en la interfaz de usuario heredada. (TGT-51741)
* Los usuarios de **[!UICONTROL Observer]ahora pueden ver el contenido de la actividad en la interfaz de usuario actualizada.**: se ha restaurado la visibilidad de los usuarios con la función Observador en la IU de actividad actualizada. Anteriormente, los observadores no podían ver las modificaciones, ofertas y cambios de contenido, una funcionalidad disponible en la interfaz de usuario heredada. (TGT-53785)
* Los usuarios de **[!UICONTROL Approver]ahora pueden editar los objetivos de la actividad sin el error de privilegio del editor.** ha resuelto un problema de permisos en la interfaz de usuario de creación de actividades que impedía que los usuarios de nivel de aprobador guardaran cambios en la configuración avanzada de objetivos. Los usuarios afectados recibieron un error de `403 Forbidden.Resource` que requería privilegios de editor, a pesar de tener acceso suficiente. (TGT-53819)

+++

**Públicos**

+++Ver detalles
* **Selección de varias audiencias se restauró en los informes de &quot;Solo esta actividad&quot;.** ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía que los usuarios seleccionaran varias audiencias en la sección [!UICONTROL This activity only] de [!UICONTROL Goals & Settings]. (TGT-53283)
* Los **gráficos de informes basados en audiencias ahora muestran correctamente los datos de conversión.** ha resuelto un problema en la ficha [!UICONTROL Reports] que provocaba que fallaran los gráficos al seleccionar audiencias no predeterminadas. Aunque había datos y métricas de confianza disponibles, el gráfico visual solo mostraba una línea sólida, lo que dificultaba el análisis. (TGT-53769)
* **La interfaz de usuario de [!UICONTROL Targeting] ahora indica claramente las reglas de audiencia excluidas.** resolvió un problema en la sección [!UICONTROL Targeting] de la interfaz de usuario de creación de actividades en el cual las reglas de audiencia establecidas en [!UICONTROL Exclude] no se mostraban claramente. Esto provocaba confusión al revisar la lógica de segmentación, especialmente para audiencias que excluían direcciones URL específicas. (TGT-53809)
* **Los valores de definición de audiencia ahora se pueden seleccionar y copiar en la pestaña [!UICONTROL Targeting].** ha resuelto un problema en la interfaz de creación de actividades que impedía que los usuarios seleccionaran y copiaran valores de reglas de audiencia en la pestaña [!UICONTROL Targeting]. Esta funcionalidad estaba disponible en la interfaz de usuario heredada pero no aparecía en la interfaz de usuario actualizada. (TGT-53856)

+++

**Localización**

+++Ver detalles
* **Se ha corregido la traducción incorrecta de &quot;quote&quot; en el contexto del editor de páginas zh_CN.** corrigió un error de traducción contextual en la configuración regional zh_CN donde el término &quot;quote&quot; se tradujo incorrectamente como &quot;报价&quot;, lo que implica un presupuesto de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el significado deseado hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53841)
* **Se ha corregido la traducción incorrecta de &quot;cita eliminada&quot; en el contexto del editor de páginas zh_CN.** corrigió un error de traducción en la configuración regional zh_CN donde &quot;cotización eliminada&quot; se representaba de forma inexacta como &quot;移除了报价&quot;, lo que implica una cotización de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53843)
* **Se ha corregido un error de traducción de &quot;cita reordenada&quot; en el contexto del editor de páginas zh_CN.** corrigió un error de traducción contextual en la configuración regional zh_CN donde &quot;oferta reordenada&quot; se traducía de forma incorrecta como &quot;重新排列了报价&quot;, lo que implica una cotización de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53844)
* **Se ha corregido la traducción errónea de &quot;quote changed&quot; en el contexto del editor de páginas zh_CN.** corrigió un error de traducción en la configuración regional zh_CN donde &quot;quote changed&quot; se representaba de forma inexacta como &quot;更改了报价&quot;, lo que sugiere un presupuesto de precio comercial. En la sección Tipografía > Estilo de encabezado > Comilla de bloque, el término hace referencia a un elemento de formato (bloque de comillas), no a los precios. (TGT-53845)

+++

**Recommendations**

+++Ver detalles
* **Los cambios en el selector de CSS para Recommendations ahora se guardan correctamente.** ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía a los usuarios actualizar el selector de CSS para las ubicaciones de recomendación. Los cambios se revirtieron después de guardar y bloquear las actualizaciones de los contenedores de segmentación. (TGT-53835)
* **La selección de eventos de carga de página ahora persiste en las modificaciones de recomendaciones.** ha resuelto un problema en la interfaz de usuario de creación de actividad que impedía a los usuarios guardar cambios al cambiar el tipo de evento de una recomendación de [!UICONTROL View] a [!UICONTROL Page Load]. Aunque la selección parecía correcta, se revirtió después de salir, bloqueando la publicación de la actividad. (TGT-53957)

+++

**Informes**

+++Ver detalles
* **&quot;[!UICONTROL Export order details to CSV]&quot; ahora descarga datos completos.** ha resuelto un problema en la interfaz de usuario [!UICONTROL Overview] actualizada que hacía que la opción &quot;[!UICONTROL Export Order details to CSV]&quot; descargara archivos vacíos, incluso cuando había datos de informe válidos. (TGT-53787)

+++

**Seguridad**

+++Ver detalles
* Se agregó **filtro previo de IMS para proteger los puntos de conexión GQL de la exposición de datos entre organizaciones.**: se ha resuelto una vulnerabilidad de seguridad en la ficha Administración que afectaba a los extremos de GraphQL licenseGroups y targetProperties. El problema se debía al uso de la API JIL con un token de cliente de administrador que se podía aprovechar para acceder a datos de productos entre organizaciones. (TGT-53837)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles
* **Se ha restaurado la estabilidad de creación en la IU de creación de actividad.** ha resuelto un problema intermitente en la interfaz de usuario del VEC que provocaba que fallara la creación y que se pudiera hacer clic en los vínculos de forma inesperada, lo que redirigía a los usuarios fuera de la página. (TGT-53153)
* **Edición restaurada para actividades guardadas en la interfaz de usuario de creación de actividades.** ha resuelto un problema que impedía que los usuarios editaran actividades después de guardar las modificaciones. Las actividades afectadas permanecieron atascadas en &quot;[!UICONTROL Applying initial modifications]&quot;, lo que bloqueó nuevas actualizaciones y ocultó el botón [!UICONTROL Cancel]. (TGT-53631)
* **El VEC ya no se detiene en &quot;[!UICONTROL Applying initial modifications]&quot;.** ha resuelto un problema de rendimiento en el VEC que provocaba largos retrasos al cargar experiencias con un alto número de modificaciones. Los usuarios afectados vieron la interfaz de usuario atascada en &quot;[!UICONTROL Applying initial modifications]&quot; durante varios minutos, especialmente en los escenarios de la Experiencia B. (TGT-53727)
* **El VEC ahora carga modificaciones sin elementos raíz.**
Se ha resuelto un problema en el VEC que provocaba que las experiencias se detuvieran al cargar modificaciones que carecían de un elemento raíz claro. Anteriormente, estas modificaciones provocaban que la interfaz de usuario se bloqueara indefinidamente en &quot;A[!UICONTROL pplying initial modifications]&quot;. (TGT-53799)
* **Guardar cambios en actividades ahora funciona según lo esperado.** ha resuelto un problema relacionado con permisos en la nueva interfaz de usuario de creación que impedía a los usuarios guardar cambios al editar objetivos y configuración avanzada en las actividades. Los usuarios afectados veían una cinta de error roja y un mensaje &quot;Forbidden.Resource&quot;, a pesar de tener el acceso adecuado. (TGT-53816)
* La interfaz de usuario de **VEC ahora conserva las modificaciones de experiencia en todas las vistas.** ha resuelto varios problemas en el VEC actualizado que afectaban al desarrollo de experiencias. Las modificaciones no persistían correctamente, especialmente al utilizar ofertas de HTML o al cambiar entre vistas. (TGT-53825)
* **Ahora todas las vistas se muestran correctamente cuando una modificación abarca varias experiencias.** ha resuelto un problema en la interfaz de usuario de creación de actividad en el cual solo se mostraba una vista cuando se aplicaba una modificación en varias vistas. La información del objeto de desplazamiento no mostraba todas las vistas asociadas, aunque la modificación se hubiera aplicado correctamente. (TGT-53827)
* **El VEC ya no se detiene intermitentemente en &quot;[!UICONTROL Applying initial modifications]&quot;.** resolvió un problema intermitente en el VEC en el cual las experiencias no se cargaban y permanecían atascadas en &quot;[!UICONTROL Applying initial modifications]&quot;. Este comportamiento era incoherente y, a veces, activaba bucles de redirección o requería la limpieza manual de la caché. (TGT-53916)
* No se pudo reproducir el problema de carga de **VEC.** Investigamos un problema informado en el cual el VEC permanecía bloqueado en &quot;[!UICONTROL Applying initial modifications]&quot; al editar actividades existentes. Se sospechaba que el comportamiento estaba relacionado con contenido de HTML que no tenía un elemento principal. Seguiremos monitorizando la periodicidad y recomendaremos el uso de contenedores estructurados para las ofertas de HTML para garantizar la estabilidad. (TGT-53972)
* El modo **[!UICONTROL Design]del VEC ya no se comporta de forma intermitente como el modo [!UICONTROL Browse].** resolvió un problema en la interfaz de usuario en el cual el modo [!UICONTROL Design] se comportaba de forma intermitente como el modo [!UICONTROL Browse], lo que permitía vínculos `<a>` en los que se podía hacer clic e impedía la selección de elementos. Esto provocaba que la casilla de verificación hover desapareciera y bloqueara los flujos de trabajo de modificación. (TGT-53136)
* **Los clics en el botón en el modo [!UICONTROL Composer] ya no almacenan en déclencheur la redirección de páginas.** ha resuelto un problema en la interfaz de usuario actualizada del VEC en el cual al hacer clic en un botón en modo [!UICONTROL Composer] se producía una redirección inesperada a la dirección URL de destino del botón. Esto impedía que los usuarios editaran los elementos de call-to-action (CTA) e interrumpía el flujo de trabajo de creación. (TGT-53137)
* **Las actualizaciones de código de oferta en las actividades de personalización automatizada ahora se guardan sin errores.** ha resuelto un problema en la nueva interfaz de usuario de creación que provocaba el error &quot;[!UICONTROL Invalid user input]&quot; al actualizar el código de oferta en las actividades [!UICONTROL Automated Personalization]. El error bloqueaba a los usuarios la posibilidad de guardar cambios, incluso cuando la entrada era válida. (TGT-53586)
* El modo **[!UICONTROL Design]del VEC ahora bloquea la navegación de vínculos para los componentes editables.** ha resuelto un problema en el VEC actualizado en el cual los elementos en los que se puede hacer clic, como botones y vínculos, activaban la redirección de páginas incluso mientras se encontraba en modo [!UICONTROL Design]. Este comportamiento imitaba el modo [!UICONTROL Browse] e impedía que los usuarios modificaran componentes clave. (TGT-53696)
* La métrica **&quot;[!UICONTROL Clicked an element]&quot; ahora funciona sin redireccionamiento ni error.** ha resuelto un problema en la nueva interfaz de usuario de creación que provocaba redirecciones inesperadas y pantallas en blanco al seleccionar la métrica de conversión &quot;[!UICONTROL Clicked an element]&quot;. Al hacer clic en un botón durante la instalación, se desencadenó la navegación en lugar de registrar el elemento, lo que provocó el error &quot;[!UICONTROL element not found]&quot;. (TGT-53817)
* **Las actividades existentes ya no se quedan atascadas en el bucle de carga infinita durante la edición.** solucionó un problema en la nueva interfaz de usuario de creación en el cual al editar una actividad existente en el VEC, la página permanecía atascada en un bucle de carga infinito. Este problema no afectaba a las actividades de nueva creación y se activaba por modificaciones preexistentes en la página. (TGT-53913)
* **Las páginas de actividad existentes con modificaciones ahora se cargan correctamente en el VEC.** ha resuelto un problema en el VEC actualizado que provocaba que las páginas permanecieran atascadas en la fase de carga al editar una actividad existente con modificaciones guardadas. Las nuevas actividades se cargaron sin problemas, pero las actividades configuradas anteriormente no se procesaron. (TGT-53967)

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
