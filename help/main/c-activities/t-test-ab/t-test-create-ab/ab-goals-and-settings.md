---
keywords: configuración de actividad;objetivos y configuración de A/B;configuración de informes;métricas de objetivo;métricas de éxito;métricas de éxito dependientes;métricas adicionales;configuración avanzada;objetivo principal;objetivo;prioridad;duración;solución de informes;públicos para informes;Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica;Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo;notas
description: Descubra cómo usar la página [!UICONTROL Objetivos y configuración] para definir los objetivos de la actividad A/B.
title: ¿Cómo se especifican los objetivos y la configuración en una actividad A/B de [!DNL Target]?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
TQID: 'https://experienceleague.adobe.com/X3JDvfXDHM2rAOodEY5N9TVO-tBpz4vNDUvhOpC0XZ4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: abab6b3e464bb9f294e9c3c455dca1f57bb0d458
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 24%
---
# Configuración y objetivos {#ab-goals-and-settings}

>[!BEGINSHADEBOX]

**En esta página:** Descubra lo que puede establecer en la página **[!UICONTROL Objetivos y configuración]** de una actividad A/B, de segmentación de experiencias (XT) o de prueba multivariable (MVT): la configuración de la actividad, la configuración de informes, la configuración avanzada y las notas.

>[!ENDSHADEBOX]

En la página **[!UICONTROL Objetivos y configuración]** de [!DNL Adobe Target] se especifica información sobre los objetivos de la actividad.

