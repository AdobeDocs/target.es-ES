---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 97b1d78de2d6ba33c1dd72494edcfc97fc3ba7e6
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 55%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!UICONTROL Visual Experience Composer] extensión del ayudante (23 de abril de 2024)

El legado [!DNL Target] La extensión de ayuda del Compositor de experiencias visuales se ha creado con Manifest V2. [!DNL Google] anunció que ya no permitirá extensiones creadas con Manifest V2 a partir de junio de 2024. Para obtener más información, consulte [[!UICONTROL Visual Experience Composer] extensión del ayudante](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] recomienda que los clientes cambien al más reciente [Extensión de Ayuda de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) tan pronto como sea posible.

## Actualizaciones para `Browser:iPad` y `Browser:iPhone` in [!UICONTROL Browser] atributos de audiencia (30 de abril de 2024)

| Actualizaciones | Detalles |
|--- |--- |
| [!UICONTROL Browser:iPad] y [!UICONTROL Browser:iPhone] actualizado en [Atributos del explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) se utiliza para crear audiencias. | [!DNL Adobe Target] le permite [segmentar en cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los visitantes que utilizan un específico [opciones del navegador o](/help/main/c-target/c-audiences/c-target-rules/browser.md) cuando visiten su página.<P>Empezando por [!DNL Target] Standard/Premium 24.3.1 (del 4 al 6 de marzo de 2024), audiencias integradas creadas con la interfaz de usuario de Target, como `Browser:iPad` y `Browser:iPhone` se actualizará para realizar el direccionamiento adecuado para [!DNL iPad] y [!DNL iPhone] usando `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` y `profile.mobile.isTablet`.<P>Esta actualización no requiere ninguna acción por parte de los clientes.<p><B>Importante</b>: para que los clientes realicen la segmentación adecuada de [!DNL iPad] y [!DNL iPhone] en los scripts de perfil (y segmentos de JavaScript), el cliente debe realizar cambios manuales de la siguiente manera: **30 de abril de 2024**. Para ver ejemplos de configuraciones alternativas que deben cambiarse manualmente, consulte [Actualizaciones para [!DNL iPad] y [!DNL iPhone] in [!UICONTROL Browser] atributos de audiencia](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!UICONTROL Visual Editing Helper] extensión (14 de marzo de 2024)

Esta versión incluye las siguientes mejoras y correcciones para [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) extensión para [!DNL Google Chrome]:

* Se ha mejorado el mecanismo de carga del iFrame al realizar la creación en los sitios web de los clientes.
* Se ha corregido un problema que hacía que la extensión duplicara cookies al realizar la creación en [!UICONTROL Visual Experience Composer] (VEC).

## [!DNL Target] Standard/Premium 24.3.1 (4-6 de marzo de 2024)

Esta versión está programada para los siguientes días:

* **4 de marzo**: región de Europa, Oriente Medio y África (EMEA)
* **5 de marzo**: región Asia-Pacífico (APAC)
* **6 de marzo**: región de las Américas

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido la lógica que calcula el número de selectores únicos en una actividad. (TGT-47878)
* Se ha corregido un problema que provocaba [!UICONTROL Multivariate] (MVT) actividades configuradas con [!UICONTROL Analytics for Target] (A4T) Los informes de no se mostrarán correctamente. (TGT-47490)
* Se ha mejorado el mensaje de advertencia que se muestra en los informes cuando se utiliza una experiencia sin tráfico como experiencia de control. (TGT-47537)
* Se han añadido muchas correcciones de back-end y localización.

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
