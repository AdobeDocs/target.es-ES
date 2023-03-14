---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 64%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.15.1 (8 y 9 de marzo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

* **8 de marzo**: región de América
* **Marzo de 9**: región de Europa, Oriente Medio y África (EMEA)
* **Marzo de 9**: región Asia-Pacífico (APAC)

>[!NOTE]
>
>Debido a problemas que se han corregido desde entonces, las métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]&quot; la función que se lanzó el 8 y 9 de marzo se ha eliminado temporalmente. Después de más pruebas internas, la función se lanzará de nuevo en las próximas semanas.

Esta versión incluye las siguientes correcciones:

* Actualizaciones para la creación de componentes web personalizados con [!UICONTROL Compositor de experiencias visuales] (VEC):

   * Se ha corregido la selección de elementos DOM sombreados en el VEC al mejorar el proceso de creación, de modo que no haya dependencia del [!DNL Target] tipo de implementación al crear la raíz en la sombra. Ahora, la selección de los elementos DOM sombreados en el VEC debería funcionar para cualquier sitio web.
   * Se ha corregido un problema que impedía cargar elementos HTML usando #Shadow DOM en el VEC. (TGT-35801)
   * SPA Se han corregido problemas del VEC con sitios web que utilizaban ShadowDOM, por lo que se eliminaron problemas de VEC. (TGT-43169)
   * Se ha corregido un problema con el objetivo de optimización: &quot;hacer clic en un elemento&quot; que no identificaba correctamente el selector de CSS en ShadowDOM.

>[!NOTE]
>
>Para garantizar la entrega de los cambios creados en el VEC, asegúrese de utilizar un [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) con una versión buena a 2.8.

**Problema conocido**: Seguimiento de clics en un elemento raíz de la sombra al utilizar [!DNL Adobe Experience Platform Web SDK] no funciona correctamente. (TNT-47012)

## Versión 2.10.2 de at.js (7 de marzo de 2023)

* Se ha corregido un problema que provocaba que `trackEvent` para devolver siempre un error.

Para obtener información sobre todas las versiones de at.js, consulte [Detalles de las versiones de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

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
