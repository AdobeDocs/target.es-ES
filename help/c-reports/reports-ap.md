---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Hay informes especializados disponibles para los usuarios de Personalización automatizada.
title: Informes Resumen de Personalización automatizada
feature: reports
uuid: 959b6814-9686-4741-8a79-5957e64f6209
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Informes Resumen de personalización automatizada{#automated-personalization-summary-reports}

Hay informes especializados disponibles para los usuarios de Personalización automatizada.

>[!NOTE]
>
>La personalización automatizada está disponible como parte de la solución [!DNL Target Premium]. No se incluye con [!DNL Target Standard] sin una licencia de [Target Premium](/help/c-intro/intro.md#premium).

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad de [!UICONTROL Personalización automatizada] que quiera de la lista y luego en la pestaña **[!UICONTROL Informes.]**

   Si tiene muchas actividades, puede filtrar la lista seleccionando [!UICONTROL Personalización automatizada] en la lista desplegable [!UICONTROL Tipo].

1. (Opcional) Haga clic en el icono [!UICONTROL Descargar] para obtener la vista de resumen (por ejemplo, para ver una comparación del tráfico de Control y el segmentado) desglosada por todas las métricas de éxito disponibles.

[!UICONTROL Personalización automatizada] ofrece los siguientes informes:

## Informe de nivel de actividad {#section_6F72FC5C790B4492B3DCECBFFA971337}

El informe [!UICONTROL Nivel de actividad] compara el rendimiento global del uso de un algoritmo de [!UICONTROL Personalización automatizada] para el contenido suministrado de manera aleatoria (control).

![Informe Nivel de actividad  ](/help/c-reports/assets/box_plot_ap.png)

Las reglas estándar de interpretación de resultados para prueba A/B aún se aplican, incluidos alza, confianza, tendencias, duración, etc. Para obtener más información sobre interpretación de resultados, consulte   [Acerca de la tasa de conversión](../c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Informe de nivel de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

El informe [!UICONTROL Nivel de oferta] para la experiencia de bosque aleatorio compara el rendimiento de cada oferta que tiene un algoritmo aplicado con la misma oferta suministrada de manera aleatoria (control). De esta manera, las ofertas no deberían comprarse entre sí en esta vista.

Haga clic en el algoritmo de la experiencia (bosque aleatorio o control) para ver el informe de nivel de oferta.

![](assets/ap_OfferLevelRpt.png)

Las ofertas se pueden mostrar dentro de grupos de informes, que se pueden contraer o expandir. Seleccione [!UICONTROL Grupo de informes] en la lista desplegable para ver información resumida por grupos de informes en lugar de por ofertas.

>[!NOTE]
>
>El icono de reloj indica que el modelo de algoritmo aún se está generando. El icono de marca de verificación indica que se ha establecido el algoritmo base.
