---
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target.
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones
seo-description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target de DNL.
seo-title: Notas de la versión de evaluación de Adobe Target
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e11f8dfee9bcdfae530efc75b239f0d7af045005

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 2 de octubre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Plataforma de destino

| Función.  / Mejora | Descripción |
| --- | --- |
| SDK de Node.js versión 1.0<br>(9 de octubre de 2019) | El SDK de Node.js de Target permite implementar Target en el servidor.<br>Este SDK de Node.js ayuda a integrar fácilmente Target con otras soluciones de Experience Cloud, como el servicio de identidad de Adobe Experience Cloud, Adobe Analytics y Adobe Audience Manager.<br>El SDK de Node.js introduce prácticas recomendadas y elimina las complejidades al integrarse con Adobe Target a través de nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial. Las siguientes son funciones destacadas que presentamos en la versión más reciente:<ul><li>Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché.</li><li>Compatibilidad para optimizar el rendimiento cuando se dispone de una integración híbrida de Target en las páginas web y en el servidor. Estamos introduciendo una configuración llamada `serverState` que se rellenará con las experiencias recuperadas a través del servidor para que at.js 2.2 ya no realice una llamada adicional al servidor para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.</li><li> Compatibilidad con la recuperación de actividades creadas por VEC mediante el SDK de Node.js, lo cual es posible gracias a la nueva API de envío.</li><li>Abra source para que los desarrolladores puedan contribuir al SDK de Node.js.</li></ul>Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)de Target Node.js. |
| API<br>de envío (9 de octubre de 2019) | En la producción habrá disponible un extremo de la API de entrega completamente nuevo (/v1/delivery). Las características destacables son:<ul><li>Un punto final para recuperar experiencias para uno o varios mboxes.</li><li>Recupere actividades creadas por VEC mediante la API.</li><li>Compatibilidad con un objeto completamente nuevo llamado Vistas que se utiliza en aplicaciones de una sola página (SPA) y aplicaciones móviles.</li></ul>Para obtener más información, consulte [Notas de la versión: API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)de servidor de Target. |
| Versión 2.2.<br><br>y at.js de at.js versión 1.8<br>(10 de octubre de 2019) | Estas versiones de at.js proporcionan:<ul><li>Se ha mejorado el rendimiento al usar tanto el servicio Experience Cloud ID (ECID) v4.4 como at.js 2.2 o at.js 1.8 en las páginas web.</li><li>Anteriormente, el ECID realizaba dos llamadas de bloqueo antes de que at.js pudiera recuperar experiencias. Esto se ha reducido a una sola llamada, lo que mejora significativamente el rendimiento.</li></ul> Para aprovechar estas mejoras de rendimiento, actualice a at.js 2.2 o at.js 1.8 junto con la biblioteca ECID v4.4.<br>at.js 2.2 proporciona:<ul><li>**serverState**: Una configuración disponible en at.js v2.2+ que se puede utilizar para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Target. La integración híbrida significa que está utilizando at.js v2.2+ en el cliente y la API de entrega o un SDK de Target en el servidor para ofrecer experiencias. `serverState` proporciona a at.js v2.2+ la capacidad de aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está ofreciendo.<br>Para obtener más información, consulte "serverState" en [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |


## Target Standard/Premium 19.10.1 (22 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Premium](/help/assets/premium.png) Recomendaciones basadas en el usuario | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como "Recomendado para usted".<br>Este criterio le permite entregar contenido y experiencias personalizados tanto a visitantes nuevos como a visitantes que regresan. La lista de recomendaciones se centra en la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el visitante navega por el sitio. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
