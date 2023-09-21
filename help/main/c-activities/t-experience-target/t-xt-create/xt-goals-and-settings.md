---
keywords: configuración de actividad;objetivos y configuración de la segmentación de experiencias;objetivos y configuración de xt;segmentación de experiencias;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;configuración avanzada;objetivo principal;métricas adicionales;objetivo;prioridad;duración;solución de informes;audiencias para informes;qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Aprenda a utilizar el [!UICONTROL Objetivos y configuración] página en [!DNL Adobe Target] para especificar información acerca de los objetivos de un [!UICONTROL Segmentación de experiencias] Actividad (XT).
title: ¿Cómo se especifica? [!UICONTROL Objetivos y configuración] en un [!UICONTROL Segmentación de experiencias] ¿Actividad?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 52%

---

# Configuración y objetivos en [!UICONTROL Segmentación de experiencias] Actividades (XT)

El [!UICONTROL Objetivos y configuración] es donde se introduce información sobre los objetivos de la prueba:

* [!UICONTROL Configuración de actividades]
* [!UICONTROL Configuración de informes. ]
* [!UICONTROL Otros metadatos]

La configuración disponible depende de si usa [!DNL Target] o [!DNL Analytics] como fuente de informes.

## [!UICONTROL Configuración de actividades] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Las configuraciones disponibles son las siguientes:

### [!UICONTROL Objetivo]

Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a su equipo a identificar la campaña.

### [!UICONTROL Prioridad]

Según la configuración, la variable [!DNL Target] IU y opciones de [!UICONTROL Prioridad] variar. Puede utilizar la configuración heredada de [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta]o puede habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se muestra la actividad con la prioridad más alta.

Si esta opción no está habilitada en [!UICONTROL Administration] (el valor predeterminado), especifique una prioridad: [!UICONTROL Baja], [!UICONTROL Mediana], o [!UICONTROL Alta].

Para habilitar prioridades específicas, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Informes]** y, a continuación, active [!UICONTROL Habilitar prioridades específicas] a la posición &quot;Activado&quot;.

Si esta opción está habilitada, especifique un valor de 0 a 999:

* 0 = Bajo
* 999 = Alto

Para actividades creadas en versiones anteriores de [!DNL Target], [!UICONTROL Baja] la prioridad se convierte en 0, [!UICONTROL Mediana] se convierte en 5, y [!UICONTROL Alta] se convierte en 10. Si lo necesita, puede ajustar estos valores.

>[!NOTE]
>
>Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a establecer todas las prioridades en 0, 5 y 10.

### [!UICONTROL Duración]

La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Del mismo modo, la actividad puede finalizar cuando se desactiva o puede establecer una fecha y una hora para que finalice la actividad. El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## [!UICONTROL Configuración de informes. ] {#section_13119392051044FBA6387D9B3B1C43CF}

Las configuraciones disponibles son las siguientes:

### [!UICONTROL Fuente de informes]

Especificar si los datos se recopilan de [!DNL Target] o de [!DNL Adobe Analytics]. Consulte [Adobe Analytics como fuente de informes para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las distintas soluciones de creación de informes y las ventajas que ofrece cada una.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T), seleccione un [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad. Para ello, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente de los resultados. Aparece un servidor de seguimiento predeterminado en la [!UICONTROL Servidor de seguimiento] field. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

Si especifica una solución de creación de informes en la configuración de la cuenta, se utilizará la solución especificada y este ajuste no será visible.

>[!NOTE]
>
>La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

### [!UICONTROL Métrica de objetivo]

Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija un [!UICONTROL Conversión] y, a continuación, establezca los parámetros que determinan cuándo se logra el éxito.

Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Si la solución de creación de informes está configurada como [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversión]. [!DNL Analytics]Las métricas de no se pueden seleccionar como un objetivo.

Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.

Si está activada, la variable [!UICONTROL Valor estimado de la conversión] campo (no disponible para [!UICONTROL Puntuación de página] métricas) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Ingresos por visitante], [!UICONTROL Valor de pedido promedio], [!UICONTROL Ventas totales], y [!UICONTROL Pedidos]), la estimación utiliza [!UICONTROL Ingresos por visitante]. El tipo de datos es moneda.

Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Este comportamiento es diferente del comportamiento predeterminado en [!DNL Target Classic], que contaba a los visitantes como nuevos si volvían a ver la prueba.

### [!UICONTROL Métricas adicionales]

Cree métricas de éxito adicionales.

Este ajuste no está disponible si la solución de creación de informes es [!DNL Analytics]. En este caso, las métricas definidas para la variable [!DNL Analytics] grupos de informes se aplican.

### [!UICONTROL Audiencias para los informes]

De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar únicamente información sobre audiencias específicas.

Esta configuración no está disponible si elige [!DNL Analytics] como solución de creación de informes. La audiencia definida para [!DNL Analytics] grupo de informes aplicado.

## [!UICONTROL Otros metadatos]

Escriba la información sobre la actividad que sea útil para el equipo. El [!UICONTROL Notas] El panel se puede cambiar de tamaño.

## [!UICONTROL Configuración avanzada] {#section_E2FE441AFB324E498793ABB025ED9974}

La configuración avanzada está disponible para [!UICONTROL Segmentación de experiencias] métricas de objetivo.

![Configuración avanzada](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Si usa [!DNL Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. El [!UICONTROL Configuración avanzada] La opción no está disponible.

Las configuraciones disponibles son las siguientes:

### [!UICONTROL ¿Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica?]

Utilice esta opción para contar los visitantes que alcanzan la métrica de éxito únicamente si previamente han alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión.

Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.

Debe definir ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.

La opción [!UICONTROL Añadir dependencia] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).

Para agregar una dependencia:

1. Después de agregar métricas adicionales, haga clic en **[!UICONTROL Configuración avanzada]**.
2. Haga clic en **[!UICONTROL Añadir dependencia]**:

   ![Añadir vínculo de dependencia](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y, a continuación, haga clic en **[!UICONTROL Alcanzado]** para alternar el valor entre [!UICONTROL Alcanzado] y [!UICONTROL No alcanzado].

   ![Cuadro de diálogo Añadir dependencia de métricas](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Puede editar o eliminar dependencias después de añadirlas.

### [!UICONTROL ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?]

Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:

* Seleccione [!UICONTROL Aumentar recuento y mantener el usuario en la actividad] para especificar cómo se aumenta el recuento.
* Seleccione [!UICONTROL Aumentar recuento, liberar usuario y permitir la reentrada] para especificar la experiencia que el usuario ve si vuelve a entrar a la actividad.
* Seleccione [!UICONTROL Aumentar recuento, liberar usuario y bloquear su reentrada] para especificar qué ve el usuario en lugar del contenido de la actividad.

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Vídeo de formación: Configuración de actividades (3:02)

Este vídeo incluye información sobre la configuración de las actividades.

* Establecer un objetivo para la actividad
* Fijar el nivel de prioridad de las actividades
* Programar las horas de inicio y fin de las actividades
* Añadir audiencias para los informes a fin de crear filtros de informes
* Escribir notas en las actividades

>[!VIDEO](https://video.tv.adobe.com/v/17381)
