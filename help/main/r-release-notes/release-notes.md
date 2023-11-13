---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d2aac088d5f1ae60a4b0e7ac1fff9960e2959130
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 82%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Estándar/Premium 23.11.1 (13 y 14 de noviembre de 2023)

Esta versión está programada para los siguientes días:

* **13 de noviembre**: región Asia-Pacífico (APAC)
* **14 de noviembre**: región de América
* **14 de noviembre**: región de Europa, Oriente Medio y África (EMEA)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha mejorado la [Control de calidad de actividad](/help/main/c-activities/c-activity-qa/activity-qa.md) función para admitir [no permitir ofertas duplicadas](/help/main/c-activities/t-automated-personalization/managing-exclusions.md) para experiencias en [!UICONTROL Automated Personalization] actividades. (TGT-46627)
* Se ha añadido información de objeto en la IU de [!DNL Target] para ayudar a los clientes a comprender por qué podría no haber datos disponibles en los informes de actividad si no se asigna tráfico a la experiencia de control. En la información de objeto se incluye un vínculo para obtener más información: [¿Por qué no hay datos disponibles para el informe de actividad?](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B). (TGT-46610)
* Se ha corregido un problema que impedía que las actividades se mostraran correctamente en la página [!UICONTROL Actividades] de algunos clientes. (TGT-46830)
* Se han corregido los siguientes problemas que afectaban a las actividades que utilizan [[!UICONTROL Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) como fuente de informes:
   * Se ha corregido un problema que impedía que algunos clientes vieran los datos de los informes. (TGT-46557)
   * Se ha corregido un problema que a veces provocaba lo siguiente [!UICONTROL Ver en Analytics] Vínculo en las páginas de informes de actividad para no funcionar correctamente. (TGT-46731)
   * Se ha corregido un problema que impedía los datos de para [!UICONTROL Alza] y [!UICONTROL Confianza] para mostrarse correctamente en la [!DNL Target] IU. (TGT-46592, TGT-46554 y TGT-46586)

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
