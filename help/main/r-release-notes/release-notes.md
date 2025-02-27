---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3b79138f305454c29850a1ce3999aa324f95359f
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 20%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.2.3 (26 de febrero de 2025)

Esta versión incluye las siguientes actualizaciones:

* Se ha resuelto un problema que impedía realizar actualizaciones de la actividad después de la versión [!DNL Target] 25.2.1 para algunas actividades. (TGT-51781)
* Se ha resuelto un problema en el cual se eliminaban todos los cambios de audiencia en el estado al cancelar el proceso de creación de actividades (seleccionando [!UICONTROL Cancel] en lugar de [!UICONTROL Add Audience]). (TGT-51769 y TGT-51770)
* Se ha resuelto un problema en el cual el [!UICONTROL Visual Experience Composer] (VEC) no se podía cargar para algunas actividades, especialmente cuando se utilizaba código personalizado.  Este problema hizo que el VEC mostrara una pantalla en blanco o que la interfaz de usuario [!DNL Target] volviera a su versión anterior. (TGT-51758)
* Se ha resuelto un problema en el cual las modificaciones se descartaban después de editar la entrega de página para las audiencias. (TGT-51756)
* Se ha resuelto un problema en el cual todas las audiencias que no eran métricas (audiencias de página y experiencia) se eliminaban de las actividades al cambiar un tipo de métrica en la página [!UICONTROL Goals & Settings]. (TGT-51753)
* Se ha resuelto un problema en el cual al hacer clic en [!UICONTROL Cancel] mientras se editaba una actividad, se navegaba desde la interfaz de usuario de Target a [!UICONTROL Activities List] en lugar de a la página de [!UICONTROL Activity Details]. (TGT-51731)
* Se ha resuelto un problema que impedía que los clientes descargaran informes a través de la opción [!UICONTROL Export Reports to CSV]. (TGT-51708)
* Se ha resuelto un problema en el Compositor de experiencias basadas en formularios en el cual se mostraba incorrectamente a [!DNL Target Standard] clientes como usuarios de [!UICONTROL Properties], una característica de [!DNL Target Premium]. (TGT-51678)
* Se ha corregido un problema que bloqueaba la visualización de atributos [!DNL Adobe Experience Platform] al crear nuevas ofertas. (TGT-51665)
* Se movieron todos los filtros activos del inventario [!DNL Recommendations] a la búsqueda rápida, alineando la interfaz de usuario con [!UICONTROL Catalog Search] en lugar del carril [!UICONTROL Filter]. (TGT-50723)

## Versión 2.11.7 de at.js (26 de febrero de 2025)

Esta versión incluye la siguiente actualización:

* Se corrigió el registro de telemetría cuando `localStorage` no está disponible. La telemetría estaba ocasionando un problema a algunos clientes que tenían `localStorage` deshabilitado en sus navegadores.

Para obtener información sobre esta versión de at.js y las anteriores, consulte [Detalles de la versión de at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

## Target Standard/Premium 25.2.1 (martes, 17 de febrero de 2025)

Esta versión incluye las siguientes actualizaciones:

* Actualización de la interfaz de usuario [!UICONTROL Activities]
* Actualización de la interfaz de usuario [!DNL Recommendations]

### Actualización de la interfaz de usuario [!UICONTROL Activities]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!UICONTROL Activities] actualizada.

>[!NOTE]
>
>A partir del 17 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Activities]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Activities]. Las fases posteriores actualizarán los clientes restantes.

En función del último sistema de diseño de [!DNL Adobe Spectrum], la actualización estandariza los patrones de diseño que antes eran incoherentes, a la vez que agrega nuevas mejoras, como las siguientes:

