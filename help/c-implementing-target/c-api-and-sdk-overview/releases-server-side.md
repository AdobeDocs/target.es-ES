---
description: Notas de la versión relacionadas con los SDK y las API del servidor de Adobe Target
keywords: at.js;api;release;updates;apis;sdks;server side;server-side;server-side;api;delivery api
seo-description: Notas de la versión relacionadas con las API del servidor de Adobe Target.
seo-title: Notas de la versión relacionadas con las API del servidor de Adobe Target.
solution: Target
title: 'Notas de la versión: API de servidor de Target'
topic: Standard
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# Notas de la versión: API de servidor de Target

Notas de la versión relacionadas con las API del lado del [!DNL Adobe Target] servidor.

## V1/entrega (9 de octubre de 2019)

Se ha lanzado un extremo de API de entrega completamente nuevo.

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* Un punto final para recuperar experiencias para uno o varios mboxes.
* Recupere actividades creadas por VEC mediante la API.

   La respuesta que contiene actividades creadas por VEC tiene selectores que se pueden usar para ocultar previamente solo las partes de la página que necesitan personalizarse. Esto ayuda a optimizar la [primera métrica](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)de pintura contextual de su página, que es un KPI importante para su empresa a fin de lograr una puntuación alta en el sistema de clasificación de páginas [de](https://en.wikipedia.org/wiki/PageRank) Google.

* Compatibilidad con un objeto completamente nuevo llamado Vistas que se utiliza para aplicaciones [de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) única (SPA) y aplicaciones [](/help/c-target-mobile-app/target-mobile-app.md)móviles.
* Compatibilidad con la recuperación previa de vistas y mboxes para optimizar el rendimiento mediante almacenamiento en caché.
* Compatibilidad para enviar notificaciones para vistas y mboxes recuperados previamente.

>[!IMPORTANT]
>
>Aún se puede acceder a la documentación [de la API heredada](https://developers.adobetarget.com/api/legacy-api/index.html) /v1/mbox y /v2/batchmbox. Sin embargo, las nuevas funciones se desarrollarán en la nueva API de entrega y no se adaptarán a las API heredadas.
