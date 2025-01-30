---
keywords: Segmentación;éxito;métrica de conversión;métrica de puntuación de página;métrica de vistas de página;métricas de ingresos;métrica de tiempo en el sitio;valor estimado;configuración avanzada;métricas de éxito;configuración avanzada;dependencia;dependiente;Aumentar recuento y mantener al usuario en la actividad;Aumentar recuento, liberar usuario y permitir la reentrada;Recuento de incrementos, liberar usuario y bloquear su reentrada
description: Obtenga información acerca de las métricas de éxito en Adobes [!DNL Target]  que le ayudarán a determinar el éxito de una actividad. Las métricas de éxito incluyen Conversión, Ingresos, Vistas de página, Puntuación personalizada y Tiempo en el sitio.
title: ¿Qué son las métricas de éxito?
feature: Success Metrics
hide: true
hidefromtoc: true
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 40%

---

# Métricas de éxito

En [!DNL Adobe Target], las métricas de éxito son parámetros usados para medir el éxito de una actividad. Las métricas de éxito incluyen medidas comerciales clave que le permiten determinar el éxito de una experiencia u oferta determinada en una actividad de [!DNL Target].

Por ejemplo, puede determinar si una oferta nueva aumenta los ingresos por visitante o si agregar un artículo a un carro de compras. Las métricas de éxito pueden resultar útiles para detectar problemas con el registro, el pedido o los canales de compra, pero también con la participación del visitante o del cliente.

## Información general

En [!DNL Target], las métricas de éxito están preconfiguradas con las opciones óptimas tanto para la generación de informes como para el seguimiento.

De manera predeterminada, los eventos de conversión se establecen en &quot;[!UICONTROL Increment count & keep user in activity]&quot;. Las conversiones se cuentan solo una vez, no se cuentan las conversiones repetidas y el visitante siempre ve el contenido de la actividad.

Las métricas de ingresos establecidas en &quot;[!UICONTROL Increment count & keep user in activity]&quot; registran los detalles de pedido únicamente para el primer pedido realizado por el mismo visitante. Todos los pedidos subsiguientes aumentan el recuento de conversiones, pero no agregarán ingresos a RPV/AOV/Sales y no se incluirán en el informe [!UICONTROL Order Details].

>[!NOTE]
>
>Para las actividades que usan [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la métrica de objetivo siempre usará la configuración &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; y &quot;[!UICONTROL On Every Impression]&quot;. Se puede configurar *no*.

Están disponibles las siguientes métricas de éxito:

| Métrica de éxito | Método de medición | Definición |
|--- |--- |--- |
| Conversión | Basado en la conversión | La conversión se produce cuando un visitante realiza una acción en el sitio que haya definido, como <ul><li>Hizo clic en un botón</li><li>Visualizó una página</li><li>Se completó una encuesta</li><li>Ha realizado una compra</li></ul>Las conversiones se pueden contabilizar una vez por visitante o cada vez que un visitante completa una conversión. |
| Ingresos | Basado en la conversión | Ingresos generados por la visita. Tiene la opción de elegir entre las siguientes métricas de ingresos:<ul><li>Ingresos por visitante (RPV)</li><li>Valor de pedido promedio (AOV)</li><li>Ventas totales</li><li>Pedidos</li></ul> |
| Vistas de páginas | Basado en la participación | Cada visita única se contabiliza como una conversión. |
| Puntuación personalizada | Basado en la participación | Puntuación agregada basada en el valor asignado a páginas visitadas del sitio, desde el momento en que el visitante ve por primera vez la primera solicitud [!DNL Target] de visualización de la actividad. |
| Tiempo en el sitio | Basado en la participación | Tiempo empleado en la visita (en segundos) desde el momento en que el visitante ve la primera solicitud de visualización de la actividad [!DNL Target] hasta la carga de la página final con una solicitud en la sesión. |

En el caso de las métricas basadas en la participación (al contrario que las basadas en la conversión o en los ingresos), los visitantes deben volver a clasificarse para la actividad en cada visita si se desea incrementar el recuento. La métrica asociada comienza a aumentar tras la reclasificación y se detiene al terminar la sesión del visitante. Una sesión termina tras 30 minutos de inactividad. Por lo tanto, no verá resultados inmediatamente durante la prueba; sin embargo, todos los resultados de esa sesión estarán disponibles unos minutos después de que finalice la sesión.

## Métricas de éxito personalizadas

También puede crear métricas de éxito personalizadas para adaptarse a sus necesidades comerciales.

Después de seleccionar la métrica de éxito, seleccione la acción realizada por un visitante para alcanzar el objetivo. Por ejemplo, elija una métrica de [!UICONTROL Conversion], configúrela para que se cuente una vez por visitante y, a continuación, establezca si se logra el éxito cuando un visitante ve una determinada página (o conjunto de páginas), visualiza una solicitud de [!DNL Target] específica o hace clic en un vínculo específico.

Si está habilitado, el campo [!UICONTROL Estimated Value of one conversion] (no disponible para las métricas [!UICONTROL Page Score]) proporciona un valor para el objetivo, pero no para el resto de métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

Las métricas de éxito que elija para la actividad estarán disponibles en la configuración de informes cuando visualice un informe de la actividad.

Algunas métricas, como [!UICONTROL Custom Scoring] y [!UICONTROL Revenue Per Visitor], requieren una implementación personalizada que pase información como totales e ID de pedidos.

## Configuración avanzada   {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use la configuración avanzada para administrar la forma de medir la métrica de éxito. Las opciones incluyen añadir dependencias, elegir si se debe mantener al usuario en la actividad o eliminarlo, y si se debe contar la métrica una vez por participante o en cada impresión.

Para obtener acceso a las opciones de [!UICONTROL Advanced Settings], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ) y, a continuación, haga clic en **[!UICONTROL Advanced Settings]**.