* [Se rediseñó el sistema de informes](/help/main/administrating-target/reporting.md) para obtener mejores datos sobre los resultados de la actividad.
* [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md) página, obteniendo ahora la información de [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} para obtener información en tiempo real.
* [Vistas de lista personalizables](/help/main/c-activities/activities.md) para obtener una mejor flexibilidad en las diferentes necesidades del equipo.
* [Información rápida y pantallas de detalles mejoradas](/help/main/c-activities/activities.md) para obtener acceso a la información con mayor facilidad.
* [Opciones de filtro y búsqueda persistentes en la sesión](/help/main/c-activities/activities.md).
* [Se ha vuelto a compilar por completo [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) con compatibilidad con las últimas actualizaciones de seguridad de los proveedores de exploradores y una interfaz de usuario moderna.

  Para obtener información sobre las diferencias entre el VEC actualizado y la versión anterior, consulte:

   * [Cambios en el Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
   * [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Se ha actualizado [!DNL Chrome] la extensión](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) que admite Manifiesto V3 para aumentar la seguridad y mejorar la compatibilidad con cookies de origen.

![Actualización de actividades](/help/main/r-release-notes/assets/activities-refresh.png)

### Actualización de la interfaz de usuario [!DNL Recommendations]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!DNL Recommendations] actualizada.

>[!NOTE]
>
>A partir del 17 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Recommendations]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Activities]. Las fases posteriores actualizarán los clientes restantes.

En función del último sistema de diseño de [!DNL Adobe Spectrum], la actualización estandariza los patrones de diseño que antes eran incoherentes, a la vez que agrega nuevas mejoras, como las siguientes:

