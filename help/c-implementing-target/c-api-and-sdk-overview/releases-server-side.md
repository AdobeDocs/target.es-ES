---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Notas de la versión relacionadas con las API de servidor de Adobe Target.
title: Notas de la versión relacionadas con las API de servidor de Adobe Target.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Notas de la versión: API de Destinatario del lado del servidor

Notas de la versión relacionadas con las API [de servidor de](https://developers.adobetarget.com/api/delivery-api/)Adobe Target.

## V1/envío (9 de octubre de 2019)

Se ha publicado un extremo de API de envío completamente nuevo.

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* Un punto final para recuperar experiencias para uno o varios mboxes.
* Recupere actividades creadas por VEC mediante la API.

   La respuesta que contiene actividades creadas por VEC tiene selectores que pueden utilizarse para ocultar previamente solo partes de la página que necesitan personalizarse. Esto ayuda a optimizar la [primera métrica](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)de pintura contextual de su página, que es un KPI importante para su empresa a fin de lograr una puntuación alta en el sistema de clasificación de páginas [de](https://en.wikipedia.org/wiki/PageRank) Google.

* Compatibilidad con un objeto completamente nuevo llamado Vistas que se utiliza para aplicaciones [de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) única (SPA) y aplicaciones [](/help/c-target-mobile-app/target-mobile-app.md)móviles.
* Compatibilidad con la recuperación previa de vistas y mboxes para optimizar el rendimiento mediante almacenamiento en caché.
* Compatibilidad con el envío de notificaciones para vistas y mboxes recuperados previamente.

>[!IMPORTANT]
>
>Aún se puede acceder a la documentación [de la API heredada](https://developers.adobetarget.com/api/legacy-api/index.html) /v1/mbox y /v2/batchmbox. Sin embargo, las nuevas funciones se desarrollarán en la nueva API de envío y no se adaptarán a las API heredadas.
