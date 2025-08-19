---
keywords: mvt;prueba multivariable;informe de contribución de ubicación
description: Aprenda a utilizar el informe Contribución de ubicación para actividades de Adobe [!DNL Target] [!UICONTROL Experience Targeting] que muestran el rendimiento de cada elemento y cada oferta.
title: ¿Cómo utilizo el informe [!UICONTROL Location Contribution] para actividades [!UICONTROL Multivariate Test]?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 35%

---

# Informe [!UICONTROL Location Contribution] (MVT)

El informe [!UICONTROL Location Contribution] muestra el rendimiento de cada elemento y cada oferta.

En la parte superior del informe se muestra la métrica, las fechas de inicio y finalización y la audiencia que se han empleado para elaborar el informe. Puede cambiar cualquiera de estos factores.

>[!NOTE]
>
>Tenga en cuenta la siguiente información cuando trabaje con el informe [!UICONTROL Location Contribution]:
>
>* Los selectores de audiencia y de métricas solo están disponibles si [!DNL Analytics] se usa como fuente de informes (A4T).
>
>* Los datos del informe [!UICONTROL Location Contribution] se recuperan del servidor [!DNL Target] aunque la actividad esté configurada para usar [!UICONTROL Analytics as the reporting source] (A4T).
>
>* Los datos del informe [!UICONTROL Location Contribution] se buscan para el entorno &quot;Producción&quot; incluso si se define un entorno predeterminado diferente en el nivel de cuenta [!DNL Target].

El informe [!UICONTROL Location Contribution] incluye dos tablas.

La primera tabla muestra la influencia relativa de cada elemento. En esta tabla se muestra cuál de los elementos en los que se han añadido ofertas da como resultado la mayor cantidad de conversiones.

La segunda tabla proporciona un informe de nivel de oferta. Muestra la tasa de conversión, el alza y la confianza para cada oferta en cada elemento. Esta tabla le ayuda a determinar qué ofertas son las más exitosas. La segunda columna muestra los valores para la métrica seleccionada (tasa de conversión, ingresos por visitante, valor de pedido promedio, pedidos o métricas de participación) de la oferta y una estandarización.

## Vídeo de formación: Crear una prueba MVT

En este vídeo se muestra cómo crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target]. El informe Contribución de ubicación se describe a partir del 8:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
