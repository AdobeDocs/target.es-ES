---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Notas de la versión
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b897829595ef1cdda28a995481fa1d2d5d1616f4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 24 de junio de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.6.1 (30 de junio de 2021)

Esta versión incorpora las siguientes nuevas funciones y mejoras. Los números entre paréntesis son para uso interno de [!DNL Adobe].

| Función | Detalles |
| --- | --- |
| [!UICONTROL Analytics for Target] (A4T) | Ahora, al hacer clic en el vínculo “[!UICONTROL Ver en Analytics]” de la página [!UICONTROL Informes] de una actividad que utiliza [!DNL Analytics] como fuente de informes (A4T), [!DNL Analysis Workspace] se abre. Anteriormente, el vínculo abría Creación de informes [!DNL Analytics]. (TGT-36959) |
| [!DNL Recommendations] ![premium](/help/assets/premium.png) | Las siguientes mejoras se aplican a los algoritmos de popularidad de [!DNL Recommendations]:<ul><li>Habrá disponible una nueva opción de ventana retrospectiva de seis horas (intervalo de datos) para todos los algoritmos de popularidad (más visitados/más vendidos) cuando [!DNL Target] sea la fuente de datos de comportamiento. (Esta ventana retrospectiva *no* está disponible cuando [!DNL Adobe Analytics] es la fuente de datos de comportamiento).</li><li>Cuando se seleccionan, los siguientes algoritmos se ejecutan aproximadamente cada tres horas (en lugar de cada doce).<ul><li>Más visitados</li><li>Más comprados</li><li>Más visitados por categoría</li><li>Más comprados por categoría</li><li>Más visitados por atributo personalizado (con la función groupBy)</li><li>Más comprados por atributo personalizado (con la función groupBy)</li></ul></ul>Fecha de lanzamiento por anunciar. (TOP-1086) |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
