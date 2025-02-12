---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 15%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: jueves, 12 de febrero de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Target Standard/Premium 25.2.1 (jueves, 12 de febrero de 2025)

Esta versión incluye las siguientes actualizaciones:

* Actualización de la interfaz de usuario [!UICONTROL Activities]
* Actualización de la interfaz de usuario [!DNL Recommendations]

### Actualización de la interfaz de usuario [!UICONTROL Activities]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!UICONTROL Activities] actualizada.

>[!NOTE]
>
>A partir del 12 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Activities]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Activities]. Las fases posteriores actualizarán los clientes restantes.

En función del último sistema de diseño de [!DNL Adobe Spectrum], la actualización estandariza los patrones de diseño que antes eran incoherentes, a la vez que agrega nuevas mejoras, como las siguientes:

* [Se rediseñó el sistema de informes](/help/main/administrating-target/reporting.md) para obtener mejores datos sobre los resultados de la actividad.
* [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md) página, obteniendo ahora la información de [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} para obtener información en tiempo real.
* [Vistas de lista personalizables](/help/main/c-activities/activities.md) para obtener una mejor flexibilidad en las diferentes necesidades del equipo.
* [Información rápida y pantallas de detalles mejoradas](/help/main/c-activities/activities.md) para obtener acceso a la información con mayor facilidad.
* [Opciones de filtro y búsqueda persistentes en la sesión](/help/main/c-activities/activities.md).
* [Se ha vuelto a compilar por completo [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) con compatibilidad con las últimas actualizaciones de seguridad de los proveedores de exploradores y una interfaz de usuario moderna. Para obtener más información, consulte las opciones de [Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

  Para obtener información sobre las diferencias entre el VEC actualizado y la versión anterior, consulte [Cambios del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md).

* [Se ha actualizado [!DNL Chrome] la extensión](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) que admite Manifiesto V3 para aumentar la seguridad y mejorar la compatibilidad con cookies de origen.

![Actualización de actividades](/help/main/r-release-notes/assets/activities-refresh.png)

### Actualización de la interfaz de usuario [!DNL Recommendations]

A medida que continúa el esfuerzo de modernización de la interfaz de usuario de [!DNL Adobe Target], nos complace anunciar la disponibilidad general de la interfaz de usuario de [!DNL Recommendations] actualizada.

>[!NOTE]
>
>A partir del 12 de febrero, los clientes tendrán acceso gradualmente a la nueva interfaz de usuario de [!UICONTROL Recommendations]. Para garantizar un despliegue sin problemas para todos los clientes, esta versión se implementará en fases controladas. La primera etapa actualizará el grupo inicial de [!DNL Target] clientes a la nueva interfaz de usuario de [!UICONTROL Activities]. Las fases posteriores actualizarán los clientes restantes.

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

Para obtener más información, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) y los subartículos de esta sección.

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
