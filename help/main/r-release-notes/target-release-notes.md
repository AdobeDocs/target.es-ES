---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 54%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 30 de junio de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.6.2 (30 de junio de 2022)

Esta versión contiene las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | ---  |
| Notificaciones en el producto | Obtenga las siguientes notificaciones relevantes en el producto:<ul><li>**Actividades**: Notificaciones para todos los tipos de actividades cuando se aprueba o desactiva una actividad, ya sea manualmente o cuando llega a su fecha de inicio o de finalización. La notificación incluye el nombre de la actividad con un vínculo a la página de información general de la actividad.</li><li>**Scripts de perfil** Notificaciones cuando se activa o desactiva un script de perfil, ya sea de forma manual o por parte de Target.</li><li>**Fuentes de Recommendations**: Notificaciones cuando se activa o desactiva una fuente de Recommendations, ya sea de forma manual o por parte de Target. Las notificaciones también se envían cuando falla una fuente de Recommendations.</li></ul> De forma predeterminada, las notificaciones se reciben por administradores de productos, editores y aprobadores. Las notificaciones se pueden configurar dentro de las preferencias del Experience Cloud.<br>Para obtener más información, consulte [Notificaciones y anuncios](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guía para desarrolladores de Adobe Target* | La variable *Guía para desarrolladores de Adobe Target* consolida todo [!DNL Target] contenido para desarrolladores en una guía práctica. La guía incluye información sobre la implementación de [!DNL Target] y [!DNL Recommendations], [!DNL Target] SDK y [!DNL Target] API.<br>Para obtener más información, consulte [Guía para desarrolladores de Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Los usuarios con la función [!UICONTROL Editor] ya no pueden editar audiencias en actividades activas. (TGT-43582)
* Aparece un mensaje de advertencia si un cliente intenta guardar una audiencia con un signo de exclamación (!) como el primer carácter del nombre de la audiencia (por ejemplo, !Londres). (TGT-43643)
* Se ha corregido un problema que provocaba que las tarjetas de detalles de definición de audiencias de algunos clientes indicaran que una actividad finalizada seguía activa. (TGT-43527)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
