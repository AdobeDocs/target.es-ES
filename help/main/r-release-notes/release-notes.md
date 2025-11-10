---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 693b862bc39fc3b1b7d93988bd80cdd51657354b
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 19%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.11.1 (10 de noviembre de 2025)


**Analytics for Target (A4T)**

+++Ver detalles
* **[!UICONTROL Goals & Settings]mensaje de error al usar [!DNL Adobe Analytics] como fuente de informes en la interfaz de usuario actualizada.** solucionó un problema en la interfaz de usuario de [!UICONTROL Overview] actualizada en el cual la sección Objetivos mostraba el error &quot;Se produjo un error. No podemos completar su solicitud. Póngase en contacto con [!DNL Adobe Client Care] si el problema persiste&quot; cuando [!DNL Adobe Analytics] (A4T) se seleccionó como origen de informes. Los objetivos ahora se muestran correctamente con las métricas [!UICONTROL Adobe Analytics], lo que garantiza una visibilidad coherente en las fuentes de informes. (TGT-54021)

+++

**Públicos**

+++Ver detalles
* **No se pueden seleccionar varias audiencias de informes en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual los usuarios no podían seleccionar varias audiencias de informes recién creadas simultáneamente al editar una actividad. Ahora se pueden asignar varias audiencias a la vez, lo que mejora la flexibilidad y eficacia en la configuración de los informes. (TGT-53253)

+++

**Ofertas de decisiones**

+++Ver detalles
* **No se pueden editar ni reemplazar las ofertas de toma de decisiones en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual las ofertas de toma de decisiones no se podían editar ni reemplazar a través del panel [!UICONTROL Modifications], y los nombres de las ofertas aparecían en blanco. Las ofertas de Decisioning ahora son totalmente accesibles y editables, lo que restaura la paridad con la IU heredada y garantiza que los clientes puedan administrar ofertas directamente dentro de las actividades. (TGT-53884)

+++

**Localización**

+++Ver detalles
* **Se corrigieron varios errores de localización en la interfaz de usuario coreana y japonesa.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 y TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles
* **La promoción por atributo con coincidencia de atributos de entidad no pudo cargar la clave de recomendación después de guardar la actividad.** Se corrigió un problema en el cual las promociones de tipo [!UICONTROL Promotion by Attribute] con tipo de regla [!UICONTROL Entity Attribute Matching] no cargaban la clave de recomendación cuando se editaban después de guardar una actividad. El problema fue causado porque `customKeyId` no se solicitó a través de GraphQL. Las claves de recomendación ahora se cargan correctamente durante las ediciones de promoción. (TGT-53117)
* **La recomendación persiste visualmente al cambiar de ExpB a ExpA.** ha resuelto un problema en el cual al insertar una recomendación en la Experiencia B y, a continuación, cambiar a la Experiencia A, se dejaba visible el cuadro de oferta de recomendación. Esto solo era una incoherencia visual; las modificaciones ahora se representan correctamente al cambiar entre experiencias, lo que garantiza un comportamiento preciso de la interfaz de usuario. (TGT-53911)
* **La clave de recomendación no se carga para [!UICONTROL Promotion by Attribute] con [!UICONTROL Entity Attribute] coincidencias.** resolvió un problema en el cual las promociones de tipo [!UICONTROL Promotion by Attribute] con tipo de regla [!UICONTROL Entity Attribute Matching] no cargaban la clave de recomendación al editarse después de guardar una actividad. Ahora, la clave de recomendación se recupera correctamente mediante GraphQL, lo que garantiza que las promociones se muestren y funcionen según lo esperado. (TGT-53917)
* **La edición de recomendaciones en elementos ocultos de HTML no funciona en la IU actualizada.** ha resuelto un problema en la interfaz de usuario de [!UICONTROL New Create] y VEC en el cual no se podían editar las actividades de recomendación aplicadas a elementos de HTML ocultos. Esta funcionalidad ahora funciona según lo esperado, restaurando la paridad con la IU heredada y asegurando que las recomendaciones se puedan modificar independientemente de la visibilidad del elemento. (TGT-53953)
* **No se pueden editar las actividades de recomendación en elementos HTML ocultos en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual no se podían editar las actividades de recomendación aplicadas a elementos ocultos de HTML. Esta funcionalidad ahora funciona según lo esperado, restaurando la paridad con la IU heredada y asegurando que las recomendaciones se puedan modificar independientemente de la visibilidad del elemento. (TGT-53951)
* **En el catálogo de recomendaciones faltan valores de atributo de forma intermitente en la IU actualizada.** ha resuelto un problema en la interfaz de usuario de [!UICONTROL Recommendations] actualizada en el cual los listados de búsqueda en el catálogo de forma intermitente no mostraban ciertos valores de atributo (por ejemplo, mensaje) aunque estuvieran presentes en la fuente del producto. Ahora, los valores de atributo se cargan de forma coherente en los resultados de búsqueda sin necesidad de reconfigurar las columnas, lo que mejora la fiabilidad y eficacia de la administración del catálogo. (TGT-52769)
* Falta el botón **[!UICONTROL Download Recommendations]para [!DNL Recommendations] actividades en la interfaz de usuario actualizada.** ha resuelto un problema en la interfaz de usuario de [!DNL Recommendations] actualizada en el cual el botón [!UICONTROL Download Recommendations] no era visible para las actividades A/B que usaban recomendaciones. El botón ahora aparece correctamente, lo que permite a los usuarios exportar los datos de recomendaciones según lo esperado y en consonancia con la funcionalidad de la IU heredada. (TGT-53768)
* Falta el botón **[!UICONTROL Download Recommendation Data]en la IU de información general actualizada.** ha resuelto un problema en la interfaz de usuario [!UICONTROL Overview] actualizada en el cual el botón [!UICONTROL Download Recommendation Data] no era visible para las actividades que contenían recomendaciones. El botón ahora aparece correctamente, lo que garantiza que los usuarios puedan exportar los datos de Recommendations directamente sin necesidad de volver a la IU heredada. (TGT-53772)
* **La edición de criterios de actividad a veces resultaba en una pantalla en blanco en la IU actualizada.** ha resuelto un problema en la interfaz de usuario actualizada en el cual al hacer clic en [!UICONTROL Edit Criteria in Experiences] se mostraba ocasionalmente una pantalla en blanco para determinadas actividades. El editor de criterios ahora se carga de forma fiable en todas las actividades, lo que garantiza que los usuarios puedan editar sin interrupción. (TGT-53961)
* **No se pueden editar los criterios de secuencia en la IU actualizada.** Se ha resuelto un problema en la interfaz de usuario actualizada que causaba que al intentar editar [!UICONTROL Sequence Criteria] la ventana emergente de criterios permaneciera atascada durante la carga y mostrara una pantalla en blanco. El editor de criterios ahora se carga correctamente, lo que permite a los usuarios editar y actualizar los criterios de secuencia sin interrupción. (TGT-53985)

