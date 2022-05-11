---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 9489655d18170c581f2abf8502f01c7b7e0626b7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 52%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target Standard/Premium] 22.5.1 (versión escalonada; 11 y 13 de mayo de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **11 de mayo**: Región de Asia y el Pacífico (APAC)
* **12 de mayo**: Región de América del Norte (NA)
* **13 de mayo**: Región de Europa, Oriente Medio y África (EMEA)

Esta versión contiene las siguientes mejoras y correcciones:

* Se ha corregido un problema que provocaba un error de JavaScript e impedía que algunos clientes accedieran a los detalles de la actividad para determinadas [!UICONTROL Automated Personalization] (AP). (TGT-43526)
* Se ha corregido un problema que impedía a algunos clientes añadir (o editar) una oferta específica a una actividad AP. (TGT-43503)
* Se ha corregido un problema en la variable [!DNL Target] Interfaz de usuario que muestra el siguiente mensaje de error: &quot;Es posible que el mbox global no esté sincronizado. Intente volver a guardarlo. Este problema era un problema de la interfaz de usuario y no afectaba a las implementaciones de los clientes. (TGT-43475)
* Se ha corregido un problema que impedía que un cliente editara refinamientos y audiencias de nivel de experiencia para una actividad si las refinaciones y audiencias se habían creado antes del nuevo [!UICONTROL Audiencias] Se ha implementado la interfaz de usuario. (TGT-43433)
* Se ha corregido un problema que permitía a los clientes seleccionar duplicados [!DNL Adobe Audience Manager] (AAM) audiencias al editar audiencias de informes para una actividad. (TGT-43430)
* Se ha corregido un problema que impedía a los clientes crear audiencias duplicadas, pero en diferentes espacios de trabajo. (TGT-43423)
* Se ha corregido un problema que impedía que los clientes eliminaran ubicaciones que tuvieran ofertas ad-hoc en actividades creadas en la variable [!UICONTROL Compositor de experiencias basadas en formularios]. (TGT-43315)
* Se ha corregido un problema que impedía a los clientes acceder a ofertas de código después de hacer clic en ofertas de imagen y actualizar la interfaz de usuario. (TGT-43566)
* Asegúrese de que la lista de métricas disponibles en la variable [!DNL Target] IU al crear actividades que utilizan [!DNL Analytics for Target] (A4T) muestra solo las métricas recopiladas por [!DNL Adobe Analytics]. (TGT-43294)
* Se ha corregido un problema que provocaba que las ediciones de los scripts de perfil volvieran al script original sin editar después de editarlo, activarlo y desactivarlo. El script de perfil ahora permanece en estado editado. (TGT-43249)
* Se ha corregido un problema que provocaba el siguiente error al intentar mover una audiencia a otro espacio de trabajo: &quot;No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste&quot;. (TGT-43212)
* Se ha corregido un error que provocaba un error al clonar modificaciones de código personalizado para páginas de aplicación de una sola página (SPA). (TGT-43137)
* Se ha corregido un problema que hacía que la promoción original se viera afectada tras duplicar una experiencia y luego editar la promoción. (TGT-41775)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/main/r-release-notes/target-release-notes.md). |
