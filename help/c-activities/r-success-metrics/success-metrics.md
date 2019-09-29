---
description: En Target Standard, las métricas de éxito están preconfiguradas tanto para la generación de informes como para el seguimiento.
keywords: Segmentación;éxito;métrica de conversión;métrica de puntuación de página;métrica de vistas de página;métricas de ingresos;métrica de tiempo en el sitio;valor estimado;configuración avanzada
seo-description: En Target Standard, las métricas de éxito están preconfiguradas tanto para la generación de informes como para el seguimiento.
seo-title: Métricas de éxito
solution: Target
title: Métricas de éxito
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Métricas de éxito{#success-metrics}

En Target Standard, las métricas de éxito están preconfiguradas tanto para la generación de informes como para el seguimiento.

Las métricas de éxito son parámetros usados para medir el éxito de una actividad. Las métricas de éxito incluyen medidas comerciales clave que permiten determinar el éxito de una experiencia u oferta determinada en una actividad de Target. Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente.

De igual manera que hace [!DNL Target Standard] para simplificar la creación de pruebas, la aplicación ajusta algunas de las opciones que se configuraban de forma manual en [!DNL Target Classic]. Por ejemplo, las métricas de éxito están preconfiguradas con las opciones óptimas.

De forma predeterminada, los eventos de conversión se establecen en “se cuenta una vez y se mantiene al participante en la actividad” en [!DNL Target Standard]. Las conversiones se cuentan una única vez, no se cuentan las conversiones repetidas y el visitante siempre ve el contenido de la prueba.

Las métricas de ingresos establecidas en “Aumentar recuento y mantener al usuario en la actividad” registran los detalles de pedido únicamente para el primer pedido realizado por el mismo visitante. Todos los pedidos posteriores aumentan el contador de conversión, pero no añaden ingresos a RPV/AOV/Sales y no se incluyen en el informe Detalles del pedido.

Están disponibles las siguientes métricas de éxito:

| Métrica de éxito | Método de medición | Definición |
|--- |--- |--- |
| Conversión | Basado en la conversión | Se produce una conversión cuando un visitante realiza en su sitio una acción que usted ha definido (hacer clic en un botón, visualizar una página, completar una encuesta o realizar una compra). Las conversiones se pueden contabilizar una vez por visitante o cada vez que un visitante completa una conversión. |
| Ingresos | Basado en la conversión | Ingresos generados por la visita. Tiene la opción de elegir entre las siguientes métricas de ingresos:<ul><li>Ingresos por visitante (RPV)</li><li>Valor de pedido promedio (AOV)</li><li>Ventas totales</li></ul> |
| Vistas de páginas | Basado en la participación | Cada visita única se contabiliza como una conversión. |
| Tiempo en el sitio | Basado en la participación | El tiempo invertido en la visita (en segundos) desde el momento en el que el visitante ve el primer mbox de visualización de la actividad hasta que se cargue la última página de la sesión que tenga un mbox. |
| Puntuación personalizada | Basado en la participación | Se ha añadido una puntuación basada en el valor asignado a páginas visitadas en el sitio, desde el punto en que el visitante ve por primera vez el primer mbox de visualización de la actividad. |

En el caso de las métricas basadas en la participación (al contrario que las basadas en la conversión o en los ingresos), los visitantes deben volver a clasificarse para la actividad en cada visita si se desea incrementar el recuento. La métrica asociada comienza a aumentar tras la reclasificación y se detiene al terminar la sesión del visitante. Una sesión termina tras 30 minutos de inactividad. Por lo tanto, no verá los resultados inmediatamente durante las pruebas, pero todos los resultados estarán disponibles pocos minutos después de haber terminado la sesión.

También puede crear métricas de éxito personalizadas para adaptarse a sus necesidades comerciales.

Después de seleccionar la métrica de éxito, seleccione la acción realizada por un visitante para alcanzar el objetivo. Por ejemplo, elija una métrica de conversión, configúrela para que sea contabilizada una vez por visitante y, a continuación, establezca si desea que el éxito se alcance cuando un visitante visite una página determinada (o un conjunto de páginas), un mbox específico o bien haga clic en un vínculo concreto.

Si está habilitado, el valor estimado de un campo de conversión (no disponible para la métrica Puntuación de página) proporciona un valor para el objetivo, pero no para el resto de las métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos (Ingresos por visitante, Valor de pedido promedio, Ventas totales y Pedidos), el cálculo usa Ingresos por visitante. El tipo de datos es moneda. Para obtener más información, consulte [Alza estimada en ingresos](../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE).

Las métricas de éxito que elija para la actividad estarán disponibles en la configuración de informes cuando visualice un informe de la actividad.

Algunas métricas, como Puntuación personalizada e Ingresos por visitante, requieren una implementación personalizada que transfiera información, como totales de pedidos e ID de pedidos.

## Configuración avanzada {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use la configuración avanzada para administrar la forma de medir la métrica de éxito. Las opciones incluyen contar la métrica por impresión o una vez por visitante, y elegir si conservar el usuario en la actividad o quitarlo.

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no estará disponible.

![Menú desplegable Configuración avanzada](/help/c-activities/r-success-metrics/assets/Menu_AdvancedSettings.png)

También puede usar la configuración avanzada para crear métricas de éxito dependientes, incrementando una métrica solo si el visitante llega a otra métrica primero.

![Agregar dependencia](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta o si entra en una página concreta antes de la conversión.

Las métricas de éxito dependientes se admiten en las actividades de pruebas A/B, Personalización automatizada, Segmentación de experiencias y Pruebas multivariable. Las actividades de Recommendations no admiten actualmente métricas de éxito dependientes.

>[!NOTE]
>
>Las métricas de éxito dependientes no se convierten en los casos siguientes:

* Si se crea una dependencia circular en la que la métrica1 depende de la métrica2 y esta, a su vez, depende de aquella, ninguna de las dos se puede convertir.
* Las actividades de Personalización automatizada liberan usuarios y reanudan la actividad cuando se alcanzan las métricas de conversión, de modo que no se convierta ninguna métrica que dependa de la métrica de conversión.

Use la configuración avanzada para determinar qué sucede después de que un usuario llegue a la métrica de objetivo. En la tabla siguiente se muestran las opciones disponibles.

| Después de que un usuario encuentra la métrica de objetivo | Opciones |
|--- |--- |
| Incremente el recuento y conserve el usuario en la actividad | Especifique cómo se incrementa el recuento:<ul><li>Una vez por participante (predeterminada)</li><li>En cada impresión, excluidas las actualizaciones de páginas</li><li>En cada impresión</li></ul> |
| Incremente el recuento, libere al usuario y permita que vuelva a participar | Seleccione la experiencia que el visitante ve si vuelve a participar en la actividad:<ul><li>La misma experiencia (predeterminada)</li><li>Una experiencia aleatoria</li><li>Una experiencia no vista</li></ul> |
| Incremente el recuento, libere al usuario y prohíba que el usuario vuelva a participar | Determine lo que el usuario ve en lugar del contenido de actividad:<ul><li>La misma experiencia, sin seguimiento (predeterminada)</li><li>Un contenido predeterminado, u otro contenido de actividad</li></ul> |

## Vídeo de formación: Métricas de actividad

Este vídeo muestra cómo se utilizan las métricas de actividad.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de conversión, ingresos y participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=spa)