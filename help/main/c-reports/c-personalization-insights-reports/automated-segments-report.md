---
keywords: Segmentación;informes de AP;informes de personalización automatizada;segmentación automática;informe de segmentación automática;personalización;perspectivas;segmentos automatizados;faq;preguntas más frecuentes
description: Descubra cómo los distintos segmentos definidos por los modelos de personalización de Adobe [!DNL Target] responden a las ofertas y experiencias de la actividad mediante el informe Segmentos automatizados.
title: ¿Qué es el informe Segmentos automatizados?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 60%

---

# Informe [!UICONTROL Automated Segments]

Información sobre el informe [!UICONTROL Automated Segments], uno de los dos informes especializados disponibles para los usuarios de las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT).

>[!NOTE]
>
>Tenga en cuenta lo siguiente al usar [!UICONTROL Personalization Insights] informes:
>
>* Las actividades de AP y AT están disponibles como parte de la solución [!DNL Target Premium]. No se incluyen en [!DNL Target Standard] sin una licencia [!DNL Target Premium].
>
>* Los informes de [!UICONTROL Personalization Insights] solo están disponibles para actividades AP y AT que utilizan un objetivo de optimización de conversión. Tampoco se admiten las actividades en las que el objetivo de optimización se cambió a la conversión de ingresos después de que la actividad ya estaba activa.
>
>* Los informes de [!UICONTROL Personalization Insights] solo están disponibles si se ha seleccionado [!UICONTROL Primary Goal] en la lista desplegable [!UICONTROL Report Metric].
>
>* Los informes de [!UICONTROL Personalization Insights] solo se admiten en el [entorno predeterminado](/help/main/administrating-target/hosts.md).
>
>* Los informes de [!UICONTROL Personalization Insights] se generan solamente para las actividades que están en estado [!UICONTROL Live] y que se han activado y recibido tráfico durante al menos 15 días.

Los distintos visitantes responden de forma diferente a las ofertas y experiencias de su actividad AP/AT. Este informe muestra cómo los distintos segmentos automatizados definidos por los modelos de personalización de Target respondieron a las ofertas y experiencias de la actividad.

## Acceso al informe Segmentos automatizados {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Haga clic en **[!UICONTROL Activities]** y luego en la actividad [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) que quiera de la lista.

   Si tiene muchas actividades, haga clic en el icono Filtro ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] y [!UICONTROL Activity Source].

