---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a5d2c07105b1d0fac6115fe507537be6a36799e9
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 33%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 19 de julio de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.7.1 (20 de julio de 2022)

Esta versión incluye las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | --- |
| Se ha mejorado la precisión de la evaluación de audiencia y la latencia del usuario final gracias a la compatibilidad con IPv6 | Las ubicaciones geográficas de los visitantes ahora están determinadas por las direcciones IPv6, si están disponibles, en lugar de solo las direcciones IPv4. Las API de envío también admiten parámetros de entrada de IPv6. El filtrado y la inclusión en la lista de permitidos admiten direcciones IPv4 e IPv6. Esta compatibilidad con IPv6 en esta versión significa que los visitantes se incluirán de forma más precisa en las audiencias (más exactamente, calificarán para actividades o se incluirán en los criterios de filtrado). También mejora la latencia de datos, ya que los clientes de IPv6 se dirigirán directamente, evitando la sobrecarga de la puerta de enlace IPv6 a IPv4. |
| Mejora de la gestión de la carga útil del lado del cliente de A4T | Con la integración del lado del servidor de A4T, si Adobe Target identifica una solicitud como proveniente de un bot, no reenvía la carga útil a Analytics y no hay ningún evento mod_stats registrado en el [!DNL Target] registros. Antes de esta versión, las integraciones del lado del cliente de A4T reenviaban la carga útil a [!DNL Analytics], incluso cuando se ha identificado como tráfico de bots. Esta incoherencia entre el lado del servidor y el del cliente crearía discrepancias, ya que los informes de A4T correspondientes a este último incluían el tráfico de bots. Además, el tráfico de bots no necesariamente se identificó ni se marcó, lo que significa que no fue posible desambiguar ni eliminar el tráfico de bots del resto del tráfico. E incluso si un cliente tuviera en cuenta el tráfico de bots por su cuenta, no coincidiría necesariamente con el conjunto de tráfico que [!DNL Target] se ha identificado y excluido como tráfico de bots, lo que provoca discrepancias divididas u otros problemas. Con esta versión, se ha mejorado el registro en el lado del cliente de A4T de modo que el comportamiento con respecto a la carga útil de A4T sea el mismo que con el lado del servidor de A4T: Los visitantes identificados como bots se excluyen de [!DNL Target] recuento/sistema de informes, tanto para implementaciones del lado del servidor como del lado del cliente. |


## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
