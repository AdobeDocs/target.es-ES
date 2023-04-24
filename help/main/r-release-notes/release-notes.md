---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 97%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.3.1 (28 y 30 de marzo de 2023)

Esta versión está disponible según la siguiente programación escalonada:

* **28 de marzo**: región de Europa, Oriente Medio y África (EMEA)
* **29 de marzo**: región Asia-Pacífico (APAC)
* **30 de marzo**: región de las Américas

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
|--- |--- |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<p>(Fecha de la versión: 30 de marzo de 2023) | [!DNL Target] permite elegir métricas basadas en eventos binomiales o métricas basadas en eventos continuos al utilizar [!UICONTROL A4T] para actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].<P>Tenga en cuenta el siguiente cambio en las métricas admitidas:<ul><li>[!DNL Target] conservó el comportamiento anterior para las actividades existentes hasta el 9 de septiembre de 2023. Después de esta fecha, las actividades que utilizan métricas no compatibles se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento.</li></ul>Para obtener más información, consulte “Métricas de objetivo admitidas” en [Compatibilidad de A4T con actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>Con esta función, se han actualizado los siguientes tutoriales:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Asignación automática] ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank}</li><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Segmentación automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank}</li></ul> |

* Se ha mejorado la sincronización de audiencias y actividades para que los elementos creados en [!DNL Adobe Experience Platform] y [!DNL Adobe Audience Manager] están disponibles en la IU de [!DNL Target] más rápido. (TGT-44568)
* Se ha mejorado la IU para permitir que los usuarios quiten la [!UICONTROL URL predeterminada] en [!UICONTROL Administración] > [!UICONTROL Compositor de experiencias visuales] > [!UICONTROL URL predeterminada]. Esta modificación permite a los clientes volver a cambiar la dirección URL predeterminada a una cadena vacía, que anteriormente no era posible tras la configuración inicial. (TGT-44577)
* Se han eliminado restricciones que impedían a los clientes editar o quitar audiencias predeterminadas (audiencias con nombres reservados). (TGT-44655)
* Se ha deshabilitado la opción &quot;[!UICONTROL Listo]&quot; mientras se veían las ruedas giratorias de carga en la IU de [!DNL Target] al crear [audiencias combinadas](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Se ha corregido el vínculo [!UICONTROL Idioma] en la parte inferior de la página [!UICONTROL Audiencias] para que se vincule correctamente a la página [!UICONTROL Preferencias de comunicación de la cuenta]. (TGT-43562)
* Se ha resuelto un problema que a veces impedía que los clientes crearan actividades de [!UICONTROL Prueba A/B] después de seleccionar la opción [!UICONTROL Adobe Analytics] en [!UICONTROL Administración] > [!UICONTROL Creación de informes] > [!UICONTROL Solución de creación de informes de Experience Cloud]. (TGT-44844)
* Se ha corregido un problema que impedía que los clientes vieran la última experiencia en una actividad de [!UICONTROL Prueba multivariada] con muchas experiencias desde dentro del [!UICONTROL Compositor de experiencias visuales] (VEC). La [Ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en la parte inferior del VEC, a veces, impedía que los clientes vieran la última experiencia. (TGT-44578)
* Se ha corregido un problema que provocaba que la URL de Examinar del VEC no reflejara la página actual que es visible en una sesión normal del explorador si esta requiere autorización o invoca redirecciones. (TGT-44350)
* Se ha corregido un problema que impedía que los clientes cambiaran la configuración [!UICONTROL Filtrar criterios no compatibles] en [!UICONTROL Recomendaciones] > [!UICONTROL Configuración]. (TGT-44398)
* Se ha corregido un problema que provocaba que las solicitudes POST para crear fuentes de [!DNL Recommendations] fallaran al utilizar las [!UICONTROL Clasificaciones de Analytics] con grupos de informes con puntos en los nombres. (TGT-44598)
* Se han actualizado los vínculos de la IU de [!DNL Target] para que apunten a la nueva [extensión Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Se ha mejorado la seguridad para evitar intentos de falsificación de solicitudes del lado del servidor (SSRF) en las fuentes de [!DNL Recommendations]. (TGT-43769)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].

## Versión 2.10.2 de at.js (7 de marzo de 2023)

* Se ha corregido un problema que provocaba que la función `trackEvent` devolviera siempre un error.

Para obtener información sobre todas las versiones de at.js, consulte [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} in the [Adobe Target Developer Guide](https://experienceleague.corp.adobe.com/docs/target-dev/developer/overview.html){target=_blank}.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

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
