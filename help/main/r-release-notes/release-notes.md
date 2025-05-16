---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 63df83fd7479c7be7e4cd4c08501ab17511a41fb
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 32%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Adobe Target] [!DNL AI Assistant] versión (16 de mayo de 2025)

¡Estamos encantados de anunciar el lanzamiento de [!DNL AI Assistant] en [!DNL Adobe Target]! Esta potente característica de interfaz de usuario se ha diseñado para ayudarle a navegar y comprender los conceptos de [!DNL Target] con facilidad. Disponible en varios productos en [!DNL Adobe Experience Cloud], incluido [!DNL Target], [!DNL AI Assistant] está aquí para revolucionar su experiencia.

[!DNL AI Assistant] en [!UICONTROL Target] es una herramienta conversacional que puede usar para acelerar sus flujos de trabajo con [!DNL Experience Platform] aplicaciones y servicios. Use [!DNL AI Assistant] para aumentar su productividad general y ampliar sus conocimientos sobre el producto

En [!DNL Target], la primera fase de [!DNL AI Assistant] proporciona un conocimiento inestimable del producto basado en la documentación de [!DNL Experience League]. Ya sea que esté configurando un script de perfil, solucionando errores o considerando una actualización a AEP Web SDK, [!DNL AI Assistant] ya lo ha cubierto.

Para obtener más información, consulte [Descripción general del Asistente de IA de Adobe Experience Platform](/help/main/c-intro/ai-assistant.md).

## [!DNL Target Standard/Premium] 25.5.2 (8 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Los usuarios de [!DNL Target] con derechos de [!UICONTROL Product Administrator] y [!UICONTROL System Administrator] ahora pueden editar toda la configuración en las páginas de [!UICONTROL Administration], independientemente de su rol en [!DNL Target]. Los usuarios sin estos permisos tienen acceso de solo lectura a esta configuración. Esta actualización asegura un control de acceso más estricto sobre [Configuración de administración](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Se ha corregido un problema de almacenamiento en caché que impedía guardar la actividad [Preferencias del sitio](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Se ha corregido un problema en el cual los clientes no podían habilitar la selección por ID y clase en la sección [!UICONTROL Site Preferences] después de cargar el sitio en el VEC. La configuración de [!UICONTROL Site Preferences] se revirtió automáticamente a deshabilitada incluso después de habilitarse. (TGT-52207)
* Se ha corregido un problema en el cual el [!UICONTROL Visual Experience Composer] (VEC) no mostraba la página correcta cuando las direcciones URL de [entrega de página](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) terminaban con una barra diagonal (/). (TGT-52237)
* Se ha corregido un problema que impedía eliminar las modificaciones de código personalizado al cambiar experiencias. (TGT-52240)
* Se ha corregido un problema en el cual las modificaciones de HTML en el VEC superponían elementos de página existentes. (TGT-52265)
* Se ha corregido un problema que impedía editar código personalizado en el VEC actualizado debido a que el código personalizado existente no era visible en el editor. (TGT-52272)
* Se ha corregido un problema que provocaba el mensaje de error &quot;No se permiten nombres duplicados&quot; al guardar una actividad de Recommendations. (TGT-52318)
* Se ha corregido un problema en el VEC actualizado que impedía a los clientes editar elementos de texto o eliminar objetos contenedores. (TGT-52348)
* Se ha corregido un problema que impedía que [!DNL Customer Journey Analytics] se mostrara correctamente en una página de actividad [!UICONTROL Overview]. (TGT-52359)
* Se ha corregido un problema que impedía que los grupos de informes persistieran en las actividades [!UICONTROL Automated Personalization] (AP). (TGT-52368)
* Se ha corregido un problema que impedía guardar actividades que incluían Offer Decisioning. (TGT-52390)
* Se ha corregido un problema por el cual se seleccionaba la oferta predeterminada, pero se mostraba otro contenido de oferta en las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Multivariate Test] (MVT). (TGT-52372)
* Se ha corregido la lógica de permisos de GET para comprobar con O entre el acceso completo a la organización y el acceso específico a la organización y al usuario. (TGT-52374)
* Se ha corregido un problema por el cual los nombres de audiencia no se mostraban después de seleccionar una audiencia para [!UICONTROL Managed Content] y [!UICONTROL Reporting Audiences], aunque [!UICONTROL Show Only Selected] estuviera habilitado. (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 (5 de mayo de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que impedía que se mostraran los refinamientos de audiencia para determinadas actividades en la IU actualizada. (TGT-52057)
* Se ha corregido un problema que impedía el uso de audiencias combinadas en actividades de. (TGT-52346)
* Se ha corregido un problema que impedía la creación de una nueva actividad en un espacio de trabajo no predeterminado mediante una audiencia solo de actividad desde el mismo espacio de trabajo. (TGE-52349)
* Se ha corregido un problema que provocaba que las audiencias solo de actividad desaparecieran de la interfaz de usuario actualizada después de crear y seleccionar una audiencia nueva. (TGT=52091)
* Se ha corregido un problema que impedía el uso de audiencias duplicadas en las actividades de. (TGT-51200 y TGT-52057)
* Se ha corregido un problema que provocaba que las refinaciones de audiencia y las audiencias de actividad se invirtieran en la interfaz de usuario actualizada. (TGT-52158)
* Se ha corregido un problema que impedía la creación de una nueva actividad debido al error de entrada del usuario: &quot;espacio de trabajo no predeterminado no permitido para este usuario&quot;. (TGT-52267)
* Se ha corregido un problema que impedía que las ofertas se mostraran en la interfaz de usuario actualizada tanto para espacios de trabajo predeterminados como no predeterminados. [!DNL Target] ahora muestra ofertas de ambos espacios de trabajo. (TGT-52339)
* Se ha corregido un problema en el cual [!DNL Target] no advertía a los clientes al editar una actividad y cambiar un elemento de sitio web modificado. (TGT-52100)
* Se ha corregido un problema por el cual al editar una oferta con ofertas ad hoc se creaba una nueva oferta en lugar de actualizar la existente. (TGT-52135)
* Se ha corregido un problema que provocaba un error de carga no válida al mover ofertas a carpetas. (TGT-52325)
* Se ha corregido un problema que provocaba un error de entrada del usuario al mover ofertas a carpetas. (TGT-52296)
* Se agregó un campo `audienceMetadata` para cada actividad, y se aseguró de que se lea y actualice al editar la actividad. (TGT-51004)

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
