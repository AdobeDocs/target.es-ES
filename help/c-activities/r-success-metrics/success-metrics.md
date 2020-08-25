---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings;dependency;dependant;Increment Count & Keep User in Activity;Increment Count, Release user, & Allow Reentry;increment Count, Release User, & Bar from Reentry
description: En Adobe Target, las métricas de éxito son parámetros utilizados para medir el éxito de una actividad. Las métricas de éxito incluyen medidas comerciales clave que permiten determinar el éxito de una experiencia u oferta determinada en una actividad de Target.
title: Métricas de éxito en Adobe Target
feature: success metrics
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 7078d8b613a0ba2ebad5a3698f72695d5dc3c93d
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 47%

---


# Métricas de éxito{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente.

## Información general

En [!DNL Target]realidad, las métricas de éxito están preconfiguradas con las opciones óptimas tanto para fines de sistema de informes como de seguimiento.

De forma predeterminada, los eventos de conversión se establecen en &quot;[!UICONTROL Aumentar recuento y mantener al usuario en actividad]&quot;. Las conversiones se cuentan una sola vez, no se cuentan las conversiones repetidas y el visitante siempre ve el contenido de la actividad.

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>El comportamiento predeterminado para actividades que utilizan [Analytics como origen](/help/c-integrating-target-with-mac/a4t/a4t.md) de sistema de informes (A4T) es &quot;[!UICONTROL Aumentar recuento y mantener al usuario en actividad]&quot; con &quot;[!UICONTROL Una vez por visitante]&quot;.

Están disponibles las siguientes métricas de éxito:

| Métrica de éxito | Método de medición | Definición |
|--- |--- |--- |
| Conversión | Basado en la conversión | La conversión se produce cuando un visitante realiza una acción en el sitio que usted ha definido, como <ul><li>Haga clic en un botón</li><li>Visualizó una página</li><li>Se completó una encuesta</li><li>Se realizó una compra</li></ul>Una conversión se puede contar una vez por visitante o cada vez que un visitante completa una conversión. |
| Ingresos | Basado en la conversión | Ingresos generados por la visita. Tiene la opción de elegir entre las siguientes métricas de ingresos:<ul><li>Ingresos por visitante (RPV)</li><li>Valor de pedido promedio (AOV)</li><li>Ventas totales</li><li>Pedidos</li></ul> |
| Vistas de páginas | Basado en la participación | Cada visita única se contabiliza como una conversión. |
| Puntuación personalizada | Basado en la participación | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| Tiempo en el sitio | Basado en la participación | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

En el caso de las métricas basadas en la participación (al contrario que las basadas en la conversión o en los ingresos), los visitantes deben volver a clasificarse para la actividad en cada visita si se desea incrementar el recuento. La métrica asociada comienza a aumentar tras la reclasificación y se detiene al terminar la sesión del visitante. Una sesión termina tras 30 minutos de inactividad. Por lo tanto, no verá los resultados inmediatamente durante la prueba; sin embargo, todos los resultados de esa sesión están disponibles en los pocos minutos posteriores a la finalización de la sesión.

## Métricas de éxito personalizadas

También puede crear métricas de éxito personalizadas para adaptarse a sus necesidades comerciales.

Después de seleccionar la métrica de éxito, seleccione la acción realizada por un visitante para alcanzar el objetivo. For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda. Para obtener más información, consulte [Alza estimada en ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

Las métricas de éxito que elija para la actividad estarán disponibles en la configuración de informes cuando visualice un informe de la actividad.

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## Configuración avanzada {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use la configuración avanzada para administrar la forma de medir la métrica de éxito. Las opciones incluyen la adición de dependencias, la elección de mantener al usuario en la actividad o eliminarlo, y la contabilización de la métrica una vez por visitante o en cada impresión.

Para acceder a las opciones de Configuración [!UICONTROL avanzada, haga clic en las elipses] **[!UICONTROL verticales > Configuración]** **** avanzada.

![Menú Configuración avanzada](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

### Añadir dependencia

Puede utilizar la configuración avanzada para crear métricas de éxito dependientes, incrementando una métrica solo si un visitante alcanza primero otra métrica.

![Agregar dependencia](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta o si entra en una página concreta antes de la conversión.

Dependency functionality is *not* supported for the following:

* [!UICONTROL Actividades de Recommendations. ] La funcionalidad admite los demás tipos de actividad.
* If you use [Analytics as your reporting source](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* El tipo de métrica “Visualizó una página”.
* El tipo de métrica “Se hizo clic en un elemento” para actividades del Compositor de experiencias visuales (VEC).

Las métricas de éxito dependientes no se convierten en los casos siguientes:

* Si se crea una dependencia circular en la que la métrica1 depende de la métrica2 y esta, a su vez, depende de aquella, ninguna de las dos se puede convertir.
* Las actividades de Personalización automatizada liberan usuarios y reanudan la actividad cuando se alcanzan las métricas de conversión, de modo que no se convierta ninguna métrica que dependa de la métrica de conversión.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?

Use la configuración avanzada para determinar qué sucede después de que un usuario llegue a la métrica de objetivo. En la tabla siguiente se muestran las opciones disponibles:

| Después de que un usuario encuentra la métrica de objetivo | Opciones |
|--- |--- |
| [!UICONTROL Aumentar recuento y mantener el usuario en la actividad] | Especifique cómo se incrementa el recuento:<ul><li>Una vez por participante  (predeterminada)</li><li>En cada impresión, excluidas las actualizaciones de páginas</li><li>En cada impresión</li></ul> |
| [!UICONTROL Aumentar recuento, liberar usuario y permitir reentrada] | Seleccione la experiencia que el visitante ve si vuelve a participar en la actividad:<ul><li>La misma experiencia  (predeterminada)</li><li>Una experiencia aleatoria</li><li>Una experiencia no vista</li></ul> |
| [!UICONTROL Aumentar recuento, liberar usuario y bloquear la reentrada] | Determine lo que el usuario ve en lugar del contenido de actividad:<ul><li>La misma experiencia, sin seguimiento  (predeterminada)</li><li>Un contenido predeterminado, u otro contenido de actividad</li></ul> |

>[!NOTE]
>
>Si configura una métrica en una de las opciones [!UICONTROL Aumentar recuento] (mencionadas anteriormente), el recuento de métricas se incrementa correctamente una vez por visitante solo en el nivel de visitante. El recuento de métricas aumenta una vez por visita para cada nueva sesión en el nivel de visita.

### Cómo se incrementará el recuento:

Elija el comportamiento que desee:

* Una vez por participante 
* En cada impresión (excluyendo actualizaciones de página)
* En cada impresión

## Vídeo de formación: Métricas de actividad

Este vídeo muestra cómo se utilizan las métricas de actividad.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de conversión, ingresos y participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)