---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: cbbaea46460b298cbff5015fcf60c37a8aff7751
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 60%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.3.1 (28-30 de marzo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **28 de marzo**: región de Europa, Oriente Medio y África (EMEA)
* **29 de marzo**: región Asia-Pacífico (APAC)
* **30 de marzo**: región de las Américas

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
|--- |--- |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<p>(Fecha de la versión: 30 de marzo de 2023) | [!DNL Target] permite elegir métricas basadas en eventos binomiales o métricas basadas en eventos continuos al utilizar [!UICONTROL A4T] para actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática].<P>Tenga en cuenta el siguiente cambio en las métricas admitidas:<ul><li>[!DNL Target] conservó el comportamiento anterior para las actividades existentes hasta el 9 de septiembre de 2023. Después de esta fecha, las actividades que utilizan métricas no compatibles se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento.</li></ul>Junto con esta función, se han actualizado los siguientes tutoriales:<ul><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Asignación automática] ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=es){target=_blank}</li><li>[Configuración de informes de A4T en [!DNL Analysis Workspace] para actividades de [!UICONTROL Segmentación automática] ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=es){target=_blank}</li></ul> |

* Se ha mejorado la sincronización de audiencias y actividades para que los elementos creados en [!DNL Adobe Experience Platform] y [!DNL Adobe Audience Manager] están disponibles en la [!DNL Target] IU más rápido. (TGT-44568)
* Se ha realizado un cambio para permitir que los usuarios eliminen el [!UICONTROL Dirección URL predeterminada] under [!UICONTROL Administración] > [!UICONTROL Compositor de experiencias visuales] > [!UICONTROL Dirección URL predeterminada]. Este cambio permite a los clientes volver a cambiar la dirección URL predeterminada a una cadena vacía, que anteriormente no era posible tras la configuración inicial. (TGT-44577)
* Se han eliminado restricciones que impedía a los clientes editar o eliminar audiencias predeterminadas (audiencias con nombres reservados). (TGT-44655)
* Se ha deshabilitado &quot;[!UICONTROL Listo]&quot; mientras se cargaban los spinners estaban visibles en el [!DNL Target] IU al crear [audiencias combinadas](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Se ha corregido la variable [!UICONTROL Idioma] vínculo en la parte inferior del [!UICONTROL Audiencias] para que se vincule correctamente al &quot;[!UICONTROL Preferencias de comunicación de la cuenta]&quot;. (TGT-43562)
* Se ha resuelto un problema que a veces impedía que los clientes crearan [!UICONTROL Prueba A/B] actividades después de seleccionar la variable [!UICONTROL Adobe Analytics] opción bajo [!UICONTROL Administración] > [!UICONTROL Informes] > [!UICONTROL Solución de Experience Cloud de informes]. (TGT-44844)
* Se ha corregido un problema que impedía que los clientes vieran la última experiencia en un [!UICONTROL Prueba multivariable] actividad con muchas experiencias desde dentro de [!UICONTROL Compositor de experiencias visuales] (VEC). La variable [Ruta DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) en la parte inferior del VEC, a veces impedía que los clientes vieran la última experiencia. (TGT-44578)
* Se ha corregido un problema que provocaba que la URL de exploración del VEC no reflejara la página actual que es visible en una sesión normal del explorador si la página requiere autorización o invoca redirecciones. (TGT-44350)
* Se ha corregido un problema que impedía que los clientes cambiaran la variable [!UICONTROL Filtrar criterios no compatibles] configurar en [!UICONTROL Recommendations] > [!UICONTROL Configuración]. (TGT-44398)
* Se ha corregido un problema que provocaba que las solicitudes de POST crearan nuevas [!DNL Recommendations] fuentes en las que se producen errores al usar [!UICONTROL Clasificaciones de Analytics] con grupos de informes con puntos en sus nombres. (TGT-44598)
* Vínculos actualizados en la variable [!DNL Target] La interfaz de usuario de señala al nuevo [Extensión de Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Seguridad mejorada para evitar intentos de falsificación de solicitudes del lado del servidor (SSRF) en [!DNL Recommendations] fuentes. (TGT-43769)
* Se ha corregido un problema que impedía a los clientes ver imágenes de vista previa en [!DNL Recommendations] diseños si el nombre de la imagen contiene [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* Se ha corregido un problema que provocaba algunos [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank} para escapar en la variable [!UICONTROL Modificaciones] panel mientras edita [!UICONTROL Texto/HTML] en una actividad [!UICONTROL Experiencias] página. (TGT-44600)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].

## Versión 2.10.2 de at.js (7 de marzo de 2023)

* Se ha corregido un problema que provocaba que la función `trackEvent` devolviera siempre un error.

Para obtener información sobre todas las versiones de at.js, consulte [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de las versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/main/r-release-notes/target-release-notes.md). |
