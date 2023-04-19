---
keywords: mvt;prueba multivariable;informe de contribución de ubicación
description: Aprenda a utilizar el informe Contribución de ubicación para el Adobe [!DNL Target] [!UICONTROL Segmentación de experiencias] actividades que muestran el rendimiento de cada elemento y cada oferta.
title: ¿Cómo utilizo la variable [!UICONTROL Contribución de ubicación] Informe de [!UICONTROL Prueba multivariable] actividades?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 37%

---

# [!UICONTROL Informe Contribución de ubicación (MVT)]

La variable [!UICONTROL Contribución de ubicación] muestra el rendimiento de cada elemento y cada oferta.

En la parte superior del informe se muestra la métrica, las fechas de inicio y finalización y la audiencia que se han empleado para elaborar el informe. Puede cambiar cualquiera de estos factores.

>[!NOTE]
>
>Tenga en cuenta la siguiente información cuando trabaje con la variable [!UICONTROL Contribución de ubicación] informe:
>
>* Los selectores de audiencia y métrica solo están disponibles si [!DNL Analytics] se utiliza como fuente de informes (A4T).
>
>* Los datos del [!UICONTROL Contribución de ubicación] se obtiene del [!DNL Target] backend incluso si la actividad está configurada para utilizar [!UICONTROL Analytics como fuente de informes] (A4T).
>
>* Los datos del [!UICONTROL Contribución de ubicación] para el entorno &quot;Producción&quot;, aunque haya definido un entorno predeterminado distinto en la variable [!DNL Target] nivel de cuenta.


La variable [!UICONTROL Contribución de ubicación] incluye dos tablas.

La primera tabla muestra la influencia relativa de cada elemento. Esta tabla muestra cuál de los elementos donde ha agregado ofertas está resultando en la mayor cantidad de conversiones.

![Informe Contribución de ubicación en Adobe Target](/help/main/c-reports/assets/locationcontributiontop.png)

La segunda tabla proporciona un informe de nivel de oferta. Muestra la tasa de conversión, el alza y la confianza para cada oferta en cada elemento. Esta tabla le ayuda a determinar qué ofertas tienen más éxito. La segunda columna muestra los valores para la métrica seleccionada (tasa de conversión, ingresos por visitante, valor de pedido promedio, pedidos o métricas de participación) de la oferta y una estandarización.

![Informe Contribución de ubicación en Adobe Target](/help/main/c-reports/assets/locationcontributionbottom.png)

## Vídeo de formación: Crear una prueba MVT ![Distintivo del tutorial](/help/main/assets/tutorial.png)

En este vídeo se explica cómo crear una prueba multivariable siguiendo el flujo de trabajo guiado de tres pasos de Target. El informe Contribución de ubicación se describe a partir del minuto 8:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
