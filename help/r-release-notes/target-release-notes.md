---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Notas de la versión
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 146395f5453093ca34b259a143ff4e4c63be949b
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 69%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 7 de junio de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.5.2 (Fecha por determinar)

Esta versión incorpora las siguientes nuevas funciones y mejoras. Los números entre paréntesis son para uso interno de [!DNL Adobe].

| Función | Detalles |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Las siguientes mejoras se aplican a los algoritmos de popularidad [!DNL Recommendations]:<ul><li>Habrá disponible una nueva opción de seis horas de &quot;ventana retrospectiva&quot; (intervalo de datos) para todos los algoritmos de popularidad (más visitados/más vendidos) cuando [!DNL Target] sea la fuente de datos de comportamiento. (Esta ventana retrospectiva está *no* disponible cuando [!DNL Adobe Analytics] es la fuente de datos de comportamiento).</li><li>Cuando se selecciona, los siguientes algoritmos se ejecutan aproximadamente cada tres horas (en lugar de cada 12 horas).<ul><li>Más visitados</li><li>Más compradas</li><li>Más visitados por categoría</li><li>Más comprados por categoría</li><li>Más visitados por atributo personalizado (con la función groupBy)</li><li>La mayoría de las compras realizadas por el atributo personalizado (con la función groupBy)</li></ul></ul>(TOP-1086) |

Esta versión incluye las siguientes correcciones.

* Se agregará contenido a medida que se aproxime la fecha de lanzamiento.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
