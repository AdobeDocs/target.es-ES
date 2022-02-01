---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 211540256d2bbaddf3053eb1cba2b30b058af8fd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de Target, los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Target Standard/Premium 22.2.1 (1 de febrero de 2022)

Esta versión de mantenimiento contiene las siguientes correcciones y mejoras para el nuevo [!UICONTROL Audiencias] La interfaz de usuario se anunció en la versión Target Standard/Premium 22.1.2 que se lanzará a los clientes de todas las regiones en las próximas seis semanas. Estas correcciones alinean la funcionalidad de las audiencias creadas en [!DNL Adobe Target Standard/Premium].

* Se ha corregido un problema que impedía importar audiencias de [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud]y [!DNL Adobe Target Classic] desde estar asignadas como audiencias de informes. (TGT-43140)
* Se ha añadido un [!UICONTROL Eliminar] en la [!UICONTROL Audiencias] lista para audiencias importadas de [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud]y [!DNL Adobe Target Classic]. También se ha agregado la funcionalidad de eliminación masiva. (TGT-42914)

## Versión 2.8.1 de at.js (28 de enero de 2022)

* Fijo `pageLoad` no está asignado a target-global-mbox en [!UICONTROL Al decidir el dispositivo] (ODD) modo de ejecución híbrido.
* Se ha corregido un problema con los detalles de análisis para la solicitud de mbox.
* Se han actualizado las dependencias de desarrollo para corregir las vulnerabilidades de seguridad.

## [!DNL Target Standard/Premium] 22.1.2 (26 de enero de 2022)

| Función | Detalles |
| --- | --- |
| [!DNL Adobe Experience Platform] audiencias en [!DNL Target] | Ahora puede consumir y utilizar [!DNL Adobe Experience Platform] audiencias en [!DNL Target]. La variable [!DNL Target] equipo, [!DNL Experience Platform] [!DNL Destinations] y [!DNL Unified Profile Service] El equipo se complace en anunciar la disponibilidad general de los casos de uso de &quot;Personalización de la misma página/página siguiente&quot;.<br>Uso de audiencias creadas en [!DNL Adobe Experience Platform] proporcione datos de clientes más completos que conduzcan a una personalización más impactante. La variable [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP), generado en [!DNL Adobe Experience Platform] ayuda a las empresas a reunir datos conocidos y anónimos de varias fuentes empresariales para crear perfiles de clientes que se puedan usar para ofrecer experiencias de clientes personalizadas en todos los canales y dispositivos en tiempo real.<br>Para obtener más información, consulte [Usar audiencias de Adobe Experience Platform](/help/c-target/c-audiences/audiences.md#aep) en *Crear audiencias*.<br>Asegúrese de leer el blog del Adobe y ver el video: [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] y [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}. |
| Actualización de la IU de las [!UICONTROL audiencias] | Como parte del esfuerzo continuo del equipo de [!DNL Adobe Target] para mejorar la experiencia del usuario para los usuarios de [!DNL Target], esta versión actualiza las páginas [!UICONTROL Audiencias] y [!UICONTROL Scripts de perfil] en la IU de [!DNL Target]. Esta actualización unifica y estandariza los patrones de diseño que anteriormente eran incoherentes, a la vez que añade nuevas mejoras, como las siguientes:<ul><li>La capacidad de seleccionar y eliminar varias audiencias simultáneamente</li><li>Un [diseño del generador de audiencias](/help/c-target/c-audiences/create-audience.md) actualizado</li><li>Compatibilidad con las reglas de exclusión en el generador de reglas de biblioteca de [!UICONTROL Audiencia]</li><li>El nuevo filtro “Fuente de audiencia” que permite una detección de audiencias más rápida</li><li>Opciones de filtro y búsqueda persistentes de sesión</li><li>La capacidad de mover audiencias entre espacios de trabajo para [!DNL Target Premium] clientes.</li></ul>Para obtener más información, consulte [Audiencias](/help/c-target/target.md).<br>**NOTA**: Esta función se implementará para clientes de diferentes regiones en las próximas ocho semanas. |
| Actualización de la IU de [!UICONTROL Scripts de perfil] | La biblioteca de [!UICONTROL Scripts de perfil] también se ha actualizado e incluye una interfaz renovada y varias actualizaciones de productividad:<ul><li>La capacidad de seleccionar y eliminar varios scripts del perfil simultáneamente</li><li>Un nuevo editor de código para scripts de perfil</li><li>Resaltado de sintaxis y comprobación de errores dentro del editor de código</li><li>Completar automáticamente los parámetros de tokens (mbox o perfil) mediante métodos abreviados del teclado</li></ul>Para obtener más información, consulte [Perfiles de los visitantes](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**NOTA**: Esta función se implementará para clientes de diferentes regiones en las próximas ocho semanas. |

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones que se realizaron en esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las [Notas de la versión de Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es). |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