1. Haga clic en **[!UICONTROL Reports]**.

   Se muestra el informe [Resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) o [Resumen de segmentación automática](/help/main/c-reports/personalization-reports/auto-target-summary-report.md), que proporciona información sobre el rendimiento de sus actividades, representadas por el primer icono de pantalla. Los dos iconos adicionales representan los dos informes de [!UICONTROL Personalization Insights]: **[!UICONTROL Automated Segments]** ( ![informe Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) y **[!UICONTROL Important Attributes]** ( ![icono Atributos importantes](/help/main/assets/icons/ViewList.svg) ). La segmentación automática tiene un icono de gráfico adicional para la vista gráfica del informe [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >El informe [!UICONTROL Automated Segments] no estará disponible hasta al menos 15 días después de que haya activado su actividad. Durante este período inicial, no podrá acceder a este informe ni hacer clic en el icono [!UICONTROL Automated Segments]. Transcurridos 15 días, y suponiendo que haya tráfico personalizado suficiente en la actividad, el informe [!UICONTROL Automated Segments] estará disponible.

1. Transcurridos 15 días desde la activación de la actividad, puede hacer clic en el icono **[!UICONTROL Automated Segments]**.

1. Seleccione el intervalo de fechas deseado.

   A diferencia del informe [!UICONTROL Summary] (informes de rendimiento), [!UICONTROL Personalization Insights], incluido [!UICONTROL Automated Segments], está disponible solamente para intervalos de fechas fijos: 15 días, 30 días y 60 días. Estos intervalos de fechas fijos permiten que [!UICONTROL Personalization Insights] use un intervalo de datos lo suficientemente grande como para reducir la probabilidad de que obtenga información de un patrón de corta duración en su actividad. Las dos opciones que tiene para el intervalo de fechas son “Fecha de finalización” y “Duración”. Verá que &quot;Inicio&quot; está atenuado. La fecha de inicio cambia automáticamente según las selecciones que realice para la fecha de finalización y la duración.

   Puede acceder a los intervalos de fechas fijos disponibles desde la lista desplegable [!UICONTROL Preset Date Range].

1. Revise los datos del informe [!UICONTROL Automated Segments].

1. (Opcional) Haga clic en el icono **[!UICONTROL Download]** ( ![Icono de descarga](/help/main/assets/icons/Download.svg) ) para [descargar el informe en formato CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) para su análisis en Excel y otras herramientas.

   >[!NOTE]
   >
   >El informe de la interfaz de usuario de Perspectivas de personalización contiene información seleccionada. La descarga de CSV para el informe Segmentos automatizados contiene detalles adicionales. La descarga del informe Segmentos automatizados incluye segmentos automatizados adicionales que se suman a los ya incluidos en la interfaz de usuario, así como información sobre el comportamiento de dichos segmentos ante sus ofertas o experiencias.

## Interpretación del informe Segmentos automatizados

La tabla siguiente explica cómo se interpreta el informe y describe sus elementos:

| Elemento | Detalles |
|--- |--- |
| Panel lateral izquierdo | El panel lateral izquierdo enumera los 20 “segmentos automatizados” más grandes que los modelos de personalización de Target han identificado para esta actividad. Un “segmento automatizado” es como una audiencia, pero se define mediante modelos de personalización de Target en vez de hacerlo el experto en marketing. Cada segmento automatizado está formado por valores (o intervalos de valores) específicos de atributos específicos.<br>Los segmentos automatizados pueden superponerse. Los segmentos automatizados se pueden definir mediante uno, dos, tres o cuatro atributos. Consulte los ejemplos siguientes para obtener más detalles.<br>Para obtener más información sobre los modelos de personalización de Target, consulte [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). Para obtener más información sobre los atributos que utilizan los modelos de personalización de Target para crear segmentos automatizados, consulte [Recopilación de datos para algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). |
| Gráfico central | Los gráficos centrales muestran el rendimiento del contenido de su actividad para el segmento automatizado resaltado. Cuando hace clic en diferentes segmentos del panel izquierdo, los gráficos centrales se actualizan. |
| Gráficos circulares | Los gráficos circulares de la parte superior del panel central muestran el tamaño del segmento automatizado, así como la cantidad total de visitas personalizadas en la actividad (por ejemplo, el tráfico a esta actividad servido por el modelo de personalización. No se incluye el tráfico de control ni el tráfico servido por el modelo ganador general). El tamaño del segmento se basa únicamente en las visitas personalizadas.<br>![Gráfico circular](/help/main/c-reports/assets/pie.png) |
| Gráfico de barras de eje doble | El gráfico de barras de eje doble incluye información sobre visitas y conversiones para cada oferta o experiencia y para ese segmento automatizado específico. |
| Barra rosa | La barra rosa representa la tasa de conversión y utiliza el eje inferior del gráfico. Puede pasar el puntero del ratón sobre la barra para obtener más información. |
| Barra azul | La barra azul representa el número de visitas y utiliza el eje superior del gráfico. Puede pasar el puntero del ratón sobre la barra para obtener más información. |
| Línea de puntos gris | La línea de puntos gris representa la tasa de conversión para todas las visitas personalizadas en la actividad, todas las ofertas/experiencias y todos los segmentos automatizados. |

**Ejemplo 1 de segmento automatizado**

Este segmento automatizado se define mediante un único atributo. Los visitantes incluidos en este segmento automatizado vieron esta actividad de AP en un día laborable, pero fuera de los horarios de trabajo habituales, o en un fin de semana.

![Ejemplo de informe Segmentos automatizados 1](/help/main/c-reports/assets/automated_segment_example_1.png)

**Ejemplo 2 de segmento automatizado**

Este segmento automatizado se define mediante dos atributos. Los visitantes incluidos en este segmento automatizado que vieron esta actividad de AP tenían menos de tres visualizaciones de página en su visita actual y se encontraban entre las latitudes 42,57 y 47,29 (aproximadamente, entre New Hampshire/Oregón y Washington/Maine para una empresa estadounidense).

![Ejemplo de informe Segmentos automatizados 2](/help/main/c-reports/assets/automated_segment_example_2.png)

## PF sobre Segmentos automatizados {#section_740910A52FA646B4AC9452F98C2F5719}

**Los informes de Perspectivas de personalización aún no están disponibles para mi actividad. ¿A qué se debe?**

Existen varias razones por las que los informes de [!UICONTROL Personalization Insights] aún no están disponibles para su actividad:

* No han transcurrido 15 días desde que activó la actividad. Los informes Segmentos automatizados y Atributos importantes no estarán disponibles al menos hasta 15 días después de haberse iniciado la actividad. Durante este periodo inicial no podrá acceder a estos informes ni hacer clic en los iconos de Segmentos automatizados o Atributos importantes.
* La actividad no tuvo suficiente tráfico durante el periodo de tiempo especificado. Transcurridos 15 días, y suponiendo que haya tráfico personalizado suficiente en la actividad para crear los modelos de personalización, estarán disponibles los informes Segmentos automatizados y Atributos importantes.
* Su actividad tiene un objetivo de optimización de ingresos. Actualmente, [!UICONTROL Personalization Insights] solo está disponible para las actividades de objetivos de optimización de conversión. Adobe añadirá compatibilidad para las actividades de objetivos de optimización de ingresos en una versión futura.

¿**Qué es un atributo?**

Un atributo es información sobre un visitante o sobre su visita específica que los algoritmos de personalización utilizan para aprender a personalizar el tráfico. Por ejemplo, un atributo podría ser el tipo de navegador, la ubicación, la hora del día de la visita, etcétera.

Para obtener más información sobre qué atributos utiliza [!DNL Target] en sus modelos de personalización, consulte [Recopilación de datos para algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Para obtener más información sobre cómo cargar nuevos atributos en Target para usarlos en modelos de personalización de Target, consulte [Métodos para introducir datos a Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}.

**¿Qué es un segmento automatizado?**

Un “segmento automatizado” es como una audiencia, pero se define mediante modelos de personalización de Target en vez de hacerlo el experto en marketing.

Un segmento automatizado está formado por valores (o intervalos de valores) específicos de atributos específicos. Consulte el paso 5 anterior para ver ejemplos de segmentos automatizados. Los segmentos pueden superponerse.

Para obtener más información acerca del algoritmo de personalización de bosque aleatorio, que es la base de los modelos de personalización de Target, vea [Algoritmo de bosque aleatorio](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**¿Qué decide el orden de los segmentos automatizados?**

Para cada segmento se calcula una puntuación en función de su tamaño y de su desempeño ante el contenido de la actividad. La combinación de estas entradas determina el orden de los segmentos automatizados, de manera que los segmentos más grandes y con diferencias mayores en la respuesta ante los distintos contenidos aparecen más arriba en la lista de segmentos.

**¿Por qué solo algunas de mis ofertas y experiencias aparecen en el informe Segmentos automatizados?**

Las actividades de AP y AT crean un modelo por oferta (en el caso de AP) y un modelo por experiencia (en el caso de AT). Estas actividades comienzan a servir tráfico personalizado y crean tu [!UICONTROL Personalization Insights] con tan solo dos modelos creados. Si no ve todas sus ofertas o experiencias en [!UICONTROL Personalization Insights], es probable que no tenga modelos creados para esas ofertas o experiencias específicas. Puede comprobar el informe [!UICONTROL Summary] de su actividad y ver si hay un icono de reloj junto a esa oferta o experiencia. Este icono indica que los modelos aún no están creados para esa oferta o experiencia.

**¿Por qué, para un determinado segmento automatizado, algunas ofertas o experiencias con una tasa de conversión menor que otras reciben una mayor cantidad de tráfico?**

Existen varias causas potenciales para que una oferta o experiencia con una tasa de conversión menor pueda tener más visitas dentro de un segmento automatizado, como las siguientes:

* Hay un número de vistas pequeño para algunas o para todas las ofertas o experiencias en un segmento automatizado concreto.
* Actividades de menor volumen en las que determinadas ofertas y experiencias carecen de modelos construidos, o para las que se construyeron modelos antes para unas ofertas y experiencias que para otras.
* Las reglas de segmentación de una oferta específica indican qué visitantes pueden ver cada oferta o experiencia.

**¿Es la información en los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes] la misma que en la descarga CSV?**

No, el informe Interfaz de usuario contiene información seleccionada. La descarga de CSV contiene detalles adicionales. La descarga del informe Perspectivas de segmentos automatizados incluye segmentos automatizados adicionales que se suman a los ya incluidos en la interfaz de usuario, así como información sobre el comportamiento de dichos segmentos ante sus ofertas o experiencias. El informe Atributos importantes incluye los 100 principales atributos de visitante y su importancia relativa, mientras que Interfaz de usuario solo incluye los 10 principales atributos de visitante.

**¿Puedo ver [!UICONTROL Personalization Insights] para un intervalo de fechas personalizado?**

Los informes de Personalization Insights (tanto [!UICONTROL Automated Segments] como [!UICONTROL Important Attributes]) solo están disponibles para intervalos de fechas fijos: 15 días, 30 días y 60 días. Estos intervalos de fechas fijos permiten que [!UICONTROL Personalization Insights] use un intervalo de datos lo suficientemente grande como para reducir la probabilidad de que obtenga información de un patrón de corta duración en su actividad. Puede seleccionar estas duraciones para cualquier fecha de finalización (mientras haya datos suficientes en la actividad para satisfacer la duración).

**¿Cómo se crea [!UICONTROL Personalization Insights]?**

[!UICONTROL Personalization Insights] se ha creado usando una técnica de Adobe con patente en trámite llamada MAGIX (Model Agnostic Globally Interpretable Explanations). Puede obtener más información sobre MAGIX en el artículo publicado por el equipo de investigación de Adobe en el [sitio web de arXiv.org](https://arxiv.org/abs/1706.07160).

**¿Por qué los datos totales de tráfico de visitantes en el informe [!UICONTROL Automated Segments] no coinciden con mi informe de resumen/rendimiento de AP o AT?**

Los informes de [!UICONTROL Personalization Insights] solo incluyen visitantes que vieron un fragmento de contenido seleccionado por los modelos de personalización de Target (es decir, no tienen en cuenta el tráfico de control ni el tráfico servido por el modelo ganador general). Este tipo de tráfico se denomina tráfico &quot;personalizado&quot;. El informe Resumen de rendimiento de AP/AT incluye el tráfico de control y el tráfico &quot;segmentado&quot;. El tráfico segmentado incluye el tráfico personalizado, así como también el tráfico servido mediante el modelo ganador general y elementos de tráfico aleatorios que se utilizan para profundizar en el aprendizaje.

**¿Los segmentos automatizados son mutuamente excluyentes?**

No, existe superposición entre los segmentos automatizados.

**¿Está [!UICONTROL Personalization Insights] disponible para los objetivos de modelado basados en los ingresos o para la meta principal?**

En este momento, [!UICONTROL Personalization Insights] solo está disponible para las actividades de objetivos de optimización de conversión. Adobe añadirá compatibilidad para las actividades de objetivos de optimización de ingresos en una versión futura.

**¿De qué maneras puedo aprovechar la información de Perspectivas de personalización?**

* Descubra nuevas audiencias a las que dirigirse: Si ve un segmento automatizado concreto que funciona bien, puede considerar la posibilidad de crear una audiencia para poder reutilizar ese segmento en otros informes.
* Pruebe su hipótesis sobre qué tipo de visitantes responden a cuál de sus experiencias.
* Descubra qué contenido funcionó para cada tipo de visitante: ¿qué ofertas fueron las responsables de atraer a un tipo concreto de visitantes?
* Identifique el contenido de bajo rendimiento.
* Averigüe qué atributos resultaron más importantes para el aprendizaje del modelo.
* Vea qué atributos se utilizan en los modelos de personalización y qué importancia tienen.
* Identifique oportunidades para incluir nuevos puntos de datos que puede pasar a Target para profundizar en la personalización.

**¿Hay alguna lógica en el orden en que aparecen los atributos en una tarjeta de segmento?**

No, el orden de las tarjetas se basa solamente en una clasificación descrita anteriormente. El orden de los atributos dentro de una tarjeta no se basa en ninguna lógica.
