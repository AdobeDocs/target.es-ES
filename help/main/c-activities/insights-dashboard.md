---
keywords: actividades;actividad;panel de información
description: '[!UICONTROL Adobe Target Dashboard] le ofrece una vista de alto nivel de cómo su organización utiliza  [!DNL Target] con el paso del tiempo, mostrando la adopción, el volumen de actividad y el uso de la experimentación de un vistazo.'
title: Panel de perspectivas de Adobe Target
feature: Activities
exl-id: 042befcd-025b-4592-a6b2-5dc0b952b031
source-git-commit: 346b54882d4082f14bbc16ede350758a362ee418
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Panel de perspectivas de Adobe Target

[!UICONTROL Adobe Target Dashboard] proporciona una vista de alto nivel de cómo su organización utiliza [!DNL Adobe Target] a lo largo del tiempo. De un vistazo, ayuda a los equipos a comprender el uso de la adopción, el volumen de actividad y la experimentación.

El tablero está diseñado tanto para profesionales como para partes interesadas que deseen una visibilidad rápida del uso de [!DNL Target] sin tener que profundizar en los informes de actividad individuales.

Cuando revise este tablero, tenga en cuenta lo siguiente:

* Las métricas pueden incluir actividades que se iniciaron antes o finalizaron después del intervalo de tiempo seleccionado.
* Una actividad se puede contar en varias métricas en función de su ciclo vital (por ejemplo, tanto publicado como completado).
* El tablero se centra en el uso y la adopción, no en los resultados del rendimiento.

Para obtener resultados detallados, alza o rendimiento estadístico, consulte [informes de actividad individual](../c-reports/reports.md) en [!DNL Adobe Target].

![](assets/insights-1.png)

## [!UICONTROL Experimentation Accelerator]

El titular del tablero proporciona acceso directo a **[!UICONTROL Experimentation Accelerator]**, un punto de entrada ligero a las herramientas que optimizan los flujos de trabajo de experimentación y simplifican la configuración, el análisis y la toma de decisiones de los experimentos.

## Selección de intervalo de tiempo

Para definir el ámbito de los datos que se muestran en el panel, seleccione un intervalo de tiempo, por ejemplo, la última semana, el año pasado o todo el tiempo. El intervalo de tiempo seleccionado se aplica de forma coherente en todas las métricas y gráficos del panel.

![](assets/insights-2.png)

Tenga en cuenta lo siguiente al interpretar las métricas en el intervalo de tiempo seleccionado:

* Algunas métricas reflejan actividades que estuvieron activas en cualquier momento durante el intervalo de tiempo.

* Otros reflejan actividades creadas, publicadas o completadas dentro del intervalo de tiempo.

* Como resultado, es posible que los totales de todas las métricas no se sumen exactamente. Por ejemplo, se pueden iniciar y finalizar muchas actividades en el mismo lapso de tiempo.

También puede exportar una instantánea del tablero seleccionando **[!UICONTROL Download as PNG]** en el menú avanzado.

![](assets/insights-3.png)

## Métricas

El panel organiza sus métricas en cuatro vistas complementarias, cada una de las cuales responde a una pregunta diferente sobre el uso de [!DNL Target]: [KPI](#kpis) ofrecen un resumen general de los recuentos de actividades, el [desglose de tipos de actividades](#activity-type-breakdown) muestra en qué capacidades se basa más, [métricas de pruebas A/B](#ab-testing-metrics) aumentan el uso de la experimentación y [Actividades a lo largo del tiempo](#activities-over-time) revela las tendencias en el intervalo de tiempo seleccionado.

### KPI

Las tarjetas de KPI en la parte superior de la página resumen los recuentos de actividad clave para el intervalo de tiempo seleccionado de un vistazo. Cada tarjeta se centra en una fase diferente del ciclo vital de la actividad, ya sea en directo, modificada, finalizada o publicada, para que pueda evaluar rápidamente el uso general y el impulso.

![](assets/insights-4.png)

La métrica **Total de actividades activas** detalla la cantidad de actividades que estuvieron activas en cualquier momento durante el intervalo de tiempo seleccionado. Una actividad se considera activa si estaba sirviendo tráfico de forma activa, incluso si se inició antes o terminó después del período seleccionado. Utilice esta métrica para lo siguiente:

* Comprenda de qué manera se utilizó [!DNL Target] activamente durante el período de tiempo.
* Mida la escala general de sus esfuerzos de personalización y prueba.

La métrica **Actividades activas o modificadas** representa la cantidad total de actividades en su organización que se activaron, crearon o modificaron dentro del lapso de tiempo seleccionado. Utilice esta métrica para lo siguiente:

* Comprenda el tamaño general de la biblioteca de actividades [!DNL Target] y cuántas actividades se están utilizando.

* Realice un seguimiento del crecimiento a largo plazo de sus programas de experimentación y personalización.

La métrica **Actividades finalizadas** representa el número de actividades que alcanzaron una fecha de finalización o detención durante el intervalo de tiempo seleccionado. Utilice esta métrica para lo siguiente:

* Comprenda cuántas actividades finalizaron durante el período de tiempo.
* Rastrear el volumen de finalización con el tiempo.

La métrica **Actividades publicadas** detalla la cantidad de actividades que se publicaron durante el intervalo de tiempo seleccionado. Una actividad se considera publicada cuando se activa por primera vez. Si una actividad se activa, se detiene y luego se vuelve a activar, solo se cuenta la primera incidencia en esta métrica. Utilice esta métrica para lo siguiente:

* Mida cuántas actividades nuevas se lanzaron.
* Comprenda la creación de actividades y la velocidad de publicación.

### Desglose por tipo de actividad

![](assets/insights-5.png)

El gráfico [!UICONTROL Activity Type] muestra la distribución de actividades activas por tipo durante el intervalo de tiempo seleccionado, incluido lo siguiente:

* [!UICONTROL A/B Test]
* [!UICONTROL Experience Targeting]
* [!UICONTROL Recommendations]
* [!UICONTROL Automated Personalization]
* [!UICONTROL Multivariate Test]

Utilice este gráfico para identificar en qué capacidades de [!DNL Target] se basa más su organización, así como para identificar oportunidades que le permitirán ampliar la combinación de tipos de actividades que ejecuta.

### Métricas de prueba A/B

![](assets/insights-6.png){align="center"}

En esta sección se resalta el uso relacionado específicamente con **[!UICONTROL A/B Test]** actividades.

La métrica **[!UICONTROL Total live A/B Test activities]** muestra el número de **[!UICONTROL A/B Test]** actividades que estuvieron activas en cualquier momento durante el intervalo de tiempo seleccionado.

**[!UICONTROL Total A/B Tests published]** muestra el número de **[!UICONTROL A/B Test]** actividades que se publicaron durante el intervalo de tiempo seleccionado.

Utilice estas métricas para comprender con qué frecuencia se utilizan las pruebas A/B y para rastrear el volumen de experimentación y la adopción a lo largo del tiempo.

### Actividades a lo largo del tiempo

![](assets/insights-7.png){align="center"}

El gráfico **[!UICONTROL Activities Over Time]** registra la cantidad de actividades creadas, modificadas y publicadas en el intervalo de tiempo seleccionado, lo que facilita la detección de tendencias, picos o períodos de silencio en el programa de experimentación.

