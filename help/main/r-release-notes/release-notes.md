---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones;actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# [!DNL Target] Notas de la versión (actuales)

Explore las últimas funciones, mejoras y correcciones de [!DNL Adobe Target]. Estas notas de la versión también tratan sobre las actualizaciones de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros componentes de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.7.4 (23 de julio de 2026)

**Creación de informes**

+++Ver detalles

* **El gráfico de tasa de conversión no está disponible para una audiencia móvil específica.** Se corrigió un problema en el cual el gráfico [!UICONTROL Tasa de conversión] no se representaba para ciertas audiencias móviles. (TGT-55611)

* El objetivo de conversión **&quot;Visualizó un mbox&quot; no funciona cuando se selecciona en el menú desplegable.** Se ha corregido un problema por el cual al seleccionar un mbox del menú desplegable en [!UICONTROL Objetivos y configuración] para un objetivo de conversión &quot;Visualizó un mbox&quot; se guardaba el nombre del mbox incorrectamente, lo que impedía que se registraran las conversiones. (TGT-55588)

+++

**Públicos**

+++Ver detalles

* **Problema de diseño en la página Biblioteca de audiencias.** Se ha corregido un problema de diseño que había cuando los filtros estaban habilitados en la página [!UICONTROL Biblioteca de audiencias] mientras la navegación lateral estaba colapsada. (TGT-55502)

+++

**[!UICONTROL Compositor de experiencias visuales] (VEC)**

+++Ver detalles

* **La versión móvil no se carga correctamente.** Se ha corregido un problema en el cual el [!UICONTROL Compositor de experiencias visuales] no ofrecía una forma de actualizar, lo que impedía que la vista móvil se cargara correctamente. (TGT-54408)

* **Las acciones de modificación de edición o eliminación no funcionan.** Se ha corregido un problema que impedía editar o eliminar una modificación de la vista [!UICONTROL Editar experiencia]. (TGT-55250)

* **El modo de exploración no responde después de que se cargue la actividad.** Se ha corregido un problema por el cual el modo [!UICONTROL Examinar] dejaba de responder para las experiencias que contenían una modificación, lo que impedía una mayor navegación y creación. (TGT-55306)

* **No se pueden seleccionar elementos dentro de Salesforce LWC (DOM en la sombra).** Se ha corregido un problema en el cual [!UICONTROL Compositor de experiencias visuales] no podía seleccionar elementos anidados dentro de Salesforce Lightning Web Components mediante Shadow DOM, lo que daba como resultado un error de tipo &quot;selector no encontrado&quot;. (TGT-54956)

* **Aparecieron ofertas duplicadas en el [!UICONTROL Compositor de experiencias visuales].** Se ha corregido un problema en el cual las modificaciones y ofertas aparecían duplicadas de forma intermitente en la IU de creación de actividades. (TGT-55685)

+++

**Administración**

+++Ver detalles

* **Se cambió el nombre del asistente de generación de contenido a [!UICONTROL Generar contenido].** Se cambió el nombre de la capacidad de generación de contenido del &quot;Asistente de IA&quot; a [!UICONTROL Generar contenido] en [!DNL Target] superficies de interfaz de usuario. (TGT-55689)

+++

**Recommendations**

+++Ver detalles

* **Recomendaciones basadas en popularidad que usan atributos de perfil.** [!DNL Target] ahora admite la agrupación dinámica de recomendaciones de popularidad, más visitados y más vendidos, según atributos de perfil del visitante como país, idioma preferido o nivel de pertenencia. (TAPER-7614)

* **La colección de recomendaciones no coincide entre [!UICONTROL Colecciones] y la configuración de la actividad.** Se ha corregido un problema por el cual una colección de [!UICONTROL Recommendations] devolvía entidades adicionales que no cumplían los requisitos al visualizarlas desde la configuración de la actividad en comparación con la vista de [!UICONTROL Recommendations] > [!UICONTROL Colecciones]. (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2 (16 de julio de 2026)

**Actividades**

+++Ver detalles

* **Información incorrecta del objetivo en la página [!UICONTROL Información general de actividad].** Se ha corregido un problema en el cual la página [!UICONTROL Información general de actividad] para [!DNL Automated Personalization] actividades mostraba objetivos adicionales en lugar del objetivo de optimización. (TGT-55553)

* **Pantalla que no responde al navegar por las páginas en el modo [!UICONTROL Examinar].** Se ha corregido un problema por el cual la pantalla dejaba de responder al navegar entre páginas en modo [!UICONTROL Examinar]. (TGT-55565)

+++

**Página principal**

+++Ver detalles

* **Cambio de interfaz de usuario para [!UICONTROL Principales ejecutantes] y [!UICONTROL Guarda].** Se ha actualizado la interfaz de usuario de los principales ejecutantes y se ha guardado la experiencia. (TGT-54975)

+++

**Públicos**

+++Ver detalles

* **Cadenas sin localizar en el cuadro de diálogo [!UICONTROL Crear script de perfil].** Se corrigió un problema en el cual las cadenas del cuadro de diálogo [!UICONTROL Crear script de perfil] no se localizaban. (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1 (9 de julio de 2026)

**Actividades**

+++Ver detalles

* **Visualización de origen incoherente en [!UICONTROL Actividades], [!UICONTROL Audiencias] y [!UICONTROL Ofertas] páginas.** Se ha corregido un problema por el cual el origen se mostraba de forma incoherente en las páginas de [!UICONTROL Actividades], [!UICONTROL Audiencias] y [!UICONTROL Ofertas]. (TGT-55247)

* **Cambios en el origen de la actividad al editar mediante la interfaz de usuario.** Se ha corregido un problema en el cual al editar una actividad a través de la IU se cambiaba el origen de la actividad original. (TGT-55248)

+++

**Públicos**

+++Ver detalles

* **Espacio de trabajo predeterminado incorrecto al editar una audiencia.** Se ha corregido un problema por el que el espacio de trabajo predeterminado era incorrecto después de editar una audiencia. (TGT-55510)

+++

**Creación de informes**

+++Ver detalles

* **Error de descarga de CSV para los informes de mayo.** Se ha corregido un problema por el cual fallaba la descarga de un informe CSV para mayo. (TGT-55524)

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
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
