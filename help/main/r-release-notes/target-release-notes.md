---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b09796cd8464b54dcc1945ae1ec00eb914ba218c
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 31%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: viernes, 24 de abril de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba discrepancias en los listados de audiencia entre la página de configuración de [!UICONTROL Activity] y la página de información general de [!UICONTROL Reporting]. (TGT-52203)
* Se ha corregido un problema que impedía añadir una nueva página a una actividad debido a un error de entrada de usuario no válido. (TGT-52263)
* Se ha corregido un problema por el cual las recomendaciones no se mostraban en el sitio web del cliente después de activar la actividad [!DNL Recommendations]. (TGT-52164)
* Se ha corregido un problema que provocaba que `OptionLocalIDs` se incrementara incorrectamente cuando la opción permanecía sin cambios. (TGT-52187)
* Se ha corregido un problema que impedía que los archivos de informes descargados mostraran correctamente los datos presentes en la interfaz de usuario de informes. (TGT-52068)
* Se ha corregido un problema para que las operaciones por lotes ya no fallaran después de agregar reglas de entrega de página. (TGT-52097)
* Se ha corregido un problema que provocaba que [!DNL Target] recortara todos los parámetros de consulta de la dirección URL del sitio web. (TGT-52100)
* Se ha resuelto un error de consola que impedía que los clientes crearan actividades tanto en la IU de Target heredada como en la actualizada. (TGT-52181)
* Se ha corregido un problema que impedía a los clientes añadir nuevas páginas, lo que provocaba un error de entrada de usuario no válido. (TGT-52258)
* Se ha corregido un problema que provocaba que las modificaciones desaparecieran después de agregar páginas adicionales y luego volver a la pestaña [!UICONTROL Experiences]. (TGT-52264)
* Se ha corregido un problema que impedía a los clientes cambiar la audiencia en una actividad de [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Se ha corregido un error que impedía editar una actividad XT debido a una regla de IU no admitida. (TGT-52273)
* Se corrigió un problema en el cual las modificaciones de la actividad no se mostraban en la interfaz de usuario de [!DNL Target] a pesar de haberse enviado correctamente a la página web. (TGT-52192)
* Se ha corregido un problema en el [!UICONTROL Visual Experience Composer] (VEC) actualizado en el cual las rutas de exploración no siempre se mostraban en la parte inferior del editor, lo que provocaba dificultades al seleccionar elementos con precisión. (TGT-51169)
* Se ha corregido un problema por el cual la lista desplegable [!UICONTROL Audience] no mostraba todas las audiencias debido a la paginación. (TGT-52204)
* Se ha corregido un problema que provocaba un mensaje de entrada de datos no válido al agregar nuevas ofertas en actividades de [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Se ha corregido un problema por el cual [!UICONTROL Analytics for Target] (A4T) se seleccionaba incorrectamente como origen de informes, aunque el cliente no tuviera acceso a A4T. (TGT-52226)
* Se ha corregido un problema que impedía guardar una actividad con la métrica de URL [!UICONTROL View a Page]. (TGT-52260)
* Se ha corregido un problema que impedía que los clientes seleccionaran espacios de trabajo al crear ofertas dentro de una actividad. (TGT-52289)
* Se ha corregido un problema por el cual las modificaciones de una experiencia se mostraban incorrectamente al cambiar a otra experiencia. (TGT-52184)
* Se corrigió un problema en el cual la oferta predeterminada se mostraba incorrectamente en la interfaz de usuario de [!DNL Target] al abrir la actividad. (TGT-52198)

## Actualización de permisos de Target (22 de abril de 2025)

Esta actualización futura mejora el control de la organización sobre las configuraciones de instancia de [!DNL Target], lo que evita actualizaciones accidentales que podrían afectar a la entrega de la actividad en varios equipos de prueba y personalización.

A partir del 22 de abril de 2025, solo los administradores de [!UICONTROL Product] y [!UICONTROL Solutions] podrán actualizar la configuración en las secciones de [!UICONTROL Administration], independientemente de sus funciones en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tendrán acceso de sólo lectura a las secciones [!UICONTROL Administration].

Para obtener más información, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
