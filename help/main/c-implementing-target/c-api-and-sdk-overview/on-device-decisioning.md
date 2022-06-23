---
keywords: servidor;sdk;sdk;sdk;en el dispositivo;toma de decisiones;en el dispositivo;en el dispositivo;latencia cero;latencia;casi cero;node.js
description: Aprenda a utilizar la toma de decisiones en el dispositivo para almacenar en caché su [!DNL Target] Actividades A/B y MVT en el servidor para realizar decisiones en memoria con latencia cercana a cero.
title: ¿Qué es la toma de decisiones en dispositivos?
feature: Implement Server-side
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 9%

---

# Toma de decisiones en el dispositivo

La toma de decisiones en el dispositivo proporciona la capacidad de almacenar en caché su [!DNL Adobe Target] [!UICONTROL Prueba A/B] y [!UICONTROL Segmentación de experiencias] (XT) en su servidor y realice la toma de decisiones en memoria con una latencia cercana a cero, sin bloquear las solicitudes de red al [!DNL Adobe Target] Red perimetral.

Para obtener más información, consulte los temas:

* [Toma de decisiones en el dispositivo para el lado del cliente](https://developer.adobe.com/target/implement/client-side/){target=_blank}
* [Toma de decisiones en el dispositivo para el lado del servidor](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank}

## Seminario web: personalice y pruebe con una latencia cero con decisiones en el dispositivo de [!DNL Adobe Target]

Más que nunca, a los especialistas en marketing, propietarios de productos y desarrolladores se les está asignando la tarea de optimizar la experiencia general del cliente en los sitios, las aplicaciones y en cualquier otro lugar donde se conecten con sus clientes. Las herramientas múltiples con silos de datos y las implementaciones complicadas son inadecuadas.

En este seminario web grabado, [!DNL Adobe Target] expertos en productos analizan cómo mover las decisiones de optimización de experiencias críticas en el dispositivo para ejecutarse localmente con latencia cercana a cero puede abrir puertas a nuevos casos de uso interesantes, al mismo tiempo que mejora el rendimiento del sitio para sus clientes.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## Prácticas recomendadas

Adobe recomienda las siguientes prácticas recomendadas al utilizar la toma de decisiones en el dispositivo:

### Prácticas recomendadas cuando el método de toma de decisiones es &quot;en el dispositivo&quot; {#best-practices-on-device}

Cuando se utiliza &quot;en el dispositivo&quot; como método de toma de decisiones, el artefacto se descarga cuando el visitante carga la página web por primera vez. Cualquier calificación de actividad que deba producirse en la primera carga de página (sin caché) solo se produce después de descargar completamente el artefacto. Existen determinadas prácticas recomendadas que puede seguir para garantizar que las cualificaciones de actividad se realicen rápidamente para un nuevo visitante anónimo.

* Desactive las actividades compatibles con &quot;dispositivos&quot; que no estén pensadas para estar en el artefacto.
* Si tiene [!DNL Target Premium], puede usar [propiedades/espacios de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) para crear diferentes archivos de artefactos para diferentes espacios de trabajo.
* Si los archivos de artefactos se vuelven muy grandes por razones legítimas, puede utilizar el método de decisión &quot;híbrido&quot;. Este método le permite descargar el artefacto en paralelo y todo [!DNL Target] Las llamadas a la API pasan por el cable hasta que se ha descargado el artefacto. Lea lo mejor [sección prácticas sobre el modo de decisión &quot;híbrido&quot;](#best-practices-hybrid) a continuación para obtener más información sobre este enfoque.
* Si tiene una aplicación de una sola página (SPA), [!DNL Adobe] recomienda cargar e inicializar at.js antes de cargar el archivo JavaScript principal de la aplicación durante la primera carga de página. Este método inicia la descarga de artefactos mucho antes, lo que permite una representación de experiencias más rápida.

### Prácticas recomendadas cuando el método de toma de decisiones es &quot;híbrido&quot; {#best-practices-hybrid}

Cuando se utiliza &quot;híbrido&quot; como método de toma de decisiones, el artefacto se descarga en paralelo. Hasta que se descargue el artefacto, cualquier [!DNL Target] Las llamadas de API pasan por alto incluso si las &quot;ubicaciones&quot; son compatibles con dispositivos. Este comportamiento es el predeterminado para todos `getOffers()` llama a y proporciona el mejor rendimiento en la mayoría de las situaciones. Si cambia el comportamiento predeterminado de `getOffers()` configurando la variable `decisioningMethod` a `on-device`, siga estas prácticas recomendadas para evitar errores y garantizar el mejor rendimiento.

* Si decide llamar a `getOffers()` con `decisioningMethod` como `on-device` cuando la página se carga por primera vez, debe hacerlo dentro del controlador de eventos at.js &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; para evitar errores. Si el artefacto es muy grande, cualquier &quot;ubicación&quot; que utilice este enfoque se procesará solo después de que el artefacto se haya descargado completamente, lo que puede retrasar el procesamiento de la experiencia. [!DNL Adobe] recomienda utilizar este método en raras ocasiones. Siga las prácticas recomendadas para reducir el tamaño de los artefactos en la sección [sección &quot;Prácticas recomendadas en el dispositivo&quot;](#best-practices-on-device) más arriba al utilizar este método.

## Tutorial: Toma de decisiones en el dispositivo

[!DNL Adobe Target] la toma de decisiones en el dispositivo habilita la entrega de contenido de latencia casi nula.

Este vídeo de 7 minutos:

* Describe la toma de decisiones en el dispositivo, incluida su comparación con otros métodos de [!DNL Target] implementación
* Muestra cómo habilitar la toma de decisiones en el dispositivo en [!DNL Target]
* Examina una actividad de compositor basada en formularios de ejemplo que se ha configurado con contenido JSON
* Muestra el código SDK de Node.JS de muestra que contiene la configuración clave necesaria para la toma de decisiones en el dispositivo.
* Muestra los resultados en un explorador

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Para obtener más vídeos y tutoriales, consulte la [Tutorials de Adobe Target](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=es) guía.

## Adobe Tech Blog - Parte 1: Ejecutar [!DNL Adobe Target] SDK de NodeJS para la experimentación y personalización en plataformas Edge (trabajadores de Akamai Edge)

[Haga clic aquí para acceder a la entrada del blog](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9).

## Adobe Tech Blog - Parte 2: Ejecución del SDK de NodeJS de [!DNL Adobe Target] para la experimentación y personalización en plataformas Edge (AWS Lambda@Edge)

[Haga clic aquí para acceder a la entrada del blog](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563).