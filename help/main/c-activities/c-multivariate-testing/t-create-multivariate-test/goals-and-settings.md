---
keywords: configuración de actividad;objetivos y configuración;multivariable;mvt
description: Aprenda a usar la página [!UICONTROL Objetivos y configuración] en [!DNL Adobe Target] para especificar información acerca de los objetivos de una actividad de [!UICONTROL prueba multivariable] (MVT).
title: ¿Cómo se especifican los objetivos y la configuración en una actividad de [!UICONTROL prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
TQID: https://experienceleague.adobe.com/FKRQnliVYaVby-SiFunkRWX7iFMi76JAP3D3TKUdMXE
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1261
ht-degree: 39%

---

# Configuración y objetivos ([!UICONTROL Prueba multivariable])

En la página [!UICONTROL Objetivos y configuración] de [!DNL Adobe Target] es donde se especifica información sobre los objetivos de las actividades de [!UICONTROL prueba multivariable] (MVT).

Las secciones disponibles son las siguientes:

* [!UICONTROL Configuración de actividades]
* [!UICONTROL Configuración de informes]
* [!UICONTROL Otros metadatos]

La configuración disponible en cada sección depende de si usa [!DNL Target] o [!DNL Analytics] como fuente de informes.

## Configuración de actividades {#section_DCBDC354261F420EBD4B43EA34947BAC}

Las configuraciones disponibles son las siguientes:

### Objetivo

Escriba un objetivo opcional. El objetivo puede ser cualquier información que le ayude a usted y a su equipo a identificar la campaña.

### Prioridad

Según la configuración, la interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Prioridad] varían. Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con el mismo público. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.

Si esta opción no está habilitada en [!UICONTROL Administración] > [!UICONTROL Informes] (la predeterminada), especifique una prioridad: [!UICONTROL Baja], [!UICONTROL Medium] o [!UICONTROL Alta].

Para habilitar prioridades específicas, haga clic en [!UICONTROL Administración] > [!UICONTROL Informes] y luego coloque la opción [!UICONTROL Habilitar prioridades específicas] en la posición &quot;Activado&quot;.

Si esta opción está habilitada, especifique un valor de 0 a 999:

* 0 = Bajo
* 999 = Alto

Para las actividades creadas en versiones anteriores de [!DNL Target], la prioridad [!UICONTROL Low] se convierte en 0, la prioridad [!UICONTROL Medium] se convierte en 5 y la prioridad [!UICONTROL High] se convierte en 10. Si lo necesita, puede ajustar estos valores.

>[!NOTE]
>
>Para deshabilitar esta opción después de usar las prioridades específicas, hay que volver a establecer todas las prioridades en 0, 5 y 10.

### Duración

La actividad se puede iniciar cuando se aprueba, o bien se puede establecer una fecha y hora específicas. Igualmente, la actividad puede finalizar cuando está desactivada o se puede establecer una fecha y hora. El selector de hora utiliza un reloj de 24 horas, siendo 00:00 la medianoche. La zona horaria se establece según la zona horaria configurada en el navegador. Para usar una zona horaria distinta, configure el navegador para otra zona horaria y reinícielo.

## Configuración de informes. {#section_13119392051044FBA6387D9B3B1C43CF}

Las configuraciones disponibles son las siguientes:

### Fuente de informes

Especifique de qué datos de solución se recopilan:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si especifica una solución de informes en la [configuración de la cuenta](/help/main/administrating-target/reporting.md), se utilizará la solución especificada y este ajuste no será visible.

La fuente de informes no se puede cambiar una vez publicada la actividad. Esto permite mantener la coherencia en los informes.

