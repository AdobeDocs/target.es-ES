---
keywords: A4T;Analytics;Analytics para Target;fuente de informes de Analytics;Adobe Analytics;fuente de informes para Target
description: Adobe “Analytics for Target” (A4T) es una integración de soluciones cruzadas que le permite crear actividades basadas en las métricas de conversión y los segmentos de audiencia de Analytics. Esta integración le permite utilizar informes de Analytics para examinar sus resultados. Si usa Analytics como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basarán en la recopilación de datos de Analytics.
title: Adobe Analytics como fuente de informes para Adobe Target (A4T)
subtopic: Integración
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Adobe Analytics como fuente de informes para Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

Adobe “Analytics for Target” (A4T) es una integración de soluciones cruzadas que le permite crear actividades basadas en las métricas de conversión y los segmentos de audiencia de Analytics. Esta integración de A4T le permite utilizar informes de Analytics para examinar sus resultados. Si usa Analytics como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basarán en la recopilación de datos de Analytics.

## Información general de A4T {#section_92B66069210C40DBA937790E8CC596CF}

La integración de Analytics for Target entre Analytics y Target proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Estos son los tres beneficios principales de utilizar los datos de Analytics en Target:

* Los especialistas en marketing pueden aplicar de forma dinámica métricas de éxito o segmentos de informes de Analytics a los informes de actividad de Target en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Disponer de una única fuente de datos elimina la variación derivada de la recopilación de datos de dos sistemas distintos.
* La implementación de Adobe Analytics existente recopila todos los datos necesarios. No es necesario implementar mboxes en páginas con el único objetivo de recopilar datos para informes. No obstante, sigue siendo recomendable implementar un mbox de confirmación de pedido para las actividades de Personalización automatizada (AP).

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Rellene [este formulario](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.
>
>La integración que permite el uso de Adobe Analytics como la fuente de datos para Adobe Target (A4T) representa la siguiente generación del complemento para integrar Test&amp;Target con SiteCatalyst. Este complemento se considera obsoleto, pero aún se ofrece asistencia técnica para aquellos clientes que todavía lo usan.

Si usa Analytics como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basarán en Analytics.

Todas las métricas de Analytics, incluidas las calculadas, están disponibles en Target Standard/Premium y, a su vez, el informe de actividades de Target también está disponible en Analytics. Del mismo modo, cualquier segmento disponible en Analytics puede aplicarse a ambas soluciones. Puede aplicar la métrica o la audiencia al informe en Target Standard/Premium después de haber iniciado la prueba, o incluso después de que esta se haya completado.

Se incluyen todas las métricas, incluida cualquier métrica de cliente o calculada que esté integrada en Analytics.

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Tenga en cuenta los siguientes puntos cuando vaya a utilizar A4T:

* Para usar Adobe Analytics como la fuente de informes para Adobe Target, tanto el usuario como la empresa deben tener acceso a Adobe Analytics y a Adobe Target. [Póngase en contacto con su representante de cuentas](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si necesita alguna de estas soluciones.
* La fuente de informes se establece por actividad. Target continuará recopilando datos para usarlos en los informes y los datos de Target seguirán estando disponibles (si prefiere que las actividades se basen en datos recopilados por Target).
* Debe usar una de las dos fuentes de informes. No puede recopilar datos de una única actividad desde ambas fuentes.
* Al utilizar A4T, todas las métricas de éxito disponibles para sus actividades serán métricas de Analytics. Sin embargo, su métrica de objetivos se puede basar en una llamada de mbox. Por ejemplo, puede utilizar las funcionalidades de seguimiento de clics integradas en A4T en lugar de tener que implementar el código de seguimiento de clics de Analytics.
* Cuando revise los informes de una actividad de A4T en la interfaz de usuario de Target, estará viendo datos de Analytics. Por ejemplo, si usa la métrica de visitantes en Target, en realidad estará usando la métrica de visitantes de Analytics, no la de Target, que ahora se llama Participantes. Esta diferencia es especialmente importante para métricas de tráfico básicas (visitantes, visitas, vistas de página) y métricas de conversión.
* Las actividades de Target existentes seguirán utilizando la recopilación de datos de Target y no se verán afectadas por la habilitación de A4T.
* Solo se admite una métrica basada en mbox si se utiliza Analytics como fuente de informes.
* Una llamada de servidor a servidor desde Target hacia Analytics envía la información de actividad y de experiencia a Analytics. Esta integración no genera llamadas al servidor adicionales para Target o Analytics.

   En algunas situaciones, la llamada de clasificación de Target a Analytics puede fallar y las actividades no muestran datos en Analytics. Si esto sucede, consulte [Solución de problemas de la integración de Analytics y Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). También puede [ponerse en contacto con Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obtener más ayuda.

## Tipos de actividades compatibles {#section_F487896214BF4803AF78C552EF1669AA}

La siguiente tabla muestra los tipos de actividades compatibles con Analytics como fuente de informes (A4T):

| Tipos de actividad | Compatible con A4T | Notas, si corresponde |
|--- |--- |--- |
| Actividad A/B con división de tráfico manual | Sí |  |
| Actividad A/B con asignación automática | No |  |
| Actividad A/B con segmentación automática | No |  |
| Segmentación de experiencias (XT) | Sí |  |
| Prueba multivariable (MVT) | Sí | Requiere una métrica de objetivos basada en mbox para obtener el informe de contribución de elementos.  En este momento, el informe de contribución de elementos no admite métricas de Analytics. |
| Actividad de personalización automatizada (AP) | No |  |
| Actividad de Recommendations | Sí |  |
| Aplicación móvil | Sí | Compatible con el SDK de Mobile Services, versión 4.13.1 o posterior.  Para obtener más información, consulte la [documentación de Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html). |
| Correo electrónico | No |  |
| API de envío del servidor | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK de NodeJS | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Integración de servicios en la nube AEM 6.1 (o anterior) | No |  |
| Integración de servicios en la nube AEM 6.2 (o posterior) | Sí | Para obtener más información, consulte [Integración con Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) en la documentación de Adobe Experience Manager 6.2. |
| Cualquier actividad que utilice una oferta de redireccionamiento | Sí | Existen requisitos mínimos más estrictos para utilizar ofertas de redireccionamiento con A4T. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sí |  |

Dado que, de momento, no todos los tipos de actividades son compatibles con A4T, es recomendable mantener o implementar algunos mboxes de conversión importantes, como el mbox “orderConfirmPage”.

## Ejemplos de informes de A4T   {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para ver los informes de A4T en [!DNL Target], haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad deseada en la lista que usa [!DNL Analytics] como fuente de informes y, a continuación, haga clic en la pestaña **[!UICONTROL Informes].**

>[!NOTE]
>
>Puede usar la lista desplegable de [!UICONTROL Fuente de informes] situada en la parte superior de la página [!UICONTROL Actividades] para mostrar solo las actividades que utilizan [!DNL Analytics] como fuente de informes.

Para cambiar entre la Visualización de tabla y la [!UICONTROL Visualización de gráfico] del informe, haga clic en el icono correspondiente en la parte superior derecha del informe.

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Métrica de informes] muestra las métricas de objetivo de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph1.png)

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Audiencia] muestra las audiencias de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph2.png)

