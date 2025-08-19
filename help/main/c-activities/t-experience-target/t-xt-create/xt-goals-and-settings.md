---
keywords: configuración de actividad;objetivos y configuración de la segmentación de experiencias;objetivos y configuración de xt;segmentación de experiencias;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;configuración avanzada;objetivo principal;métricas adicionales;objetivo;prioridad;duración;solución de informes;audiencias para informes;qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Aprenda a usar la página [!UICONTROL Goals & Settings] en  [!DNL Adobe Target] para especificar información acerca de los objetivos de una actividad [!UICONTROL Experience Targeting] (XT).
title: ¿Cómo se especifica [!UICONTROL Goals & Settings] en una actividad de [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 38%

---

# Configuración y objetivos en actividades [!UICONTROL Experience Targeting] (XT)

En la página [!UICONTROL Goals & Settings] se escribe información sobre los objetivos de la prueba:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

La configuración disponible depende de si usa [!DNL Target] o [!DNL Analytics] como fuente de informes.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Las configuraciones disponibles son las siguientes:

### [!UICONTROL Objective]

Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a su equipo a identificar la campaña.

### [!UICONTROL Priority]

Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Priority] varían. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se muestra la actividad con la prioridad más alta.

Si esta opción no está habilitada en [!UICONTROL Administration] (la predeterminada), especifique una prioridad: [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High].

Para habilitar prioridades específicas, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Reporting]** y luego coloque la opción [!UICONTROL Enable Fine-Grained Priorities] en la posición &quot;Activado&quot;.

Si esta opción está habilitada, especifique un valor de 0 a 999:

* 0 = Bajo
* 999 = Alto

Para las actividades creadas en versiones anteriores de [!DNL Target], la prioridad [!UICONTROL Low] se convierte en 0, [!UICONTROL Medium] en 5 y [!UICONTROL High] en 10. Si lo necesita, puede ajustar estos valores.

>[!NOTE]
>
>Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a establecer todas las prioridades en 0, 5 y 10.

### [!UICONTROL Duration]

La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Del mismo modo, la actividad puede finalizar cuando se desactiva o puede establecer una fecha y una hora para que finalice la actividad. El selector de hora utiliza un reloj de 24 horas, siendo 00:00 la medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

Las configuraciones disponibles son las siguientes:

### [!UICONTROL Reporting Source]

Especifique de qué datos de solución se recopilan:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si especifica una solución de informes en la [configuración de la cuenta](/help/main/administrating-target/reporting.md), se utilizará la solución especificada y este ajuste no será visible.

La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

**[!DNL Adobe Analytics]**: vea [[!DNL Adobe Analytics] como fuente de informes de [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de informes y las ventajas de cada una.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T), selecciona un grupo de informes [!DNL Analytics] para recibir [!DNL Target] datos de actividad. Para ello, elija primero una de las [!DNL Analytics] empresas a la que esté asociada su cuenta y, a continuación, seleccione el grupo de informes adecuado para la actividad. Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes aún no aparece en la lista, comuníquese con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente sobre los resultados. Aparece un servidor de seguimiento predeterminado en el campo [!UICONTROL Tracking Server]. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

**[!DNL Adobe Customer Journey Analytics]**: vea [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].

### [!UICONTROL Goal Metric]

Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija una métrica de [!UICONTROL Conversion] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito.

Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Si la solución de creación de informes se establece en [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversion]. [!DNL Analytics] métricas no se pueden seleccionar como un objetivo.

Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.

Si está habilitado, el campo [!UICONTROL Estimated Value of the Conversion] (no disponible para [!UICONTROL Page Score] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] y [!UICONTROL Orders]), la estimación utiliza [!UICONTROL Revenue per Visitor]. El tipo de datos es moneda.

Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Este comportamiento es diferente del comportamiento predeterminado en [!DNL Target Classic], que contaba los visitantes como nuevos si vuelven a ver la prueba.

### [!UICONTROL Additional Metrics]

Cree métricas de éxito adicionales.

Esta configuración no está disponible si la solución de creación de informes está establecida en [!DNL Analytics]. En este caso, se aplican las métricas definidas para el grupo de informes [!DNL Analytics].

### [!UICONTROL Audiences for Reporting]

De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar únicamente información sobre audiencias específicas.

Esta configuración no está disponible si elige [!DNL Analytics] como solución de sistema de informes. Se aplica la audiencia definida para el grupo de informes [!DNL Analytics].

## [!UICONTROL Other Meta Data]

Escriba la información sobre la actividad que sea útil para el equipo. Se puede cambiar el tamaño del panel [!UICONTROL Notes].

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

La Configuración avanzada está disponible para [!UICONTROL Experience Targeting] métricas de objetivo.

![Configuración avanzada](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Si usa [!DNL Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción [!UICONTROL Advanced Settings] no está disponible.

Las configuraciones disponibles son las siguientes:

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

Utilice esta opción para contar los visitantes que alcanzan la métrica de éxito únicamente si previamente han alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión.

Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.

Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.

La opción [!UICONTROL Add Dependency] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).

Para agregar una dependencia:

1. Después de agregar métricas adicionales, haga clic en **[!UICONTROL Advanced Settings]**.
2. Haga clic **[!UICONTROL Add Dependency]**:

   ![Añadir vínculo de dependencia](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en **[!UICONTROL Reached]** para alternar el valor entre [!UICONTROL Reached] y [!UICONTROL Not Reached].

   ![Cuadro de diálogo Añadir dependencia de métricas](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Puede editar o eliminar dependencias después de añadirlas.

### [!UICONTROL What will happen after a user encounters this goal metric?]

Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:

* Seleccione [!UICONTROL Increment Count & Keep User in Activity] para especificar cómo se incrementa el recuento.
* Seleccione [!UICONTROL Increment Count, Release User & Allow Reentry] para especificar la experiencia que el usuario verá si vuelve a entrar a la actividad.
* Seleccione [!UICONTROL Increment Count, Release User & Bar from Reentry] para especificar lo que el usuario verá en lugar del contenido de la actividad.

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Vídeo de formación: Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)
