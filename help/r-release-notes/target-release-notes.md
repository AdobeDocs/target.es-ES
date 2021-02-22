---
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Adobe Target, incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la próxima versión?
feature: ' Notas de la versión '
translation-type: tm+mt
source-git-commit: 453106f7534f83c205722421bbf00044fde7da67
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 25%

---


# Notas de la versión de Target (versión previa)

Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 17 de febrero de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información en estas páginas puede ser la misma, según el tiempo de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Adobe recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o de la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (9 y 10 de marzo de 2021)

Esta versión de mantenimiento contiene las siguientes mejoras, correcciones y cambios.

Los números entre paréntesis son para uso interno de [!DNL Adobe].

* Se ha aumentado el tamaño de oferta permitido:

   | Tipo  | Límite anterior | Nuevo límite |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | Ofertas visuales de la interfaz de usuario de Destinatario | 64 kB | 1024 KB por cada experiencia |
   | Mediante API | 512 kB | 1024 KB |

* Se corrigió un problema que ocasionaba que la dependencia actual no se mostrara cuando los clientes hacían clic en [!UICONTROL Editar dependencia] en la página [!UICONTROL Objetivos y configuración] de una actividad. (TGT-39340)
* Se corrigió un problema al actualizar la [!UICONTROL biblioteca de Audiencias] de un espacio de trabajo. Antes de la actualización, se mostraban las audiencias del espacio de trabajo seleccionado. Después de la actualización, se muestra el [!UICONTROL espacio de trabajo predeterminado] y sus audiencias. El espacio de trabajo actual y sus audiencias ahora persisten después de la actualización. (TGT-38871)
* Se corrigió un problema al copiar una actividad [!UICONTROL Recommendations] y posteriormente editar la actividad original cambiando su secuencia de criterios. El cambio en la secuencia de criterios de la actividad original también se aplicó incorrectamente a la actividad copiada. (TGT-39155)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
