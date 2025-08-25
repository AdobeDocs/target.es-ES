---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 65bc050a189b65af57b1258afeff497a0dafcfb5
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 44%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 21 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (28 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**[!DNL Recommendations]**

+++Ver detalles
**Se ha actualizado la interfaz de usuario de modo que el filtrado de búsqueda avanzada en [!UICONTROL Product Catalog Search] no distingue entre mayúsculas y minúsculas**: La interfaz de usuario de [!UICONTROL Advanced Search] de la página [!UICONTROL Product Catalog Search] anteriormente realizaba la coincidencia exacta de mayúsculas y minúsculas en los valores devueltos, aunque tanto las consultas del servidor como las de GraphQL no distinguían entre mayúsculas y minúsculas. Esta incoherencia causaba confusión y reducía la precisión de la búsqueda. El filtrado de [!UICONTROL Advanced Search] ahora no distingue entre mayúsculas y minúsculas, se alinea con el comportamiento del back-end y mejora la facilidad de uso.

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Ver detalles
* **Se ha corregido un problema que consistía en que el cambio de nombre de una ubicación en una actividad [!UICONTROL Automated Personalization] (AP) o [!UICONTROL Multivariate Test] (MVT) no persistiera después de ir al paso [!UICONTROL Targeting] y regresar.** Los clientes ahora pueden editar y guardar correctamente los nombres de las ubicaciones, y los cambios permanecerán visibles a lo largo del proceso de creación de actividades. (TGT-52367)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
