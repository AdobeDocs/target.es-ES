---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5566393192b131b837fece1bb2a6781e2f953190
workflow-type: ht
source-wordcount: '1055'
ht-degree: 100%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Versión de API de modelos (23 de noviembre de 2022)

La nueva API de modelos [!DNL Adobe Target], también denominada API de lista de bloqueados, permite a los usuarios ver y administrar la lista de funciones utilizadas en los modelos de aprendizaje automático para actividades de [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] (AT).

Para obtener más información, consulte [Información general sobre API de modelos](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} en la *Guía para desarrolladores de Adobe Target*.

## [!DNL Target] Standard/Premium 22.10.3 (versión escalonada del 25 al 27 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **25 de octubre**: región de Europa, Oriente Medio y África (EMEA)
* **26 de octubre**: región Asia-Pacífico (APAC)
* **27 de octubre**: región de América

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| Métricas de A4T optimizadas para [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]<br> (disponible para clientes seleccionados para realizar pruebas. Estará disponible para todos los clientes en una versión futura). | Tenga en cuenta los siguientes cambios:<ul><li>Se ha añadido compatibilidad con las métricas no binarias y de maximización en la creación de informes de [!UICONTROL Analytics for Target] (A4T) para las actividades de [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática]</li><li>Se ha mantenido el comportamiento para las actividades existentes hasta febrero de 2023. Después de esta fecha, las actividades se suspenderán para forzar la migración de la actividad existente a un nuevo comportamiento</li><li>A partir del 20 de febrero de 2023, la compatibilidad con las métricas `averagetimespentonsite`, `bouncerate` y `entries` en las actividades de [!DNL Target] quedará obsoleta.</li></ul> |

* Se ha añadido información en la IU de [!DNL Target] para ayudar a los clientes a navegar por el generador de audiencias de forma más eficaz y para aprender a utilizar funciones que pueden ser desconocidas. (TGT-44139)
* Funcionalidad agregada para evitar que los clientes editen una actividad deshabilitada por [!DNL Target] porque utiliza métricas no admitidas. Un mensaje en la IU indica a los clientes que dupliquen la actividad y que luego actualicen las métricas de conversión.

   Con esta versión, las métricas `averagetimespentonsite`, `bouncerate` y `entries` en las actividades de [!DNL Target] quedarán obsoletas para las nuevas actividades. Las actividades existentes pueden seguir utilizando estas métricas hasta mayo de 2023.

* Se ha añadido información en la IU de [!DNL Target] para ayudar a los clientes a seleccionar criterios de optimización al crear o editar una actividad de [!UICONTROL Segmentación automática] que utiliza A4T.

## [!DNL Target] Standard/Premium 22.10.1 (versión escalonada del 10 al 13 de octubre de 2022)

Esta versión estará disponible según la siguiente programación escalonada:

* **10 de octubre**: región Asia-Pacífico (APAC)
* **12 de octubre**: región de América
* **13 de octubre**: región de Europa, Oriente Medio y África (EMEA)

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
| --- | --- |
| Fragmentos de experiencias de [!DNL Adobe Experience Manager] (AEM) | Las actualizaciones de la funcionalidad de fragmentos de experiencias de AEM incluyen lo siguiente:<ul><li>Se ha agregado la capacidad de filtrar Fragmentos de experiencias de AEM por tipo (HTML o JSON) en la lista [!UICONTROL Ofertas]. (TGT-43121)</li><li>Se ha corregido un problema que permitía a los clientes insertar ofertas de [!UICONTROL Fragmento de experiencia] JSON al usar el VEC, lo cual no es compatible. Las ofertas JSON solo se pueden insertar al usar el compositor de [!UICONTROL Experiencias basadas en formularios]. (TGT-43846)</li></ul>Para obtener más información, consulte [Fragmentos de experiencias](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM. |
| Nueva extensión del [!UICONTROL Compositor de experiencias visuales] para Google Chrome | Una nueva extensión [!UICONTROL Compositor de experiencias visuales] (VEC) de [!DNL Adobe Target] para Chrome está disponible en Chrome Web Store.<br>A partir de enero de 2023, la extensión del ayudante del VEC de [!DNL Target] dejará de funcionar en Google Chrome porque Google no permitirá extensiones con Manifest V2. Descargue la nueva extensión para continuar creando de forma visual sus sitios web en [!DNL Target] a partir del nuevo año.<br>Los siguientes vínculos muestran las dos extensiones en la Chrome Web Store:<ul><li>[Nueva extensión](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensión antigua](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obtener más información, consulte [extensión del Asistente de edición visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Actualizaciones de documentación | Las principales actualizaciones de la documentación son las siguientes:<ul><li>La [Documentación de la API de informes y administración de Adobe Target](https://developer.adobe.com/target/administer/admin-api/){target=_blank} nueva y actualizada incluye una cobertura completa de los extremos de las API de informes y administración, incluidas propiedades, ofertas, hosts, entornos, clientes, audiencias, actividades y mucho más.<br>Consulte este y el contenido adicional para desarrolladores en la sección [[!DNL Adobe Target] [!UICONTROL Guía para desarrolladores]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br> Este artículo documenta los cálculos estadísticos detallados utilizados en las pruebas A/Bn manuales en [!DNL Adobe Target].<br>La información de este artículo sustituye al archivo PDF *Cálculos de Adobe Target para Pruebas A/B* que anteriormente estaba disponible para su descarga en este sitio.</li></ul> |

* Se ha corregido un problema que impedía que la información de reglas de audiencias se mostrara correctamente en la ventana de información [!UICONTROL Refinamientos de audiencias]. (TGT-43917)
* Se ha mejorado el rendimiento de la IU de [!DNL Target] al cargar audiencias que se aproximan al [límite recomendado de las reglas de segmentación](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Se ha corregido un problema que hacía que algunos componentes no se mostraran correctamente en el panel [!UICONTROL Modificaciones] de la página [!UICONTROL Experiencias] al crear o editar actividades en el VEC después de cambiar del modo [!UICONTROL Componer] a [!UICONTROL Examinar]. (TGT-43300)
* Se ha corregido un problema que impedía que algunos clientes archivaran actividades de [!UICONTROL Prueba A/B] que utilizan [!UICONTROL Segmentación automática]. (TGT-40978)
* Se ha añadido la capacidad de usar automáticamente una sola oferta en varias ubicaciones dentro de un único grupo de creación de informes. (TGT-40689)

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