+++

**[!UICONTROL Reports]**

+++Ver detalles
* Las ubicaciones **[!UICONTROL Multivariate Test] (MVT) y el problema de informe de gráficos impidieron la generación del informe.** ha resuelto un problema en el cual las actividades MVT no podían generar informes de [!UICONTROL Location Contribution] y Graph en la interfaz de usuario de Target, y mostraba el error &quot;Se produjo un error. No podemos completar su solicitud&quot;. Ahora, los informes se cargan correctamente en la interfaz de usuario, lo que garantiza una visibilidad completa. (TGT-53654)
* **Los informes de MVT no se cargan debido a un error en el informe de contribución de [!UICONTROL Element].** Se ha corregido un problema por el que los informes de actividad MVT no se cargaban en la interfaz de usuario de Target y mostraban el error &quot;No se pudo recuperar el informe de contribución de elementos&quot;. Los informes ahora se muestran correctamente, lo que garantiza una visibilidad completa de las contribuciones de elementos. (TGT-53691)
* **Exportar detalles del pedido a un problema de CSV para las actividades [!UICONTROL Experience Targeting] (XT).** Se ha corregido un problema por el cual la opción [!UICONTROL Export Order Details to CSV] aparecía incorrectamente en las actividades XT y devolvía un archivo vacío. La opción ahora solo se muestra para actividades AP, lo que garantiza una funcionalidad de exportación precisa y evita confusiones. (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles
* **[!UICONTROL Delete Modification]problema con el botón impidió la eliminación de las modificaciones de la actividad.** ha resuelto un problema en el cual el botón [!UICONTROL Delete Modification] de la interfaz de usuario de [!DNL Target] no funcionaba, lo que impedía a los usuarios eliminar modificaciones dentro de las actividades. Ahora el botón funciona según lo esperado, lo que permite eliminar las modificaciones de forma fiable y sin demora. (TGT-53728)
* **Los selectores preferidos no se reconocen en la IU actualizada.** ha resuelto un problema en la IU actualizada en el cual los selectores preferidos, como `data-target-component-id`, no aparecían en la lista de selectores de CSS dentro del VEC. Los usuarios ahora pueden seleccionar de forma fiable los atributos preferidos en lugar de los nombres de clase generados dinámicamente, lo que garantiza una segmentación estable en las actualizaciones de la página de SPA. (TGT-53908)
* **La alineación de la ubicación de la actividad no coincide entre [!UICONTROL Edit] y [!UICONTROL Overview] páginas.** ha resuelto un problema en el cual la numeración de la ubicación de la actividad en la página [!UICONTROL Overview] no se alineaba con las actualizaciones realizadas en la página [!UICONTROL &#x200B; Edit Experience]. Las ubicaciones ahora son coherentes en ambas vistas, lo que garantiza una alineación precisa y evita que falten posiciones o no estén numeradas correctamente. (TGT-53960 y TGT-53954)
* **No se puede volver a cambiar al modo [!UICONTROL Design] en el VEC actualizado.** ha resuelto un problema en la interfaz de usuario actualizada del VEC en el cual los usuarios no podían volver al modo [!UICONTROL Design] después de navegar a una nueva página en modo [!UICONTROL Browse]. La opción [!UICONTROL Design] ahora funciona correctamente, lo que permite aplicar las modificaciones sin problemas en todas las páginas. (TGT-53988 y TGT-53993)
* **El parámetro de consulta no se muestra en la descripción general de la actividad.** ha resuelto un problema en la interfaz de usuario actualizada en el cual los parámetros de consulta no se mostraban en la página [!UICONTROL Overview] de las actividades, lo que provocaba discrepancias entre [!UICONTROL Overview] y las direcciones URL de entrega de página. Los parámetros de consulta ahora se muestran correctamente, lo que garantiza que las ubicaciones de la actividad estén completamente representadas y sean coherentes en todas las vistas. (TGT-53701)

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
