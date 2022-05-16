---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 41db493ad71a2e0909346f81b897d2b1db631116
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 9 de mayo de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

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

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre próximas mejoras de productos para [!DNL Target] y otros [!DNL Adobe Experience Cloud] soluciones, regístrese para [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
