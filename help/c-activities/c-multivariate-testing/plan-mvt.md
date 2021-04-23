---
keywords: prueba multivariable;mvt;planificación de mvt;planificar prueba multivariable
description: Aprenda a planificar una prueba multivariable en Adobe [!DNL Target] para poder crear una prueba con éxito.
title: ¿Cómo planeo una prueba multivariable?
feature: Pruebas multivariable
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 91%

---

# Planificar una prueba multivariable

Con las [!UICONTROL pruebas multivariadas] (MVT) en [!DNL Adobe Target] se requiere cierta planificación para poder crear una prueba con resultados satisfactorios.

Las MVT deben disponer de tráfico suficiente para generar resultados útiles. Antes de configurar la prueba, debe conocer la cantidad de tráfico que normalmente recibe, incluido el número de impresiones y conversiones. Con esta información, habrá menos probabilidades de que diseñe una prueba cuyos requisitos excedan el tráfico de su sitio.

Es recomendable que los elementos sean independientes entre sí. (Por ejemplo, no realice una prueba del diseño y del contenido a la vez).

Examine el código HTML de las páginas en las que desea realizar la prueba. Asegúrese de que los elementos HTML de su sitio no tengan ID de DOM duplicados. Los ID duplicados pueden ocasionar que el mismo fragmento de contenido se publique en más de una ubicación.

Planifique la prueba de los elementos de la página que tienen probabilidad de generar resultados relevantes. Por ejemplo, un banner o una imagen a pantalla completa (hero) tienen más posibilidades de generar conversiones que un cambio en el pie de página. Si incluye elementos con menos influencia en la prueba, solo conseguirá aumentar el tráfico y el tiempo necesario para probar los elementos más destacados de la página.

Por último, antes de crear la prueba, debe crear el contenido que desea probar. Conozca las diferencias de contenido para cada oferta y cree cualquier oferta de imagen, texto y HTML que tenga pensado usar en la prueba.

## Vídeo de formación: Creación de pruebas multivariable (9:25)  ![Distintivo del tutorial](/help/assets/tutorial.png)

En este vídeo explicamos cómo planificar y crear una prueba multivariable siguiendo el flujo de trabajo guiado de tres pasos de Target.

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)
