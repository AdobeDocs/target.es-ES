---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Notas de la versión
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7badceff58e00f8406d24621534d24ea4067a224
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 58%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 3 de agosto de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.8.1 (4 de agosto de 2021)

Esta versión de mantenimiento contiene muchas mejoras del back-end, incluido el siguiente cambio de cara al cliente:

* Se ha corregido un problema que provocaba que los informes para actividades de [!UICONTROL Personalización automática] creadas en el [!UICONTROL Compositor de experiencias basadas en formularios] hicieran referencia a ofertas eliminadas en los informes. Esto provocó que se mostrara el siguiente mensaje de error: &quot;Tenemos problemas para recuperar datos para este informe. Póngase en contacto con el servicio de atención al cliente de Adobe si el problema persiste.&quot; (TGT-41028)

## API de envío de Target (3 de agosto de 2021)

Esta versión contiene las siguientes mejoras:

* El límite de parámetros de mbox se ha aumentado a 100 parámetros. El límite anterior era de 50 parámetros. (TNT-41717)
* El límite de `categoryId` se ha aumentado a 256 caracteres. El límite anterior era de 128 caracteres.
* Se han añadido los siguientes detalles [!DNL Adobe Audience Manager] (AAM) a la API de envío:

   * UUID AAM: ID de AAM interno que se utiliza para identificar a un usuario de forma exclusiva.
   * dataPartnerId: El ID de un socio de datos.
   * dataPartnerUserId: ID de usuario proporcionado por un socio de datos.

   Anteriormente, la API de envío solo incluía `dcsLocationHint` y `blob`. (TNT-41644)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
