---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluyen en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 01c36c0288a15d68f99a6c2f136da9066ccf2e62
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 34%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 13 de abril de 2022**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Versión de la plataforma de Target (13 de abril de 2022)

Esta versión contiene la siguiente actualización:

* Se ha corregido un problema para garantizar que el último octeto de direcciones IP se confunda correctamente al capturarse mediante scripts de perfil. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (versión escalonada, fecha por determinar)

Esta versión contiene las siguientes mejoras y cambios:

* Se ha corregido un problema que provocaba que las ediciones de los scripts de perfil volvieran al script original sin editar después de editarlo, activarlo y desactivarlo. El script de perfil ahora permanece en estado editado. (TGT-43249)
* Se ha corregido un problema que provocaba el siguiente mensaje de error en la variable [!DNL Target] IU al mover una audiencia utilizada en una actividad con el estado &quot;borrador&quot;: &quot;No podemos completar su solicitud. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste&quot;. (TGT-43212)
* Se ha corregido un problema que hacía que la variable [!UICONTROL Incluir] y [!UICONTROL Excluir] opciones que se deshabilitarán para audiencias combinadas al editar una actividad. (TGT-43422)
* Se ha corregido un problema que impedía a algunos clientes ver la lista de audiencias disponibles al editar una actividad. (TGT-43404)
* Se ha corregido un problema que impedía que algunos clientes eliminaran una dirección IP de &quot;[!UICONTROL IP de las que excluir [!DNL Target] datos de informes]&quot; en [!UICONTROL Administración] > [!UICONTROL Informes]. (TGT-43384)
* Se ha corregido un problema que impedía el uso de números negativos en criterios de audiencia que comprobaban que cualquier variable era &quot;buena que&quot;, &quot;buena o igual que&quot;, &quot;menor que&quot; o &quot;menor o igual que&quot;. (TGT-43367)
* Se ha corregido un problema que impedía que los clientes vieran la variable [!UICONTROL Detalles de audiencia] al crear audiencias combinadas. (TGT-43303)
* Se ha corregido un problema que hacía que la variable [!DNL Target] IU o nueva [!UICONTROL Audiencias] La interfaz de usuario de para agotar el tiempo de espera prematuramente para algunos clientes. (TGT-42590 y TGT-43273)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
