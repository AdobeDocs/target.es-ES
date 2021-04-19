---
keywords: Notas de la versión;nuevas funciones;versiones;actualizaciones;actualización;versión;mejora;mejoras;correcciones;correcciones de errores;actualizaciones
description: Conozca las nuevas funciones, mejoras y correcciones incluidas en la versión actual de Adobe Target, incluidos SDK, API y bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluyen en la versión actual?
feature: ' Notas de la versión '
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: 9b6123fd0f9d44e43bd8e6bae1ddd7ef8c00d2e3
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 35%

---

# Notas de la versión de Target (actual)

Estas notas de la versión proporcionan información sobre características, mejoras y correcciones para cada versión [!DNL Adobe Target Standard] y [!DNL Target Premium]. Además, también se incluyen notas de la versión de API de Target, SDK, la biblioteca JavaScript (at.js) y otros cambios de plataforma, cuando corresponde.

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021,  [!DNL Adobe Target] no es compatible con la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado.
>
>Migrar a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar problemas potenciales con sus sitios. Para obtener más información, consulte [Información general: implementar Target para la web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Los números entre paréntesis son para uso interno de [!DNL Adobe]).

## Target Standard/Premium 21.4.1 (19 de abril de 2021)

Esta versión contiene las siguientes nuevas funciones y mejoras. Los números entre paréntesis son para uso interno de [!DNL Adobe].

| Función | Detalles |
| --- | --- |
| Compatibilidad con la toma de decisiones en el dispositivo para at.js | La toma de decisiones en dispositivos permite a los especialistas en marketing y a los desarrolladores ofrecer experimentación y personalización en el navegador de un usuario con una latencia cercana a cero.<br>Para obtener más información, consulte  [Decisiones en el dispositivo para at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![](/help/assets/premium.png) Operadores basados en PremiumList para reglas de filtrado de entidades | [!DNL Target Recommendations] admite nuevos operadores basados en listas para reglas de filtrado de entidades. (TGT-39234)<br>Los operadores añadidos recientemente incluyen:<br><ul><li>Está contenido en la lista</li><li>No está contenido en la lista</li><li>La Lista Contiene Un Elemento De</li><li>La Lista No Contiene Un Elemento En</li><li>La lista contiene todos los elementos de</li><li>La Lista No Contiene Todos Los Elementos De</li></ul>Para obtener más información, consulte &quot;Operadores disponibles&quot; en [Uso de reglas de inclusión dinámicas y estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Esta versión contiene las siguientes correcciones.

* Se ha corregido un problema que impedía que una actividad se sincronizara después de cambiar la audiencia a [!UICONTROL Todos los visitantes]. (TGT-40259)
* Se ha corregido un problema que impedía que las ofertas se duplicaran cuando se usaban en distintas ubicaciones en actividades [!UICONTROL Automated Personalization] aunque la opción [!UICONTROL No permitir duplicados] estuviera habilitada. (TGT-39567)
* Se ha corregido un problema que impedía que la página [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] se cargara correctamente. (TGT-39918)
* Se ha corregido un problema que provocaba que las propiedades se asignaran al espacio de trabajo incorrecto. (TGT-39869)
* Se ha corregido un problema que provocaba una carga infinita si la solicitud fallaba después de cambiar el entorno al crear una exclusión de Recommendations. (TGT-39948)

## Versión 2.5.0 de at.js (19 de abril de 2021)

Esta versión de at.js incluye las siguientes mejoras y cambios:

* [Compatibilidad de ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) decisiones en el dispositivo para at.js.
* [Vista previa de ](/help/c-activities/c-activity-qa/activity-qa.md) vínculos Compatibilidad con actividades de Automated Personalization.

Esta versión también elimina la compatibilidad con Microsoft Internet Explorer 10 y versiones posteriores.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que no se incluyen en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte Notas de la versión del  [Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Actualización de producto prioritario de Adobe | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
