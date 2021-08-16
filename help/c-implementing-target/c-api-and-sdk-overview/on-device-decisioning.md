---
keywords: servidor;sdk;sdk;sdk;en el dispositivo;toma de decisiones;en el dispositivo;en el dispositivo;latencia cero;latencia;casi cero;node.js
description: Aprenda a utilizar la toma de decisiones en el dispositivo para almacenar en caché las actividades  [!DNL Target] A/B y MVT en el servidor para realizar la toma de decisiones en la memoria con una latencia cercana a cero.
title: ¿Qué es la toma de decisiones en dispositivos?
feature: Implementación del lado del servidor
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 10%

---

# Toma de decisiones en el dispositivo

La toma de decisiones en dispositivos permite almacenar en caché sus actividades [!DNL Adobe Target] [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) en el servidor y realizar decisiones en memoria con una latencia cercana a cero, sin bloquear las solicitudes de red a la [!DNL Adobe Target] Red perimetral.

Para obtener más información, consulte [Introducción a la toma de decisiones en el dispositivo](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) en la *[documentación de los SDK para Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)*.

## Seminario web: Personalice y pruebe con una latencia cero con decisiones en el dispositivo de [!DNL Adobe Target]

Más que nunca, a los especialistas en marketing, propietarios de productos y desarrolladores se les está asignando la tarea de optimizar la experiencia general del cliente en los sitios, las aplicaciones y en cualquier otro lugar donde se conecten con sus clientes. Las herramientas múltiples con silos de datos y las implementaciones complicadas son inadecuadas.

En este seminario web grabado, los expertos en productos [!DNL Adobe Target] analizan cómo mover las decisiones de optimización de experiencias críticas en el dispositivo para ejecutarse localmente con latencia cercana a cero puede abrir las puertas a nuevos casos de uso interesantes, a la vez que mejoran el rendimiento del sitio para sus clientes.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## Prácticas recomendadas

Adobe recomienda las siguientes prácticas recomendadas al utilizar la toma de decisiones en el dispositivo:

### Prácticas recomendadas cuando el método de toma de decisiones es &quot;en el dispositivo&quot; {#best-practices-on-device}

Cuando se utiliza &quot;en el dispositivo&quot; como método de toma de decisiones, el artefacto se descarga cuando el visitante carga la página web por primera vez. Cualquier calificación de actividad que deba producirse en la primera carga de página (sin caché) solo se produce después de descargar completamente el artefacto. Existen determinadas prácticas recomendadas que puede seguir para garantizar que las cualificaciones de actividad se realicen rápidamente para un nuevo visitante anónimo.

* Desactive las actividades compatibles con &quot;dispositivos&quot; que no estén pensadas para estar en el artefacto.
* Si tiene [!DNL Target Premium], puede utilizar [propiedades/espacios de trabajo](/help/administrating-target/c-user-management/property-channel/property-channel.md) para crear diferentes archivos de artefactos para diferentes espacios de trabajo.
* Si los archivos de artefactos se vuelven muy grandes por razones legítimas, puede utilizar el método de decisión &quot;híbrido&quot;. Este método le permite descargar el artefacto en paralelo y todas las llamadas a la API [!DNL Target] pasan por el cable hasta que el artefacto se ha descargado. Lea las mejores [prácticas en el modo de decisión &quot;híbrido&quot;](#best-practices-hybrid) a continuación para obtener más información sobre este enfoque.
* Si tiene una aplicación de una sola página (SPA), [!DNL Adobe] recomienda cargar e inicializar at.js antes de cargar el archivo JavaScript principal de la aplicación durante la primera carga de página. Este método inicia la descarga de artefactos mucho antes, lo que permite una representación de experiencias más rápida.

### Prácticas recomendadas cuando el método de toma de decisiones es &quot;híbrido&quot; {#best-practices-hybrid}

Cuando se utiliza &quot;híbrido&quot; como método de toma de decisiones, el artefacto se descarga en paralelo. Hasta que se descargue el artefacto, cualquier llamada de API [!DNL Target] pasa por el cable incluso si las &quot;ubicaciones&quot; son compatibles con el dispositivo. Este comportamiento es el predeterminado para todas las llamadas `getOffers()` y proporciona el mejor rendimiento en la mayoría de las situaciones. Si cambia el comportamiento predeterminado de `getOffers()` estableciendo `decisioningMethod` en `on-device`, siga estas prácticas recomendadas para evitar errores y garantizar el mejor rendimiento.

* Si decide llamar a `getOffers()` con `decisioningMethod` como `on-device` cuando la página se cargue por primera vez, debe hacerlo dentro del controlador de eventos at.js &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; para evitar errores. Si el artefacto es muy grande, cualquier &quot;ubicación&quot; que utilice este enfoque se procesará solo después de que el artefacto se haya descargado completamente, lo que puede retrasar el procesamiento de la experiencia. [!DNL Adobe] recomienda utilizar este método en raras ocasiones. Siga las prácticas recomendadas para reducir el tamaño de los artefactos en la sección [&quot;Prácticas recomendadas en el dispositivo&quot;](#best-practices-on-device) anterior al utilizar este método.

## Tutorial: Toma de decisiones en el dispositivo

[!DNL Adobe Target] la toma de decisiones en el dispositivo habilita la entrega de contenido de latencia casi nula.

Este vídeo de 7 minutos:

* Describe la toma de decisiones en el dispositivo, incluida su comparación con otros métodos de implementación de [!DNL Target]
* Muestra cómo habilitar la toma de decisiones en el dispositivo en [!DNL Target]
* Examina una actividad de compositor basada en formularios de ejemplo que se ha configurado con contenido JSON
* Muestra el código SDK de Node.JS de muestra que contiene la configuración clave necesaria para la toma de decisiones en el dispositivo.
* Muestra los resultados en un explorador

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Para obtener más vídeos y tutoriales, consulte la guía [Tutorials de Adobe Target](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=es).

## Adobe Tech Blog - Parte 1: Ejecute [!DNL Adobe Target] SDK de NodeJS para la experimentación y personalización en plataformas Edge (trabajadores de Akamai Edge)

[Haga clic aquí para acceder al post](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9) del blog.

## Adobe Tech Blog - Parte 2: Ejecución del SDK de NodeJS de [!DNL Adobe Target] para la experimentación y personalización en plataformas Edge (AWS Lambda@Edge)

[Haga clic aquí para acceder al post](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563) del blog.