---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 29%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 19 de junio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado la opción [!UICONTROL Rearrange] a la interfaz de usuario [!UICONTROL Visual Experience Composer] (VEC) actualizada para alinearla con la funcionalidad disponible en el VEC heredado. (TGT-46957)
* Se ha corregido un problema que causaba que, al copiar una actividad de un espacio de trabajo a otro, se produjeran errores como &quot;no debe ser nulo&quot; o &quot;Se ha producido un error&quot;. (TGT-52474)
* Se corrigió un problema en el cual los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes] no se generaban para ciertas actividades. (TNT-52904)
* Se ha corregido un problema en el VEC actualizado en el cual la administración de contenido predeterminado en las actividades [!UICONTROL Automated Personalization] (AP) no coincidía con la IU heredada. El sistema ahora agrega automáticamente un(a) `optionGroup` predeterminado denominado &quot;Contenido predeterminado&quot; con `optionGroupLocalId = 0` cuando no se agrega ningún grupo explícitamente. Este grupo incluye la opción predeterminada (por ejemplo, `optionLocalId: 0`). Si se elimina el contenido predeterminado, también se elimina el grupo de opciones correspondiente. (TGT-52651)
* Se ha corregido un problema en las actividades [!UICONTROL Multivariate Test] (MVT) en el cual se impedía incorrectamente reutilizar un(a) `experienceLocalId` de experiencias eliminadas anteriormente. (TNT-52672)
* Se ha corregido un problema por el cual las direcciones URL de las ubicaciones de actividades no mostraban los parámetros de consulta debido a caracteres no válidos, como barras inclinadas (/). (TNT52845)
* Se mejoró el mensaje de error de validación para [!DNL A/B Test] actualizaciones de la actividad a través de la API back-end. Cuando hay nombres de ubicación duplicados, el mensaje ahora indica claramente: &quot;No se permiten nombres duplicados&quot; para `locations.selectors`. (TGT-52589)
* Se ha corregido un error que se producía al actualizar una actividad [!UICONTROL Recommendations] activa debido a una propiedad no reconocida en la carga de la solicitud. El sistema ahora gestiona correctamente el JSON no válido. Error de &quot;nombre de propiedad no reconocido&quot;. (TNT52723)
* Se ha corregido un error de validación de servidor que provocaba el error &quot;400 Bad Request&quot; al guardar una actividad [!UICONTROL Recommendations]. (TNT-52716)
* Se ha corregido un problema en [!UICONTROL Form-Based Experience Composer] por el cual al pasar el ratón por encima de un mbox con caracteres especiales en la lista desplegable [!UICONTROL Location], el editor se quedaba en blanco y se activaba un mensaje &quot;No se pudo ejecutar &#39;querySelector&#39; en &#39;Elemento&#39;&quot;. No se pudo recuperar la dirección de URL especificada. (TGT-52717)
* Se ha mejorado la precisión del estado de la fuente con un nuevo indicador &quot;PARTIALLY_IMPORTED&quot;. Anteriormente, las fuentes se marcaban como &quot;correctas&quot; incluso cuando no se importaban todas las filas de un archivo, lo que resultaba confuso.
* Se corrigió un error en el cual, después de migrar a AP V2, ciertas llamadas de API a `/admin/rest/ui/v1/campaigns` devolvían errores del lado del cliente (HTTP 4xx). (TGT-52721)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
