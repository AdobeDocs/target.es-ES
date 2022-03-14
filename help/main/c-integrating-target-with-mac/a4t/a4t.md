---
keywords: a4t;analytics;analytics para target;fuente de informes de analytics;adobe analytics como fuente de informes para target;atjs;at.js;sdk web de adobe experience platform;sdk web de platform;sdk de plataforma
description: Uso [!DNL Analytics] para [!DNL Target] (A4T) para crear actividades basadas en [!DNL Analytics] métricas de conversión y segmentos de audiencia y usar [!DNL Analytics] informes para examinar los resultados.
title: ¿Qué es [!DNL Analytics] para [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 32%

---

# [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que le permite crear actividades basadas en [!DNL Analytics] métricas de conversión y segmentos de audiencia. La integración de A4T le permite utilizar [!DNL Analytics] para examinar los resultados. Si usa [!DNL Analytics] como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basan en [!DNL Analytics] recopilación de datos.

## Información general {#section_92B66069210C40DBA937790E8CC596CF}

La variable [!DNL Analytics for Target] integración entre [!DNL Analytics] y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Los tres beneficios principales de utilizar [!DNL Analytics] datos en [!DNL Target] son:

* Los especialistas en marketing pueden aplicar dinámicamente [!DNL Analytics] métricas de éxito o informes de segmentos a [!DNL Target] informes de actividad en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Disponer de una única fuente de datos elimina la variación derivada de la recopilación de datos de dos sistemas distintos.
* Su [!DNL Analytics] la implementación recopila todos los datos necesarios. No es necesario implementar mboxes en páginas con el único objetivo de recopilar datos para informes.

Si usa [!DNL Analytics] como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basan en [!DNL Analytics].

Todo [!DNL Analytics] las métricas, incluidas las calculadas, están disponibles en [!DNL Target] y [!UICONTROL Actividades de Target] informe en [!DNL Analytics], con una excepción. Las métricas calculadas para [!UICONTROL Alza y confianza] no son compatibles. Del mismo modo, cualquier segmento disponible en [!DNL Analytics] se puede aplicar a ambas soluciones. Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de que se haya iniciado la actividad, o incluso después de que se haya completado la actividad.

Se incluyen todas las métricas, incluidas las métricas personalizadas o calculadas que estén integradas [!DNL Analytics].

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Tenga en cuenta los siguientes puntos cuando vaya a utilizar A4T:

* Para usar [!DNL Analytics] como fuente de informes para [!DNL Target], tanto usted como su empresa deben tener acceso a [!DNL Analytics] y [!DNL Target]. [Póngase en contacto con su representante de cuentas](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si necesita alguna de estas soluciones.
* La fuente de informes se establece por actividad. [!DNL Target][!DNL Target] continuará recopilando datos para usarlos en los informes y los datos de seguirán estando disponibles (si prefiere que las actividades se basen en datos recopilados por [!DNL Target].
* Utilice una fuente de informes o la otra. No puede recopilar datos de una única actividad desde ambas fuentes.
* Al utilizar A4T, todas las métricas de éxito disponibles para sus actividades son [!DNL Analytics] métricas. Sin embargo, la métrica de objetivos puede basarse en una llamada de mbox si se usa at.js. Por ejemplo, puede utilizar las capacidades de rastreo de clics integradas de Target con A4T en lugar de tener que implementar [!DNL Analytics] código de seguimiento de clics.
* Al ver los informes de una actividad de A4T en la variable [!DNL Target] IU, está viendo [!DNL Analytics] datos. Por ejemplo, si utiliza la variable [!UICONTROL Visitante] métrica en [!DNL Target], está utilizando la variable [!DNL Analytics] [!UICONTROL Visitante] métrica, no la variable [!DNL Target] [!UICONTROL Visitantes] métrica, que ahora se denomina [!UICONTROL Participantes]. Esta diferencia es especialmente importante para las métricas de tráfico básicas ([!UICONTROL Visitantes], [!UICONTROL Visitas], [!UICONTROL Vistas de páginas]) y métricas de conversión.
* Cualquier [!DNL Target] las actividades siguen utilizando [!DNL Target] la recopilación de datos y no se ven afectadas por la activación de A4T.
* Solo se permite una métrica basada en mbox al utilizar A4T.
* Una llamada de servidor a servidor desde [!DNL Target] a [!DNL Analytics] envía información de actividad y experiencia a [!DNL Analytics]. Esta integración no genera llamadas adicionales al servidor para [!DNL Target] o [!DNL Analytics].

   En algunas situaciones, las clasificaciones de [!DNL Target] a [!DNL Analytics] falla y las actividades no muestran datos en [!DNL Analytics]. Consulte [Resolución de problemas de integración de Analytics y Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). También puede [póngase en contacto con Client Care](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obtener más ayuda.

## Implementación de A4T

Para obtener información sobre la implementación de A4T con at.js y la variable [!DNL Adobe Experience Platform Web SDK], consulte [Analytics para [!DNL Target] implementación](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Tipos de actividades compatibles {#section_F487896214BF4803AF78C552EF1669AA}

Las secciones siguientes contienen información sobre tipos de actividades compatibles al usar la variable [!DNL Adobe Experience Platform Web SDK] o at.js:

| Tipos de actividad | Compatible con A4T | Notas, si corresponde |
|--- |--- |--- |
| [Actividad A/B con división de tráfico manual](/help/main/c-activities/t-test-ab/test-ab.md) | Sí |  |
| [Actividad A/B con asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sí | Consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [Actividad A/B con segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Sí | Consulte [Compatibilidad de A4T con actividades de asignación automática y segmentación automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Segmentación de experiencias (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sí |  |
| [Prueba multivariable (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sí | Requiere una métrica de objetivos basada en mbox para obtener la variable [!UICONTROL Contribución de elementos] informe. La variable [!UICONTROL Contribución de elementos] informe no es compatible actualmente [!DNL Analytics] métricas. |
| [Actividad de personalización automatizada (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | No |  |
| [Actividad de Recommendations](/help/main/c-recommendations/recommendations.md) | Sí |  |
| [Cualquier actividad que utilice una oferta de redireccionamiento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Sí |

Como todos los tipos de actividades aún no son compatibles con A4T, se recomienda mantener o implementar mboxes de conversión importantes, como el `orderConfirmPage` mbox.

## Ejemplos de informes de A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para ver los informes de A4T en [!DNL Target], haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad que desee en la lista que use [!DNL Analytics] como fuente de informes, haga clic en el botón **[!UICONTROL Informes]** pestaña .

>[!NOTE]
>
>Puede usar la variable [!UICONTROL Fuente de informes] lista desplegable en la parte superior del [!UICONTROL Actividades] para mostrar solo las actividades que utilizan A4T.

Puede alternar entre los [!UICONTROL Vista de tabla] y [!UICONTROL Visualización de gráfico] del informe haciendo clic en el icono correspondiente en la parte superior derecha del informe.

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Métrica de informes] muestra las métricas de objetivo de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph1.png)

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Audiencia] muestra las audiencias de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph2.png)

En la ilustración siguiente, se muestra la [!UICONTROL Visualización de tabla] de un informe de A4T:

![](assets/a4t_report_table.png)

Para ver el informe en [!DNL Analytics] en lugar de en [!DNL Target], haga clic en **[!UICONTROL Ver en Analytics]** en la parte superior del informe.

## Tutorial Analytics &amp; Target: Best Practices for Analysis (en inglés) {#section_3438E6E77A464424B717A4FD333B84B2}

Abra el [Analytics y Target: Prácticas recomendadas para el análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, proporcionado por [!DNL Adobe Experience League].

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos abordados en este tema.

### Analytics for Adobe Target (A4T) (4:32) ![Distintivo Información general](/help/main/assets/overview.png)

En este vídeo se explica cómo utilizar [!DNL Analytics] como fuente de informes en [!DNL Target] para dirigir el análisis de su programa de optimización.

* Explicar qué es A4T y por qué debería utilizarlo
* Explicar cómo funciona A4T
* Entender los requisitos necesarios antes de utilizar A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Integración Analytics/Adobe Target (A4T) (40:33) ![Distintivo del tutorial](/help/main/assets/tutorial.png)

Este vídeo es una grabación de “[Horario de oficina](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo configurar y validar que la integración está funcionando
* Cómo funciona la integración
* Obtenga información sobre los informes ideales para su uso en Analytics
* Respuestas a preguntas más frecuentes sobre A4T

[Integración de Analytics/Target (A4T) Horario de oficina](https://helpx.adobe.com/es/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics para [!DNL Target] implementación](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md): Contiene información de implementación para at.js y el SDK web de plataforma.
>* [Ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [¿Qué es el SDK web de Adobe Experience Platform?](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html): Contiene información general sobre el SDK web de Platform.
>* [Información general de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html): Contiene información específica de [!DNL Target] y [!DNL Platform Web SDK].

