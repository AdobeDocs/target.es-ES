---
keywords: configuración de actividad;objetivos y configuración;multivariable;mvt
description: Aprenda a utilizar el [!UICONTROL Goals & Settings] página en [!DNL Adobe Target] para especificar información acerca de los objetivos de un [!UICONTROL Multivariate Test] Actividad de (MVT).
title: ¿Cómo especifico los objetivos y la configuración en una? [!UICONTROL Multivariate Test] ¿Actividad de (MVT)?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 41%

---

# Configuración y objetivos ([!UICONTROL Multivariate Test])

El [!UICONTROL Goals & Settings] página en [!DNL Adobe Target] es donde se introduce información acerca de los objetivos de [!UICONTROL Multivariate Test] Actividades de (MVT).

Las secciones disponibles son las siguientes:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

La configuración disponible en cada sección depende de si utiliza [!DNL Target] o [!DNL Analytics] como fuente de informes.

## Configuración de actividades {#section_DCBDC354261F420EBD4B43EA34947BAC}

Las configuraciones disponibles son las siguientes:

### Objetivo

Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a su equipo a identificar la campaña.

### Prioridad

Según la configuración, la variable [!DNL Target] IU y opciones de [!UICONTROL Priority] variar. Puede utilizar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium], o [!UICONTROL High]o puede habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

Si esta opción no está habilitada en [!UICONTROL Administration] > [!UICONTROL Reporting] (el valor predeterminado), especifique una prioridad: [!UICONTROL Low], [!UICONTROL Medium], o [!UICONTROL High].

Para habilitar prioridades específicas, haga clic en [!UICONTROL Administration] > [!UICONTROL Reporting]y, a continuación, active [!UICONTROL Enable Fine-Grained Priorities] a la posición &quot;Activado&quot;.

Si esta opción está habilitada, especifique un valor de 0 a 999:

* 0 = Bajo
* 999 = Alto

Para actividades creadas en versiones anteriores de [!DNL Target], [!UICONTROL Low] la prioridad se convierte en 0, [!UICONTROL Medium] la prioridad se convierte en 5 y [!UICONTROL High] la prioridad se convierte en 10. Si lo necesita, puede ajustar estos valores.

>[!NOTE]
>
>Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a establecer todas las prioridades en 0, 5 y 10.

### Duración

La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## Configuración de informes.  {#section_13119392051044FBA6387D9B3B1C43CF}

Las configuraciones disponibles son las siguientes:

### Fuente de informes

Especifique de qué datos de solución se recopilan:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si se especifica una solución de creación de informes en su [configuración de cuenta](/help/main/administrating-target/reporting.md), se utiliza la solución especificada y esta configuración no es visible.

La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

**[!DNL Adobe Analytics]**: consulte [[!DNL Adobe Analytics] como fuente de informes para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de creación de informes y las ventajas de cada una.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T), seleccione un [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad. Para ello, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente de los resultados. Aparece un servidor de seguimiento predeterminado en la [!UICONTROL Tracking Server] field. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

**[!DNL Adobe Customer Journey Analytics]**: consulte [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].

### Métrica de objetivo

Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija un [!UICONTROL Conversion] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito.

>[!NOTE]
>
>Si la solución de creación de informes está configurada como [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversion]. [!DNL Analytics] las métricas no se pueden seleccionar como un objetivo.

Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.

Si está activada, la variable [!UICONTROL Estimated Value of the Conversion] campo (no disponible para el [!UICONTROL Page Score] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda.

Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Este comportamiento es diferente del comportamiento predeterminado en [!DNL Target Classic], que cuenta los visitantes como nuevos si vuelven a ver la prueba.

### Métricas adicionales

Cree métricas de éxito adicionales.

Esta configuración no está disponible si la solución de creación de informes está configurada como [!DNL Analytics]. En este caso, las métricas definidas para la variable [!DNL Analytics] grupos de informes se aplican.

### Audiencias para los informes

De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar únicamente información sobre audiencias específicas.

### Configuración avanzada   {#section_E2FE441AFB324E498793ABB025ED9974}

La configuración avanzada está disponible para [!UICONTROL Multivariate Test] métricas de objetivo.

![Menú Configuración avanzada](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

#### ¿Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica?

Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión.

Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.

Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.

El [!UICONTROL Add Dependency] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).

Para agregar una dependencia:

1. Después de agregar métricas adicionales, haga clic en **[!UICONTROL Advanced Settings]**.
2. Haga clic en **[!UICONTROL Add Dependency]** opción:

   ![Agregar dependencia](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en **[!UICONTROL Reached]** para alternar el valor entre Alcanzado y No alcanzado

   ![Dependencia alcanzada](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Puede editar o eliminar dependencias después de añadirlas.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?

Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:

* [!UICONTROL Select Increment Count & Keep User in Activity] para especificar cómo se incrementa el recuento.
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] para especificar la experiencia que el usuario ve si vuelve a entrar en la actividad.
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] para especificar lo que el usuario ve en lugar del contenido de la actividad.

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

La configuración disponible es la siguiente:

### Notas

Escriba la información sobre la actividad que sea útil para el equipo. El [!UICONTROL Notes] El panel se puede cambiar de tamaño.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Creación de pruebas multivariable (9:25)

En este vídeo se muestra cómo crear una prueba multivariable con el [!DNL Target] flujo de trabajo guiado de tres pasos. Los objetivos y la configuración se describen a partir del minuto 7:00.

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)
