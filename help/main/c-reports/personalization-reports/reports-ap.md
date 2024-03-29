---
keywords: Segmentación;informes AP;informes de personalización automatizada;informe de nivel de actividad;informe de nivel de oferta;informe de detalle de oferta;faq
description: Obtenga información sobre cómo interpretar el informe Resumen de Automated Personalization en Adobe Target. Puede cambiar a los informes Segmentos automatizados y Atributos importantes desde este informe.
title: ¿Cómo utilizo los informes de resumen de Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 33%

---

# Informes resumen de Automated Personalization

Hay informes de resumen especializados disponibles para los usuarios de [!UICONTROL Automated Personalization] actividades en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL La personalización automatizada] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una licencia de [Target Premium](/help/main/c-intro/intro.md#premium).

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad de [!UICONTROL Personalización automatizada] que quiera de la lista y luego en la pestaña **[!UICONTROL Informes.]**

   Si tiene muchas actividades, puede filtrar la lista seleccionando [!UICONTROL Personalización automatizada] en la lista desplegable [!UICONTROL Tipo].

1. (Opcional) Haga clic en el icono **[!UICONTROL Descargar]** para obtener la vista de resumen (por ejemplo, para ver una comparación del tráfico de Control y el segmentado) desglosada por todas las métricas de éxito disponibles.

[!UICONTROL Personalización automatizada] ofrece los siguientes informes:

* Nivel de actividad
* Nivel de oferta
* Segmentos automatizados
* Atributos importantes

## Informe de nivel de actividad {#section_6F72FC5C790B4492B3DCECBFFA971337}

El informe [!UICONTROL Nivel de actividad] compara el rendimiento global del uso de un algoritmo de [!UICONTROL Personalización automatizada] para el contenido suministrado de manera aleatoria (control).

![Informe Nivel de actividad  ](/help/main/c-reports/assets/box_plot_ap.png)

Las reglas estándar de interpretación de resultados para prueba A/B aún se aplican, incluidos alza, confianza, tendencias, duración, etc. Para obtener más información sobre interpretación de resultados, consulte   [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Informe de nivel de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

El informe [!UICONTROL Nivel de oferta] para la experiencia de bosque aleatorio compara el rendimiento de cada oferta que tiene un algoritmo aplicado con la misma oferta suministrada de manera aleatoria (control). De esta manera, las ofertas no deberían comprarse entre sí en esta vista.

Haga clic en el algoritmo de experiencia (bosque aleatorio o control) para ver la variable [!UICONTROL Nivel de oferta] informe.

![Informe Nivel de oferta en Adobe Target](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>Un icono de reloj indica que el modelo de algoritmo aún se está generando. Un icono de marca de verificación indica que se ha establecido el algoritmo base.

Las ofertas se pueden mostrar dentro de [grupos de informes](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md), y estos grupos de informes se pueden contraer y expandir. Clic **[!UICONTROL Control]** o **[!UICONTROL Objetivos]** en la tabla para ver información resumida por grupos de informes, en lugar de por ofertas.

## Segmentos automatizados

Haga clic en [!UICONTROL Segmentos automatizados] icono. Este informe muestra cómo los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

![Icono Segmentos automatizados](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Para obtener más información, consulte [Informe Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Haga clic en [!UICONTROL Atributos importantes] icono. Este informe muestra cómo, en diferentes actividades, distintos atributos son más (o menos) importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

![Icono Atributos importantes](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Para obtener más información, consulte [Informe Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Preguntas frecuentes

### ¿Por qué hay diferencias en los datos entre los informes Nivel de actividad y Nivel de oferta?

**[!UICONTROL Nivel de actividad] informe**: Visitas registradas en [!UICONTROL Nivel de actividad] Los informes de capturan el número de visitas a las experiencias de control en comparación con el tráfico &quot;segmentado&quot;. El tráfico segmentado incluye una combinación de tráfico de exploración y tráfico personalizado.

**Informe Nivel de oferta**: Impresiones registradas en [!UICONTROL Nivel de oferta] informe captura el número de impresiones de cada oferta. Por lo tanto, en una actividad con más de una ubicación, el número total de visitas registradas en la variable [!UICONTROL Nivel de oferta] en todos los grupos de informes es igual al múltiplo del número de visitas registrado para tráfico de control o segmentado en el [!UICONTROL Nivel de actividad] El informe multiplica el número total de ubicaciones en la actividad. Las impresiones de contenido predeterminado que se producen en ubicaciones donde el contenido predeterminado era una opción disponible se registran en el grupo de ofertas &quot;Contenido predeterminado&quot;. Las impresiones de ofertas que no se han asignado a un grupo de informes se registran en el grupo de ofertas &quot;Desagrupadas&quot;.

>[!NOTE]
>
>El número de impresiones registradas en el [!UICONTROL Nivel de oferta] es posible que el informe no sea un múltiplo entero exacto del número de visitas registradas en la [!UICONTROL Nivel de actividad] informe. Esto se debe a discrepancias de poca envergadura que se producen en la captura del tráfico de datos de informes a través de Internet (la tasa de discrepancia típica es inferior al 5 %). Por lo tanto, el número de impresiones no será un múltiplo exacto cuando el número de ubicaciones disponibles en la actividad cambie después de activarse la actividad.
