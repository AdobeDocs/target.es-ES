---
keywords: Segmentación;éxito;métrica de conversión;métrica de puntuación de página;métrica de vistas de página;métricas de ingresos;métrica de tiempo en el sitio;valor estimado;configuración avanzada;métricas de éxito;configuración avanzada;dependencia;dependiente;Aumentar recuento y mantener al usuario en la actividad;Aumentar recuento, liberar usuario y permitir la reentrada;Recuento de incrementos, liberar usuario y bloquear su reentrada
description: Obtenga información sobre las métricas de éxito en Adobes [!DNL Target] que ayudan a determinar el éxito de una actividad. Las métricas de éxito incluyen Conversión, Ingresos, Vistas de página, Puntuación personalizada y Tiempo en el sitio.
title: ¿Qué son las métricas de éxito?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 43%

---

# Métricas de éxito

Entrada [!DNL Adobe Target] las métricas de éxito son parámetros utilizados para medir el éxito de una actividad. Las métricas de éxito incluyen medidas comerciales clave que permiten determinar el éxito de una experiencia u oferta determinadas en una [!DNL Target] actividad.

Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente.

## Información general

Entrada [!DNL Target]Sin embargo, las métricas de éxito están preconfiguradas con las opciones óptimas tanto para la creación de informes como para el seguimiento.

De forma predeterminada, los eventos de conversión se establecen en &quot;[!UICONTROL Aumentar el recuento y mantener al usuario en la actividad].&quot; Las conversiones se cuentan solo una vez, no se cuentan las conversiones repetidas y el visitante siempre ve el contenido de la actividad.

Métricas de ingresos configuradas como &quot;[!UICONTROL Aumentar el recuento y mantener al usuario en la actividad]&quot; registrar detalles de pedidos solo para el primer pedido realizado por el mismo visitante. Todos los pedidos subsiguientes aumentan el recuento de conversiones, pero no añaden ingresos a RPV/AOV/Sales y no se incluyen en la [!UICONTROL Detalles del pedido] informe.

>[!NOTE]
>
>Para actividades que utilizan [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la métrica de objetivo siempre utilizará el valor &quot;[!UICONTROL Aumentar recuento y mantener el usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]Configuración de &quot;. Esto es *no* configurable.

Están disponibles las siguientes métricas de éxito:

| Métrica de éxito | Método de medición | Definición |
|--- |--- |--- |
| Conversión | Basado en la conversión | La conversión se produce cuando un visitante realiza una acción en el sitio que haya definido, como <ul><li>Hizo clic en un botón</li><li>Visualizó una página</li><li>Se completó una encuesta</li><li>Ha realizado una compra</li></ul>Las conversiones se pueden contabilizar una vez por visitante o cada vez que un visitante completa una conversión. |
| Ingresos | Basado en la conversión | Ingresos generados por la visita. Tiene la opción de elegir entre las siguientes métricas de ingresos:<ul><li>Ingresos por visitante (RPV)</li><li>Valor de pedido promedio (AOV)</li><li>Ventas totales</li><li>Pedidos</li></ul> |
| Vistas de páginas | Basado en la participación | Cada visita única se contabiliza como una conversión. |
| Puntuación personalizada | Basado en la participación | Puntuación agregada basada en el valor asignado a páginas visitadas del sitio, desde el momento en que el visitante ve por primera vez la primera visualización de la actividad [!DNL Target] solicitud. |
| Tiempo en el sitio | Basado en la participación | Tiempo empleado en la visita (en segundos) desde el momento en que el visitante ve la primera visualización de la actividad [!DNL Target] a la carga de la página final con una solicitud en la sesión. |

En el caso de las métricas basadas en la participación (al contrario que las basadas en la conversión o en los ingresos), los visitantes deben volver a clasificarse para la actividad en cada visita si se desea incrementar el recuento. La métrica asociada comienza a aumentar tras la reclasificación y se detiene al terminar la sesión del visitante. Una sesión termina tras 30 minutos de inactividad. Por lo tanto, no verá resultados inmediatamente durante la prueba; sin embargo, todos los resultados de esa sesión estarán disponibles unos minutos después de que finalice la sesión.

## Métricas de éxito personalizadas

También puede crear métricas de éxito personalizadas para adaptarse a sus necesidades comerciales.

Después de seleccionar la métrica de éxito, seleccione la acción realizada por un visitante para alcanzar el objetivo. Por ejemplo, elija un [!UICONTROL Conversión] , configúrela para que se cuente una vez por visitante y, a continuación, establezca si el éxito se logra cuando un visitante ve una página determinada (o un conjunto de páginas), ve una página específica [!DNL Target] o hace clic en un vínculo específico.

Si está activada, la variable [!UICONTROL Valor estimado de una conversión] campo (no disponible para el [!UICONTROL Puntuación de página] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Ingresos por visitante], [!UICONTROL Valor de pedido promedio], [!UICONTROL Ventas totales], y [!UICONTROL Pedidos]), la estimación utiliza [!UICONTROL Ingresos por visitante]. El tipo de datos es moneda. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

