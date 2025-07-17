---
keywords: Segmentación;éxito;métrica de conversión;métrica de puntuación de página;métrica de vistas de página;métricas de ingresos;métrica de tiempo en el sitio;valor estimado;configuración avanzada;métricas de éxito;configuración avanzada;dependencia;dependiente;Aumentar recuento y mantener al usuario en la actividad;Aumentar recuento, liberar usuario y permitir la reentrada;Recuento de incrementos, liberar usuario y bloquear su reentrada
description: Obtenga información sobre las métricas de éxito que le ayudan a determinar el éxito de una actividad. Las métricas de éxito incluyen Conversión, Ingresos, Vistas de página, Puntuación personalizada y Tiempo en el sitio.
title: ¿Qué son las métricas de éxito?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: ad26684d40ccb5239a345da73adfa924a04189ef
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 22%

---

# [!UICONTROL Success metrics]

Las métricas de éxito de [!DNL Adobe Target] son indicadores clave que ayudan a medir el rendimiento de las actividades. Estas métricas capturan resultados comerciales importantes, como conversiones, ingresos por visitante y participación de los clientes, lo que le permite evaluar el impacto de experiencias u ofertas específicas.

Por ejemplo, puede realizar un seguimiento si una nueva promoción aumenta los ingresos por visitante o genera más elementos agregados a los carros de compras. Las métricas de éxito también ayudan a identificar problemas en los flujos de usuarios como los procesos de registro, cierre de compra o compra, a la vez que proporcionan información sobre el comportamiento general del visitante.

## Información general

En [!DNL Target], las métricas de éxito están preconfiguradas con la configuración recomendada para garantizar un sistema de informes preciso y un seguimiento eficaz.

De manera predeterminada, los eventos de conversión utilizan la configuración **[!UICONTROL Increment count & keep user in activity].** Esta configuración significa que cada visitante se cuenta como una conversión solo una vez. No se cuentan las conversiones repetidas. Estos visitantes siguen viendo el contenido de la actividad durante toda la sesión.

Para las métricas de ingresos que utilizan la misma configuración, solo el primer pedido de un visitante registra los detalles de pedido. Mientras que los pedidos subsiguientes aumentan el recuento de conversiones, no contribuyen a métricas basadas en ingresos como [!UICONTROL Revenue per Visitor (RPV)], [!UICONTROL Average Order Value (AOV)] o [!DNL Total Sales]. Estos pedidos adicionales también se excluyen del informe [!UICONTROL Order Details].

>[!NOTE]
>
>Para las actividades que usan [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), la métrica de objetivo siempre usa la configuración &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; y &quot;[!UICONTROL On Every Impression]&quot;. Estas configuraciones *no* se pueden configurar.

Las siguientes métricas de éxito se pueden configurar en la sección [!UICONTROL Reporting Settings] del [!UICONTROL Activity Settings page], en el paso [!UICONTROL Goals & Settings]:

| Métrica de éxito | Método de medición | Definición |
|--- |--- |--- |
| [!UICONTROL Con]versión | Basado en la conversión | La conversión se produce cuando un visitante realiza una acción en el sitio que haya definido, como <ul><li>Visualizó una página</li><li>Visualizó un mbox</li><li>Se hizo clic en un elemento</li></ul>Las conversiones se pueden contabilizar una vez por visitante o cada vez que un visitante completa una conversión. |
| [!UICONTROL Revenue] | Basado en la conversión | Ingresos generados por la visita. Solo puede elegir una métrica de ingresos:<ul><li>Visualizó un mbox</li></ul>Para obtener más información sobre los cambios en la interfaz de usuario [!DNL Target] actualizada en lo que respecta a las métricas de éxito de ingresos, consulte [Cambios de la interfaz de usuario relacionados con las métricas de éxito](#changes) a continuación. |
| [!UICONTROL Engagement] | Basado en la participación | Participación generada por la visita. Puede elegir entre las siguientes métricas de participación:<UL><li>Vistas de página: cada visita única se cuenta como una conversión.</li><li>[!UICONTROL Custom Scoring]: puntuación acumulada basada en el valor asignado a páginas visitadas del sitio, desde el momento en que el visitante ve por primera vez la primera solicitud de visualización de la actividad [!DNL Target].</li>[!DNL Time on Site]: tiempo empleado en la visita (en segundos) desde el momento en que el visitante ve la primera solicitud de visualización de la actividad [!DNL Target] hasta la carga de la última página con una solicitud de la sesión.</UL> |

En el caso de las métricas basadas en la participación (al contrario que las basadas en la conversión o en los ingresos), los visitantes deben volver a clasificarse para la actividad en cada visita para incrementar el recuento. La métrica asociada comienza a aumentar tras la reclasificación y se detiene al terminar la sesión del visitante. Una sesión termina tras 30 minutos de inactividad. Por lo tanto, no ve los resultados inmediatamente durante la prueba; sin embargo, todos los resultados de esa sesión están disponibles unos minutos después de la finalización de la sesión.

## Métricas de éxito personalizadas

También puede crear métricas de éxito personalizadas para adaptarse a sus necesidades comerciales.

Después de seleccionar la métrica de éxito, seleccione la acción realizada por un visitante para alcanzar el objetivo. Por ejemplo, elija una métrica de [!UICONTROL Conversion], configúrela para que se cuente una vez por visitante y, a continuación, establezca si se logra el éxito cuando un visitante ve una determinada página (o conjunto de páginas), visualiza una solicitud de [!DNL Target] específica o hace clic en un vínculo específico.

Si está habilitado, el campo [!UICONTROL Estimated Value of one conversion] (no disponible para las métricas [!UICONTROL Page Score]) proporciona un valor para el objetivo, pero no para el resto de métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda. Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

Las métricas de éxito que elija para su actividad están disponibles en la configuración del informe al ver un informe de la actividad.

Algunas métricas, como [!UICONTROL Custom Scoring] y [!UICONTROL Revenue Per Visitor], requieren una implementación personalizada que pase información, como totales e ID de pedidos.

## Configuración avanzada   {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use la configuración avanzada para administrar la forma de medir la métrica de éxito. Las opciones incluyen añadir dependencias, elegir si se debe mantener al usuario en la actividad o eliminarlo, y si se debe contar la métrica una vez por participante o en cada impresión.

Para obtener acceso a las opciones de [!UICONTROL Advanced Settings], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallListVert.svg) ) y, a continuación, haga clic en **[!UICONTROL Advanced Settings]**.

