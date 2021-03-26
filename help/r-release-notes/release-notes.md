---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de Adobe Target, incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: ' Notas de la versión '
translation-type: tm+mt
source-git-commit: 8dc0e5084834102e387492eb4668761382e699f3
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 36%

---


# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre características, mejoras y correcciones para cada versión [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de API de Target, SDK, la biblioteca JavaScript (at.js) y otros cambios de plataforma, cuando corresponde.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: El 31 de marzo de 2021, ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Migrar a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## at.js 2.4.1 (23 de marzo de 2021)

Esta versión de at.js es de mantenimiento e incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema por el que `targetPageParams` se incluía en las solicitudes de mbox. `targetPageParams` solo debe incluirse en las  `pageLoad` solicitudes. (TNT-40247)
* Se ha corregido un problema con los objetos globales de documento y ventana en la extensión A[!DNL dobe Experience Platform Launch] al reemplazar las dependencias de objeto global de Platform launch por referencias directas a ellos. (TNT-37124)

## Cambios en las direcciones IP de los servidores de procesamiento de fuentes de Recommendations (16 de marzo de 2021)

Las direcciones IP del servidor de procesamiento de fuentes [!DNL Target Recommendations] se actualizaron el 16 de marzo de 2021. Para obtener más información, consulte [Direcciones IP utilizadas por los servidores de procesamiento de fuentes de Recommendations](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

## Target Standard/Premium 21.2.1 (9 de marzo de 2021). 

Esta versión de mantenimiento contiene las siguientes mejoras, correcciones y cambios.

Los números entre paréntesis son para uso interno de [!DNL Adobe].

* Se ha aumentado el tamaño de oferta permitido (TGT-38304):

   | Tipo  | Límite anterior | Nuevo límite |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | Ofertas visuales de la interfaz de usuario de Target | 64 kB | 1024 kB para cada experiencia |
   | A través de la API | 512 kB | 1024 KB |

* [!UICONTROL Los informes ] de Perspectivas de personalización para las actividades de segmentación  [!UICONTROL automática]  (AT) y  [!UICONTROL Automated Personalization]  (AP) ahora se producen a diario. Puede elegir un informe que proporcione [!UICONTROL Segmentos automatizados] o [!UICONTROL Atributos importantes] para los últimos 15, 30 y 60 días. Se han eliminado las opciones de 45 días y 90 días para permitir que el resto de la configuración de la ventana retrospectiva se ejecute a diario. (TGT-39472)
* Se ha corregido un problema que hacía que la dependencia actual no se mostrara cuando los clientes hacían clic en [!UICONTROL Editar dependencia] en la página [!UICONTROL Objetivos y configuración] de una actividad. (TGT-39340)
* Se ha corregido un problema al actualizar la [!UICONTROL Biblioteca de audiencias] de un espacio de trabajo. Antes de la actualización, se mostraban las audiencias del espacio de trabajo seleccionado. Después de la actualización, se mostraban el [!UICONTROL espacio de trabajo predeterminado] y sus audiencias. El espacio de trabajo actual y sus audiencias persisten ahora después de la actualización. (TGT-38871)
* Se ha corregido un problema que se producía al copiar una actividad [!UICONTROL Recommendations] y posteriormente editarla cambiando la secuencia de criterios. El cambio en la secuencia de criterios de la actividad original también se aplicó incorrectamente a la actividad copiada. (TGT-39155)
* Se ha corregido un problema que provocaba que se mostrara un número incorrecto de productos para las exclusiones [!UICONTROL Recommendations] . (TGT-39599)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas de la versión del  [Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Actualización de producto prioritario de Adobe | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
