---
keywords: Segmentación;informes de AP;informes de personalización automatizada;segmentación automática;segmentación;automática;informe de segmentación automática;informe;personalización;perspectivas;faq;preguntas frecuentes;atributos importantes
description: Aprenda a utilizar el informe [!UICONTROL Important Attributes] que muestra los principales atributos que influyeron en el modelo de personalización y su importancia relativa.
title: ¿Qué es el informe Atributos importantes?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1773'
ht-degree: 57%

---

# Informe Atributos importantes

Información sobre el informe [!UICONTROL Important Attributes], uno de los dos informes especializados disponibles para los usuarios de las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT).

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

En las distintas actividades, distintos atributos son más o menos importantes para el modo en que el modelo decide realizar la personalización. Este informe muestra los atributos que más influyeron en el modelo y su importancia relativa.

## Acceso al informe [!UICONTROL Important Attributes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Haga clic en **[!UICONTROL Activities]** y luego en la actividad [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) o [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md) que quiera de la lista.

   Si tiene muchas actividades, haga clic en el icono Filtro ( ![Icono de filtro](/help/main/assets/icons/Filter.svg) ) para filtrar la lista seleccionando opciones en las listas desplegables [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] y [!UICONTROL Activity Source].

1. Haga clic en **[!UICONTROL Reports]**.

   Se muestra el informe [Resumen de Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) o [Resumen de segmentación automática](/help/main/c-reports/personalization-reports/auto-target-summary-report.md), que proporciona información sobre el rendimiento de sus actividades, representadas por el primer icono de pantalla. Los dos iconos adicionales representan los dos informes de [!UICONTROL Personalization Insights]: **[!UICONTROL Automated Segments]** ( ![informe Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) y **[!UICONTROL Important Attributes]** ( ![icono Atributos importantes](/help/main/assets/icons/ViewList.svg) ).


   Observe que [!UICONTROL Auto-Target] tiene un icono de gráfico adicional para la vista gráfica del informe [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >El informe [!UICONTROL Important Attributes] no estará disponible hasta al menos 15 días después de que haya activado su actividad. Durante este período inicial, no podrá acceder a este informe ni hacer clic en el icono [!UICONTROL Important Attributes]. Transcurridos 15 días, y suponiendo que haya tráfico personalizado suficiente en su actividad, el informe [!UICONTROL Important Attributes] estará disponible.

1. Transcurridos 15 días a partir de la activación de la actividad, haga clic en el icono **[!UICONTROL Important Attributes]** ( ![icono de Atributos importantes](/help/main/assets/icons/ViewList.svg) )icono.

1. Seleccione el intervalo de fechas deseado.

   A diferencia del informe [!UICONTROL Summary] (informes de rendimiento), [!UICONTROL Personalization Insights], incluido [!UICONTROL Important Attributes], está disponible solamente para intervalos de fechas fijos: 15 días, 30 días y 60 días.

   Estos intervalos de fechas fijos permiten que [!UICONTROL Personalization Insights] use un intervalo de datos lo suficientemente grande como para reducir la probabilidad de que obtenga información de un patrón de corta duración en su actividad. Las dos opciones que tiene para el intervalo de fechas son “Fecha de finalización” y “Duración”. Observe que “Inicio” aparece atenuado. La fecha de inicio cambia automáticamente según las selecciones que realice para la fecha de finalización y la duración.

   Puede acceder a los intervalos de fechas fijos disponibles desde la lista desplegable [!UICONTROL Preset Date Range].

1. Revise los datos del informe [!UICONTROL Important Attributes].

1. (Opcional) Haga clic en el icono Descargar ( ![Icono de descarga](/help/main/assets/icons/Download.svg) ) para [descargar el informe en formato CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) para su análisis en Excel y otras herramientas.

   >[!NOTE]
   >
   >El informe de la interfaz de usuario de Perspectivas de personalización contiene información seleccionada. La descarga de CSV para el informe Atributos importantes contiene detalles adicionales. La descarga del informe Atributos importantes incluye la lista completa de los 100 principales atributos, mientras que el informe Interfaz de usuario solo incluye los 10 primeros. Si busca un atributo específico en el informe, pero no aparece, no significa que el atributo no influyera en esta actividad, solo que no estuvo entre los 100 principales.

## Interpretación del informe Atributos importantes

La tabla siguiente explica cómo se interpreta el informe y describe sus elementos:

| Elemento | Detalles |
|--- |--- |
| Gráfico de barras | El gráfico de barras multicolor en la parte superior de la pantalla le permite visualizar estas puntuaciones de importancia relativa. Los valores se representan con el color de punto que se indica en la tabla junto a cada atributo. También puede pasar el puntero por encima de un color específico del gráfico de barras para ver a qué atributo representa.  Las puntuaciones de importancia de los 100 principales atributos suman el 100 %. Para obtener más información sobre cómo agregar más atributos que los modelos de personalización de Target puedan usar, consulte [Carga de datos para los algoritmos de Personalization de Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Gráfico de Clasificación de atributos de modelo | Clasificación de atributos de modelo incluye los 10 atributos que fueron más importantes para que el modelo de personalización de Target determinara qué contenido se asignaba a cada visitante. La puntuación de importancia muestra, en relación con los 100 principales atributos, el peso que tuvo un atributo específico en los modelos de personalización de Target para la actividad. |

## PF sobre Atributos importantes {#section_740910A52FA646B4AC9452F98C2F5719}

Consulte las siguientes preguntas frecuentes para obtener respuestas a preguntas frecuentes acerca del uso del informe [!UICONTROL Important Attributes].

### Los informes de Personalization Insights aún no están disponibles para mi actividad. ¿Por qué?

Existen varias razones por las que los informes de [!UICONTROL Personalization Insights] podrían no estar aún disponibles para su actividad:

* No han transcurrido 15 días desde que se activó la actividad. Los informes Segmentos automatizados y Atributos importantes no estarán disponibles al menos hasta 15 días después de haberse iniciado la actividad. Durante este periodo inicial no podrá acceder a estos informes ni hacer clic en los iconos de Segmentos automatizados o Atributos importantes.
* La actividad no tuvo suficiente tráfico durante el periodo de tiempo especificado. Transcurridos 15 días, y suponiendo que haya [tráfico personalizado suficiente](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) en la actividad para crear los modelos de personalización, estarán disponibles los informes Segmentos automatizados y Atributos importantes.
* Su actividad tiene un objetivo de optimización de ingresos. En este momento, [!UICONTROL Personalization Insights] solo está disponible para las actividades de objetivos de optimización de conversión. En una futura versión añadiremos compatibilidad con las actividades de optimización de los ingresos.

### ¿Qué es un atributo?

Un atributo es información sobre un visitante o sobre su visita específica que los algoritmos de personalización utilizan para aprender a personalizar el tráfico. Por ejemplo, un atributo podría ser el tipo de navegador, la ubicación, la hora del día de la visita, etcétera.

Para obtener más información sobre qué atributos utiliza [!DNL Target] en sus modelos de personalización, consulte [Recopilación de datos para algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Para obtener más información sobre cómo cargar nuevos atributos en Target para usarlos en modelos de personalización de Target, consulte [Métodos para introducir datos a Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}.

### Veo uno o más atributos que no quiero que el modelo use para el aprendizaje. ¿Puedo quitarlos del modelo de aprendizaje? {#models-api}

La [!UICONTROL Models API], también denominada API de Lista de bloqueados, permite a los usuarios ver y administrar la lista de atributos (también denominados características) utilizados en los modelos de aprendizaje automático para las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT). Si desea excluir uno o más atributos de la utilización por parte de los modelos para actividades AP o AT, puede utilizar la API de modelos para añadir esos atributos a la &quot;lista de bloqueados&quot;.

Para obtener información detallada, consulte [Resumen de API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=es){target=_blank} en la *Guía para desarrolladores de Adobe Target*. Para usar la API para bloquear atributos, consulte [API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html?lang=es){target=_blank}.

### ¿La información de los informes [!UICONTROL Automated Segments] y [!UICONTROL Important Attributes] es la misma que la de la descarga CSV?

No, el informe Interfaz de usuario contiene información seleccionada. La descarga de CSV contiene detalles adicionales. La descarga del informe Perspectivas de segmentos automatizados incluye segmentos automatizados adicionales que se suman a los ya incluidos en la interfaz de usuario, así como información sobre el comportamiento de dichos segmentos ante sus ofertas o experiencias. El informe Atributos importantes incluye los 100 principales atributos de visitante y su importancia relativa, mientras que Interfaz de usuario solo incluye los 10 principales atributos de visitante.

### ¿Puedo ver Personalization Insights para un intervalo de fechas personalizado?

Los informes de Personalization Insights (tanto [!UICONTROL Automated Segments] como [!UICONTROL Important Attributes]) solo están disponibles para intervalos de fechas fijos: 15 días, 30 días, 45 días, 60 días y 90 días. Estos intervalos de fechas fijos permiten que [!UICONTROL Personalization Insights] use un intervalo de datos lo suficientemente grande como para reducir la probabilidad de que obtenga información de un patrón de corta duración en su actividad. Puede seleccionar estas duraciones para cualquier fecha de finalización (mientras haya datos suficientes en la actividad para satisfacer la duración).

### ¿Cómo se crea [!UICONTROL Personalization Insights]?

[!UICONTROL Personalization Insights] se ha creado usando una técnica de Adobe con patente en trámite llamada MAGIX (Model Agnostic Globally Interpretable Explanations). Puede obtener más información sobre MAGIX en el artículo publicado por el equipo de investigación de Adobe en el [sitio web de arXiv.org](https://arxiv.org/abs/1706.07160).

### ¿Están disponibles [!UICONTROL Personalization Insights] para los objetivos de modelado basados en los ingresos o para el objetivo principal?

En este momento, [!UICONTROL Personalization Insights] solo está disponible para las actividades de objetivos de optimización de conversión. En una futura versión añadiremos compatibilidad con las actividades de optimización de los ingresos.

### ¿Qué representa la puntuación de importancia de atributo en el informe Atributos importantes?

La puntuación de importancia en la parte “Clasificación de la importancia del atributo” del informe ofrece información sobre cuáles de las variables que el algoritmo utilizó para aprender fueron más importantes al decidir el reparto de todos los visitantes entre los segmentos identificados. Se asigna una puntuación porcentual a los 100 principales atributos utilizados por el modelo.

### ¿Por qué, para un determinado segmento automatizado, algunas ofertas o experiencias con una tasa de conversión menor que otras reciben una mayor cantidad de tráfico?

Existen varias causas potenciales para que una oferta o experiencia con una tasa de conversión menor pueda tener más visitas dentro de un segmento automatizado, como las siguientes:

* Hay un número de vistas pequeño para algunas o para todas las ofertas o experiencias en un segmento automatizado concreto.
* Actividades de menor volumen en las que determinadas ofertas o experiencias no tienen modelos creados.
* Actividades de menor volumen en las que los modelos se crearon antes para algunas ofertas o experiencias. Por ejemplo, supongamos que se creó un modelo adicional el día 22 y que está viendo los datos de los días 10-24.
* Las reglas de segmentación de una oferta específica limitan a los visitantes que pueden ver cada oferta o experiencia.
* No existen intervalos de confianza en los informes de perspectivas. Sin embargo, si las tasas de conversión son lo suficientemente cercanas, el modelo podría servir tráfico para que sea más alto en la cantidad de punto, pero no son números &quot;estadísticamente diferentes&quot;.

Saber cómo funciona el modelo que proporciona tráfico puede ser útil. Cada persona se sirve en función de su perfil total. Sin embargo, los informes de perspectivas generalizan este comportamiento para hacerlo más interpretativo por parte de un humano. Como resultado, los segmentos no son mutuamente excluyentes. Esto puede generar segmentos individuales que muestren este tipo de comportamiento, porque la misma persona puede aparecer en varios segmentos.

### ¿Cuáles son las diferentes maneras de aprovechar la información en Personalization Insights?

* Descubra nuevas audiencias para segmentar: si detecta un segmento automatizado concreto que funciona especialmente bien, plantéese crear una audiencia para poder reutilizarlo en otros informes.
* Pruebe hipótesis sobre el tipo de visitantes que responderán a cada una de sus experiencias.
* Descubra qué contenido funcionó para cada tipo de visitante: ¿qué ofertas fueron las responsables de atraer a un tipo concreto de visitantes?
* Identifique el contenido de bajo rendimiento.
* Averigüe qué atributos resultaron más importantes para el aprendizaje del modelo.
* Vea qué atributos se utilizan en los modelos de personalización y qué importancia tienen.
* Identifique oportunidades para incluir nuevos puntos de datos que puede pasar a Target para profundizar en la personalización.

## Problemas conocidos

El equipo de ingeniería de [!DNL Target] está investigando actualmente el siguiente problema.

* Los nombres de segmento [!DNL Adobe Experience Platform] no se muestran en el informe [!UICONTROL Important Attributes] para las actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target] (AT). (TOP-3813)
