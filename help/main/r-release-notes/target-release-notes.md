---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 15%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 22 de julio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.3 (viernes, 24 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles
* Se corrigió un problema en el cual el método `buildViews` de la clase de generador establecía incorrectamente `viewMaxLocalId` en el recuento total de vistas, en lugar de en la asignación de `viewLocalId` más alta. (TGT-53207)
* Se ha introducido un nuevo extremo de API que permite a los usuarios restaurar las opciones de actividad eliminadas anteriormente desde una base de datos secundaria. Esta funcionalidad aprovecha la infraestructura existente proporcionada por las clases `RemovedCampaignElements` y `RemovedOptionInfo`, lo que garantiza la reintegración perfecta de las opciones eliminadas en las actividades activas. (TGT-52903)
* Se ha corregido un problema en la interfaz de usuario [!DNL Target] actualizada en el cual las ofertas eliminadas en las actividades [!UICONTROL Automated Personalization] (AP) se mostraban como `Deleted option with ID: X` en lugar de sus nombres originales (por ejemplo, `Offer Name [Deleted]`, como se muestra en la interfaz de usuario heredada). Esta corrección restaura el etiquetado significativo de las ofertas eliminadas, lo que mejora la claridad y hace que la creación de informes sea más precisa y fácil de usar. (TGT-52921)
* Se ha corregido un problema en la capa de persistencia del back-end por el cual las opciones eliminadas se almacenaban correctamente, pero no se podía acceder a ellas a través de puntos finales de API existentes. Como resultado, las aplicaciones de front-end no pudieron recuperar nombres significativos para las opciones eliminadas, lo que afectó a las vistas históricas de los informes. Esta corrección garantiza que los datos de opciones eliminados conservados ahora se puedan mostrar correctamente en la interfaz de usuario. (TGT-52973)
* Se ha corregido un problema en el cual algunas actividades migradas del front-end de Target a Target Central tenían configuraciones de métricas incoherentes debido a un error de sincronización corregido anteriormente. Específicamente, las actividades que originalmente usaron una métrica de conversión y luego se actualizaron a una métrica basada en análisis retuvieron valores obsoletos en los campos `primaryMetricType` y `successCriteria`. (TGT-52643)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] que hacía que el editor se bloqueara después de hacer clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) ) al crear o editar una actividad [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalles
* Se ha corregido un problema que impedía que [!UICONTROL Catalog Search] cargara resultados adicionales al desplazarse hasta la parte inferior de la lista, restaurando un comportamiento coherente con la interfaz de usuario heredada. (TGT-53088)
* Se ha corregido un problema en el cual la columna [!UICONTROL Number of Products] faltaba en la página [!UICONTROL Collections] en la interfaz de usuario [!DNL Target] actualizada. La columna ahora se muestra correctamente, restaurando la funcionalidad esperada. (TGT-53168)
* Se corrigió un problema en el cual las reglas de [!UICONTROL Collection] no se filtraban correctamente de acuerdo con las reglas. (TGT-53254)
* Se ha corregido un problema que bloqueaba la eliminación de elementos del cuadro de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Se ha corregido un problema que impedía abrir o interactuar con productos sin nombre. Este problema se producía al seleccionar entornos que devolvían resultados sin nombre, lo que impedía el acceso a los detalles del producto. (TGT-53007)
* Se ha corregido un problema que hacía que la página [!UICONTROL Catalog Search] se bloqueara y mostrara una pantalla en blanco al seleccionar ciertos productos. (TGT-53087)
* Se ha corregido un problema en el cual las actividades [!DNL Recommendations] que contenían nombres de métricas de más de 25 caracteres no se podían abrir ni editar debido a limitaciones de API. Esta corrección garantiza la compatibilidad con los nombres de métricas que superan el límite de caracteres y restaura el acceso completo a las actividades afectadas. (TGT-52839)
* Se ha corregido un problema en el cual los usuarios no podían editar la actividad de site_cart_z1 [!DNL Recommendation] en la interfaz de usuario de [!DNL Target]. Al intentar abrir la actividad, se produjo un error en la página [!UICONTROL Overview] que bloqueó el acceso al editor. (TGT-53221)

+++

**Creación de informes**

+++Ver detalles
* Se corrigió un problema en el cual el campo de espacio aislado de la base de datos de actividad no se borraba al cambiar el origen de informes de [!DNL Customer Journey Analytics] o [!DNL Analytics] a [!DNL Target]. Anteriormente, la interfaz de usuario enviaba correctamente la zona protegida: null, pero el backend ignoraba este valor, lo que dejaba los datos obsoletos de la zona protegida en su lugar. El servidor ahora borra correctamente el campo de la zona protegida cuando se recibe un valor nulo. (TGT-52798)
* Se ha vuelto a implementar la capa de persistencia de opciones eliminadas en el backend de Target para admitir la creación de informes históricos precisos en actividades [!UICONTROL Automated Personalization] (AP). Anteriormente, cuando se eliminaba una opción, se perdía su nombre, lo que dificultaba la interpretación de los datos de rendimiento anteriores.

  **Mejoras de clave**:

   * Las opciones eliminadas ahora se rastrean usando la infraestructura existente de `RemovedCampaignElements` y `RemovedOptionInfo`.
   * Cuando se elimina una opción de una actividad AP, se conservan sus metadatos (por ejemplo, ID y nombre).
   * La interfaz de usuario de creación de informes ahora puede mostrar el nombre de opción original (por ejemplo, `Option Name [Deleted]`) junto con las métricas históricas, lo que mejora la claridad y la facilidad de uso.

  Esta actualización garantiza la creación de informes coherentes y significativos, incluso después de eliminar las opciones de una actividad. (TGT-52986)

* Se implementó un nuevo extremo de migración para admitir la transferencia de opciones de actividad eliminadas de actividades basadas en JCR a [!DNL Target] actividades centrales. Esta funcionalidad permite un seguimiento y un sistema de informes coherentes entre sistemas. Esta característica garantiza que las opciones eliminadas se conserven y sincronicen en el front-end y back-end de [!DNL Target], lo que mejora la integridad de los datos y los informes históricos. (TGT-53217)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Se ha corregido un problema en el VEC por el cual la aplicación de una modificación a una vista provocaba duplicación y activaba un error de &quot;entrada de usuario no válida&quot;. (TGT-52886)
* Se corrigió un problema con la funcionalidad [!UICONTROL Undo] para las opciones [!UICONTROL Insert Before] y [!UICONTROL Insert After] al configurar ofertas de imagen en el VEC.

  Anteriormente, deshacer una acción de [!UICONTROL Insert Before] o [!UICONTROL Insert After] en ofertas de imagen resultaba en un comportamiento incoherente o en un error al revertir correctamente la modificación, especialmente en las actividades creadas en la interfaz de usuario de [!DNL Target] heredada. Este problema se ha resuelto para garantizar que las acciones de deshacer ahora funcionen de forma fiable para estas modificaciones. (TGT-52809)

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

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
