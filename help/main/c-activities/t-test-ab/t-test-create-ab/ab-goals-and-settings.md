---
keywords: configuración de actividad;objetivos y configuración de A/B;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;métricas adicionales;configuración avanzada;objetivo principal;objetivo;prioridad;duración;solución de informes;audiencias para informes;Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Aprenda a utilizar el [!UICONTROL Configuración y objetivos] página en [!DNL Adobe Target] para especificar información sobre los objetivos de una actividad A/B.
title: ¿Cómo especifico los objetivos y la configuración en una? [!DNL Target] ¿Actividad A/B?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 53%

---

# Configuración y objetivos

El [!UICONTROL Objetivos y configuración] página en [!DNL Adobe Target] es donde se especifica información sobre los objetivos de la actividad.

La configuración disponible depende de si usa Target o [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fuente de informes.

## [!UICONTROL Configuración de actividades] {#section_DCBDC354261F420EBD4B43EA34947BAC}

El [!UICONTROL Configuración de actividades] de la sección [!UICONTROL Objetivos y configuración] Esta página permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Objetivo] | Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a los integrantes del equipo a identificar la actividad. |
| [!UICONTROL Prioridad] | Según la configuración, la variable [!DNL Target] IU y opciones de [!UICONTROL Prioridad] variar. Puede utilizar la configuración heredada de [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta]o puede habilitar prioridades específicas de 0 a 999.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>Si esta opción no está habilitada en [!UICONTROL Administration] (el valor predeterminado), especifique una prioridad: [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta].<P>Para habilitar [prioridades específicas](/help/main/administrating-target/reporting.md), haga clic en [!UICONTROL Administration] > [!UICONTROL Informes]y, a continuación, active [!UICONTROL Habilitar prioridades específicas] a la posición &quot;Activado&quot;. <P>Si esta opción está habilitada, especifique un valor de 0 a 999: 0 = [!UICONTROL Baja] y 999 = [!UICONTROL Alta]. <P>Para actividades creadas en versiones anteriores de [!DNL Target], [!UICONTROL Baja] la prioridad se convierte en 0, [!UICONTROL Mediana] se convierte en 5, y [!UICONTROL Alta] se convierte en 10. Si lo necesita, puede ajustar estos valores.<P>Nota: para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a fijar todas las prioridades en 0, 5 y 10. |
| Duración | La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo. |

## [!UICONTROL Configuración de informes. ] {#section_13119392051044FBA6387D9B3B1C43CF}

El [!UICONTROL Configuración de informes] de la sección [!UICONTROL Objetivos y configuración] Esta página permite configurar las siguientes opciones:

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL Fuente de informes] | Especificar si los datos se recopilan de [!DNL Adobe Target] o de [!DNL Adobe Analytics]. Consulte [Adobe Analytics como fuente de informes para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las distintas soluciones de creación de informes y las ventajas que ofrece cada una. Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], seleccione una [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad.<P>Para especificar una fuente de informes, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.<P>Si especifica una fuente de informes en la configuración de la cuenta, se utilizará la fuente especificada y este ajuste no será visible.<P>Nota: La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes. |
| [!UICONTROL Métrica de objetivo] | Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija un [!UICONTROL Conversión] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito. Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Nota: Si la solución de creación de informes está configurada en [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversión]. [!DNL Analytics]Las métricas de no se pueden seleccionar como un objetivo. Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.<P>Si está activada, la variable [!UICONTROL Valor estimado de la conversión] campo (no disponible para el [!UICONTROL Puntuación de página] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Ingresos por visitante], [!UICONTROL Valor de pedido promedio], [!UICONTROL Ventas totales], y [!UICONTROL Pedidos]), la estimación utiliza [!UICONTROL Ingresos por visitante]. El tipo de datos es moneda.<P>Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Es distinto del comportamiento predeterminado en [!DNL Target Classic], que cuenta los visitantes como nuevos si vuelven a ver la actividad. |
| [!UICONTROL Métricas adicionales] | Cree métricas de éxito adicionales. Este ajuste no está disponible si la solución de creación de informes es [!DNL Analytics]. En este caso, las métricas definidas para la variable [!DNL Analytics] grupos de informes se aplican. |
| [!UICONTROL Audiencias para los informes] | De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar información solo sobre audiencias específicas. Esta configuración no está disponible si elige [!DNL Analytics] como solución de creación de informes. La audiencia definida para [!DNL Analytics] grupo de informes aplicado. |

## Configuración avanzada   {#section_E2FE441AFB324E498793ABB025ED9974}

El [!UICONTROL Configuración avanzada] de la sección [!UICONTROL Objetivos y configuración] Esta página permite configurar las siguientes opciones:

Para especificar la configuración avanzada, haga clic en **[!UICONTROL Más]** (los puntos suspensivos verticales) y haga clic en **[!UICONTROL Configuración avanzada]**, como se muestra en la siguiente ilustración.

![Menú Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

![Configuración avanzada](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuración | Descripción |
|--- |--- |
| [!UICONTROL ¿Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica?] | Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de actividad podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión. Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente. Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra. La opción [!UICONTROL Añadir dependencia] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza). Para agregar una dependencia:<ul><li>Después de agregar métricas adicionales, haga clic en [!UICONTROL Configuración avanzada].</li><li>Haga clic en la opción [!UICONTROL Añadir dependencia]:</li><li>Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en [!UICONTROL Alcanzado] para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado].</li><li>Puede editar o eliminar dependencias después de añadirlas.</li></ul> |
| [!UICONTROL ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?] | Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:<ul><li>Seleccione [!UICONTROL Aumentar recuento y mantener el usuario en la actividad] para especificar cómo se aumenta el recuento.</li><li>Seleccione [!UICONTROL Aumentar recuento, liberar usuario y permitir la reentrada] para especificar la experiencia que el usuario ve si vuelve a entrar a la actividad.</li><li>Seleccione [!UICONTROL Aumentar recuento, liberar usuario y bloquear su reentrada] para especificar qué ve el usuario en lugar del contenido de la actividad.</li></ul> |
| [!UICONTROL ¿Cómo aumentará el recuento?] | Hay tres opciones para el aumento del recuento:<ul><li>[!UICONTROL Una vez por participante]</li><li>[!UICONTROL En cada impresión (excluidas las actualizaciones de páginas)]</li><li>[!UICONTROL En cada impresión]</li></ul> |

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

El [!UICONTROL Otros metadatos] de la sección [!UICONTROL Objetivos y configuración] Esta página permite especificar cualquier información acerca de la actividad que sea útil tener disponible para el usuario u otros integrantes del equipo. El panel Notas se puede redimensionar.|

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
