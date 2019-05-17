---
description: 'Información sobre la función adobe. target. triggerview (viewname, options) para at. js. '
keywords: adobe.target.notification;elemento;selector;notificación;extensión
seo-description: Información sobre la función adobe. target. triggerview (viewname, options) para la biblioteca JavaScript de Adobe Target at. js.
seo-title: Información sobre la función adobe. target. triggerview (viewname, options) para la biblioteca JavaScript de Adobe Target at. js.
solution: Target
subtopic: Primeros pasos
title: adobe.target.triggerview (viewname, options)
topic: Standard
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe. target. triggerview (viewname, options) - at. js 2. x

Se puede llamar a esta función cada vez que se carga una página nueva o cuando se vuelve a procesar un componente de una página. `adobe.target.triggerView()` debe implementarse para aplicaciones de una sola página (SPA) a fin de utilizar el Compositor de experiencias visuales (VEC) para crear pruebas A/B y actividades de segmentación de experiencias (XT). Si `adobe.target.triggerView()` no se implementa en el sitio, el VEC no se puede utilizar para SPA. Para obtener más información, consulte [Implementación de aplicación de una sola página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Esta función se introdujo en at. js 2. x. Esta función no está disponible para la versión 1 de at. js.*x*.

| Parámetro | Tipo | ¿Requerido? | Descripción |
| --- | --- | --- | --- |
| Nombre de vista | Cadena | Sí | Pase cualquier nombre como tipo de cadena que desee que represente la vista. Este nombre de vista aparece en el panel [!UICONTROL Modificaciones] del VEC para que los especialistas en marketing creen acciones y ejecuten sus actividades A/B y XT. |
| opciones | Objeto | No |
| opciones &gt; página | Booleano | No | **VERDADERO:** el valor predeterminado de la página es verdadero. Cuando la página es “page=true”, las notificaciones se envían al back-end [!DNL Target] para incrementar el recuento de impresiones.<br>**FALSO:** Cuando página = false, las notificaciones no se envían para incrementar el recuento de impresiones. Debe utilizarse cuando desee volver a procesar un componente en una página con una oferta. |

## Llamada de ejemplo `triggerView()` que envía una notificación al back-end de Target para incrementar el recuento de impresiones.

```
adobe.target.triggerView("homeView")
```

## Llamada de ejemplo `triggerView()` para no tener notificaciones enviadas al back-end de Target para el recuento de impresiones.

```
adobe.target.triggerView("homeView", {page: false})
```
