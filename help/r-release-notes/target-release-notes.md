---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Adobe Target, incluidos SDK, API y bibliotecas JavaScript.
title: ¿Qué nuevas funciones se incluyen en la próxima versión?
feature: ' Notas de la versión '
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 22%

---


# Notas de la versión de Target (versión previa)

Este artículo contiene información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 1 de marzo de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma, en función del momento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: El 31 de marzo de 2021, ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Adobe recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (9 de marzo de 2021). 

Esta versión de mantenimiento contiene las siguientes mejoras, correcciones y cambios.

Los números entre paréntesis son para uso interno de [!DNL Adobe].

* Se ha aumentado el tamaño de oferta permitido (TGT-38304):

   | Tipo  | Límite anterior | Nuevo límite |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | Ofertas visuales de la interfaz de usuario de Target | 64 kB | 1024 kB para cada experiencia |
   | A través de la API | 512 kB | 1024 KB |

* [!UICONTROL Los ] informes de Perspectivas de personalización para las actividades de Segmentación  [!UICONTROL automática]  (AT) y Personalización  [!UICONTROL automatizada]  (AP) ahora se producen diariamente. Puede elegir un informe que proporcione [!UICONTROL Segmentos automatizados] o [!UICONTROL Atributos importantes] para los últimos 15, 30 y 60 días. Se han eliminado las opciones de 45 y 90 días para permitir que el resto de la configuración de la ventana retrospectiva se ejecute diariamente. (TGT-39472)
* Se ha corregido un problema que hacía que la dependencia actual no se mostrara cuando los clientes hacían clic en [!UICONTROL Editar dependencia] en la página [!UICONTROL Objetivos y configuración] de una actividad. (TGT-39340)
* Se ha corregido un problema al actualizar la [!UICONTROL Biblioteca de audiencias] de un espacio de trabajo. Antes de la actualización, se mostraban las audiencias del espacio de trabajo seleccionado. Después de la actualización, se mostraban el [!UICONTROL espacio de trabajo predeterminado] y sus audiencias. El espacio de trabajo actual y sus audiencias persisten ahora después de la actualización. (TGT-38871)
* Se ha corregido un problema que se producía al copiar una actividad de [!UICONTROL Recommendations] y posteriormente editarla cambiando la secuencia de criterios. El cambio en la secuencia de criterios de la actividad original también se aplicó incorrectamente a la actividad copiada. (TGT-39155)
* Se ha corregido un problema que provocaba que se mostrara un número incorrecto de productos para exclusiones [!UICONTROL Recommendations] . (TGT-39599)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
