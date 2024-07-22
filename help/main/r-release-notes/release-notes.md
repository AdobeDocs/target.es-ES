---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44445f269a69a3ac3e3bc88bab8abf9fc4d51663
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 58%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Informes de [!DNL Target] en [!DNL Adobe Customer Journey Analytics] (8 de mayo de 2024)

La integración entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Las principales ventajas de utilizar [!DNL Customer Journey Analytics] como fuente de creación de informes para [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito de [!DNL Customer Journey Analytics] a informes de actividad de [!DNL Target] en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Los especialistas en marketing pueden aprovechar las características de [!DNL Customer Journey Analytics], como el [Panel de experimentación](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analizar más a fondo la personalización de su sitio web.
* Los especialistas en marketing pueden tener una única fuente de informes para [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} y [!DNL Target]. Ambos productos de personalización se pueden conectar a [!DNL Customer Journey Analytics] para obtener una vista más integral de la personalización web.

Para obtener más información, consulte Informes de [Target en Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## Extensión del ayudante de [!UICONTROL Visual Experience Composer] (23 de abril de 2024)

La extensión de ayuda heredada del Compositor de experiencias visuales [!DNL Target] se creó con Manifiesto V2. [!DNL Google] anunció que ya no permitirá extensiones creadas con Manifest V2 a partir de junio de 2024. Para obtener más información, vea [[!UICONTROL Visual Experience Composer] extensión de ayudante ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] recomienda que los clientes cambien a la nueva extensión [Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) lo antes posible.

## Actualizaciones para `Browser:iPad` y `Browser:iPhone` en [!UICONTROL Browser] atributos de audiencia (30 de abril de 2024)

| Actualizaciones | Detalles |
|--- |--- |
| [!UICONTROL Browser:iPad] y [!UICONTROL Browser:iPhone] se han actualizado en [Atributos del explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) que se usan al crear audiencias. | [!DNL Adobe Target] le permite [segmentar cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los visitantes que usan [opciones de explorador o explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) específicas cuando visitan la página.<P>A partir de [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), las audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone`, se actualizarán para realizar el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] mediante `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.<P>Esta actualización no requiere ninguna acción por parte de los clientes.<p><B>Importante</b>: Para que los clientes realicen el direccionamiento adecuado de [!DNL iPad] y [!DNL iPhone] en scripts de perfil (y segmentos de JavaScript), el cliente debe realizar cambios manuales antes del **30 de abril de 2024**. Para ver ejemplos de configuraciones alternativas que deben cambiarse manualmente, consulte [Actualizaciones para [!DNL iPad] y [!DNL iPhone] en [!UICONTROL Browser] atributos de audiencia](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

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
