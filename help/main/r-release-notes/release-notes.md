---
keywords: notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones,actualizaciones actuales
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target], incluidos SDK, API y bibliotecas de JavaScript.
landing-page-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
short-description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones incluidas en la versión actual de  [!DNL Adobe Target].
title: ¿Qué se incluye en la versión actual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d823e9993ff17f1970dc1deac996928781c7e79d
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 39%

---

# [!DNL Target] Notas de la versión (actuales)

Estas notas de la versión proporcionan información sobre funciones, mejoras, correcciones y problemas conocidos para todas las versiones de [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de las API de [!DNL Target], los SDK, [!DNL Adobe Experience Platform Web SDK], at.js y otros cambios de la plataforma, cuando corresponda.

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## [!DNL Adobe Experience Platform Web SDK] `__view__` optimización del ámbito (22 de octubre de 2024)

Entre el 22 de julio de 2024 y el 15 de agosto de 2024, el equipo de [!DNL Target] optimizó el ámbito de `__view__`, lo que mejoró la precisión de los informes de impresión de actividad, visitas y visitantes. Esta optimización pretende capturar automáticamente los datos de los informes para las propuestas procesadas automáticamente y debe ser transparente para la mayoría de las cuentas.

Todos los clientes nuevos de [!DNL Adobe Experience Platform Web SDK] tendrán habilitada esta optimización. Sin embargo, los clientes que migraron desde at.js y no han seguido los pasos de implementación a continuación tienen la optimización deshabilitada. Instamos a estos clientes a revisar sus implementaciones antes del 3 de febrero de 2025. Después de esta fecha, habilitaremos la optimización para todos los clientes. Si no se revisan y ajustan las implementaciones para entonces, los informes podrían verse afectados, como se menciona a continuación. Póngase en contacto con [!DNL Adobe Customer Care] si necesita confirmar si la implementación se ve afectada o si necesita más tiempo para ajustar la implementación.

Para beneficiarse de esta optimización en caso de procesamiento manual de propuestas, revise su [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} para asegurarse de que está enviando notificaciones después de procesar manualmente experiencias o cuando utilice el método `applyPropositions` (o la acción correspondiente de [!DNL Launch] como ayudante) para procesar experiencias.

Los escenarios más comunes en los que las experiencias se procesan manualmente incluyen:

* Uso de ofertas JSON
* Utilizando un ámbito de decisión personalizado en una actividad creada en [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* No se usa `renderDecisions: true` al recuperar una actividad creada con [!UICONTROL Form-Based Experience Composer] que usa el ámbito global `__view__`

Si las notificaciones no se implementan como se documenta en [Procesar contenido personalizado](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} en la guía de *Recopilación de datos*, es posible que falten datos de informes en [!DNL Target] y en [Informes de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). En algunos casos, es posible que observe una división de tráfico incorrecta porque no se capturan los datos del sistema de informes. O, en otros casos, informar del mismo evento repetidamente.

Según la implementación, compruebe el impacto de los informes de [!DNL Analytics] y A4T.

[!DNL Platform Web SDK] admite dos tipos de implementación para procesar experiencias y personalizaciones:

* **Una sola llamada para personalización y medición.**

  Inicialmente recomendado, el método de una sola llamada para [!DNL Platform Web SDK] está programado para quedar obsoleto y pasar a ser el método de llamada dividida. Adobe recomienda a todas las nuevas implementaciones que utilicen el nuevo método de llamada dividida y recomienda que los clientes existentes también realicen la transición al método de llamada dividida.

  Si sigue usando el método de una sola llamada, es posible que observe los siguientes cambios inesperados en los informes de [!DNL Analytics]:

   * Un descenso en devoluciones.
   * Las visitas de A4T y [!UICONTROL Page View] no se han vinculado, lo que dificulta la realización de determinados desgloses y correlaciones en los informes de A4T con [!DNL Analytics] eVars y eventos.

* **Dividir llamadas (también conocidas como eventos de principio y final de página).**

  Este tipo de implementación es el nuevo [enfoque de implementación de llamada dividida](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recomendado por [!DNL Adobe]. Con este enfoque, la nueva optimización no afecta a los informes de [!DNL Analytics] ni A4T.

Si tiene preguntas, comuníquese con el Servicio de atención al cliente de [Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

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