Las métricas de éxito que elija para la actividad estarán disponibles en la configuración de informes cuando visualice un informe de la actividad.

Algunas métricas, como [!UICONTROL Puntuación personalizada] y [!UICONTROL Ingresos por visitante], requieren una implementación personalizada que pase información como los totales y los ID de pedidos.

## Configuración avanzada   {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use la configuración avanzada para administrar la forma de medir la métrica de éxito. Las opciones incluyen añadir dependencias, elegir si se debe mantener al usuario en la actividad o eliminarlo, y si se debe contar la métrica una vez por participante o en cada impresión.

Para acceder a [!UICONTROL Configuración avanzada] , haga clic en el botón **[!UICONTROL elipses verticales]** > **[!UICONTROL Configuración avanzada]**.

![Menú Configuración avanzada](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. El [!UICONTROL Configuración avanzada] Esta opción no estará disponible. Para obtener más información, consulte [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Agregar dependencia

Puede usar la configuración avanzada para crear métricas de éxito dependientes, incrementando una métrica solo si el visitante llega a otra métrica primero.

![Agregar dependencia](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta o si entra en una página concreta antes de la conversión.

La funcionalidad de dependencia es *no* compatible con lo siguiente:

* Actividades de [!UICONTROL Recommendations. ] La funcionalidad admite los demás tipos de actividad.
* Si utiliza [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* El tipo de métrica &quot;Visualizó una página&quot;.
* El tipo de métrica &quot;Se hizo clic en un elemento&quot; para actividades del Compositor de experiencias visuales (VEC).

Las métricas de éxito dependientes no se convierten en los casos siguientes:

* Si se crea una dependencia circular en la que la métrica1 depende de la métrica2 y esta, a su vez, depende de aquella, ninguna de las dos se puede convertir.
* Las actividades de Personalización automatizada liberan usuarios y reanudan la actividad cuando se alcanzan las métricas de conversión, de modo que no se convierta ninguna métrica que dependa de la métrica de conversión.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?

Use la configuración avanzada para determinar qué sucede después de que un usuario llegue a la métrica de objetivo. En la tabla siguiente se muestran las opciones disponibles:

| Después de que un usuario encuentra la métrica de objetivo | Opciones |
|--- |--- |
| [!UICONTROL Aumentar recuento y mantener el usuario en la actividad] | Especifique cómo se incrementa el recuento:<ul><li>Una vez por participante  (predeterminada)</li><li>En cada impresión, excluidas las actualizaciones de páginas</li><li>En cada impresión</li></ul> |
| [!UICONTROL Aumentar recuento, liberar usuario y permitir la reentrada] | Seleccione la experiencia que el visitante ve si vuelve a participar en la actividad:<ul><li>La misma experiencia  (predeterminada)</li><li>Una experiencia aleatoria</li><li>Una experiencia no vista</li></ul> |
| [!UICONTROL Aumentar recuento, liberar usuario y bloquear su reentrada] | Determine lo que el usuario ve en lugar del contenido de actividad:<ul><li>La misma experiencia, sin seguimiento  (predeterminada)</li><li>Un contenido predeterminado, u otro contenido de actividad</li></ul> |

>[!NOTE]
>
>Si configura una métrica para una de las [!UICONTROL Aumentar recuento] opciones (mencionadas anteriormente), el recuento de métricas aumenta correctamente una vez por visitante solo en el nivel de visitante. El recuento de métricas aumenta una vez por visita en cada nueva sesión a nivel de visita.

### ¿Cómo se incrementará el recuento?

Elija el comportamiento deseado:

* Una vez por participante 
* En cada impresión (excluidas las actualizaciones de páginas)
* En cada impresión

## Problemas conocidos

* Las métricas de éxito con la opción avanzada “Cómo se incrementará el recuento” establecida en “con cada impresión” o en “con cada impresión (excluyendo actualizaciones)” no se pueden utilizar como métricas de éxito de las que dependa otra métrica.

Cuando una métrica de éxito se configura para que se incremente con cada impresión, [!DNL Target] vuelve a contar el visitante cada vez que visita esta métrica de éxito. [!DNL Target]A continuación,  restablece la métrica de éxito “abono” a 0 para que pueda contar de nuevo la siguiente impresión. Por lo tanto, si otra métrica requiere que esta métrica se haya visto primero, [!DNL Target] nunca reconoce que el usuario ha visto la primera métrica.

## Vídeo de formación: Métricas de actividad

Este vídeo muestra cómo se utilizan las métricas de actividad.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de Conversión, Ingresos y Participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
