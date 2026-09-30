---
keywords: prueba multivariable;mvt;planificación de mvt;planificar prueba multivariable
description: Aprenda a planificar una [!UICONTROL prueba multivariable] en [!DNL Adobe Target] para que pueda crear una prueba con resultados satisfactorios.
title: ¿Cómo planifico una [!UICONTROL prueba multivariable]?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
TQID: 'https://experienceleague.adobe.com/Fg9jOrPlkLxpbJdG-AKoWHD3YvIGEJPu7Os-RdfXvQA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 62%
---
# Planificar una [!UICONTROL prueba multivariable]

Las actividades de [!UICONTROL pruebas multivariable] (MVT) en [!DNL Adobe Target] requieren cierta planificación para poder crear una prueba con resultados satisfactorios.

La prueba multivariable requiere tráfico suficiente para generar resultados útiles. Antes de configurar la prueba, debe conocer la cantidad de tráfico que normalmente recibe, incluido el número de impresiones y conversiones. Tener esta información ayuda a reducir la probabilidad de diseñar una prueba con requisitos que superen el tráfico del sitio.

Los elementos deben ser independientes entre sí. Por ejemplo, no realice una prueba del diseño y del contenido a la vez.

Examine el código HTML de las páginas que desea probar. Asegúrese de que los elementos HTML de su sitio no tengan ID de DOM duplicados. Los ID duplicados pueden ocasionar que el mismo fragmento de contenido se publique en más de una ubicación.

Planifique la prueba de los elementos de la página que tienen probabilidad de generar resultados relevantes. Por ejemplo, un banner o una imagen principal tienen más posibilidades de generar conversiones que un cambio en el pie de página. Si incluye elementos con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar los elementos más destacados de la página.

Por último, antes de crear la prueba, debe crear el contenido que desea probar. Conozca las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba.

## Vídeo de formación: Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se muestra cómo planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/29713?captions=spa)
