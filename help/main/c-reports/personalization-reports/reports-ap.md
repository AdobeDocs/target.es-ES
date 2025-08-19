---
keywords: Segmentación;informes AP;informes de personalización automatizada;informe de nivel de actividad;informe de nivel de oferta;informe de detalle de oferta;faq
description: Obtenga información sobre cómo interpretar el informe Resumen de Automated Personalization en Adobe Target. Puede cambiar a los informes Segmentos automatizados y Atributos importantes desde este informe.
title: ¿Cómo utilizo los informes de resumen de Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 11%

---

# Informes resumen de Automated Personalization

Hay informes de resumen especializados disponibles para los usuarios de [!UICONTROL Automated Personalization] actividades en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).

1. Haga clic en **[!UICONTROL Activities]**, en la actividad [!UICONTROL Automated Personalization] que quiera de la lista y luego en la ficha **[!UICONTROL Reports]**.

   Si tiene muchas actividades, haga clic en el icono Filtro ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] y [!UICONTROL Activity Source].

1. (Opcional) Haga clic en el icono **[!UICONTROL Download]** ( ![Icono de descarga](/help/main/assets/icons/Download.svg) ) para descargar la vista de resumen (por ejemplo, comparando el tráfico de control y segmentado) desglosada por todas las métricas de éxito disponibles.

[!UICONTROL Automated Personalization] proporciona los siguientes informes:

* Nivel de actividad
* Nivel de oferta
* Segmentos automatizados
* Atributos importantes

## Informe de nivel de actividad {#section_6F72FC5C790B4492B3DCECBFFA971337}

El informe [!UICONTROL Activity Level] compara el rendimiento agregado del uso de un algoritmo [!UICONTROL Automated Personalization] con el contenido proporcionado aleatoriamente (control).

Las reglas estándar de interpretación de resultados para prueba A/B aún se aplican, incluidos alza, confianza, tendencias, duración, etc. Para obtener más información acerca de la interpretación de los resultados, vea [Cálculos estadísticos en pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Informe de nivel de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

El informe [!UICONTROL Offer Level] de la experiencia de bosque aleatorio compara el rendimiento de cada oferta aplicada mediante algoritmos con la misma oferta servida aleatoriamente (Control). Por lo tanto, las ofertas no deben compararse entre sí en esta vista.

Haga clic en el algoritmo de experiencia (bosque aleatorio o control) para ver el informe [!UICONTROL Offer Level].

>[!NOTE]
>
>Un icono de reloj indica que el modelo de algoritmo aún se está generando. Un icono de marca de verificación indica que se ha establecido el algoritmo base.

Las ofertas se pueden mostrar en [grupos de informes](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md), y estos grupos de informes se pueden contraer y expandir. Haga clic en **[!UICONTROL Control]** o **[!UICONTROL Targeted]** en la tabla para ver información resumida por grupos de informes, no por ofertas.

## Segmentos automatizados

Haga clic en el icono [!UICONTROL Automated Segments]. Este informe muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

Para obtener más información, consulte [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Haga clic en el icono [!UICONTROL Important Attributes]. Este informe muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

Para obtener más información, consulte [Informe sobre atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Preguntas frecuentes

### ¿Por qué hay diferencias en los datos entre los informes Nivel de actividad y Nivel de oferta?

**[!UICONTROL Activity Level]informe**: Las visitas registradas en el informe [!UICONTROL Activity Level] capturan el número de visitas a las experiencias de control en comparación con el tráfico &quot;segmentado&quot;. El tráfico segmentado incluye una combinación de tráfico de exploración y tráfico personalizado.

**Informe de nivel de oferta**: Las impresiones registradas en el informe [!UICONTROL Offer Level] capturan el número de impresiones de cada oferta. Por lo tanto, en una actividad con más de una ubicación, el número total de visitas registradas en el informe [!UICONTROL Offer Level] en todos los grupos de informes es igual al múltiplo del número de visitas registradas para tráfico de control o segmentado en el informe [!UICONTROL Activity Level] multiplicado por el número total de ubicaciones en la actividad. Las impresiones de contenido predeterminado que se producen en ubicaciones donde el contenido predeterminado era una opción disponible se registran en el grupo de ofertas &quot;Contenido predeterminado&quot;. Las impresiones de ofertas que no se han asignado a un grupo de informes se registran en el grupo de ofertas &quot;Desagrupadas&quot;.

>[!NOTE]
>
>Es posible que el número de impresiones registradas en el informe [!UICONTROL Offer Level] no sea un múltiplo entero exacto del número de visitas registradas en el informe [!UICONTROL Activity Level]. Esto se debe a discrepancias de poca envergadura que se producen en la captura del tráfico de datos de informes a través de Internet (la tasa de discrepancia típica es inferior al 5 %). Por lo tanto, el número de impresiones no será un múltiplo exacto cuando el número de ubicaciones disponibles en la actividad cambie después de activarse la actividad.
