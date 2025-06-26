---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar;acceso anticipado
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 926a045e5bcebc8d094ea41a6c1b7c59568a35ab
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 27%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 26 de junio de 2025**

>[!NOTE]
>
>* Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>* Para ver información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md).
>
>* Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.4 (viernes, 26 de junio de 2025)

Esta versión de incluye las siguientes correcciones y actualizaciones:

* Se ha agregado la opción [!UICONTROL Rearrange] a la interfaz de usuario [!UICONTROL Visual Experience Composer] (VEC) actualizada para alinearla con la funcionalidad disponible en el VEC heredado. (TGT-46957 y TGT-52876)
* Se corrigió un problema en el cual las modificaciones realizadas en experiencias de variante (por ejemplo, la Experiencia B) en una actividad [!UICONTROL A/B Test] no se conservaban. Después de cambiar entre experiencias, los cambios en la variante desaparecerían. Este problema no afectaba a la experiencia de control de Campaign. (TGT-52664)
* Se ha corregido un problema en el cual algunos clientes no podían crear ni guardar actividades, mientras que otros podían realizar las mismas acciones sin problema. El problema era inconsistente entre cuentas.(TGT-52842)
* Se ha corregido un problema en el cual en el VEC actualizado, los usuarios no podían mover modificaciones al [!UICONTROL Page Load event], una capacidad que existía en la IU heredada. (TGT-52617)
* Se ha corregido un problema que impedía que algunas modificaciones de la actividad se mostraran correctamente en el VEC actualizado. (TGT-52818)
* Se ha corregido una excepción de puntero nulo que se producía al recuperar datos de informes para actividades [!UICONTROL Automated Personalization] (AP). (TGT-52362)
* Se ha corregido un problema que impedía que los detalles de nivel de oferta aparecieran en el archivo .CSV para actividades [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Se ha corregido un problema que se producía al aplicar modificaciones en el VEC actualizado; los cambios aparecen inicialmente correctamente, incluido el [!UICONTROL Experience Fragment] esperado. Sin embargo, al cambiar de experiencia o al realizar ediciones adicionales, algunas modificaciones no se aplican debido a problemas con el selector. (TGT-52679)
* Se ha corregido un problema por el cual cuando se creaba una nueva actividad clonando una existente, los vínculos de control de calidad de la actividad clonada retenían incorrectamente las direcciones URL de la página de la actividad original. (TGT-52775)
* Se ha corregido un problema que impedía involuntariamente que [!UICONTROL On-device Decisioning] estuviera disponible en el VEC actualizado. (TGT-52371)
* Se ha corregido un problema que impedía editar una actividad de producto [!DNL Recommendations]. Al intentar acceder al VEC a través de la interfaz de usuario de Target, apareció un error en la página [!UICONTROL Overview] que impedía realizar ediciones. (TGT-52823)
* Se ha corregido un problema que impedía guardar una actividad de [!DNL Recommendations] cuando los nombres de experiencia superaban los 50 caracteres. (TGT-52619)
* Se ha corregido un problema en el cual los clientes no podían guardar una actividad de Recommendations después de modificar los criterios en la nueva interfaz de usuario. El problema parece estar relacionado con los permisos y no afecta a todos los usuarios con funciones similares. (TGT-52816)
* Se ha corregido un problema en el cual los usuarios con el rol [!UICONTROL Editor] no podían editar una actividad [!DNL Recommendations]. Al intentar cambiar el diseño y guardar la actividad, se produjo un error 403 prohibido, que indica que se requería el privilegio &quot;[editor]&quot;, aunque el usuario ya tuviera esa función en el espacio de trabajo relevante. (TGT-52836)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
