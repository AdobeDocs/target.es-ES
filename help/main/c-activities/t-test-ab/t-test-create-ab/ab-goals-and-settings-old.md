---
keywords: configuración de actividad;objetivos y configuración de A/B;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;métricas adicionales;configuración avanzada;objetivo principal;objetivo;prioridad;duración;solución de informes;audiencias para informes;Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Aprenda a utilizar la página [!UICONTROL Goals and Settings] para especificar información acerca de los objetivos de una actividad A/B.
title: ¿Cómo se especifican los objetivos y la configuración en una actividad  [!DNL Target] A/B?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 33%

---

# Configuración y objetivos

En la página [!UICONTROL Goals & Settings] de [!DNL Adobe Target] se especifica información sobre los objetivos de la actividad.

La configuración disponible depende de si usa Target o [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fuente de informes.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La sección [!UICONTROL Activity Settings] de la página [!UICONTROL Goals & Settings] le permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Objective] | Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a los integrantes del equipo a identificar la actividad. |
| [!UICONTROL Priority] | Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Priority] varían. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administration] (la predeterminada), especifique una prioridad: [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High].<P>Para habilitar [prioridades específicas](/help/main/administrating-target/reporting.md), haga clic en [!UICONTROL Administration] > [!UICONTROL Reporting] y luego coloque la opción [!UICONTROL Enable Fine-Grained Priorities] en la posición &quot;Activado&quot;. <P>Si esta opción está habilitada, especifique un valor de 0 a 999: 0 = [!UICONTROL Low] y 999 = [!UICONTROL High]. <P>Para las actividades creadas en versiones anteriores de [!DNL Target], la prioridad [!UICONTROL Low] se convierte en 0, [!UICONTROL Medium] en 5 y [!UICONTROL High] en 10. Si lo necesita, puede ajustar estos valores.<P>Nota: Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
| Duración | La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora utiliza un reloj de 24 horas, siendo 00:00 la medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo. |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

La sección [!UICONTROL Reporting Settings] de la página [!UICONTROL Goals & Settings] le permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Reporting Source] | Especifique de qué datos de solución se recopilan:<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Si se especifica una fuente de informes en la [configuración de la cuenta](/help/main/administrating-target/reporting.md), se utilizará la fuente especificada y esta configuración no será visible.<P>La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.<P>**Adobe Analytics**: vea [Adobe Analytics como el Source de informes para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de informes y las ventajas de cada una. Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], selecciona un grupo de informes [!DNL Analytics] para recibir [!DNL Target] datos de actividad.<P>Para especificar una fuente de informes, primero elija una de las [!DNL Analytics] empresas a las que esté asociada su cuenta y luego seleccione el grupo de informes apropiado para la actividad. Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.<P><P>**Adobe Customer Journey Analytics**: Ver [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información acerca de la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].<P>La creación de informes de [!DNL Target] en [!DNL Customer Journey Analytics] es compatible con actividades A/B con división de tráfico manual. Las actividades A/B [!UICONTROL Auto-Target] y [!UICONTROL Auto-Allocate] no pueden usar los informes [!DNL Target] en [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija una métrica de [!UICONTROL Conversion] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito. Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Nota: Si la solución de creación de informes se establece en [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversion]. [!DNL Analytics] métricas no se pueden seleccionar como un objetivo. Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.<P>Si está habilitado, el campo [!UICONTROL Estimated Value of the Conversion] (no disponible para las métricas [!UICONTROL Page Score]) proporciona un valor para el objetivo, pero no para el resto de métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda.<P>Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Es distinto del comportamiento predeterminado en [!DNL Target Classic], que cuenta los visitantes como nuevos si vuelven a ver la actividad. |
| [!UICONTROL Additional Metrics] | Cree métricas de éxito adicionales. Esta configuración no está disponible si la solución de creación de informes está establecida en [!DNL Analytics]. En este caso, se aplican las métricas definidas para el grupo de informes [!DNL Analytics]. |
| [!UICONTROL Audiences for Reporting] | De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar información solo sobre audiencias específicas. Esta configuración no está disponible si elige [!DNL Analytics] como solución de sistema de informes. Se aplica la audiencia definida para el grupo de informes [!DNL Analytics]. |

## Configuración avanzada   {#section_E2FE441AFB324E498793ABB025ED9974}

La sección [!UICONTROL Advanced Settings] de la página [!UICONTROL Goals & Settings] le permite configurar las siguientes opciones:

Para especificar la configuración avanzada, haga clic en el icono **[!UICONTROL More]** (los puntos suspensivos verticales) y, a continuación, haga clic en **[!UICONTROL Advanced Settings]**, como se muestra en la siguiente ilustración.

![Menú Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

![Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de actividad podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión. Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente. Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra. La opción [!UICONTROL Add Dependency] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza). Para agregar una dependencia:<ul><li>Después de agregar métricas adicionales, haga clic en [!UICONTROL Advanced Settings].</li><li>Haga clic en la opción [!UICONTROL Add Dependency]:</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Reached] para alternar el valor entre [!UICONTROL Reached] y [!UICONTROL &#x200B; Not Reached].</li><li>Puede editar o eliminar dependencias después de añadirlas.</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:<ul><li>Seleccione [!UICONTROL Increment Count & Keep User in Activity] para especificar cómo se incrementa el recuento.</li><li>Seleccione [!UICONTROL Increment Count, Release User & Allow Reentry] para especificar la experiencia que el usuario verá si vuelve a entrar a la actividad.</li><li>Seleccione [!UICONTROL Increment Count, Release User & Bar from Reentry] para especificar lo que el usuario verá en lugar del contenido de la actividad.</li></ul> |
| [!UICONTROL How will the count be incremented?] | Hay tres opciones para el aumento del recuento:<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

La sección [!UICONTROL Other Metadata] de la página [!UICONTROL Goals & Settings] le permite especificar cualquier información sobre la actividad que sea útil tener disponible para usted o para otros integrantes del equipo. Se puede cambiar el tamaño del panel Notas.|

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

### Creando pruebas A/B (8:36) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se ve la configuración de actividades dentro del flujo de trabajo guiado de tres pasos al crear una actividad. Los objetivos y la configuración se discuten a partir de 5:30.

* Crear una actividad A/B en Adobe Target
* Asignar tráfico usando una división manual o una asignación automática

>[!VIDEO](https://video.tv.adobe.com/v/30133?captions=spa)
