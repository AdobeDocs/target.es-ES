---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Los usuarios de actividades de Automated Personalization en Adobe Target pueden acceder a informes especializados.
title: Informes Resumen de Personalización automatizada
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 72%

---


# ![PREMIUM](/help/assets/premium.png) Informes Resumen de personalización automatizada{#automated-personalization-summary-reports}

Los usuarios de actividades [!UICONTROL Automated Personalization] pueden obtener informes especializados en [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL La personalización automatizada] está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una licencia de [Target Premium](/help/c-intro/intro.md#premium).

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad de [!UICONTROL Personalización automatizada] que quiera de la lista y luego en la pestaña **[!UICONTROL Informes.]**

   Si tiene muchas actividades, puede filtrar la lista seleccionando [!UICONTROL Personalización automatizada] en la lista desplegable [!UICONTROL Tipo].

1. (Opcional) Haga clic en el icono [!UICONTROL Descargar] para obtener la vista de resumen (por ejemplo, para ver una comparación del tráfico de Control y el segmentado) desglosada por todas las métricas de éxito disponibles.

[!UICONTROL Personalización automatizada] ofrece los siguientes informes:

## Informe de nivel de actividad {#section_6F72FC5C790B4492B3DCECBFFA971337}

El informe [!UICONTROL Nivel de actividad] compara el rendimiento global del uso de un algoritmo de [!UICONTROL Personalización automatizada] para el contenido suministrado de manera aleatoria (control).

![Informe Nivel de actividad  ](/help/c-reports/assets/box_plot_ap.png)

Las reglas estándar de interpretación de resultados para prueba A/B aún se aplican, incluidos alza, confianza, tendencias, duración, etc. Para obtener más información sobre interpretación de resultados, consulte   [Acerca de la tasa de conversión](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Informe de nivel de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

El informe [!UICONTROL Nivel de oferta] para la experiencia de bosque aleatorio compara el rendimiento de cada oferta que tiene un algoritmo aplicado con la misma oferta suministrada de manera aleatoria (control). De esta manera, las ofertas no deberían comprarse entre sí en esta vista.

Haga clic en el algoritmo de experiencia (bosque aleatorio o control) para vista del informe [!UICONTROL Nivel de Oferta].

![](assets/ap_OfferLevelRpt.png)

Las ofertas se pueden mostrar dentro de grupos de informes, que se pueden contraer o expandir. Seleccione [!UICONTROL Grupo de informes] en la lista desplegable para ver información resumida por grupos de informes en lugar de por ofertas.

>[!NOTE]
>
>El icono de reloj indica que el modelo de algoritmo aún se está generando. El icono de marca de verificación indica que se ha establecido el algoritmo base.

## Segmentos automatizados

Haga clic en el icono [!UICONTROL Segmentos automatizados]. Este informe muestra cómo los diferentes visitantes responden de manera diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

![Icono de segmentos automatizados](/help/c-reports/assets/icon-automated-sements-ap.png)

Para obtener más información, consulte [Informe Segmentos automatizados](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Haga clic en el icono [!UICONTROL Atributos importantes]. Este informe muestra cómo, en diferentes actividades, los diferentes atributos son más (o menos) importantes para la forma en que el modelo decide personalizar. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

![Icono de atributos importantes](/help/c-reports/assets/icon-important-attributes-ap.png)

Para obtener más información, consulte [Informe de atributos importantes](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).