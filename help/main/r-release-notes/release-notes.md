---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b06cc6f4a8e7d1617dd5d3a8226e2b77474cfe77
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 59%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.5.2 (31 de mayo de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

| Función | Detalles |
|--- |--- |
| Atributos de perfil de Real-Time CDP compartidos con [!DNL Target] | Los [!UICONTROL Atributos de perfil de Real-Time CDP] se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y JSON.<P>Para obtener más información, consulte [Uso compartido de atributos de perfil de Real-Time CDP con [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

* Se ha corregido un problema que provocaba que se mostrara una página en blanco al generar un token de autorización de API de perfil. (TGT-45387 y TGT-45423)
* Se ha corregido un problema que impedía que se mostrara una imagen en la [!UICONTROL Crear diseño] panel si el nombre de la imagen contiene caracteres GB 18030. (TGT-44614)
* Se ha corregido un problema por el cual algunos caracteres de símbolo GB 18030 se escapaban incorrectamente en Texto/HTML en experiencias. (TGT-44600)
* Se ha corregido un problema que generaba informes para [!UICONTROL Personalización automática] actividades para congelar durante el análisis. (TGT-44820)
* Se ha corregido un problema que impedía buscar una actividad en [!UICONTROL Actividad] página si el nombre de la actividad contiene un corchete ( [ o ] ). (TGT-44777)
* Se ha corregido un problema que impedía que una actividad se sincronizara si el objetivo de la actividad contenía caracteres especiales. (TGT-44982)
* Se ha corregido un problema que hacía que no se mostraran actividades en [!DNL Target] IU para el espacio de trabajo predeterminado de determinados clientes. (TGT-45286)
* Se ha actualizado el comportamiento del indicador No permitir duplicados. Los indicadores de ofertas repetidas excluidas se actualizan para permitir ofertas repetidas si son la oferta de contenido predeterminada (para las API v3 y v4) y permitir opciones duplicadas si las opciones hacen referencia a la oferta de contenido predeterminada y no tienen plantillas definidas. (TNT-46617)
* Se ha corregido un problema por el cual se agregaba un parámetro de consulta a una dirección URL que impedía que la página se cargara en [!UICONTROL Compositor de experiencias visuales] (VEC). (TGT-44873)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].

## [!DNL Target] Estándar/Premium 23.5.1 (23-25 de mayo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

23 de mayo: Región de Europa, Oriente Medio y África (EMEA) 24 de mayo: Región de Asia y el Pacífico (APAC) 25 de mayo: Región de América

Esta versión incorpora las siguientes mejoras y correcciones nuevas:

* Se ha corregido un problema que impedía que ciertos clientes crearan audiencias con perfiles de visitantes que usaran los operadores &quot;bueno que&quot; o &quot;menor que&quot;. (TGT-45271)
* Se han realizado varias correcciones de localización en la IU de [!DNL Target].
* Se ha actualizado la interfaz de usuario de Target en varios lugares para una próxima actualización de la interfaz de usuario (los cambios irán detrás de un indicador de función hasta que se publiquen las actualizaciones).

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| [Cambios de la documentación](/help/main/r-release-notes/doc-change.md) | Vea información detallada sobre las actualizaciones que se realizaron en esta guía y que no se incluyen en estas notas de la versión. |
| [Notas de la versión para versiones anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium. |
| [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es){target=_blank} | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud. |

## Información previa al lanzamiento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Reciba notificaciones avanzadas acerca de próximas mejoras de productos para [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud]. |
| [Notas de la versión de Target: versión preliminar](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Información acerca de las versiones de Target publicadas en el mes actual, incluida la información sobre la versión preliminar. |
