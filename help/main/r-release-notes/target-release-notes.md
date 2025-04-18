---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 872e56662e04e3fabda7ff38233adfea32efbe48
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 47%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: viernes, 17 de abril de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.5 (24 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un problema que provocaba que se mostraran varias audiencias de experiencia al editar o guardar una actividad. (TGT-52134)
* Se ha corregido un problema por el cual las recomendaciones no se mostraban en el sitio web del cliente después de activar la actividad [!DNL Recommendations]. (TGT-52164)
* `OptionLocalIDs` ya no se incrementa incorrectamente cuando la opción permanece sin cambios. (TGT-52187)
* Los archivos de informes descargados ahora muestran correctamente los datos presentes en la interfaz de usuario de informes. (TGT-52068)
* Se ha corregido un problema que impedía que Target reconociera el carácter &quot;#&quot; en la dirección URL de un sitio web. (TGT-52093)
* Las operaciones por lotes ya no fallan después de agregar reglas de envío de página. (TGT-52097)
* Se ha corregido un problema que provocaba que [!DNL Target] recortara todos los parámetros de consulta de la dirección URL del sitio web. (TGT-52100)
* Se ha corregido un problema que provocaba que las refinaciones de audiencia y las audiencias de actividad se invirtieran en la interfaz de usuario actualizada. (TGT-52158)

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
