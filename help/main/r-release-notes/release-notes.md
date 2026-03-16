---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: 44d9cd4de7ff2064e6005a4d7ece7f37194fbf2f
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 41%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.3.2 (10 de marzo de 2026)

**Actividades**

+++Ver detalles

* **Los cambios de oferta directa en la experiencia no se han guardado.** Esta corrección resuelve un problema en el cual las modificaciones realizadas en las ofertas directas dentro de una experiencia de actividad no se guardaban. Anteriormente, cuando los usuarios abrían una oferta directa, realizaban cambios y la guardaban, estos aparecían reflejados inicialmente, pero se perdían al volver a abrir la oferta. La corrección garantiza que los cambios en las ofertas directas se guarden correctamente y se mantengan cuando se vuelva a abrir la oferta. (TGT-54653)

+++

**Implementación**

+++Ver detalles

* **Agregar la opción de administración de parpadeo en la pantalla Implementación.** Se ha agregado una nueva opción a la pantalla [!UICONTROL Implementation] para controlar la habilitación de la configuración de administración de parpadeo. Esta opción permite a los administradores configurar la administración de parpadeo directamente desde la pantalla Implementación. (TGT-52247)

+++

**Información general**

+++Ver detalles

* **Mostrar el nombre completo de la audiencia y la experiencia en la página de Información general.** Esta mejora actualiza la página [!UICONTROL Overview] para mostrar el nombre completo de las audiencias y experiencias. Anteriormente, los nombres largos se truncaban y no eran totalmente visibles, lo que requería que los usuarios hicieran triple clic para seleccionar todo el texto y ver el nombre completo. La actualización garantiza que los nombres completos de audiencia y experiencia sean visibles, lo que facilita a los usuarios la identificación y revisión de las configuraciones de actividad. (TGT-53323)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles

* **Los cambios del VEC no se reflejan en los sitios que usan Shadow DOM (Salesforce Lightning Web Components).** Esta corrección soluciona un problema en el que los cambios realizados en Adobe Target (como los cambios de color de CTA) no se guardaban ni se reflejaban en el sitio activo para sitios basados en Salesforce que usan Lightning Web Components (LWC). CMS no aceptaba actualizaciones de actividades de Target, un problema que se producía de forma coherente en todas las pruebas A/B y en otros tipos de actividades. (TGT-54059)

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
