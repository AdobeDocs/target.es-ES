---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;functions;function;viewName;viewname;view name
description: Información sobre la función adobe.target.triggerView (viewName, options) para la biblioteca JavaScript at.js de Adobe Target.
title: 'adobe.target.triggerView (viewName, options): at.js 2.x'
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 100%

---


# adobe.target.triggerView (viewName, options): at.js 2.x

Se puede llamar a esta función cada vez que se carga una página nueva o cuando se vuelve a procesar un componente de una página. `adobe.target.triggerView()` debe implementarse para aplicaciones de una sola página (SPA) a fin de utilizar el Compositor de experiencias visuales (VEC) para crear pruebas A/B y actividades de segmentación de experiencias (XT). Si `adobe.target.triggerView()` no se implementa en el sitio, el VEC no se puede utilizar para SPA. Para obtener más información, consulte [Implementación de aplicación de una sola página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Esta función se introdujo en at.js 2.x. Esta función no está disponible para la at.js versión 1.*x*.

| Parámetro | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| Nombre de vista | Cadena | Sí | Pase cualquier nombre como tipo de cadena que desee que represente la vista. Este nombre de vista aparece en el panel [!UICONTROL Modificaciones] del VEC para que los especialistas en marketing creen acciones y ejecuten sus actividades A/B y XT. |
| opciones | Objeto | No |  |
| opciones > página | Booleano | No | **VERDADERO:** el valor predeterminado de la página es verdadero. Cuando la página es “page=true”, las notificaciones se envían al back-end [!DNL Target] para incrementar el recuento de impresiones.<br>Si no se asocia ninguna experiencia de actividad o métrica de actividad a la vista, no se envía ninguna notificación.<br>**FALSO:** Cuando la página es “page=false”, las notificaciones no se envían para incrementar el recuento de impresiones. Debe utilizarse cuando desee volver a procesar un componente en una página con una oferta. |

## Ejemplo: True

Llamada de `triggerView()` para enviar una notificación al backend de Target para aumentar las impresiones de actividad y otras métricas.

```
adobe.target.triggerView("homeView")
```

## Ejemplo: False

Llamada de `triggerView()` para no tener notificaciones enviadas al backend de Target para el recuento de impresiones.

```
adobe.target.triggerView("homeView", {page: false})
```
