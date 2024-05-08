---
keywords: configuración de actividad;objetivos y configuración de A/B;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;métricas adicionales;configuración avanzada;objetivo principal;objetivo;prioridad;duración;solución de informes;audiencias para informes;Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Aprenda a utilizar el [!UICONTROL Goals and Settings] para especificar información sobre los objetivos de una actividad A/B.
title: ¿Cómo especifico los objetivos y la configuración en una? [!DNL Target] ¿Actividad A/B?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: b5f508d283390c859085d4ee52c582312085addc
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 35%

---

# Configuración y objetivos

El [!UICONTROL Goals & Settings] página en [!DNL Adobe Target] es donde se especifica información sobre los objetivos de la actividad.

La configuración disponible depende de si usa Target o [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fuente de informes.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

El [!UICONTROL Activity Settings] de la sección [!UICONTROL Goals & Settings] Esta página permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Objective] | Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a los integrantes del equipo a identificar la actividad. |
| [!UICONTROL Priority] | Según la configuración, la variable [!DNL Target] IU y opciones de [!UICONTROL Priority] variar. Puede utilizar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium], o [!UICONTROL High]o puede habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administration] (el valor predeterminado), especifique una prioridad: [!UICONTROL Low], [!UICONTROL Medium], o [!UICONTROL High].<P>Para habilitar [prioridades específicas](/help/main/administrating-target/reporting.md), haga clic en [!UICONTROL Administration] > [!UICONTROL Reporting]y, a continuación, active [!UICONTROL Enable Fine-Grained Priorities] a la posición &quot;Activado&quot;. <P>Si esta opción está habilitada, especifique un valor de 0 a 999: 0 = [!UICONTROL Low] y 999 = [!UICONTROL High]. <P>Para actividades creadas en versiones anteriores de [!DNL Target], [!UICONTROL Low] la prioridad se convierte en 0, [!UICONTROL Medium] se convierte en 5, y [!UICONTROL High] se convierte en 10. Si lo necesita, puede ajustar estos valores.<P>Nota: Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
| Duración | La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo. |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

El [!UICONTROL Reporting Settings] de la sección [!UICONTROL Goals & Settings] Esta página permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Reporting Source] | Especifique de qué datos de solución se recopilan:<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Si especifica una fuente de informes en su [configuración de cuenta](/help/main/administrating-target/reporting.md), se utiliza el origen especificado y esta configuración no es visible.<P>La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.<P>**Adobe Analytics**: consulte [Adobe Analytics como fuente de informes para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de creación de informes y las ventajas de cada una. Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], seleccione una [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad.<P>Para especificar una fuente de informes, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.<P><P>**Adobe Customer Journey Analytics**: consulte [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].<P>[!DNL Target] creación de informes en [!DNL Customer Journey Analytics] es compatible con actividades A/B con división de tráfico manual. [!UICONTROL Auto-Target] y [!UICONTROL Auto-Allocate] Las actividades A/B no pueden utilizar [!DNL Target] creación de informes en [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija un [!UICONTROL Conversion] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito. Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Nota: Si la solución de creación de informes está configurada en [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversion]. [!DNL Analytics] las métricas no se pueden seleccionar como un objetivo. Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.<P>Si está activada, la variable [!UICONTROL Estimated Value of the Conversion] campo (no disponible para el [!UICONTROL Page Score] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda.<P>Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Es distinto del comportamiento predeterminado en [!DNL Target Classic], que cuenta los visitantes como nuevos si vuelven a ver la actividad. |
| [!UICONTROL Additional Metrics] | Cree métricas de éxito adicionales. Esta configuración no está disponible si la solución de creación de informes está configurada como [!DNL Analytics]. En este caso, las métricas definidas para la variable [!DNL Analytics] grupos de informes se aplican. |
| [!UICONTROL Audiences for Reporting] | De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar información solo sobre audiencias específicas. Esta configuración no está disponible si elige [!DNL Analytics] como solución de creación de informes. La audiencia definida para [!DNL Analytics] grupo de informes aplicado. |

## Configuración avanzada   {#section_E2FE441AFB324E498793ABB025ED9974}

El [!UICONTROL Advanced Settings] de la sección [!UICONTROL Goals & Settings] Esta página permite configurar las siguientes opciones:

Para especificar la configuración avanzada, haga clic en **[!UICONTROL More]** (los puntos suspensivos verticales) y haga clic en **[!UICONTROL Advanced Settings]**, como se muestra en la siguiente ilustración.

![Menú Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

![Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de actividad podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión. Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente. Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra. El [!UICONTROL Add Dependency] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza). Para agregar una dependencia:<ul><li>Después de agregar métricas adicionales, haga clic en [!UICONTROL Advanced Settings].</li><li>Haga clic en [!UICONTROL Add Dependency] opción:</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Reached] para alternar el valor entre [!UICONTROL Reached] y[!UICONTROL  Not Reached].</li><li>Puede editar o eliminar dependencias después de añadirlas.</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:<ul><li>Seleccionar [!UICONTROL Increment Count & Keep User in Activity] para especificar cómo se incrementa el recuento.</li><li>Seleccionar [!UICONTROL Increment Count, Release User & Allow Reentry] para especificar la experiencia que el usuario ve si vuelve a entrar en la actividad.</li><li>Seleccionar [!UICONTROL Increment Count, Release User & Bar from Reentry] para especificar lo que el usuario ve en lugar del contenido de la actividad.</li></ul> |
| [!UICONTROL How will the count be incremented?] | Hay tres opciones para el aumento del recuento:<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

El [!UICONTROL Other Metadata] de la sección [!UICONTROL Goals & Settings] Esta página permite especificar cualquier información acerca de la actividad que sea útil tener disponible para el usuario u otros integrantes del equipo. Se puede cambiar el tamaño del panel Notas.|

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Configuración de actividades (3:02) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

(https://video.tv.adobe.com/v/17381?captions=spa)

### Creación de pruebas A/B (8:36) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se ve la configuración de actividades dentro del flujo de trabajo guiado de tres pasos al crear una actividad. Los objetivos y la configuración se describen a partir del minuto 5:30.

* Crear una actividad A/B en Adobe Target
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
