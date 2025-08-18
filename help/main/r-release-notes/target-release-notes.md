---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8f7cdf94438763679273b3631e45b1b41899cda5
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 21%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 18 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**Recommendations**

+++Ver detalles
* **Se ha corregido un problema en la interfaz de usuario de Recs por el que la descarga de CSV con criterios personalizados arrojaba el error 404**. Se ha corregido un problema por el que los clientes no podían descargar CSV con criterios personalizados en el proceso de creación de actividades. (TGT-51966)
* **Se corrigió una carga incoherente de imágenes en[!UICONTROL Catalog Search]**: se corrigió un problema por el que las miniaturas y las imágenes de [!UICONTROL &#x200B; Catalog Search] no se cargaban de manera consistente en el proceso de creación de actividades. Las imágenes no aparecían a menos que la columna &quot;URL en miniatura&quot; estuviera visible y algunas imágenes de producto se cargaran parcialmente o no se cargaran después de las acciones de navegación o búsqueda. (TGT-52778)
* **Se ha corregido un problema por el cual editar una recomendación en una experiencia duplicada afectaba a la experiencia original**: Los clientes notificaron que modificar una recomendación en una experiencia duplicada alteraba involuntariamente la experiencia original. En concreto, después de duplicar la Experiencia B en el proceso de creación de actividades y editar su diseño o criterios, los mismos cambios se reflejaron en la Experiencia B original, a pesar de ser entidades independientes. (TGT-53369)
* **Se ha corregido un problema por el cual los cambios realizados en una experiencia duplicada afectaban involuntariamente a la experiencia original de una actividad:** Los clientes notificaron que, al duplicar una experiencia dentro de una actividad y asignar una nueva audiencia, cualquier cambio realizado en el diseño o los criterios de la experiencia duplicada también se reflejaba en la experiencia original. Esto ocurría aunque no se realizaban ediciones directamente en la versión original, lo que afectaba a la capacidad de crear variaciones independientes dentro de la misma actividad. (TGT-53361)
* **Se ha corregido un problema que hacía que [!UICONTROL Recommendation Catalog] no mostrara de forma intermitente todos los datos de atributos del producto**: en la interfaz de usuario de [!DNL Recommendations] actualizada, los clientes experimentaban un problema por el que algunos atributos del producto, como el mensaje, no se mostraban de forma coherente en los resultados de búsqueda del catálogo a pesar de que los datos existían en la fuente. Este problema requería que los clientes reconfiguraran manualmente la visibilidad de la columna para recuperar los valores que faltaban. (TGT-52769)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalles
* **Se ha corregido un problema en el proceso de creación de actividades que bloqueaba la progresión al paso [!UICONTROL Targeting] en las actividades AP**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían continuar al paso [!UICONTROL Targeting] en las actividades [!UICONTROL Automated Personalization] (AP) a menos que se agregaran dos ubicaciones. Este comportamiento difería de la experiencia anterior, en la que una sola ubicación con varias ofertas era suficiente. El requisito se ha corregido, lo que permite a los clientes seguir utilizando configuraciones de una sola ubicación como parte de sus flujos de trabajo de AP. (TGT-53426)

+++

**[!UICONTROL Workspaces]**

+++Ver detalles
* **Se ha corregido un problema en el cual un cliente restringido a un solo espacio de trabajo podía ver actividades desde otros espacios de trabajo**: Los clientes con acceso limitado a un espacio de trabajo inesperadamente podían ver actividades en todos los espacios de trabajo al seleccionar [!UICONTROL All Workspaces] en el proceso de creación de actividades. Esta visibilidad planteaba el riesgo de cambios no deseados en las actividades activas en otros espacios de trabajo, lo que podría afectar al rendimiento del sitio web. (TGT-53101)
* **Se ha corregido un problema en el cual un cliente podía ver actividades desde [!UICONTROL Default Workspace] sin tener acceso:** Un cliente con acceso limitado al área de trabajo de ensayo pudo ver actividades desde [!UICONTROL Default Workspace] mediante el proceso de creación de actividades. Esto ocurría a pesar de la configuración back-end y los derechos de acceso correctos. (TGT-53297)

+++

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
