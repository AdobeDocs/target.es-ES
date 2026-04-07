---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: cad8c365028b28bd9349d2d283370e2c8a750180
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 35%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Actualizaciones con distinción de tiempo que debe conocer {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para actualizaciones con distinción de tiempo relacionadas con [!DNL Adobe Target] y su implementación, [!DNL Adobe] proporciona notas de la versión detalladas y documentación a través de [!UICONTROL Experience League]. Estos son algunos aspectos destacados relevantes para su implementación:

### [!DNL Target] versión de interfaz de usuario conmutar obsolescencia

Para obtener más información, consulte [[!DNL Target] Preguntas frecuentes sobre la actualización de la IU](/help/main/c-intro/updated-ui-faq.md).


## [!DNL Target Standard/Premium] 26.4.1 (viernes, 02 de abril de 2026)

**Actividades**

+++Ver detalles

* **Atributos de audiencia visibles en la vista Actividades.** Se ha corregido un problema por el cual los detalles de regla de audiencia vistos desde un **[!UICONTROL Activity]** no mostraban ciertos atributos que aparecían al abrir la misma audiencia desde la sección **[!UICONTROL Audiences]**. (TGT-54742)

* **Código personalizado se conserva cuando se aplica a vistas adicionales.** Se ha corregido un problema por el cual el código personalizado aplicado a un(a) **[!UICONTROL View]** se podía eliminar al agregar o guardar código personalizado para otro(a) **[!UICONTROL View]** en el mismo(a) **[!UICONTROL Activity]**. (TGT-53933)

* **Exportar CSV en páginas de lista de Actividades y Audiencias.** agregó una acción **[!UICONTROL Export CSV]** para que pueda exportar listas de actividades desde la interfaz de usuario, incluso cuando se aplican filtros, sin depender únicamente de las API para las exportaciones de rutina. (TGT-51466)

* **Modificaciones de experiencias marcadas cuando no se encuentran selectores.** modificaciones de experiencia ahora ejecutan una comprobación de existencia de selectores; cuando no se encuentra un selector en la página, la modificación se marca como no válida. (TGT-54815)

* **[!UICONTROL Automated personalization]actividades.** Se han corregido problemas de carga de actividades e interfaces que evitaban que los usuarios crearan, editaran o administraran de forma fiable actividades de Automated Personalization, lo que bloqueaba la configuración de campañas y los casos de uso de personalización retrasada. (TGT-54421)

+++

**Públicos**

+++Ver detalles

* **Nombre y descripción de audiencia visibles al crear audiencias a partir de una actividad.** Se ha corregido un problema por el cual los campos de audiencia **[!UICONTROL Name]** y **[!UICONTROL Description]** no se destacaban claramente al crear o editar una audiencia a partir del flujo de actividad, en comparación con la creación de la audiencia directamente debajo de **[!UICONTROL Audiences]**. (TGT-54837)

+++

**Datos**

+++Ver detalles

* **[!UICONTROL Live Activities]cuentan con Insights.** Se ha corregido un problema en el cual la métrica **[!UICONTROL Live Activities]** del panel de información podía notificar un total mayor que el número de actividades que aparecían como activas en **[!UICONTROL All Activities]**. (TGT-54788)

+++

**Recommendations**

+++Ver detalles

* **Listas de ID largas en [!UICONTROL Global Exclusions].** Se corrigió un problema en el cual al pegar o escribir una larga lista de identificadores en **[!UICONTROL Global Exclusions]** se podía truncar en la interfaz actualizada en comparación con la heredada, lo que provocaba una lista de exclusión incompleta. (TGT-54422)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles

* **Indicador de estado del Compositor de experiencias mejorado (EEC) en [!UICONTROL Visual Experience Composer].** El indicador EEC indica si Enhanced Experience Composer está habilitado. Su presentación se ha revisado para que ya no parezca una opción interactiva, ya que solo sirve como visualización de estado no interactiva. (TGT-54828)

* **Carril izquierdo contraíble en [!UICONTROL Visual Experience Composer].**: el carril izquierdo ahora se puede contraer mientras se abre una actividad para su edición. Esto mejora el acceso a **[!UICONTROL Components]** y **[!UICONTROL Properties]** para actividades que incluyen varias audiencias y páginas, incluso en pantallas más pequeñas. (TGT-54269)

+++

## [!DNL Target Standard/Premium] 26.3.7 (26 de marzo de 2026)

**Públicos**

+++Ver detalles

* **Precisión de etiqueta de origen de audiencia en la interfaz de audiencias.** Se ha corregido un problema por el cual las audiencias que venían del destino Adobe Target v2 en Adobe Experience Platform podían aparecer con **Adobe Experience Cloud** como origen en lugar de **Adobe Experience Platform**. Esta actualización mejora la coherencia de las etiquetas de origen al filtrar y revisar las audiencias. (TGT-54802)

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
