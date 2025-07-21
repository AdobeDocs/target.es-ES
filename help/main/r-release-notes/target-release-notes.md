---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2812132c2720f54fa7bee2b0a5e16623362fdc33
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 10 de julio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.3 (viernes, 24 de julio de 2025)

Debido a problemas identificados recientemente, relacionados principalmente con las personalizaciones complejas de los clientes, esta versión incluye las siguientes correcciones y actualizaciones:

**Actividades**

+++Ver detalles
* Se corrigió un problema en el cual el método `buildViews` de la clase de generador establecía incorrectamente `viewMaxLocalId` en el recuento total de vistas, en lugar de en la asignación de `viewLocalId` más alta. (TGT-53207)

+++

**Compositor de experiencias basadas en formularios**

+++Ver detalles
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] que hacía que el editor se bloqueara después de hacer clic en el icono **[!UICONTROL Manage Content]** ( ![icono Administrar contenido](/help/main/assets/icons/Experience.svg) ) al crear o editar una actividad [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalles
* Se ha corregido un problema que impedía que [!UICONTROL Catalog Search] cargara resultados adicionales al desplazarse hasta la parte inferior de la lista, restaurando un comportamiento coherente con la interfaz de usuario heredada. (TGT-53088)
* Se ha corregido un problema en el cual la columna [!UICONTROL Number of Products] faltaba en la página [!UICONTROL Collections] en la interfaz de usuario [!DNL Target] actualizada. La columna ahora se muestra correctamente, restaurando la funcionalidad esperada. (TGT-53168)
* Se corrigió un problema en el cual las reglas de [!UICONTROL Collection] no se filtraban correctamente de acuerdo con las reglas. (TGT-53254)
* Se ha corregido un problema que bloqueaba la eliminación de elementos del cuadro de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Se ha corregido un problema que impedía abrir o interactuar con productos sin nombre. Este problema se producía al seleccionar entornos que devolvían resultados sin nombre, lo que impedía el acceso a los detalles del producto. (TGT-53007)
* Se ha corregido un problema que hacía que la página [!UICONTROL Catalog Search] se bloqueara y mostrara una pantalla en blanco al seleccionar ciertos productos. (TGT-53087)

+++

**Compositor de experiencias visuales (VEC)**

+++Ver detalles

* Se ha corregido un problema en el VEC por el cual la aplicación de una modificación a una vista provocaba duplicación y activaba un error de &quot;entrada de usuario no válida&quot;. (TGT-52886)
* Se corrigió un problema con la funcionalidad [!UICONTROL Undo] para las opciones [!UICONTROL Insert Before] y [!UICONTROL Insert After] al configurar ofertas de imagen en el VEC.

  Anteriormente, deshacer una acción de [!UICONTROL Insert Before] o [!UICONTROL Insert After] en ofertas de imagen resultaba en un comportamiento incoherente o en un error al revertir correctamente la modificación, especialmente en las actividades creadas en la interfaz de usuario de [!DNL Target] heredada. Este problema se ha resuelto para garantizar que las acciones de deshacer ahora funcionen de forma fiable para estas modificaciones. (TGT-52809)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
