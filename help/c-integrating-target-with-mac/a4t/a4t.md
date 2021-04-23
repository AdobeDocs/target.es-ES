---
keywords: A4T;Analytics;Analytics para Target;fuente de informes de Analytics;Adobe Analytics;fuente de informes para Target
description: Utilice Analytics for [!DNL Target]  (A4T) para crear actividades basadas en métricas de conversión y segmentos de audiencia de Analytics y utilice los informes de Analytics para examinar los resultados.
title: ¿Qué es Analytics para [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
translation-type: tm+mt
source-git-commit: cb42be6b0791711d3a9ddf5680cf6d6e32045579
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 41%

---

# Adobe Analytics como fuente de informes para el Adobe [!DNL Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) es una integración entre soluciones que le permite crear actividades basadas en métricas de  [!DNL Analytics] conversión y segmentos de audiencia. La integración de A4T permite utilizar informes [!DNL Analytics] para examinar los resultados. Si utiliza [!DNL Analytics] como fuente de informes para una actividad, todos los informes y la segmentación de dicha actividad se basarán en la [!DNL Analytics] recopilación de datos.

## Información general de A4T {#section_92B66069210C40DBA937790E8CC596CF}

La integración [!DNL Analytics for Target] entre [!DNL Analytics] y [!DNL Target] proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización.

Los tres beneficios principales de utilizar [!DNL Analytics] datos en [!DNL Target] son:

* Los especialistas en marketing pueden aplicar de forma dinámica [!DNL Analytics] métricas de éxito o segmentos de informes a [!DNL Target] informes de actividad en cualquier momento. No es necesario especificarlo todo antes de ejecutar la actividad.
* Disponer de una única fuente de datos elimina la variación derivada de la recopilación de datos de dos sistemas distintos.
* La implementación existente [!DNL Analytics] recopila todos los datos necesarios. No es necesario implementar mboxes en páginas con el único objetivo de recopilar datos para informes. Adobe recomienda implementar un mbox de confirmación de pedido para las actividades [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP).

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de integración para su cuenta. Rellene [este formulario](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.
>
>La integración que habilita [!DNL Analytics] como fuente de datos para [!DNL Target] (A4T) representa la siguiente generación del complemento de SiteCatalyst de Test&amp;Target. Este complemento se considera obsoleto, pero aún se ofrece asistencia técnica para aquellos clientes que todavía lo usan.

Si utiliza [!DNL Analytics] como fuente de informes para una actividad, todos los informes y la segmentación de dicha actividad se basarán en [!DNL Analytics].

Todas las métricas [!DNL Analytics], incluidas las métricas calculadas, están disponibles en [!DNL Target] y el informe [!UICONTROL Actividades de Target] en [!DNL Analytics]. Del mismo modo, cualquier segmento disponible en [!DNL Analytics] puede aplicarse a ambas soluciones. Puede aplicar la métrica o la audiencia al informe en [!DNL Target] después de iniciar la actividad o incluso después de que se haya completado la actividad.

Se incluyen todas las métricas, incluidas las métricas personalizadas o calculadas que estén incorporadas en [!DNL Analytics].

Tras el periodo de clasificación, los datos aparecen en estos informes aproximadamente una hora después de recabarse del sitio web. Todas las métricas, los segmentos y los valores de los informes proceden del grupo de informes que seleccionó cuando configuró la actividad.

Tenga en cuenta los siguientes puntos cuando vaya a utilizar A4T:

* Para usar [!DNL Analytics] como fuente de informes para [!DNL Target], tanto usted como su empresa deben tener acceso a [!DNL Analytics] y a [!DNL Target]. [Póngase en contacto con su representante de cuentas](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si necesita alguna de estas soluciones.
* La fuente de informes se establece por actividad. [!DNL Target][!DNL Target] continuará recopilando datos para usarlos en los informes y los datos de seguirán estando disponibles (si prefiere que las actividades se basen en datos recopilados por [!DNL Target].
* Utilice una fuente de informes o la otra. No puede recopilar datos de una única actividad desde ambas fuentes.
* Al utilizar A4T, todas las métricas de éxito disponibles para sus actividades son [!DNL Analytics] métricas. Sin embargo, su métrica de objetivos se puede basar en una llamada de mbox. Por ejemplo, puede utilizar las capacidades de rastreo de clics integradas de Target con A4T en lugar de tener que implementar el código de seguimiento de clics [!DNL Analytics].
* Al ver los informes de una actividad de A4T en la interfaz de usuario [!DNL Target], está viendo los datos [!DNL Analytics]. Por ejemplo, si utiliza la métrica [!UICONTROL Visitante] en [!DNL Target], está utilizando la métrica [!DNL Analytics] [!UICONTROL Visitante], no la métrica [!DNL Target] [!UICONTROL Visitantes], que ahora se denomina [!UICONTROL Participantes]. Esta diferencia es especialmente importante para las métricas de tráfico básicas ([!UICONTROL Visitantes], [!UICONTROL Visitas], [!UICONTROL Vistas de página]) y las métricas de conversión.
* Las actividades existentes [!DNL Target] siguen utilizando la recopilación de datos [!DNL Target] y no se ven afectadas por la activación de A4T.
* Solo se permite una métrica basada en mbox al usar [!DNL Analytics] como fuente de informes.
* Una llamada de servidor a servidor de [!DNL Target] a [!DNL Analytics] envía información de actividad y experiencia a [!DNL Analytics]. Esta integración no genera más llamadas al servidor para [!DNL Target] o [!DNL Analytics].

   En algunas situaciones, las clasificaciones de [!DNL Target] a [!DNL Analytics] fallan y las actividades no muestran datos en [!DNL Analytics]. Consulte [Resolución de problemas de integración de Analytics y Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). También puede [ponerse en contacto con ClientCare](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obtener más ayuda.

## Tipos de actividades compatibles {#section_F487896214BF4803AF78C552EF1669AA}

La siguiente tabla muestra qué tipos de actividades admiten [!DNL Analytics] como fuente de informes en [!DNL Target] (A4T):

| Tipos de actividad | Compatible con A4T | Notas, si corresponde |
|--- |--- |--- |
| Actividad A/B con división de tráfico manual | Sí |  |
| Actividad A/B con asignación automática | Sí | Consulte [Compatibilidad con A4T para actividades de asignación automática y segmentación automática](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| Actividad A/B con segmentación automática | Sí | Consulte [Compatibilidad con A4T para actividades de asignación automática y segmentación automática](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| Segmentación de experiencias (XT) | Sí |  |
| Prueba multivariable (MVT) | Sí | Requiere una métrica de objetivos basada en mbox para obtener el informe [!UICONTROL Contribución de elementos]. El informe [!UICONTROL Contribución de elementos] no admite actualmente métricas [!DNL Analytics]. |
| Actividad de personalización automatizada (AP) | No |  |
| Actividad de Recommendations | Sí |  |
| Aplicación móvil | Sí | Compatible con el SDK de Mobile Services, versión 4.13.1 o posterior. Para obtener más información, consulte la [documentación de Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| Correo electrónico | No |  |
| API de envío del lado del servidor | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK de NodeJS | Sí | Para obtener más información, consulte [Lado de servidor: implementación de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Integración de servicios en la nube AEM 6.1 (o anterior) | No |  |
| Integración de servicios en la nube AEM 6.2 (o posterior) | Sí | Para obtener más información, consulte [Integración con Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) en la documentación de [!DNL Adobe Experience Manager] 6.2. |
| Cualquier actividad que utilice una oferta de redireccionamiento | Sí | Existen requisitos mínimos más estrictos para utilizar ofertas de redireccionamiento con A4T. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sí | Para obtener más información, consulte [Node.js SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk) en la guía *Adobe Target SDK*. |
| SDK de Java | Sí | Para obtener más información, consulte [Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk) en la guía *Adobe Target* SDK. |

Como todos los tipos de actividades aún no admiten A4T, se recomienda mantener o implementar mboxes de conversión importantes, como el mbox `orderConfirmPage`.

## Ejemplos de informes de A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para ver los informes de A4T en [!DNL Target], haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad deseada en la lista que usa [!DNL Analytics] como fuente de informes y, a continuación, haga clic en la pestaña **[!UICONTROL Informes]**.

>[!NOTE]
>
>Puede usar la lista desplegable de [!UICONTROL Fuente de informes] situada en la parte superior de la página [!UICONTROL Actividades] para mostrar solo las actividades que utilizan [!DNL Analytics] como fuente de informes.

Para cambiar entre la [!UICONTROL Visualización de tabla] y la [!UICONTROL Vista de gráfico] del informe, haga clic en el icono correspondiente en la parte superior derecha del informe.

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Métrica de informes] muestra las métricas de objetivo de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph1.png)

En la ilustración siguiente, se ve la [!UICONTROL Visualización de gráfico] de un informe de A4T. La lista desplegable [!UICONTROL Audiencia] muestra las audiencias de [!DNL Analytics] disponibles:

![](assets/a4t_report_graph2.png)

En la ilustración siguiente, se muestra la [!UICONTROL Visualización de tabla] de un informe de A4T:

![](assets/a4t_report_table.png)

Para ver el informe en [!DNL Analytics] en lugar de en [!DNL Target], haga clic en **[!UICONTROL Ver en Analytics]** en la parte superior del informe.

## Tutorial Analytics &amp; Target: Best Practices for Analysis (en inglés){#section_3438E6E77A464424B717A4FD333B84B2}

Abra [Analytics &amp; Target: Tutorial Prácticas recomendadas para el análisis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), proporcionado por [!DNL Adobe Experience League].

## Vídeos de formación:

Los siguientes vídeos contienen más información sobre los conceptos abordados en este tema.

### Analytics for Adobe Target (A4T) (4:32) ![Distintivo de información general](/help/assets/overview.png)

En este vídeo se explica cómo utilizar [!DNL Analytics] como fuente de informes en [!DNL Target] para dirigir el análisis del programa de optimización.

* Explicar qué es A4T y por qué debería utilizarlo
* Explicar cómo funciona A4T
* Entender los requisitos necesarios antes de utilizar A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Integración de Analytics/Adobe Target (A4T) (40:33) ![Distintivo de tutorial](/help/assets/tutorial.png)

Este vídeo es una grabación de “[Horario de oficina](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo configurar y validar que la integración está funcionando
* Cómo funciona la integración
* Obtenga información sobre los informes ideales para su uso en Analytics
* Respuestas a preguntas más frecuentes sobre A4T

[Integración de Analytics/Target (A4T) Horario de oficina](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)
