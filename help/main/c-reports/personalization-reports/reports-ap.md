---
keywords: Segmentación;informes AP;informes de personalización automatizada;informe de nivel de actividad;informe de nivel de oferta;informe de detalle de oferta;faq
description: Obtenga información sobre cómo interpretar el informe Resumen de Automated Personalization en Adobe Target. Puede cambiar a los informes Segmentos automatizados y Atributos importantes desde este informe.
title: ¿Cómo utilizo los informes de resumen de Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
TQID: https://experienceleague.adobe.com/Gj9Jo0NHnSxGE4BpvFbd0SudYjbkP4yrV3GFHWHNPjw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 702
ht-degree: 21%

---

# Informes resumen de Automated Personalization

Hay informes de resumen especializados disponibles para los usuarios de [!UICONTROL Automated Personalization] actividades en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una [licencia de Target Premium](/help/main/c-intro/intro.md#premium).

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad de [!UICONTROL Personalización automatizada] que quiera de la lista y luego en la pestaña **[!UICONTROL Informes]**.

   Si tiene muchas actividades, haga clic en el icono Filtro (![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Source de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas] y [!UICONTROL Source de actividades].

1. (Opcional) Haga clic en el icono **[!UICONTROL Descargar]** (![Icono de descarga](/help/main/assets/icons/Download.svg) ) para descargar la vista de resumen (por ejemplo, comparando el tráfico de control y el tráfico de destino) desglosada por todas las métricas de éxito disponibles.

[!UICONTROL Personalización automatizada] ofrece los siguientes informes:

* Nivel de actividad
* Nivel de oferta
* Segmentos automatizados
* Atributos importantes

## Informe de nivel de actividad {#section_6F72FC5C790B4492B3DCECBFFA971337}

El informe [!UICONTROL Nivel de actividad] compara el rendimiento global del uso de un algoritmo de [!UICONTROL Personalización automatizada] para el contenido suministrado de manera aleatoria (control).

Las reglas estándar de interpretación de resultados para prueba A/B aún se aplican, incluidos alza, confianza, tendencias, duración, etc. Para obtener más información acerca de la interpretación de los resultados, vea [Cálculos estadísticos en pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Informe de nivel de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

El informe [!UICONTROL Nivel de oferta] para la experiencia de bosque aleatorio compara el rendimiento de cada oferta que tiene un algoritmo aplicado con la misma oferta suministrada de manera aleatoria (control). De esta manera, las ofertas no deberían comprarse entre sí en esta vista.

Haga clic en el algoritmo de experiencia (bosque aleatorio o control) para ver el informe [!UICONTROL Nivel de oferta].

>[!NOTE]
>
>Un icono de reloj indica que el modelo de algoritmo aún se está generando. Un icono de marca de verificación indica que se ha establecido el algoritmo base.

Las ofertas se pueden mostrar en [grupos de informes](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md), y estos grupos de informes se pueden contraer y expandir. Haga clic en **[!UICONTROL Control]** o **[!UICONTROL Objetivos]** en la tabla para ver información resumida por grupos de informes, en lugar de por ofertas.

## Segmentos automatizados

Haga clic en el icono [!UICONTROL Segmentos automatizados]. Este informe muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

Para obtener más información, consulte [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Haga clic en el icono [!UICONTROL Atributos importantes]. Este informe muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

Para obtener más información, consulte [Informe sobre atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Preguntas frecuentes

### ¿Por qué hay diferencias en los datos entre los informes Nivel de actividad y Nivel de oferta?

**[!UICONTROL Informe de nivel de actividad]**: Las visitas registradas en el informe de nivel de actividad [!UICONTROL 4&rbrace; capturan el número de visitas a las experiencias de control en comparación con el tráfico &quot;segmentado&quot;. &#x200B;]El tráfico segmentado incluye una combinación de tráfico de exploración y tráfico personalizado.

**Informe de nivel de oferta**: Las impresiones registradas en el informe [!UICONTROL Nivel de oferta] capturan el número de impresiones de cada oferta. Por lo tanto, en una actividad con más de una ubicación, el número total de visitas registradas en el informe [!UICONTROL Nivel de oferta] en todos los grupos de informes es igual al múltiplo del número de visitas registradas para tráfico de control o segmentado en el informe [!UICONTROL Nivel de actividad] multiplicado por el número total de ubicaciones en la actividad. Las impresiones de contenido predeterminado que se producen en ubicaciones donde el contenido predeterminado era una opción disponible se registran en el grupo de ofertas &quot;Contenido predeterminado&quot;. Las impresiones de ofertas que no se han asignado a un grupo de informes se registran en el grupo de ofertas &quot;Desagrupadas&quot;.

>[!NOTE]
>
>El número de impresiones registradas en el informe [!UICONTROL Nivel de oferta] podría no ser un múltiplo entero exacto del número de visitas registradas en el informe [!UICONTROL Nivel de actividad]. Esto se debe a discrepancias de poca envergadura que se producen en la captura del tráfico de datos de informes a través de Internet (la tasa de discrepancia típica es inferior al 5 %). Por lo tanto, el número de impresiones no será un múltiplo exacto cuando el número de ubicaciones disponibles en la actividad cambie después de activarse la actividad.
