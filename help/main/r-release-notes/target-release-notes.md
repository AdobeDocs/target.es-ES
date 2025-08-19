---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3b80ca92a445bbdab6202a28c03130d24920dfd0
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 16%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 19 de agosto de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. La información de este artículo se actualiza con frecuencia, especialmente antes de las versiones de.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versión incluye las siguientes actualizaciones y correcciones:

**Decisiones de oferta**

+++Ver detalles
* **Se ha corregido un problema que impedía que los clientes editaran ofertas de decisión y seleccionaran elementos de página específicos en la interfaz de usuario actualizada**: en el proceso de creación de actividades actualizado, los clientes no podían editar ofertas de decisión existentes ni seleccionar elementos de página específicos en el Compositor de experiencias visuales (VEC). Las ofertas de decisión se mostraban incorrectamente como ofertas de HTML y los cambios realizados durante la edición no se guardaban. Además, ciertas direcciones URL regionales, como el sitio de Japón, no se cargaban correctamente en el VEC, lo que bloqueaba la creación y las actualizaciones de actividades. (TGT-53425)
* **Se ha corregido un problema por el cual los selectores [!UICONTROL Offer Decision] no se podían modificar ni cambiar inesperadamente después de guardar**: en el proceso actualizado de creación de actividades, los clientes no podían modificar el selector [!UICONTROL Offer Decision] según lo previsto. Los intentos de cambiar el selector no se han realizado correctamente y el selector se ha revertido a un valor incorrecto después de guardar. Esto provocaba que la oferta de decisión desapareciera del Compositor de experiencias visuales (VEC), lo que bloqueaba futuras ediciones. (TGT-53433)
* **Se ha corregido un problema por el cual [!UICONTROL Offer Decisions] desaparecía de la actividad después de guardar**: [!UICONTROL Offer Decisions] agregados durante el proceso de creación de la actividad no se conservaban después de guardar y volver a abrir la actividad. Este problema se producía al editar contenido dinámico e insertar [!UICONTROL Offer Decisions] con selectores y propiedades específicos. (TGT-53434)

+++

**Recommendations**

+++Ver detalles
* **Se ha corregido un problema en la interfaz de usuario de Recs por el que la descarga de CSV con criterios personalizados arrojaba el error 404**. Se ha corregido un problema por el que los clientes no podían descargar CSV con criterios personalizados en el proceso de creación de actividades. (TGT-51966)
* **Se corrigió una carga incoherente de imágenes en[!UICONTROL Catalog Search]**: se corrigió un problema por el que las miniaturas y las imágenes de [!UICONTROL  Catalog Search] no se cargaban de manera consistente en el proceso de creación de actividades. Las imágenes no aparecían a menos que la columna &quot;URL en miniatura&quot; estuviera visible y algunas imágenes de producto se cargaran parcialmente o no se cargaran después de las acciones de navegación o búsqueda. (TGT-52778)
* **Se ha corregido un problema por el cual editar una recomendación en una experiencia duplicada afectaba a la experiencia original**: Los clientes notificaron que modificar una recomendación en una experiencia duplicada alteraba involuntariamente la experiencia original. En concreto, después de duplicar la Experiencia B en el proceso de creación de actividades y editar su diseño o criterios, los mismos cambios se reflejaron en la Experiencia B original, a pesar de ser entidades independientes. (TGT-53369)
* **Se ha corregido un problema por el cual los cambios realizados en una experiencia duplicada afectaban involuntariamente a la experiencia original de una actividad:** Los clientes notificaron que, al duplicar una experiencia dentro de una actividad y asignar una nueva audiencia, cualquier cambio realizado en el diseño o los criterios de la experiencia duplicada también se reflejaba en la experiencia original. Esto ocurría aunque no se realizaban ediciones directamente en la versión original, lo que afectaba a la capacidad de crear variaciones independientes dentro de la misma actividad. (TGT-53361)
* **Se ha corregido un problema que hacía que [!UICONTROL Recommendation Catalog] no mostrara de forma intermitente todos los datos de atributos del producto**: en la interfaz de usuario de [!DNL Recommendations] actualizada, los clientes experimentaban un problema por el que algunos atributos del producto, como el mensaje, no se mostraban de forma coherente en los resultados de búsqueda del catálogo a pesar de que los datos existían en la fuente. Este problema requería que los clientes reconfiguraran manualmente la visibilidad de la columna para recuperar los valores que faltaban. (TGT-52769)
+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalles
* **Se ha corregido un problema en el proceso de creación de actividades que bloqueaba la progresión al paso [!UICONTROL Targeting] en las actividades AP**: se ha corregido un problema en el proceso de creación de actividades por el que los clientes no podían continuar al paso [!UICONTROL Targeting] en las actividades [!UICONTROL Automated Personalization] (AP) a menos que se agregaran dos ubicaciones. Este comportamiento difería de la experiencia anterior, en la que una sola ubicación con varias ofertas era suficiente. El requisito se ha corregido, lo que permite a los clientes seguir utilizando configuraciones de una sola ubicación como parte de sus flujos de trabajo de AP. (TGT-53426)
* **Se ha corregido un problema por el que el nuevo proceso de creación de actividades no establecía el parámetro fmt=png-alpha para imágenes transparentes**: En la interfaz de usuario actualizada, las imágenes insertadas durante el proceso de creación de actividades ya no incluían el parámetro `fmt=png-alpha` de forma predeterminada, lo que resultaba en una pérdida de transparencia. Este comportamiento difería del de la IU anterior, que añadía automáticamente el parámetro a las direcciones URL de la imagen, conservando los fondos transparentes. (TGT-52615)

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