![Menú Configuración avanzada](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

Para obtener más información sobre las opciones de [!UICONTROL Advanced Settings] (&quot;[!UICONTROL What will happen after a user encounters this goal]&quot; y &quot;[!UICONTROL How will the count be incremented]&quot;), consulte [Qué sucede después de que un usuario encuentre esta métrica de objetivo](#what-happens)?

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción [!UICONTROL Advanced Settings] no está disponible. Para obtener más información, consulte [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

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
* Las actividades de [!UICONTROL Automated Personalization] liberan usuarios y reinician la actividad cuando se alcanzan las métricas de conversión, por lo que cualquier métrica que dependa de la métrica de conversión no se convierte.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo? {#what-happens}

Use la configuración avanzada para determinar qué sucede después de que un usuario llegue a la métrica de objetivo. En la tabla siguiente se muestran las opciones disponibles:

| Después de que un usuario encuentra la métrica de objetivo | Opciones |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Especifique cómo se incrementa el recuento:<ul><li>Una vez por participante (predeterminado)</li><li>En cada impresión, excluidas las actualizaciones de páginas</li><li>En cada impresión</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Seleccione la experiencia que el visitante ve si vuelve a participar en la actividad:<ul><li>Misma experiencia (predeterminado)</li><li>Una experiencia aleatoria</li><li>Una experiencia no vista</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Determine lo que el usuario ve en lugar del contenido de actividad:<ul><li>Misma experiencia, sin seguimiento (predeterminado)</li><li>Un contenido predeterminado, u otro contenido de actividad</li></ul> |

>[!NOTE]
>
>Si configura una métrica para una de las opciones [!UICONTROL Increment Count] (mencionadas anteriormente), el recuento de métricas aumenta correctamente una vez por visitante solo en el nivel de visitante. El recuento de métricas aumenta una vez por visita en cada nueva sesión a nivel de visita.

### Cómo se incrementa el recuento:

Elija el comportamiento deseado:

* Una vez por participante 
* En cada impresión (excluidas las actualizaciones de páginas)
* En cada impresión

## Problemas conocidos

* Las métricas de éxito con la opción avanzada “Cómo se incrementará el recuento” establecida en “con cada impresión” o en “con cada impresión (excluyendo actualizaciones)” no se pueden utilizar como métricas de éxito de las que dependa otra métrica.

  Cuando una métrica de éxito se establece para que se incremente con cada impresión, [!DNL Target] vuelve a contar el visitante cada vez que visita esa métrica de éxito. [!DNL Target] restablece la métrica de éxito &quot;abono&quot; a 0 para que pueda contar de nuevo la siguiente impresión. Por lo tanto, si otra métrica requiere que esta métrica se haya visto primero, [!DNL Target] nunca reconocerá que el usuario ha visto la métrica primero.

## Cambios actualizados en la IU de Target

La versión de [[!DNL Target Standard/Premium] 25.2.1](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2), lanzada el 17 de febrero de 2015, introdujo las IU de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC) actualizadas. Esta sección describe las diferencias clave entre la IU heredada y la actualizada, específicamente en lo que respecta a la configuración y administración de las métricas de éxito.

### Cambios en la IU relacionados con [!UICONTROL Revenue] métricas de éxito {#changes}

En la interfaz [!DNL Target] actualizada, se ha eliminado la lista desplegable [!UICONTROL Default View for Reporting]. Este campo era redundante, ya que anteriormente guardaba la vista de informes predeterminada en [!DNL Overview] > [!UICONTROL Reports] en la interfaz de usuario heredada.

Con la interfaz de usuario actualizada, la métrica de informes predeterminada ahora siempre está establecida en [!UICONTROL Revenue per Visitor (RPV)]. Puede personalizar la vista en la sección [!UICONTROL Reports] para mostrar las métricas que sean más relevantes para su análisis.

Este cambio no afecta a las métricas de envío. Este cambio solo afecta al filtro predeterminado que se muestra en la vista del sistema de informes. Dado que RPV es la métrica más utilizada entre los clientes, este valor predeterminado se seleccionó para optimizar los flujos de trabajo de creación de informes. Puede cambiar a otras métricas en cualquier momento dentro de la sección [!UICONTROL Reports].