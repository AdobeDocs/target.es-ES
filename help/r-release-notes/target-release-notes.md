---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Adobe Target, incluidos SDK, API y bibliotecas JavaScript.
title: ¿Qué nuevas funciones se incluyen en la próxima versión?
feature: ' Notas de la versión '
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: a45cfbd52df935fa3138eda6cc7f1028c13ff81d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 24%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 9 de abril de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas podría ser la misma, dependiendo del tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021,  [!DNL Adobe Target] no es compatible con la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js fallan correctamente e influyen en las páginas que tienen [!DNL Target] actividades ejecutándose al servir contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.4.1 (19 de abril de 2021)

Esta versión contiene las siguientes nuevas funciones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

| Función | Detalles |
| --- | --- |
| Compatibilidad con la toma de decisiones en el dispositivo para at.js | La toma de decisiones en dispositivos permite a los especialistas en marketing y a los desarrolladores ofrecer experimentación y personalización en el navegador de un usuario con una latencia cercana a cero. |

Esta versión contiene las siguientes mejoras, correcciones y cambios.

* Se ha corregido un problema que impedía que una actividad se sincronizara después de cambiar la audiencia a [!UICONTROL Todos los visitantes]. (TGT-40259)
* Se ha corregido un problema que impedía que las ofertas se duplicaran cuando se usaban en distintas ubicaciones en actividades [!UICONTROL Automated Personalization] aunque la opción [!UICONTROL No permitir duplicados] estuviera habilitada. (TGT-39567)
* Se ha corregido un problema que impedía que la página [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] se cargara correctamente. (TGT-39918)
* Se ha corregido un problema que provocaba que las propiedades se asignaran al espacio de trabajo incorrecto. (TGT-39869)
* [!DNL Target Recommendations] admite nuevos operadores basados en listas para reglas de filtrado de entidades. (TGT-39234)

   Los operadores recién añadidos incluyen:

   * Está contenido en la lista
   * No está contenido en la lista
   * La Lista Contiene Un Elemento De
   * La Lista No Contiene Un Elemento En
   * La lista contiene todos los elementos de
   * La Lista No Contiene Todos Los Elementos De

* Se ha corregido un problema que provocaba una carga infinita si la solicitud fallaba después de cambiar el entorno al crear una exclusión de Recommendations. (TGT-39948)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
