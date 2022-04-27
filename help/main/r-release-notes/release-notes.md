---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 25dac5f4712fec80323df9b0e00feb9750f5b155
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 56%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, las notas de la versión para [!DNL Target] API, SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de plataforma también se incluyen, cuando corresponde.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] versión de plataforma (27 de abril de 2022)

Esta versión contiene el siguiente cambio:

* Con esta versión puede recuperar previamente contenido para [!UICONTROL Personalización automática] (AP) y [!UICONTROL Segmentación automática] Actividades (AT) (anteriormente no devueltas por [!DNL Target]). Esto puede cambiar las experiencias que los usuarios finales ven en caso de una llamada de recuperación previa (sin cambios en el flujo &quot;ejecutar&quot;) si una actividad AP/AT está en la ruta de entrega y tiene mayor prioridad que otras actividades AB/XT que utilizan la misma ubicación para la entrega de contenido.

## Versión de la plataforma de Target (13 de abril de 2022)

Esta versión contiene la siguiente actualización:

* Se ha corregido un problema para garantizar que el último octeto de direcciones IP se confunda correctamente al capturarse mediante scripts de perfil. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (5 de abril de 2022)

Esta versión contiene las siguientes mejoras y cambios:

* Se ha corregido un problema que hacía que la variable [!UICONTROL Incluir] y [!UICONTROL Excluir] opciones que se deshabilitarán para audiencias combinadas al editar una actividad. (TGT-43422)
* Se ha corregido un problema que impedía a algunos clientes ver la lista de audiencias disponibles al editar una actividad. (TGT-43404)
* Se ha corregido un problema que impedía que algunos clientes eliminaran una dirección IP de &quot;[!UICONTROL IP de las que excluir [!DNL Target] datos de informes]&quot; en [!UICONTROL Administración] > [!UICONTROL Informes]. (TGT-43384)
* Se ha corregido un problema que impedía el uso de números negativos en criterios de audiencia que comprobaban que cualquier variable era &quot;buena que&quot;, &quot;buena o igual que&quot;, &quot;menor que&quot; o &quot;menor o igual que&quot;. (TGT-43367)
* Se ha corregido un problema que impedía que los clientes vieran la variable [!UICONTROL Detalles de audiencia] al crear audiencias combinadas. (TGT-43303)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

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