![Menú Configuración avanzada](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción [!UICONTROL Advanced Settings] no estará disponible. Para obtener más información, consulte [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Agregar dependencia

Puede usar la configuración avanzada para crear métricas de éxito dependientes, incrementando una métrica solo si el visitante llega a otra métrica primero.

Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta o si entra en una página concreta antes de la conversión.

La funcionalidad de dependencia *no* es compatible con lo siguiente:

* [!UICONTROL Recommendations] actividades. La funcionalidad admite los demás tipos de actividad.
* Si usa [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* El tipo de métrica &quot;Visualizó una página&quot;.
* El tipo de métrica &quot;Se hizo clic en un elemento&quot; para actividades del Compositor de experiencias visuales (VEC).

Las métricas de éxito dependientes no se convierten en los casos siguientes:

* Si se crea una dependencia circular en la que la métrica1 depende de la métrica2 y esta, a su vez, depende de aquella, ninguna de las dos se puede convertir.
* Las actividades de [!UICONTROL Automated Personalization] liberan usuarios y reinician la actividad cuando se alcanzan las métricas de conversión, por lo que las métricas que dependen de la métrica de conversión no se convertirán.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?

Use la configuración avanzada para determinar qué sucede después de que un usuario llegue a la métrica de objetivo. En la tabla siguiente se muestran las opciones disponibles:

| Después de que un usuario encuentra la métrica de objetivo | Opciones |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Especifique cómo se incrementa el recuento:<ul><li>Una vez por participante (predeterminado)</li><li>En cada impresión, excluidas las actualizaciones de páginas</li><li>En cada impresión</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Seleccione la experiencia que el visitante ve si vuelve a participar en la actividad:<ul><li>Misma experiencia (predeterminado)</li><li>Una experiencia aleatoria</li><li>Una experiencia no vista</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Determine lo que el usuario ve en lugar del contenido de actividad:<ul><li>Misma experiencia, sin seguimiento (predeterminado)</li><li>Un contenido predeterminado, u otro contenido de actividad</li></ul> |

>[!NOTE]
>
>Si configura una métrica para una de las opciones [!UICONTROL Increment Count] (mencionadas anteriormente), el recuento de métricas aumenta correctamente una vez por visitante solo en el nivel de visitante. El recuento de métricas aumenta una vez por visita en cada nueva sesión a nivel de visita.

### ¿Cómo se incrementará el recuento?

Elija el comportamiento deseado:

* Una vez por participante 
* En cada impresión (excluidas las actualizaciones de páginas)
* En cada impresión

## Problemas conocidos

* Las métricas de éxito con la opción avanzada “Cómo se incrementará el recuento” establecida en “con cada impresión” o en “con cada impresión (excluyendo actualizaciones)” no se pueden utilizar como métricas de éxito de las que dependa otra métrica.

Cuando una métrica de éxito se establece para que se incremente con cada impresión, [!DNL Target] vuelve a contar el visitante cada vez que visita esa métrica de éxito. [!DNL Target] restablece la métrica de éxito &quot;abono&quot; a 0 para que pueda contar de nuevo la siguiente impresión. Por lo tanto, si otra métrica requiere que esta métrica se haya visto primero, [!DNL Target] nunca reconocerá que el usuario ha visto la métrica primero.

## Vídeo de formación: Métricas de actividad

Este vídeo muestra cómo se utilizan las métricas de actividad.

* Qué son las métricas de “objetivo”
* Qué son y cómo compilar las métricas de conversión, ingresos y participación
* Compilar una métrica para el rastreo de clics

>[!VIDEO](https://video.tv.adobe.com/v/17380)
