---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe “Analytics for Target” (A4T) es una integración de soluciones cruzadas que le permite crear actividades basadas en las métricas de conversión y los segmentos de audiencia de Analytics. Esta integración le permite utilizar informes de Analytics para examinar sus resultados. Si usa Analytics como fuente de informes de una actividad, todos los informes y la segmentación de dicha actividad se basarán en la recopilación de datos de Analytics.
title: Adobe Analytics como fuente de informes para Adobe Target (A4T)
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 48%

---


# Adobe Analytics como fuente de informes para Adobe Target (A4T)

[!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que permite crear actividades basadas en métricas de  [!DNL Analytics] conversión y segmentos de audiencia. La integración de A4T permite utilizar [!DNL Analytics] informes para examinar los resultados. Si utiliza [!DNL Analytics] como fuente de sistema de informes para una actividad, todo el sistema de informes y la segmentación para esa actividad se basa en la recopilación de datos [!DNL Analytics].

## Información general de A4T {#section_92B66069210C40DBA937790E8CC596CF}

La [!DNL Analytics for Target] integración entre [!DNL Analytics] y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Los tres beneficios principales del uso de [!DNL Analytics] datos en [!DNL Target] son:

* Los especialistas en marketing pueden aplicar [!DNL Analytics] métricas de éxito o segmentos de sistema de informes de forma dinámica a [!DNL Target] informes de actividad en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Disponer de una única fuente de datos elimina la variación derivada de la recopilación de datos de dos sistemas distintos.
* La implementación existente [!DNL Analytics] recopila todos los datos necesarios. No es necesario implementar mboxes en páginas con el único objetivo de recopilar datos para informes. Aunque aún se recomienda implementar un mbox de confirmación de pedido para actividades [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP).

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Rellene [este formulario](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.
>
>La integración que habilita [!DNL Analytics] como fuente de datos para [!DNL Target] (A4T) representa la próxima generación del complemento de Test&amp;Destinatario a SiteCatalyst. Este complemento se considera obsoleto, pero aún se ofrece asistencia técnica para aquellos clientes que todavía lo usan.

Si utiliza [!DNL Analytics] como fuente de sistema de informes para una actividad, todo el sistema de informes y la segmentación para esa actividad se basa en [!DNL Analytics].

Todas las [!DNL Analytics] métricas, incluidas las métricas calculadas, están disponibles en [!DNL Target] y el informe [!UICONTROL Actividades de Destinatario] en [!DNL Analytics]. Del mismo modo, cualquier segmento disponible en [!DNL Analytics] puede aplicarse a ambas soluciones. Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de que se haya iniciado la actividad o incluso después de que la actividad se haya completado.

Se incluyen todas las métricas, incluida cualquier métrica de cliente o calculada que esté integrada en [!DNL Analytics].

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Tenga en cuenta los siguientes puntos cuando vaya a utilizar A4T:

* Para utilizar [!DNL Analytics] como fuente de sistema de informes para [!DNL Target], tanto usted como su compañía deben tener acceso a [!DNL Analytics] y a [!DNL Target]. [Póngase en contacto con su representante de cuentas](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si necesita alguna de estas soluciones.
* La fuente de informes se establece por actividad. [!DNL Target][!DNL Target] continuará recopilando datos para usarlos en los informes y los datos de seguirán estando disponibles (si prefiere que las actividades se basen en datos recopilados por [!DNL Target].
* Debe usar una de las dos fuentes de informes. No puede recopilar datos de una única actividad desde ambas fuentes.
* Al utilizar A4T, todas las métricas de éxito disponibles para sus actividades son [!DNL Analytics] métricas. Sin embargo, su métrica de objetivos se puede basar en una llamada de mbox. Por ejemplo, puede utilizar las capacidades de rastreo de clics integradas del Destinatario con A4T en lugar de tener que implementar el código de seguimiento de clics [!DNL Analytics].
* Al ver el sistema de informes de una actividad de A4T en la interfaz de usuario [!DNL Target], está viendo [!DNL Analytics] datos. Por ejemplo: si utiliza la métrica [!UICONTROL Visitante] en [!DNL Target], está utilizando la métrica [!DNL Analytics] [!UICONTROL Visitante], no la métrica [!DNL Target] [!UICONTROL Visitantes], que ahora se denomina [!UICONTROL Entrantes]. Esta diferencia es especialmente importante para las métricas de tráfico básicas ([!UICONTROL Visitantes], [!UICONTROL Visitas], [!UICONTROL Vistas de página]) y las métricas de conversión.
* Todas las actividades existentes [!DNL Target] siguen utilizando la recopilación de datos [!DNL Target] y no se ven afectadas por la habilitación de A4T.
* Solo se permite una métrica basada en mbox cuando se utiliza [!DNL Analytics] como fuente de sistema de informes.
* Una llamada de servidor a servidor de [!DNL Target] a [!DNL Analytics] envía información de actividad y experiencia a [!DNL Analytics]. Esta integración no resulta en llamadas al servidor adicionales para [!DNL Target] o [!DNL Analytics].

   En algunas situaciones, la llamada de clasificación de [!DNL Target] a [!DNL Analytics] puede fallar y las actividades no muestran datos en [!DNL Analytics]. Si esto sucede, consulte [Solución de problemas de la integración de Analytics y Destinatario (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). También puede [ponerse en contacto con Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obtener más ayuda.

## Tipos de actividad admitidos {#section_F487896214BF4803AF78C552EF1669AA}

La siguiente tabla muestra qué tipos de actividades admiten [!DNL Analytics] como fuente de sistema de informes en [!DNL Target] (A4T):

| Tipos de actividad | Compatible con A4T | Notas, si corresponde |
|--- |--- |--- |
| Actividad A/B con división de tráfico manual | Sí |  |
| Actividad A/B con asignación automática | Sí | Consulte [Compatibilidad de Analytics para Destinatario (A4T) con la asignación automática y las actividades de Destinatario automático](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Actividad A/B con segmentación automática | Sí | Consulte [Compatibilidad de Analytics para Destinatario (A4T) con la asignación automática y las actividades de Destinatario automático](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Segmentación de experiencias (XT) | Sí |  |
| Prueba multivariable (MVT) | Sí | Requiere el objetivo de métrica de objetivos basado en mbox para obtener el informe [!UICONTROL Contribución de elementos].  El informe [!UICONTROL Contribución de elementos] no admite actualmente [!DNL Analytics] métricas. |
| Actividad de personalización automatizada (AP) | No |  |
| Actividad de Recommendations | Sí |  |
| Aplicación móvil | Sí | Compatible con el SDK de Mobile Services, versión 4.13.1 o posterior.  Para obtener más información, consulte la [documentación de Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| Correo electrónico | No |  |
| API de envío del servidor | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK de NodeJS | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Integración de servicios en la nube AEM 6.1 (o anterior) | No |  |
| Integración de servicios en la nube AEM 6.2 (o posterior) | Sí | Para obtener más información, consulte [Integración con Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) en la documentación de [!DNL Adobe Experience Manager] 6.2. |
| Cualquier actividad que utilice una oferta de redireccionamiento | Sí | Existen requisitos mínimos más estrictos para utilizar ofertas de redireccionamiento con A4T. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sí | Para obtener más información, consulte [SDK de Node.js](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk) en la guía *SDK de Adobe Target*. |
| Java SDK | Sí | Para obtener más información, consulte [Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk) en la guía *Adobe Target* SDK. |

Dado que todos los tipos de actividades aún no admiten A4T, se recomienda mantener o implementar mboxes de conversión importantes, como el mbox `orderConfirmPage`.

## Ejemplos de informes de A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para vista de informes de A4T en [!DNL Target], haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad que desee de la lista que utiliza [!DNL Analytics] como fuente de sistema de informes y, a continuación, haga clic en la ficha **[!UICONTROL Informes]**.

>[!NOTE]
>
>Puede usar la lista desplegable de [!UICONTROL Fuente de informes] situada en la parte superior de la página [!UICONTROL Actividades] para mostrar solo las actividades que utilizan [!DNL Analytics] como fuente de informes.

Puede alternar entre la [!UICONTROL Vista de tabla] y [!UICONTROL Vista de gráfico] del informe haciendo clic en el icono correspondiente en la parte superior derecha del informe.

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Métrica de informes] muestra las métricas de objetivo de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph1.png)

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Audiencia] muestra las audiencias de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph2.png)

En la ilustración siguiente, se muestra la [!UICONTROL Visualización de tabla] de un informe de A4T:

![](assets/a4t_report_table.png)

Para ver el informe en [!DNL Analytics] en lugar de en [!DNL Target], haga clic en **[!UICONTROL Ver en Analytics]** en la parte superior del informe.

## Tutorial Analytics &amp; Target: Best Practices for Analysis (en inglés){#section_3438E6E77A464424B717A4FD333B84B2}

Abra el [Destinatario y análisis: Prácticas recomendadas para el tutorial de Análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por [!DNL Adobe Experience League].

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos tratados en este tema.

### Analytics para Destinatario (A4T) (4:32) ![Distintivo de información general](/help/assets/overview.png)

En este vídeo se explica cómo utilizar [!DNL Analytics] como fuente de sistema de informes en [!DNL Target] para impulsar la análisis del programa de optimización.

* Explicar qué es A4T y por qué debería utilizarlo
* Explicar cómo funciona A4T
* Entender los requisitos necesarios antes de utilizar A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Integración de Analytics/Destinatario (A4T) (40:33) ![distintivo de tutorial](/help/assets/tutorial.png)

Este vídeo es una grabación de “[Horario de oficina](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo configurar y validar que la integración está funcionando
* Cómo funciona la integración
* Obtenga información sobre los informes ideales para su uso en Analytics
* Respuestas a preguntas más frecuentes sobre A4T

[Horas de oficina de Analytics/Integración de Destinatario (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)