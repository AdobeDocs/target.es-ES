---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d0b6f81507cc5d5bc17d029c3d8f5b36c2c71a29
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 56%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 18 de julio de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.7.1 (20 de julio de 2022)

Esta versión incluye las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | --- |
| Se ha mejorado la precisión de la evaluación de audiencia y la latencia del usuario final gracias a la compatibilidad con IPv6 | Las ubicaciones geográficas de los visitantes ahora están determinadas por las direcciones IPv6, si están disponibles, en lugar de solo las direcciones IPv4. Las API de envío también admiten parámetros de entrada de IPv6. El filtrado y la inclusión en la lista de permitidos admiten direcciones IPv4 e IPv6. Esta compatibilidad con IPv6 en esta versión significa que los visitantes se incluirán de forma más precisa en las audiencias (más exactamente, calificarán para actividades o se incluirán en los criterios de filtrado). También mejora la latencia de datos, ya que los clientes de IPv6 se dirigirán directamente, evitando la sobrecarga de la puerta de enlace IPv6 a IPv4. |
| Mejora de la gestión de la carga útil del lado del cliente de A4T | Con la integración del lado del servidor de A4T, si Adobe Target identifica una solicitud como proveniente de un bot, no reenvía la carga útil a Analytics y no hay ningún evento mod_stats registrado en los registros de Target. Antes de esta versión, las integraciones del lado del cliente de A4T reenviaban la carga útil a Analytics, incluso cuando se había identificado como tráfico de bots. Esta incoherencia entre el lado del servidor y el del cliente crearía discrepancias, ya que los informes de A4T correspondientes a este último incluían el tráfico de bots. Además, el tráfico de bots no necesariamente se identificó ni se marcó, lo que significa que no fue posible desambiguar ni eliminar el tráfico de bots del resto del tráfico. E incluso si un cliente tuviera en cuenta el tráfico de bots por su cuenta, no coincidiría necesariamente con el conjunto de tráfico que Target identificó y excluyó como tráfico de bots, lo que produciría discrepancias divididas u otros problemas. Con esta versión, se ha mejorado el registro en el lado del cliente de A4T de modo que el comportamiento con respecto a la carga útil de A4T sea el mismo que con el lado del servidor de A4T: Los visitantes identificados como bots se excluyen del recuento/sistema de informes de Target, tanto en el servidor como en el lado del cliente. |

## [!DNL Target Standard/Premium] 22.6.2 (30 de junio de 2022)

Esta versión incluye las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | ---  |
| Notificaciones en el producto | Obtenga las siguientes notificaciones relevantes en el producto:<ul><li>**Actividades**: notificaciones para todos los tipos de actividades cuando se aprueba o desactiva una actividad, ya sea manualmente o cuando llega a su fecha de inicio o de finalización. La notificación incluye el nombre de la actividad con un vínculo a la página de información general de la actividad.</li><li>**Scripts de perfil**: notificaciones cuando se activa o desactiva un script de perfil, ya sea de forma manual o por parte de Target.</li><li>**Fuentes de Recommendations**: notificaciones cuando se activa o desactiva una fuente de Recommendations, ya sea de forma manual o por parte de Target. Las notificaciones también se envían cuando falla una fuente de Recommendations.</li></ul> De forma predeterminada, las notificaciones se reciben por administradores de productos, editores y aprobadores. Las notificaciones se pueden configurar dentro de las preferencias de Experience Cloud.<br>Para obtener más información, consulte [Notificaciones y anuncios](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guía para desarrolladores de Adobe Target* | La *Guía para desarrolladores de Adobe Target* consolida todo el contenido de [!DNL Target] para desarrolladores en una guía práctica. La guía incluye información acerca de la implementación de [!DNL Target] y [!DNL Recommendations], SDK de [!DNL Target] y API de [!DNL Target].<br>Para obtener más información, consulte [Guía para desarrolladores de Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Los usuarios con la función [!UICONTROL Editor] ya no pueden editar audiencias en actividades activas. (TGT-43582)
* Aparece un mensaje de advertencia si un cliente intenta guardar una audiencia con un signo de exclamación (!) como el primer carácter del nombre de la audiencia (por ejemplo, !Londres). (TGT-43643)
* Se ha corregido un problema que provocaba que las tarjetas de detalles de definición de audiencias de algunos clientes indicaran que una actividad finalizada seguía activa. (TGT-43527)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