En la ilustración siguiente, se muestra la [!UICONTROL Visualización de tabla] de un informe de A4T:

![](assets/a4t_report_table.png)

Para ver el informe en [!DNL Analytics] en lugar de en [!DNL Target], haga clic en **[!UICONTROL Ver en Analytics]** en la parte superior del informe.

## Tutorial Analytics &amp; Target: Best Practices for Analysis (en inglés){#section_3438E6E77A464424B717A4FD333B84B2}

Abra el tutorial [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) (Analytics y Target: prácticas recomendadas para el análisis), proporcionado por Adobe Experience League.

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Analytics for Target (A4T) (4:32)

Este vídeo explica cómo utilizar Adobe Analytics como una fuente de informes en Adobe Target para dirigir el análisis de su programa de optimización.

* Explicar qué es A4T y por qué debería utilizarlo
* Explicar cómo funciona A4T
* Entender los requisitos necesarios antes de utilizar A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384?captions=spa)

### Integración Analytics / Target (A4T) (40:33)

Este vídeo es una grabación de “[Horario de oficina](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo configurar y validar que la integración está funcionando
* Cómo funciona la integración
* Obtenga información sobre los informes ideales para su uso en Analytics
* Respuestas a preguntas más frecuentes sobre A4T

[Horas de oficina de la integración de Analytics/Target (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)