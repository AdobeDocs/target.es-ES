---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7e23eea48abdebd60f37ad1bf453813a63779d33
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 28%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: viernes, 10 de abril de 2025**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Actualización de permisos de Target (22 de abril de 2025)

Esta actualización futura mejora el control de la organización sobre las configuraciones de instancia de [!DNL Target], lo que evita actualizaciones accidentales que podrían afectar a la entrega de la actividad en varios equipos de prueba y personalización.

A partir del 22 de abril de 2025, solo los administradores de [!UICONTROL Product] y [!UICONTROL Solutions] podrán actualizar la configuración en las secciones de [!UICONTROL Administration], independientemente de sus funciones en [!DNL Target] espacios de trabajo. Los usuarios sin este permiso tendrán acceso de sólo lectura a las secciones [!UICONTROL Administration].

Para obtener más información, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (15 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha añadido un mensaje de error para guiar a los usuarios en la resolución de opciones duplicadas en una actividad. (TGT-51927)
* Se ha corregido un problema en el cual los selectores de ClickTrack no se eliminaban al eliminar páginas o experiencias con ofertas de redireccionamiento. (TGT-51952)
* Se ha corregido un problema en el cual [!DNL Target] no podía detectar correctamente un carácter &quot;#&quot; en la dirección URL de la actividad. (TGT-52093)
* Se ha corregido un problema por el cual las definiciones de audiencia no eran visibles al editar la segmentación a nivel de oferta en actividades [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Se ha corregido un problema por el cual las refinaciones de audiencia y las audiencias de segmentación de actividad se invertían en la interfaz de usuario. (TGT-52158)

## [!DNL Target Standard/Premium] 25.4.3 (10 de abril de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha corregido un error que impedía que los clientes abrieran la ventana emergente de información de audiencia para determinadas actividades de [!UICONTROL Experience Targeting] (XT). (TGT-52049)
* Se ha corregido un problema que impedía a los clientes insertar un(a) [!UICONTROL Experience Fragment] en el espacio de trabajo predeterminado. (TGT-52073)
* Se ha corregido un problema por el cual una oferta se mostraba como &quot;Contenido no encontrado&quot; y no se mostraba en la página [!UICONTROL Offers] de una actividad [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Se ha añadido la capacidad de permitir audiencias duplicadas dentro de una actividad. (TGT-51200)
* Se ha corregido un problema por el cual se mostraba un nombre de mbox incorrecto en la página [!UICONTROL Goals & Settings] para una actividad XT después de editar. (TGT-52026)
* Se corrigió un problema en el cual `defaultContent` se mostraba en las opciones a pesar de no estar en `experiences/optionLocations`. (TGT-52036)
* Se ha corregido un problema para garantizar que las cadenas vacías no se convirtieran en valores nulos. (TGT-52037)
* Se ha corregido un problema que requería que los clientes reconfiguraran [!UICONTROL Optimization Goal] en [!UICONTROL Reporting Settings] en la página [!UICONTROL Goals & Settings] después de las ediciones. (TGT-52071)
* Se ha corregido un problema en el cual una actividad sin reglas de entrega de página mostraba varias reglas en la página [!UICONTROL Overview]. (TGT-52084)
* Se ha añadido un mensaje de error para los usuarios que intentan guardar una oferta con caracteres fuera del plano multilingüe básico, como emojis. (TGT-52105)
* Se ha corregido un problema que causaba que, al abrir una actividad, se mostrara el siguiente mensaje de error: &quot;Esta actividad está utilizando una o más audiencias eliminadas en el origen&quot;. (TGT-52120)
* Se ha corregido un problema en el cual las métricas de ClickTrack no se mostraban en el [!UICONTROL Visual Experience Composer] (VEC) actualizado durante la edición. (TGT-52152)
* Se corrigió un problema en el cual una dirección URL con un parámetro de consulta como ubicación de la actividad no mostraba el parámetro de consulta en la página [!UICONTROL Overview] de la actividad. (TGT-51635)
* Se ha corregido un problema que impedía que se mostrara toda la dirección URL de la experiencia en [!UICONTROL Browse mode] dentro del [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Se ha corregido un problema por el cual al editar una actividad de, la entrega de la página agregaba &quot;/&quot; al final de la dirección URL, lo que resultaba no válido. (TGT-52114)
* Se ha corregido un problema por el cual el vínculo [!UICONTROL Activity QA] en [!UICONTROL Form-Based Experience Composer] se redireccionaba incorrectamente a la página principal de [!DNL Adobe Experience Cloud]. (TGT-52055)
* Se corrigió un problema en el cual las páginas adicionales agregadas a la actividad [!UICONTROL A/B Test] no se conservaban después de guardar y volver a abrir. (TGT-51994)
* Se ha corregido un problema que impedía que los clientes eliminaran estilos en la sección de estilos en línea. (TGT-52070)
* Se ha restaurado el acceso a [tarjetas de definición de audiencia](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) en el cuadro de diálogo [!UICONTROL Activity QA], de forma similar a la IU heredada. (TGT-52056)
* La IU actualizada no guardó páginas o audiencias sin realizar modificaciones. Si los clientes agregaron nuevas páginas o audiencias a una actividad pero no realizaron cambios en ellas, [!DNL Target] descartó las audiencias sin modificar al guardar. Se han añadido notificaciones en lugares relevantes para informar a los usuarios de este comportamiento. (TGT-52104)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