La configuración disponible depende de si usa Target o [Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

La misma configuración se aplica a las actividades [!UICONTROL Segmentación de experiencias] (XT) y [!UICONTROL Prueba multivariada] (MVT), excepto a la [Metodología estadística](#section_statistical-methodology), que solo está disponible para actividades A/B.

* [Configuración de actividades](#section_DCBDC354261F420EBD4B43EA34947BAC): objetivo, prioridad y duración
* [Configuración de informes](#section_13119392051044FBA6387D9B3B1C43CF): fuente de informes, métrica de objetivo, métricas adicionales y audiencias
* [Configuración avanzada](#section_E2FE441AFB324E498793ABB025ED9974): dependencias y lo que sucede después de que un visitante alcance la meta
* [Metodología estadística](#section_statistical-methodology): cómo se analizan los resultados
* [Otros metadatos](#section_2E8917BEFB954480A4206B9E9E917F80): notas

## [!UICONTROL Configuración de actividades] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La sección **[!UICONTROL Configuración de actividad]** de la página **[!UICONTROL Objetivos y configuración]** le permite configurar las siguientes opciones.

![](../../assets/goals-ab-1.png)

### Objetivo {#objective}

Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a los integrantes del equipo a identificar la actividad.

### Prioridad {#priority}

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con el mismo público. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de **[!UICONTROL Prioridad]** varían:

* **Prioridades heredadas (predeterminado):** Si esta opción no está habilitada en **[!UICONTROL Administración]** (la predeterminada), especifique una prioridad de **[!UICONTROL Baja]**, **[!UICONTROL Medium]** o **[!UICONTROL Alta]**.
* **Prioridades específicas:** Especifique un valor de 0 a 999, donde 0 = **[!UICONTROL Bajo]** y 999 = **[!UICONTROL Alto]**.

  Para habilitar [prioridades específicas](/help/main/administrating-target/reporting.md), acceda a **[!UICONTROL Administración]** > **[!UICONTROL Informes]** y luego cambie la opción **[!UICONTROL Habilitar prioridades específicas]**.

Para las actividades creadas en versiones anteriores de [!DNL Target], la prioridad **[!UICONTROL Low]** se convierte en 0, **[!UICONTROL Medium]** se convierte en 5 y **[!UICONTROL High]** se convierte en 10. Si lo necesita, puede ajustar estos valores.

>[!NOTE]
>
>Para deshabilitar las prioridades específicas después de usarlas, hay que volver a fijar todas las prioridades en 0, 5 y 10.

### Duración {#duration}

La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora.

El selector de hora usa un reloj de 24 horas, donde 00:00 equivale a medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## [!UICONTROL Configuración de informes] {#section_13119392051044FBA6387D9B3B1C43CF}

La sección **[!UICONTROL Configuración de informes]** de la página **[!UICONTROL Objetivos y configuración]** le permite configurar las siguientes opciones.

![](../../assets/goals-ab-2.png)

### Fuente de informes {#reporting-source}

Especifique de qué datos de solución se recopilan:

* [!DNL Adobe Target]

* [!DNL Adobe Analytics]

  +++ Más información sobre Analytics como fuente de informes

  Consulte [Adobe Analytics como fuente de informes para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las distintas soluciones de creación de informes y las ventajas que ofrece cada una. Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], selecciona un grupo de informes [!DNL Analytics] para recibir [!DNL Target] datos de actividad.

  Para especificar una fuente de informes, primero elija una de las [!DNL Analytics] empresas a las que esté asociada su cuenta y luego seleccione el grupo de informes apropiado para la actividad. Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve los grupos de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.

  [!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente sobre los resultados. Aparece un servidor de seguimiento predeterminado en el campo **[!UICONTROL Servidor de seguimiento]**. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.
  +++

* [!DNL Adobe Customer Journey Analytics]

  +++ Más información sobre Customer Journey Analytics como fuente de informes

  Consulte [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para ver los tipos de actividades compatibles, la selección de zonas protegidas y vistas de datos, las métricas de objetivo y la configuración de informes en [!DNL Customer Journey Analytics].
  +++

Si se especifica una fuente de informes en la [configuración de la cuenta](/help/main/administrating-target/reporting.md), se utilizará la fuente especificada y esta configuración no será visible.

La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

### Métrica de objetivo {#goal-metric}

>[!NOTE]
>
>Si la solución de creación de informes se establece en [!DNL Analytics], la única métrica de objetivo disponible es **[!UICONTROL Conversión]**. [!DNL Analytics] métricas no se pueden seleccionar como un objetivo.

Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija una métrica **[!UICONTROL Conversión]** y establezca los parámetros que determinan cuándo se logra el éxito.

Para obtener más información sobre cómo definir métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).

Para obtener más opciones, haga clic en el icono **[!UICONTROL Más]** junto a la métrica de objetivo y luego haga clic en **[!UICONTROL Configuración avanzada]**. Consulte [Configuración avanzada](#section_E2FE441AFB324E498793ABB025ED9974).

![](../../assets/goals-ab-3.png)

Si está habilitado, el **[!UICONTROL Valor estimado de la conversión]** proporciona un valor para el objetivo, pero no para otras métricas. Los siguientes puntos se aplican a este campo:

* El valor permite que [!DNL Target] calcule un alza estimada de ingresos.
* El campo es opcional; sin embargo, los ingresos incrementales de cualquier métrica que no sea de ingresos no se pueden calcular sin él.
* El campo no está disponible para las métricas **[!UICONTROL Puntuación de página]**.
* Para todas las métricas de ingresos (**[!UICONTROL Ingresos por visitante]**, **[!UICONTROL Valor promedio de pedido]**, **[!UICONTROL Ventas totales]** y **[!UICONTROL Pedidos]**), la estimación usa **[!UICONTROL Ingresos por visitante]**. El tipo de datos es moneda.

### Métricas adicionales {#additional-metrics}

Esta configuración no está disponible si la solución de creación de informes está establecida en [!DNL Analytics]. En este caso, se aplican las métricas definidas para el grupo de informes [!DNL Analytics].

### Audiencias para los informes {#audiences-for-reporting}

![](../../assets/goals-ab-4.png)

De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar audiencias de informes para mostrar información solo sobre audiencias específicas.

Tenga en cuenta que esta configuración no está disponible si elige [!DNL Analytics] como solución de sistema de informes. Se aplica la audiencia definida para el grupo de informes [!DNL Analytics].

## Configuración avanzada {#section_E2FE441AFB324E498793ABB025ED9974}

La sección **[!UICONTROL Configuración avanzada]** de la página **[!UICONTROL Objetivos y configuración]** le permite configurar las opciones avanzadas.

Para especificar la configuración avanzada, haga clic en el icono **[!UICONTROL Más]** ( ![Icono de más](/help/main/assets/icons/MoreSmallList.svg) ) en la sección **[!UICONTROL Mi objetivo principal]** y, a continuación, haga clic en **[!UICONTROL Configuración avanzada]**.

![](../../assets/goals-ab-3.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

### ¿Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica? {#dependencies}

Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de actividad podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión.

Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente. Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra. La opción **[!UICONTROL Añadir dependencia]** permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).

Para agregar una dependencia:

1. Después de agregar métricas adicionales, haga clic en **[!UICONTROL Configuración avanzada]**.

1. Haga clic en la opción **[!UICONTROL Añadir dependencia.]**

1. Arrastre y suelte las métricas que desee y, a continuación, haga clic en **[!UICONTROL Alcanzado]** para alternar el valor entre **[!UICONTROL Alcanzado]** y **[!UICONTROL No alcanzado]**.

Puede editar o eliminar dependencias después de añadirlas.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo? {#after-goal}

Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Es distinto del comportamiento predeterminado en [!DNL Target Classic], que contaba los visitantes como nuevos si vuelven a ver la actividad.

Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:

* **[!UICONTROL Aumentar recuento y mantener el usuario en la actividad]** para especificar cómo se incrementa el recuento.
* **[!UICONTROL Aumentar recuento, liberar usuario y permitir la reentrada]** para especificar la experiencia que el usuario verá si vuelve a entrar a la actividad.
* **[!UICONTROL Aumentar recuento, liberar usuario y bloquear su reentrada]** para especificar lo que el usuario ve en lugar del contenido de la actividad.

### ¿Cómo aumentará el recuento? {#count-increment}

Hay tres opciones para el aumento del recuento:

* **[!UICONTROL Una vez por participante]**
* **[!UICONTROL En cada impresión (excluidas las actualizaciones de páginas)]**
* **[!UICONTROL En cada impresión]**

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

## Metodología estadística {#section_statistical-methodology}

La sección **[!UICONTROL Metodología estadística]** de la página **[!UICONTROL Objetivos y configuración]** le permite elegir cómo se analizan los resultados del experimento.

### Opciones de metodología {#methodology-options}

Esta opción determina el marco estadístico, las métricas de resultados y los criterios de decisión utilizados para la métrica de objetivo **[!UICONTROL Conversión]** de esta actividad:

* **[!UICONTROL Bayesiano]:** Toma de decisiones basada en la probabilidad que actualiza las creencias a medida que llegan los datos y admite la supervisión continua y tamaños de muestra más pequeños. Los resultados se expresan como la probabilidad de que una variante sea mejor que otra, por ejemplo &quot;92% de probabilidad de que la Variante B venza a Control&quot;.
  * Ideal para tamaños de muestra más pequeños, monitorización continua, partes interesadas que prefieren probabilidades o cuando tiene conocimientos previos de pruebas anteriores para aplicar.
  * No es ideal cuando necesita una estricta aprobación regulatoria o de cumplimiento, o cuando necesita valores p tradicionales.
  * Los informes muestran **[!UICONTROL Posibilidad de control de pulsaciones]** y un intervalo creíble en lugar de la columna de frecuencia **[!UICONTROL Confianza]**.
* **[!UICONTROL Prueba t de Welch (Frecuentista)]:** Metodología tradicional de prueba de hipótesis. Utiliza valores p y requiere un tamaño de muestra fijo. Los informes muestran un porcentaje de **[!UICONTROL confianza]** e intervalo de confianza.

Esta configuración solo está disponible para actividades cuya métrica de objetivo principal sea **[!UICONTROL Conversión]**. Las actividades con un objetivo principal de **[!UICONTROL Ingresos]** o **[!UICONTROL Participación]** siempre usan la prueba t de **[!UICONTROL Welch]**.

Para obtener más información sobre cómo se calcula y se informa de cada metodología, consulte [Cálculos estadísticos en Pruebas A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

### Configuración bayesiana {#bayesian-configuration}

Esta configuración solo se muestra cuando **[!UICONTROL Bayesiano]** está seleccionado como **[!UICONTROL Metodología estadística]**. Configure las siguientes opciones:

* **[!UICONTROL Intervalo creíble]**: establece el intervalo dentro del cual se espera que se produzca el efecto verdadero.
* **[!UICONTROL Umbral de decisión]**: Establece la probabilidad mínima que debe alcanzar una variante, en relación con **[!UICONTROL Control]**, para que se pueda declarar como ganadora.
* **[!UICONTROL Use conocimientos previos de pruebas anteriores?]**: Active esta opción para proporcionar conocimientos previos del rendimiento anterior e informar el cálculo **[!UICONTROL bayesiano]**.

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

La sección **[!UICONTROL Otros metadatos]** de la página **[!UICONTROL Objetivos y configuración]** le permite especificar cualquier información acerca de su actividad que sea útil tener disponible para usted o para otros integrantes del equipo.
