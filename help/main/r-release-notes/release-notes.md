---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d54f3c4c75031788316a94acf3d14a8db2a17366
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 100%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Versión de la plataforma de [!DNL Target] (20 de julio de 2022)

Esta versión incluye las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | --- |
| Se ha mejorado la precisión de la evaluación de audiencia y se ha reducido la latencia del usuario final gracias a la compatibilidad con IPv6 (TNT-43364, TNT-44692) | Las ubicaciones geográficas de los visitantes ahora están determinadas por las direcciones IPv6, si están disponibles, en lugar de solo las direcciones IPv4. Las API de entrega también admiten parámetros de entrada de IPv6. El filtrado y la inclusión en la lista de permitidos admiten direcciones IPv4 e IPv6. La compatibilidad con IPv6 en esta versión significa que los visitantes se incluirán de forma más precisa en las audiencias (más exactamente, calificarán para actividades o se incluirán en los criterios de filtrado). También mejora la latencia de datos, ya que los clientes de IPv6 se dirigirán directamente, lo que evita la sobrecarga de la puerta de enlace IPv6 a IPv4. |
| Se ha corregido un problema de gestión de carga útil del lado del cliente de A4T (TNT-44926) | Con la integración del lado del servidor de A4T, si Adobe Target identifica una solicitud como proveniente de un bot, no reenvía la carga útil a Analytics y no hay ningún evento mod_stats registrado en los registros de [!DNL Target]. Con esta versión, se ha mejorado el registro en el lado del cliente de A4T, de modo que el comportamiento con respecto a la carga útil de A4T sea el mismo que con el del lado del servidor de A4T. Los visitantes identificados como bots se excluyen del recuento/creación de informes de [!DNL Target]. Tenga en cuenta que el problema en cuestión se limitaba a las implementaciones que utilizaban la gestión de la carga útil del lado del cliente; del lado del servidor no se vieron afectadas. Con esta versión, el comportamiento ahora es coherente para la gestión de carga útil del lado del servidor y del lado del cliente. |

## [!DNL Target Standard/Premium] 22.6.2 (30 de junio de 2022)

Esta versión incluye las siguientes funciones, mejoras y correcciones:

| Función | Descripción |
| --- | ---  |
| Notificaciones en el producto | Obtenga las siguientes notificaciones relevantes en el producto:<ul><li>**Actividades**: notificaciones para todos los tipos de actividades cuando se aprueba o desactiva una actividad, ya sea manualmente o cuando llega a su fecha de inicio o de finalización. La notificación incluye el nombre de la actividad con un vínculo a la página de información general de la actividad.</li><li>**Scripts de perfil**: notificaciones cuando se activa o desactiva un script de perfil, ya sea de forma manual o por parte de Target.</li><li>**Fuentes de Recommendations**: notificaciones cuando se activa o desactiva una fuente de Recommendations, ya sea de forma manual o por parte de Target. Las notificaciones también se envían cuando falla una fuente de Recommendations.</li></ul> De forma predeterminada, las notificaciones se reciben por administradores de productos, editores y aprobadores. Las notificaciones se pueden configurar dentro de las preferencias de Experience Cloud.<br>Para obtener más información, consulte [Notificaciones y anuncios](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guía para desarrolladores de Adobe Target* | La *Guía para desarrolladores de Adobe Target* consolida todo el contenido de [!DNL Target] para desarrolladores en una guía práctica. La guía incluye información acerca de la implementación de [!DNL Target] y [!DNL Recommendations], SDK de [!DNL Target] y API de [!DNL Target].<br>Para obtener más información, consulte [Guía para desarrolladores de Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Los usuarios con la función [!UICONTROL Editor] ya no pueden editar audiencias en actividades activas. (TGT-43582)
* Aparece un mensaje de advertencia si un cliente intenta guardar una audiencia con un signo de exclamación (!) como el primer carácter del nombre de la audiencia (por ejemplo, !Londres). (TGT-43643)
* Se ha corregido un problema que provocaba que las tarjetas de detalles de definición de audiencias de algunos clientes indicaran que una actividad finalizada seguía activa. (TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1 (versión escalonada: 7 y 9 de junio de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **7 de junio**: Región de Asia y el Pacífico (APAC)
* **8 de junio**: Región de América
* **9 de junio**: Región de Europa, Oriente Medio y África (EMEA)

Esta versión incluye las siguientes mejoras y correcciones:

* Se mejoró la nueva página [!UICONTROL Audiencias] para evitar un estado incoherente entre la antigua base de datos donde las audiencias se almacenaron en el pasado y la nueva arquitectura que está recuperando la información directamente desde el servidor. (TGT-43552)
* Se ha corregido un problema que impedía que algunos clientes guardaran audiencias combinadas provocadas por la creación de contenedores &quot;vacíos&quot; por la interfaz de usuario de Target. (TGT-43588)

## Versión de la plataforma de Target (25 de mayo de 2022)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha añadido compatibilidad con [Sugerencias para el cliente del agente de usuario](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}.
* Se ha corregido un problema que ocasionaba tiempos de espera intermitentes al procesar [!UICONTROL Decisiones de oferta] en actividades de [!UICONTROL Segmentación de experiencias] (XT). (TNT-44611)

## Versión 2.9.0 de at.js (27 de mayo de 2022)

* Se ha añadido compatibilidad con [Sugerencias para el cliente del agente de usuario](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}.
* Se ha corregido un error por el cual varias solicitudes de mbox en la misma página tenían ID de impresión diferentes.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/main/r-release-notes/target-release-notes.md). |
