---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: 'https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ece061af0f50ec45e07b9710d355a9c91731578e
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 42%
---
# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.10.2 (15 de octubre de 2026)

**[!UICONTROL Actividades]**

+++Ver detalles

* **Se muestra una configuración de metas incorrecta en la Descripción general de la actividad**. Se ha corregido un problema por el cual la configuración de objetivos mostrada en la página **[!UICONTROL Información general]** de una actividad era incorrecta. Por ejemplo, `https://` se agregó a la dirección URL de la página, y no se mostró la condición **[!UICONTROL URL contiene]**, aunque la configuración real del objetivo era correcta. (TGT-56326)

+++

**[!UICONTROL Recommendations]**

+++Ver detalles

* **Se muestran recomendaciones de copia de seguridad después de actualizar una promoción en una actividad activa**. Se ha corregido un problema por el cual al editar una promoción en una actividad de [!DNL Recommendations] activa, [!DNL Target] creaba nuevas promociones y unidades de recomendación aunque no hubiera cambiado nada en su definición. (TGT-56369)

+++

**[!UICONTROL Informes]**

+++Ver detalles

* **Ajustes preestablecidos de informes eliminados después de dos semanas**. Se ha corregido un problema por el cual los ajustes preestablecidos de informes que los usuarios guardaban para una actividad se eliminaban automáticamente después de aproximadamente dos semanas. (TGT-56374)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* Se agregó compatibilidad con **Safari a[!DNL Adobe Target]**. [!DNL Target] ahora se admite en el explorador [!DNL Safari]. Tenga en cuenta que el Compositor de experiencias visuales y [!DNL Enhanced Experience Composer] no se admiten en [!DNL Safari]. Como resultado, ahora aparece una superposición en [!DNL VEC] para notificar a los usuarios que deben cambiar a [!DNL Chrome] para utilizar el editor. (TGT-55853)
  [Más información](../c-experiences/c-visual-experience-composer/visual-experience-composer.md#browser-requirements)
+++


## [!DNL Target Standard/Premium] 26.10.1 (13 de octubre de 2026)

**[!UICONTROL Analytics for Target]**

+++Ver detalles

* **Error en la creación de informes de A4T: &quot;Se ha producido un error&quot;**. Se ha corregido un problema por el cual las actividades de [!DNL A4T] que usaban un grupo de informes recién agregado mostraban el error &quot;Se produjo un error&quot; en el informe [!DNL Target] en lugar de en los resultados. Al hacer clic en **[!UICONTROL Ver en Analytics]**, también se mostró un mensaje &quot;Grupo de informes incompatible&quot; en el que faltaba información de clasificación [!DNL Analytics for Target]. (TGT-56389)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* Se muestra **HTML sin procesar en lugar del nombre de oferta de [!DNL Experience Fragments] entregado a través de un mbox**. Se ha corregido un problema en el cual el panel **[!UICONTROL Modificaciones]** mostraba HTML/código sin procesar en lugar del nombre de la oferta cuando se entregaba un [!DNL Experience Fragment] a través de un mbox. (TGT-56241)

+++

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

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
| [Adobe Priority Product Update](https://www.adobe.com/es/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