* La [búsqueda en el catálogo de productos](/help/main/c-recommendations/c-products/catalog-search.md) ahora incluye una base de datos actualizada que permite una sincronización de productos en tiempo real.
* Los objetos de [!UICONTROL Recommendations] ([!UICONTROL Criteria], [!UICONTROL Designs], [!UICONTROL Collections] y [!UICONTROL Exclusions]) [creados mediante API ya están disponibles en la interfaz de usuario](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* [La configuración de Recommendations](/help/main/administrating-target/recommendations-settings.md) se ha consolidado en la sección [!UICONTROL Administration].
* Vistas de lista personalizables para una mejor flexibilidad en diferentes necesidades del equipo.
* Editores de código JSON y HTML actualizados con [resaltado de sintaxis y numeración de líneas](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Pantallas de información y detalles rápidos y mejorados para un acceso más sencillo a la información.
* Opciones de filtro y búsqueda persistentes de sesión.

![Actualización de la interfaz de usuario de Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

## Target Standard/Premium 25.1.1 (viernes, 09 de enero de 2025).

Esta versión incluye las siguientes actualizaciones:

### Actualización de la interfaz de usuario [!UICONTROL Offers Library]

Para mejorar la experiencia de usuario de [!DNL Adobe Target] usuarios, esta versión actualiza la interfaz de usuario de [!UICONTROL Offers Library].

>[!NOTE]
>
>Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. En el primer paso se actualizó el grupo inicial de clientes de Target a la nueva interfaz de usuario de Ofertas. Las fases posteriores actualizarán los clientes restantes.

Con el último sistema de diseño de [!DNL Adobe Spectrum], esta actualización estandariza los patrones de diseño incoherentes e introduce nuevas mejoras, entre las que se incluyen las siguientes:

* **Administración de ofertas en lotes**: Seleccione y elimine o mueva varias ofertas simultáneamente.

* **[!UICONTROL Code Editor]actualizaciones**: editores HTML y JSON actualizados con resaltado de sintaxis y numeración de líneas.

* **Tarjetas de oferta mejoradas**: Información rápida y tarjetas de detalles mejoradas para facilitar el acceso a la información.

* **Filtros y búsquedas persistentes**: agrega opciones de filtro y búsqueda persistentes en la sesión.

Para obtener más información, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) y los subartículos de esta sección. Todos los artículos de Ofertas de esta sección se han actualizado para reflejar estos cambios en la interfaz de usuario.

Este breve vídeo resalta los cambios que se han producido en esta versión:

![Vídeo de actualización de la IU de ofertas](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] `__view__` optimización del ámbito (22 de octubre de 2024)

Entre el 22 de julio de 2024 y el 15 de agosto de 2024, el equipo de [!DNL Target] optimizó el ámbito de `__view__`, lo que mejoró la precisión de los informes de impresión de actividad, visitas y visitantes. Esta optimización pretende capturar automáticamente los datos de los informes para las propuestas procesadas automáticamente y debe ser transparente para la mayoría de las cuentas.

Todos los clientes nuevos de [!DNL Adobe Experience Platform Web SDK] tendrán habilitada esta optimización. Sin embargo, los clientes que migraron desde at.js y no han seguido los pasos de implementación a continuación tienen la optimización deshabilitada. Instamos a estos clientes a revisar sus implementaciones antes del 3 de febrero de 2025. Después de esta fecha, habilitaremos la optimización para todos los clientes. Si no se revisan y ajustan las implementaciones para entonces, los informes podrían verse afectados, como se menciona a continuación. Póngase en contacto con [!DNL Adobe Customer Care] si necesita confirmar si la implementación se ve afectada o si necesita más tiempo para ajustar la implementación.

>[!IMPORTANT]
>
>Si no puede completar la revisión de la implementación y resolver cualquier problema antes del 3 de febrero de 2025, puede solicitar una extensión única de seis meses. Asegúrese de que su solicitud se haya enviado antes del 31 de enero de 2025. Adobe revisará y decidirá sobre su solicitud.

Para beneficiarse de esta optimización en caso de procesamiento manual de propuestas, revise su [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} para asegurarse de que está enviando notificaciones después de procesar manualmente experiencias o cuando utilice el método `applyPropositions` (o la acción correspondiente de [!DNL Launch] como ayudante) para procesar experiencias.

Los escenarios más comunes en los que las experiencias se procesan manualmente incluyen:

* Uso de ofertas JSON
* Utilizando un ámbito de decisión personalizado en una actividad creada en [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* No se usa `renderDecisions: true` al recuperar una actividad creada con [!UICONTROL Form-Based Experience Composer] que usa el ámbito global `__view__`

Si las notificaciones no se implementan como se documenta en [Procesar contenido personalizado](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} en la guía de *Recopilación de datos*, es posible que falten datos de informes en [!DNL Target] y en [Informes de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). En algunos casos, es posible que observe una división de tráfico incorrecta porque no se capturan los datos del sistema de informes. O, en otros casos, informar del mismo evento repetidamente.

Según la implementación, compruebe el impacto de los informes de [!DNL Analytics] y A4T.

[!DNL Platform Web SDK] admite dos tipos de implementación para procesar experiencias y personalizaciones:

* **Una sola llamada para personalización y medición.**

  Inicialmente recomendado, el método de una sola llamada para [!DNL Platform Web SDK] está programado para quedar obsoleto y pasar a ser el método de llamada dividida. Adobe aconseja a todas las nuevas implementaciones que utilicen el nuevo método de llamada dividida y recomienda que los clientes existentes también realicen la transición al método de llamada dividida.

  Si sigue usando el método de una sola llamada, es posible que observe los siguientes cambios inesperados en los informes de [!DNL Analytics]:

   * Un descenso en devoluciones.
   * Las visitas de A4T y [!UICONTROL Page View] no se han vinculado, lo que dificulta la realización de determinados desgloses y correlaciones en los informes de A4T con [!DNL Analytics] eVars y eventos.

* **Dividir llamadas (también conocidas como eventos de principio y final de página).**

  Este tipo de implementación es el nuevo [enfoque de implementación de llamada dividida](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recomendado por [!DNL Adobe]. Con este enfoque, la nueva optimización no afecta a los informes de [!DNL Analytics] ni A4T.

Si tiene preguntas, comuníquese con el [Servicio de atención al cliente de Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

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