**[!DNL Adobe Analytics]**: vea [[!DNL Adobe Analytics] como fuente de informes de [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conocer las diferencias entre las soluciones de informes y las ventajas de cada una.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T), selecciona un grupo de informes [!DNL Analytics] para recibir [!DNL Target] datos de actividad. Para ello, elija primero una de las [!DNL Analytics] empresas a la que esté asociada su cuenta y, a continuación, seleccione el grupo de informes adecuado para la actividad. Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes aún no aparece en la lista, comuníquese con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente sobre los resultados. Aparece un servidor de seguimiento predeterminado en el campo [!UICONTROL Servidor de seguimiento]. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

**[!DNL Adobe Customer Journey Analytics]**: vea [[!DNL Target] creación de informes en [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obtener más información sobre la integración entre [!DNL Adobe Customer Journey Analytics] y [!DNL Target].

### Métrica de objetivo

Seleccione la acción realizada por un visitante para conseguir el objetivo. Por ejemplo, elija una métrica [!UICONTROL Conversión] y establezca los parámetros que determinan cuándo se logra el éxito.

>[!NOTE]
>
>Si la solución de creación de informes se establece en [!DNL Analytics], la única métrica de objetivo disponible es [!UICONTROL Conversión]. [!DNL Analytics] métricas no se pueden seleccionar como un objetivo.

Cuando selecciona la métrica de éxito, se muestra un selector. Utilice el selector para elegir los datos específicos de la métrica de éxito.

Si se habilita, el campo [!UICONTROL Valor estimado de la conversión] (no disponible para las métricas [!UICONTROL Puntuación de página]) proporciona un valor para el objetivo, pero no para otras métricas. Este valor permite a [!DNL Target] calcular un alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. Para todas las métricas de ingresos ([!UICONTROL Ingresos por visitante], [!UICONTROL Valor promedio de pedido], [!UICONTROL Ventas totales] y [!UICONTROL Pedidos]), la estimación usa [!UICONTROL Ingresos por visitante]. El tipo de datos es moneda.

Después de alcanzar el objetivo de la actividad, un visitante continúa viendo el contenido de esta, a menos que cumpla los requisitos de una actividad de prioridad más alta. Si alcanza el objetivo nuevamente, se cuenta como otra conversión. Este comportamiento es diferente del comportamiento predeterminado en [!DNL Target Classic], que cuenta los visitantes como nuevos si vuelven a ver la prueba.

### Métricas adicionales

Cree métricas de éxito adicionales.

Esta configuración no está disponible si la solución de creación de informes está establecida en [!DNL Analytics]. En este caso, se aplican las métricas definidas para el grupo de informes [!DNL Analytics].

### Audiencias para los informes

De manera predeterminada, en los informes se muestran resultados de todos los visitantes cualificados. Puede agregar públicos de informes para mostrar únicamente información sobre públicos específicos.

### Configuración avanzada {#section_E2FE441AFB324E498793ABB025ED9974}

La Configuración avanzada está disponible para las métricas de objetivo de [!UICONTROL Prueba multivariable].

![Menú Configuración avanzada](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes, el servidor [!DNL Analytics] es el que administra la configuración. La opción de configuración avanzada no está disponible.

#### ¿Qué métrica de éxito debe alcanzarse antes de incrementar esta métrica?

Utilice esta opción para contar a alguien como alguien que alcanza la métrica de éxito si anteriormente ha alcanzado una métrica de éxito diferente. Por ejemplo, una conversión de prueba podría ser válida únicamente si el visitante hace clic en la oferta, o alcanza una página concreta antes de la conversión.

Dispone de dependencia respecto a varias métricas y tiene la posibilidad de elegir si una métrica debe alcanzarse o no para que su contador aumente.

Defina ambas (o varias) métricas de éxito antes de poder hacer una dependiente de la otra.

La opción [!UICONTROL Añadir dependencia] permite que la métrica de éxito aumente si se alcanza otra métrica de éxito (o todo lo contrario, si no se alcanza).

Para agregar una dependencia:

1. Después de agregar métricas adicionales, haga clic en **[!UICONTROL Configuración avanzada]**.
2. Haga clic en la opción **[!UICONTROL Añadir dependencia]**:

   ![Agregar dependencia](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Arrastre y suelte las métricas deseadas del panel izquierdo al panel derecho y haga clic en **[!UICONTROL Alcanzado]** para alternar el valor entre Alcanzado y No alcanzado

   ![Dependencia alcanzada](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Puede editar o eliminar dependencias después de añadirlas.

### ¿Qué ocurrirá después de que un usuario encuentre esta métrica de objetivo?

Existen tres opciones para lo que ocurre después de que un visitante alcance la métrica de objetivo:

* [!UICONTROL Seleccione Aumentar recuento y mantener el usuario en la actividad] para especificar cómo se incrementa el recuento.
* [!UICONTROL Seleccione Aumentar recuento, liberar usuario y permitir la reentrada] para especificar la experiencia que el usuario verá si vuelve a entrar a la actividad.
* [!UICONTROL Seleccione Aumentar recuento, liberar usuario y bloquear su reentrada] para especificar lo que el usuario verá en lugar del contenido de la actividad.

Para obtener más información sobre la configuración avanzada, consulte [Métricas de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Otros metadatos {#section_2E8917BEFB954480A4206B9E9E917F80}

La configuración disponible es la siguiente:

### Notas

Escriba la información sobre la actividad que sea útil para el equipo. Se puede cambiar el tamaño del panel [!UICONTROL Notas].

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

En este vídeo se muestra cómo crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target]. Los objetivos y la configuración se discuten a partir de las 7:00.

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/17395)
